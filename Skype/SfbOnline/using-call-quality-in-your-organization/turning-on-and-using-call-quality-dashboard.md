---
title: 打开和使用呼叫质量仪表板
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.ToolsCallQualityDashboard
ms.custom:
- Reporting
description: '请参阅如何启用和 Skype 用于业务联机呼叫质量仪表板并获取呼叫的质量摘要报告。 '
ms.openlocfilehash: f8a7a71a0e0c0e64ceb7447c53c15483d977e16a
ms.sourcegitcommit: 5a0b3fe49b64f08979c89443f66b15827034e755
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>打开和使用呼叫质量仪表板的 Microsoft 团队和 Skype 业务 online

了解如何配置 Office 365 组织使用呼叫质量仪表板来监视呼叫质量。
  
呼叫质量仪表板 (CQD) 的 Microsoft 团队和 Skype 业务 online 使您能够获得见解进行业务服务使用的 Microsoft 团队和 Skype 的呼叫的质量。 本主题介绍的步骤，您需要完成要开始收集数据。
  
> [!NOTE]
> 详细 CQD 报告当前是可用作技术预览版，但适用于所有的客户。 
  
## <a name="latest-changes-and-updates"></a>最新更改和更新

对 CQD 的最新更改如下所示：
  
- 包括除了 Skype Online 业务数据的 Microsoft 团队数据。
    
- 摘要报告包括产品筛选器以选择所有数据、 Microsoft 团队数据或 Skype Online 业务数据。
    
请参阅此列表的[维度和度量值可用呼叫质量仪表板中](dimensions-and-measures-available-in-call-quality-dashboard.md)的文章。
  
> [!NOTE]
> 有关更新和向仪表板的更改的信息可通过单击中的链接**好消息 ！** 标题显示仪表板上时。
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a>激活 Microsoft 呼叫质量仪表板 (CQD) 摘要报告

您可以开始使用 CQD 之前，您需要激活的 Office 365 组织。
  
1. 登录到 Office 365 组织使用管理帐户，，然后选择**管理员**图块打开在管理中心。
    
2. 在左窗格中，在**管理中心**，选择打开业务管理中心的 Skype **for Business 的 Skype** 。
    
