# 00｜RAWGraphs 概念与方法

## 1. 项目定义
RAWGraphs 是一个开放式、面向浏览器的可视化工具，用于基于表格数据创建可定制的矢量图形。项目以 D3.js 等 Web 可视化技术为基础，连接电子表格工具与矢量图形编辑工具。

项目 README 说明：支持表格数据及复制粘贴文本；可视化以 SVG 为重要输出形式；数据在浏览器端处理，不进行服务端数据存储或处理；工具面向设计师及需要定制可视化表达的使用者。

## 2. 项目组成

### 2.1 RAWGraphs App（应用层）
仓库：https://github.com/rawgraphs/rawgraphs-app

源码中可核实的主要界面模块：
- DataLoader：数据导入。
- ParsingOptions：分隔符、数字格式、日期等解析选项。
- DataTable / DataGrid：数据预览。
- ChartSelector：图表选择。
- DataMapping：字段与图表维度映射。
- ChartOptions：视觉参数设置。
- ChartPreview：图表预览。
- Exporter：结果导出。

src/charts.js 汇集并注册 App 使用的图表；其中 Calendar Heatmap 由单独依赖 @rawgraphs/rawgraphs-calendar-heatmap 引入。

### 2.2 RAWGraphs Charts（图表实现层）
仓库：https://github.com/rawgraphs/rawgraphs-charts

该仓库 README 将其定义为 RAWGraphs App 使用的一组精选图表，并说明图表通过 RAWGraphs Core API 定义行为。具体图表目录常见文件职责：
- metadata.js：名称、图标、缩略图、ID、类别、描述和教程。
- dimensions.js：可映射维度、允许的数据类型、必需性及聚合设置。
- mapping.js：原始记录到图表数据结构的转换。
- visualOptions.js：可调视觉选项。
- render.js：图形绘制。
- 图表主文件与 SVG：组件实现、图标和缩略图。

并非所有目录都是正式图表；应结合 App 注册表和目录内容判断。测试、空图表、颜色测试和样式辅助目录需要单独标注。

### 2.3 RAWGraphs Core（底层接口层）
Charts 使用 Core API 定义图表行为。研究具体图表时，应进一步对照 Core 对图表接口、数据类型、聚合器和导出能力的定义；未直接核验的接口细节不在此推定。

## 3. 工作流程
1. 数据导入（Data Loading）
2. 数据解析（Data Parsing）
3. 图表选择（Chart Selection）
4. 数据映射（Data Mapping）
5. 数据转换与聚合（Data Transformation / Aggregation）
6. 视觉参数配置（Visual Options）
7. 预览与检查（Preview）
8. 导出（Export）

这是对 App 组件和图表实现流程的研究性归纳，不代表仓库中存在完全同名的八个软件步骤。

## 4. 数据逻辑与视觉映射：Bar Chart 源码示例
源码中 Bar chart 的维度定义显示：
- bars：必需维度，可接受 number、string、date。
- size：可选数值维度，支持聚合，默认 sum。
- color：可选维度，可接受 number、string、date，并按数据类型设置聚合默认值。
- series：可选分组维度。

其 mapping.js 使用 D3 分组汇总逻辑，按 Series 和 Bars 分组；映射 Size 时执行聚合，未映射 Size 时以组内记录数作为大小；Color 未映射时使用默认颜色。

因此图表结果共同受到数据字段与类型、维度定义、字段映射、分组聚合、缺省值处理、视觉选项和渲染规则影响。

## 5. 统一分析框架
A. 图表定义：中英文名、源码 ID、官方描述、实现路径。
B. 数据逻辑：记录单位、字段、数据类型、必需/可选维度、分组与聚合。
C. 统计或计算机制：统计汇总、排序、比例、坐标转换、布局算法或几何计算。
D. 视觉编码：位置、长度、角度、面积、颜色、形状、连线、标签。
E. 信息架构：类别、数值、层级、关系、时间或空间信息组织。
F. 视觉叙事：强调、比较和揭示的关系；设计意图不得冒充源码事实。
G. 适用条件与限制：任务、数据要求、误读风险和不适用场景。
H. 实践参数：可调选项、参数影响、版式和标注建议。
I. 证据记录：仓库、版本、文件路径、官方链接和核验日期。

## 6. 图表二次分类
可为检索建立比较与排序、时间与变化、分布与密度、相关与多变量、层级与包含、网络与流向、空间分区与几何布局、矩阵与日历表达等家族。此为本知识库的研究分类，不是 RAWGraphs 官方唯一分类；图表可能跨类。

## 7. 研究边界
- 图表清单以 App 注册表为入口，并与图表实现仓库交叉核对。
- rawgraphs-charts 目录数不等于 App 正式图表数。
- 统计计算、布局算法与视觉编码分开描述。
- 视觉属性应以对应图表的 dimensions.js、mapping.js、visualOptions.js 和 render.js 为证据。
- 本文件以当前可读取的 master 分支为基础；不同版本的结论需注明版本。
