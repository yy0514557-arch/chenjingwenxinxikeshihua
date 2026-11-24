# 01｜图表体系与分类

本文件夹建立 RAWGraphs 图表目录、图形家族索引与分类依据。

## 图表核验方法
1. 检查 App 的 src/charts.js，确认实际注册图表。
2. 对照 rawgraphs-charts/src/ 中各图表目录。
3. 查看 metadata.js，记录名称、ID、描述、类别及教程。
4. 查看 dimensions.js，记录数据维度与类型约束。
5. 单独记录 App 引入的扩展图表，如 Calendar Heatmap。
6. 排除或单独标记测试图表、空图表、样式资源和辅助模块。

## App 注册表图表
当前读取的 rawgraphs-app/src/charts.js 注册项包括：

Alluvial Diagram、Arc Diagram、Bar Chart、Multiset Bar Chart、Stacked Bar Chart、Beeswarm、Box Plot、Bubble Chart、Bump Chart、Calendar Heatmap、Chord Diagram、Circle Packing、Circular Dendrogram、Contour Plot、Convex Hull、Dendrogram、Gantt Chart、Hexagonal Binning、Horizon Graph、Line Chart、Matrix Plot、Parallel Coordinates、Pie Chart、Radar Chart、Sankey Diagram、Slope Chart、Streamgraph、Sunburst、Treemap、Violin Plot、Voronoi Diagram、Voronoi Treemap。

Calendar Heatmap 由 App 单独依赖的 @rawgraphs/rawgraphs-calendar-heatmap 提供，不属于 rawgraphs-charts 仓库中的同一图表目录。

## 研究用二次分类
| 图形家族 | 代表图表 | 主要表达任务 |
|---|---|---|
| 比较与排序 | Bar、Stacked Bar、Multiset Bar、Slope、Bump | 类别比较、构成比较、排名变化 |
| 时间与变化 | Line、Streamgraph、Horizon、Gantt、Calendar Heatmap | 时间序列、阶段、周期与变化 |
| 分布与密度 | Box Plot、Violin、Beeswarm、Hexagonal Binning、Contour | 分布形态、密度与离散程度 |
| 相关与多变量 | Bubble、Parallel Coordinates、Radar、Matrix Plot | 多变量关系与模式 |
| 层级与包含 | Treemap、Sunburst、Circle Packing、Dendrogram、Circular Dendrogram | 层级、组成与包含关系 |
| 网络与流向 | Chord、Arc、Sankey、Alluvial | 连接、流动、转移与关系 |
| 空间分区与几何 | Voronoi、Voronoi Treemap、Convex Hull | 邻近分区、空间组织与边界 |

此表为研究用二次分类，不是 RAWGraphs 官方分类；具体定义回到源码与官方说明。

## 后续文档命名
编号-中文名称-英文名称.md

每篇至少包含定义、适用数据、数据维度、映射与聚合、统计/计算机制、视觉编码、信息架构、视觉叙事、优缺点、源码证据与案例。