3. 在业务管理中心的 Skype，在左侧窗格中，选择**工具**，然后选择**业务联机呼叫质量仪表板的 Skype**。
    
     ![Skype 业务工具](../images/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. 在打开的页面上，使用您的全局管理员帐户，登录，然后提供帐户出现提示时的凭据。
    
     ![CQD 登录](../images/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
您登录后，一旦被激活后之后, CQD 将开始收集和处理数据。
  
> [!NOTE]
> 可能需要几个小时处理数据不足，无法在报表中显示有意义的结果。 
  
## <a name="features-of-the-call-quality-dashboard-for-skype-for-business-online"></a>联机 for Business 的 Skype 呼叫质量仪表板的功能
<a name="BKMKFeaturesOfTheCQD"> </a>

CQD 摘要报告提供计划的详细的报告功能的子集。 下面总结了两种版本之间的差异：
  
|**功能**|**摘要报告**|**详细的报告**|
|:-----|:-----|:-----|
|应用程序共享指标  <br/> |否  <br/> |是  <br/> |
|构建信息支持的客户  <br/> |是  <br/> |是  <br/> |
|深入分析支持  <br/> |否  <br/> |是  <br/> |
|媒体可靠性指标  <br/> |否  <br/> |是  <br/> |
|即开报告  <br/> |是  <br/> |是  <br/> |
|概述报告  <br/> |是  <br/> |是  <br/> |
|每个用户报告集  <br/> |否  <br/> |是  <br/> |
|设置自定义报表 （添加、 删除、 修改报表）  <br/> |否  <br/> |是  <br/> |
|基于视频的屏幕共享指标  <br/> |否  <br/> |是  <br/> |
|视频指标  <br/> |否  <br/> |是  <br/> |
|可用的数据量  <br/> |过去 6 个月  <br/> |过去 6 个月  <br/> |
|Microsoft 团队数据  <br/> |是  <br/> |是  <br/> |
   
### <a name="out-of-the-box-reports"></a>即开报告

CQD 这两个版本提供的-全新体验，请为您提供呼叫质量指标，无需创建任何新的报表。 一旦在后端处理数据时，您可以开始查看在报告呼叫质量数据。
  
### <a name="overview-reports"></a>概述报告

CQD 这两个版本提供高级入口点的整个呼叫质量信息，但信息显示在摘要报表的方式是不同的详细报告。
  
摘要报告提供使用户能够快速浏览和了解整个呼叫质量状态和趋势的简化的选项卡式的页面报表视图。
  
四个选项卡包括：
  
- **总体呼叫质量**-提供有关所有流，即服务器到客户端流聚合和客户端客户端流，以及单独的服务器到客户端和客户端客户端流时，在每月和每日的趋势的窗体的信息。
    
- **服务器的客户端**-服务器和客户端终结点之间的流提供其他详细信息。
    
- **客户端的客户端**-提供两个客户端终结点之间的流的其他详细信息。
    
- **语音质量 SLA** -提供有关呼叫的业务联机语音质量 SLA Skype 中包含的信息。
    
### <a name="overall-call-quality-tab"></a>总体呼叫质量选项卡

使用此选项卡上的数据评估呼叫质量状态和趋势看流计数和质量欠佳的百分比。 在右上角的图例显示的颜色和可视元素表示这些指标。
  
![CQD 数据键](../images/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
流分为三个组： 良好、 不佳，和未分类。 存在进行还计算*差 %* 值的授予您的流比率归类为*质量欠佳*到总保密的流计数。 由于*差 %= 差流 / （不佳流 + 良好流） * 100* ，这将使*差 %* 受到与多个*自解除保密*流状态。 有关将用于分类为质量欠佳或良好流，请参阅[呼叫质量阈值](https://aka.ms/cqd_quality_thresholds)。
  
使用左侧刻度度量值流计数。
  
![CQD 数据计数](../images/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
使用右侧比例来测量的差 %值。
  
![CQD 数据每年会](../images/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
您还可以通过将鼠标悬停在条上获取实际数值。
  
> [!NOTE]
> 下面的示例是一个非常小示例数据集，从，值不是实际的实际部署。 
  
![CQD 数据数字](../images/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
整体流卷是确定如何相关差的计算的百分比的重要因素。 整体流量较小，不可靠的报告不佳的百分比值。
  
### <a name="server-client-tab-and-client-client-tabs"></a>服务器到客户端选项卡和客户端客户端选项卡

以下两个选项卡提供其他详细信息发生在其终结点到终结点方案中的流。 这两个选项卡具有四个可折叠部分，表示将在其下流媒体流的四种情况。
  
- 有线内
    
- 外部有线
    
- Wifi 内部
    
- Wifi 以外
    
#### <a name="inside-test"></a>内部测试

在处理期间，CQD 后端分类为*内部*或*外部*使用构建信息流，如果存在。 终结点的每个流是与子网地址关联。 如果子网为子 InsideCorp 标记中上载的构建信息的列表中，将其视为*内部*。 如果在构建信息具有尚未上载内, 测试将始终为*外部*分类流。 请注意，内部服务器到客户端方案的测试只考虑客户端终结点。 因为服务器始终之外从用户的角度来看，这不占测试中。
  
#### <a name="wired-vs-wifi"></a>与 wifi 有线

指示名称，这是基于客户端连接类型分类标准。 同样，服务器始终有线，且该不包含计算中。
  
> [!NOTE]
> 如果两个终结点之一连接到 Wifi 网络给定流，然后归为 Wifi CQD 中。 
  
## <a name="selecting-product-data-to-see-in-reports"></a>选择要查看报告中的产品数据
<a name="BKMKFeaturesOfTheCQD"> </a>

在摘要和位置增强报告中，您可以使用**产品筛选器**下拉列表以显示所有产品数据，只有 Microsoft 团队数据或仅联机业务数据的 Skype。
  
![屏幕快照显示了具有所有选项、 Microsoft 团队和 for Business 的 Skype 的产品筛选器控件。](../images/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
在详细的报告，您可以使用**是团队**维度筛选 Online 业务数据的报表定义一部分的 Microsoft 团队或 Skype 的数据。
  
## <a name="upload-building-information"></a>上载构建信息
<a name="BKMKFeaturesOfTheCQD"> </a>

CQD 摘要报告仪表板包含一个**租户数据上载**的页，通过从右上角的设置菜单中选择**租户数据上载**访问。 此页用于 admins 上载他们自己的信息，如映射的 IP 地址和地理信息，每个无线 AP 和其 MAC 地址映射，等等。
  
![CQD 仪表板](../images/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. 在**租户数据上载**页上，使用下拉菜单中选择上载的数据文件类型。 文件数据类型表示文件的内容 （例如，"Building"指的 IP 地址映射和构建以及其他地理信息）。 当前我们要仅支持"构建"数据类型。 将与后续版本添加几个更多的数据类型。
    
2. 选择后的文件数据类型，单击**浏览**选择数据文件。
    
  - 数据文件必须.tsv （制表符分隔值） 文件或.csv （以逗号分隔值） 文件。 如果使用.csv 文件，包含逗号分隔的任何字段必须用引号引起来，或已删除的逗号。 例如，如果您构建的名称是 NY，NY.csv 文件中其应以输入"NY，NY"。
    
  - 数据文件必须是不超过 50 MB 的大小。
    
  - 对于每个数据文件，文件中的每个列必须匹配一个预定义的数据类型，本主题后面所述。
    
3. 选择数据文件之后，指定**开始日期**和 （可选）**指定的结束日期**。
    
4. 选择后**开始日期**，选择**上载**以将文件上载到 CQD 服务器。
    
    上载文件之前，请首先验证。 一旦验证，它在 Azure blob 存储。 如果验证失败或文件无法在 Azure 的 blob 存储请求更正文件显示错误消息。 下图显示在数据文件中的列数不正确时出现错误。
    
     ![CQD 示例上载验证错误](../images/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. 如果验证过程中不发生任何错误，将会成功上载文件。 您随后可以看到**我上载**表，其中显示所有上载文件的完整列表，该页面底部当前租户中上载的数据文件。
    
    每个记录显示一个上载的租户数据文件的文件类型、 上次更新时间、 时间段、 说明、 删除图标和下载图标。 若要删除文件，请选择表中的回收站图标。 若要下载文件，在**下载**列中的表中选择下载图标。
    
     ![CQD 我上载表](../images/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### <a name="tenant-data-file-format-and-building-data-file-structure"></a>租户数据文件格式和构建数据文件结构
<a name="BKMKTenantDataFile"> </a>

您上载的数据文件的格式必须满足以下内容以通过在上载之前验证检查。
  
- 文件必须.tsv 文件，这意味着在每个行中，列分隔选项卡上或以逗号分隔每一列的.csv 文件。
    
- 数据文件的内容不包括表格标题。 不头，表示的数据文件的第一行应该真实数据，如"网络"等。
    
- 每个列的数据类型仅可以是字符串、 号码或 Bool。 如果它是数字，值必须是数值;如果是 Bool，值必须是 0 或 1。
    
- 每个列的数据类型为 string，如果数据可以为空 （但仍必须用相应的分隔符 （即，选项卡或逗号分隔） 分隔。 这只是分配该字段空字符串值。
    
- 必须为每个行的 14 列，每个列必须具有以下数据类型和列必须下表中列出的顺序：
    
|**列名称**|**数据类型**|**示例**|
|:-----|:-----|:-----|
|网络  <br/> |字符串  <br/> |192.168.1.0  <br/> |
|NetworkName  <br/> |字符串  <br/> |美国/西雅图/西雅图-SEA-1  <br/> |
|NetworkRange  <br/> |数字  <br/> |26  <br/> |
|BuildingName  <br/> |字符串  <br/> |西雅图-SEA-1  <br/> |
|OwnershipType  <br/> |字符串  <br/> |Contoso  <br/> |
|BuildingType  <br/> |字符串  <br/> |IT 终止  <br/> |
|BuildingOfficeType  <br/> |字符串  <br/> |Engineering  <br/> |
|城市  <br/> |字符串  <br/> |西雅图  <br/> |
|邮政编码  <br/> |字符串  <br/> |98001  <br/> |
|国家/地区  <br/> |字符串  <br/> |我们  <br/> |
|省/市/自治区  <br/> |字符串  <br/> |WA  <br/> |
|区域  <br/> |字符串  <br/> |MSU  <br/> |
|InsideCorp  <br/> |Bool  <br/> |1  <br/> |
|ExpressRoute  <br/> |Bool  <br/> |0  <br/> |
   
> [!IMPORTANT]
> 网络范围可以用于表示 supernet （单个路由前缀开头的几个子网的组合）。 所有新的生成上载将检查有任何重叠的区域。 如果先前已上载的生成文件，您应将当前文件下载并重新上载以找出任何重叠并再次上载之前修复问题。 重叠之前上载文件的任何情况可能会导致建筑物报告中的子网的错误映射。 某些 VPN 实现未准确报告的子网信息。 当将 VPN 子网添加到该生成文件，而不是一个条目的子网，建议的单独添加条目的 VPN 子网中每个地址作为单独的 32 位网络。 每行可以有相同的构建元数据。 例如，而不是一个 172.16.18.0/24 行中，您应具有 256 行，通过为每个地址之间 172.16.18.0/32 172.16.18.255/32，非独占一行。 
  
## <a name="selecting-media-type-in-detailed-reports"></a>详细的报告中的选择媒体类型
<a name="BKMKFeaturesOfTheCQD"> </a>

详细的报告支持看质量和媒体可靠性的音频、 视频、 应用程序共享和基于视频的屏幕共享的媒体类型。 维度、 度量和特定于单个媒体类型的筛选器具有"音频"、"视频"、"的"或"VBSS"作为前缀。
  
![呼叫质量仪表板尺寸。](../images/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
如果您想要查看的维度和度量的单个媒体类型，可能需要的新 MediaType 维度和筛选器。 例如，要让显示会话总数的计数不同媒体类型的报告，包括 MediaType 维度。
  
![呼叫质量仪表板总流计数。](../images/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a>相关主题
[设置 Skype for Business 通话分析](set-up-call-analytics.md)

[使用呼叫分析解决质量欠佳的呼叫质量](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Cll 分析和呼叫质量仪表板](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 