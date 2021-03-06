---

copyright:
  years: 2016, 2017
lastupdated: "2017-03-16"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Team Dynamics（试验性）
{: #gettingstarted}

{{site.data.keyword.DRA_full}} Team Dynamics 利用社交编码分析来识别团队成员之间的交互级别，以便团队可以改进低成效的实践。
{:shortdesc}

在工具链中打开 {{site.data.keyword.DRA_short}} 后，单击 **Team Dynamics**。在其中，可以选择分析类别，以更深入地探究团队的协作习惯和实践。每组数据指示的内容可能因团队而不同，您可以向下钻取到每个可视化以获取帮助和指导。  

## 数据类别

{{site.data.keyword.DRA_short}} 用于填充其仪表板的数据会自动从团队的源代码控制存储库中进行挖掘。可以通过单击任何图表上的**信息**或**指南**，获取有关数据含义以及可以如何将其应用于项目的更多信息。

### 社交编码

社交编码图以直观、高度交互的方式显示项目贡献者之间的关系。图中的每个节点表示一名开发者。节点大小与开发者对项目的贡献成对数关系。节点之间的连线指示协作程度；线条越粗，表示两位开发者之间在所选时间段内的协作越多。 

每个节点的颜色为不同深浅的蓝色和红色。蓝色指示代码贡献者添加的代码行数占该贡献者处理总行数的比例。红色指示代码贡献者除去的代码行数。只添加了代码的贡献者将用全蓝表示，而添加的代码行数和除去的代码行数相等的贡献者将用半蓝半红表示。 

### 作者

“作者”类别提供每个存储库贡献者的落实数、行更改数和文件更改数。虽然不应该使用编写的代码总行数之类的指标来确定团队成员对项目的净贡献，但这些信息对于团队负责人和经理来说非常有用。贡献超多行更改数的团队成员可能工作量过大，也可能表示流程中存在瓶颈，或相比其他团队成员以更繁琐的方式编码。 
