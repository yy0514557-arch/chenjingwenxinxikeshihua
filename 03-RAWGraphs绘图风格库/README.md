# 03-RAWGraphs绘图风格库

本目录系统研究 RAWGraphs 的图表类型、数据映射、视觉编码和设计实践，形成可检索、可复用的信息可视化风格知识库。

## 目录
- [01-图表体系与分类](./01-图表体系与分类/README.md)：图表清单、图形家族、数据适用条件与分类依据。
- [02-数据映射与视觉编码](./02-数据映射与视觉编码/README.md)：字段映射、聚合、位置、尺寸、颜色、形状及参数。
- [03-图表案例研究](./03-图表案例研究/README.md)：逐图分析数据逻辑、编码结构、视觉语法和适用场景。
- [04-设计实践](./04-设计实践/README.md)：图表选择、参数调整、组合表达与项目实践。
- [00-RAWGraphs概念与方法](./00-RAWGraphs概念与方法.md)：项目定位、工作流程、技术结构与研究方法。

## 研究对象
1. [RAWGraphs App](https://github.com/rawgraphs/rawgraphs-app)：应用层，负责数据导入、图表选择、数据映射、参数配置、预览与导出。
2. [RAWGraphs Charts](https://github.com/rawgraphs/rawgraphs-charts)：图表实现层，包含元数据、维度定义、数据映射、视觉选项与渲染代码。
3. [RAWGraphs Core](https://github.com/rawgraphs/rawgraphs-core)：图表接口与底层能力。
4. [RAWGraphs Calendar Heatmap](https://github.com/rawgraphs/rawgraphs-calendar-heatmap)：App 单独引入的日历热力图扩展。

## 研究原则
- 区分源码事实、知识库二次分类和设计推论。
- 不把测试目录、空图表、辅助组件全部视为正式图表。
- 不将本知识库的二次分类误写为 RAWGraphs 官方分类。
- 每种图表从数据条件出发分析，不只收集外观截图。
- 记录源码版本、文件路径与核验日期。
