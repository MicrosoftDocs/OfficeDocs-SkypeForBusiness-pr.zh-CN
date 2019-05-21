---
title: 打开并使用通话质量仪表板
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.ToolsCallQualityDashboard
- ms.teamsadmincenter.directrouting.cqd
ms.custom:
- Reporting
description: '了解如何打开和使用 Skype for Business Online 呼叫质量仪表板和获取通话质量的摘要报告。 '
ms.openlocfilehash: afcb0243144784929e8516308084fda791b0bcec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291534"
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>打开和使用 Microsoft 团队和 Skype for business Online 的通话质量仪表板

了解如何配置 Office 365 组织以使用呼叫质量仪表板来监控通话质量。
  
Microsoft 团队和 Skype for business Online 的通话质量仪表板 (CQD) 使你可以深入了解使用 Microsoft 团队和 Skype for business 服务时所进行的通话质量。 本主题介绍了开始收集数据需要完成的步骤。
  
  
## <a name="latest-changes-and-updates"></a>最新更改和更新

对 CQD 的最新更改如下所示:
  
- 除了 Skype for Business Online 数据之外, 还包括 Microsoft 团队数据。
    
- 摘要报告包括一个用于选择所有数据、Microsoft 团队数据或 Skype for Business Online 数据的产品筛选器。

- 视频和 VBSS 流质量分类逻辑已更新。 有关最新分类器定义, 请参阅[通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。

有关[通话质量仪表板中可用的维度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)的列表, 请参阅本文。
  
> [!NOTE]
> 通过单击**好消息**中的链接可找到有关仪表板的更新和更改的信息! 仪表板上显示的标题。
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a>激活 Microsoft 通话质量仪表板 (CQD) 摘要报告

在开始使用 CQD 之前, 你需要为你的 Office 365 组织激活它。
![](media/teams-logo-30x30.png) **使用 Microsoft 团队管理中心的**teams-logo-30x30
 
1. 使用 Microsoft 团队服务管理员帐户登录到你的 Office 365 组织, 然后选择 "**管理员**" 磁贴以打开管理中心。
    
2. 在左窗格中的 "**管理中心**" 下, 选择 " **microsoft 团队**" 以打开 "microsoft 团队管理中心"。
    
3. 在 "Microsoft 团队管理中心" 中, 在左窗格中选择 "**呼叫质量" 仪表板**。
    
  
4. 在打开的页面上, 用全局管理员帐户或 Microsoft 团队服务管理员帐户登录, 然后在出现提示时提供帐户的凭据。
    
     ![CQD 登录](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
登录后, 一旦激活, CQD 将开始收集和处理数据。  
> [!NOTE]
> 可能需要几个小时才能处理足够多的数据, 以在报表中显示有意义的结果。 

![](media/sfb-logo-30x30.png) **使用 Skype for business 管理中心**sfb-logo-30x30
 
1. 使用管理员帐户登录到您的 Office 365 组织, 然后选择 "**管理员**" 磁贴以打开管理中心。
    
2. 在左窗格中, 在 "**管理中心**" 下, 选择 " **skype** for Business" 以打开 skype for business 管理中心。
    
3. 在 Skype for Business 管理中心中, 选择左窗格中的 "**工具**", 然后选择 " **Skype For Business Online 呼叫质量" 仪表板**。
    
     ![Skype for Business 工具](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. 在打开的页面上, 用全局管理员帐户登录, 然后在出现提示时提供帐户的凭据。
    
     ![CQD 登录](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
登录后, 一旦激活, CQD 将开始收集和处理数据。


  
## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Microsoft 团队和 Skype for business Online 的通话质量仪表板的功能 
<a name="BKMKFeaturesOfTheCQD"> </a>

CQD 摘要报告提供为详细报告规划的功能的子集。 下面总结了这两个版本之间的差异:
  
|**功能**|**摘要报告**|**详细报告**|
|:-----|:-----|:-----|
|应用程序共享跃点数  <br/> |否  <br/> |是  <br/> |
|客户构建信息支持  <br/> |是  <br/> |是   <br/> |
|客户终结点信息支持  <br/> |仅在 cqd.teams.microsoft.com 中  <br/> |仅在 cqd.teams.microsoft.com 中  <br/> |
|向下钻取分析支持  <br/> |否  <br/> |是  <br/> |
|媒体可靠性指标  <br/> |否  <br/> |是  <br/> |
|现成的报表  <br/> |是  <br/> |是   <br/> |
|概述报表  <br/> |是  <br/> |是   <br/> |
|每用户报告集  <br/> |否  <br/> |是  <br/> |
|报表集自定义 (添加、删除、修改报表)  <br/> |否  <br/> |是  <br/> |
|基于视频的屏幕共享指标  <br/> |否  <br/> |是  <br/> |
|视频指标  <br/> |否  <br/> |是  <br/> |
|可用数据量  <br/> |过去6个月  <br/> |过去6个月  <br/> |
|Microsoft 团队数据  <br/> |是  <br/> |是   <br/> |
   
### <a name="out-of-the-box-reports"></a>现成的报表

这两个版本的 CQD 都提供全新的体验, 从而为你提供了无需创建任何新报表的通话质量指标。 在后端处理完数据后, 您可以在报告中开始查看通话质量数据。
  
### <a name="overview-reports"></a>概述报表

CQD 的两个版本都为整体通话质量信息提供高级别的入口点, 但在摘要报告中显示信息的方式与详细报告不同。
  
摘要报告提供简化的选项卡式页面报告视图, 使用户可以快速浏览并理解整体通话质量状态和趋势。
  
四个选项卡包括:
  
- **整体通话质量**-提供有关所有流的信息, 这些流是服务器客户端流和客户端客户端流以及独立的服务器客户端和客户端客户端流 (按月和每天的趋势的形式)。
    
- **服务器-客户**端-提供服务器和客户端终结点之间的流的其他详细信息。
    
- **客户**端-客户端-提供两个客户端终结点之间的数据流的其他详细信息。
    
- **语音质量 SLA** -提供有关 Skype For Business Online 语音质量 SLA 中所含通话的信息。
    
### <a name="overall-call-quality-tab"></a>"整体通话质量" 选项卡

使用此选项卡上的数据, 通过查看流计数和较差的百分比来评估通话质量状态和趋势。 右上角的图例将显示哪些颜色和视觉元素表示这些指标。
  
![CQD 数据键](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
流分为三个组: "完好"、"差" 和 "未分类"。 还计算出的*百分比*值太差, 可让你将流的比率划分为*较差*的分类流计数。 由于*较差的% = 不良流/(差流 + 正常流) * 100* , 因此** 不受与多个未*分类*流的影响导致不受影响。 对于用于将流分类为差或好的内容, 请参阅["呼叫质量" 仪表板中的 "流分类](stream-classification-in-call-quality-dashboard.md)"。
  
使用左侧的刻度测量流计数值。
  
![CQD 数据计数](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
使用右侧的刻度测量差的百分比值。
  
![按分币 CQD 数据](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
也可以通过将鼠标悬停在条上来获取实际数值。
  
> [!NOTE]
> 下面的示例来自非常小的示例数据集, 并且值对于实际部署不切合实际。 
  
![CQD 数据数值](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
整个流卷是确定计算出的较差百分比的相关程度的重要因素。 总体流的数量越小, 报告的百分比值越低越可靠。
  
### <a name="server-client-tab-and-client-client-tabs"></a>服务器-客户端选项卡和客户端-客户端选项卡

这两个选项卡提供了在其终结点到终结点方案中发生的流的其他详细信息。 两个选项卡都具有四个可折叠的部分, 表示媒体流将流经的四个方案。
  
- 内部有线
    
- 外部有线
    
- 内部 Wifi
    
- 外部 Wifi
    
#### <a name="inside-test"></a>内部测试

在处理期间, CQD 后端使用建筑物信息将流分类为*内部*或*外部*流 (如果存在)。 每个流的终结点与子网地址相关联。 如果子网位于上载的生成信息中标记为 "InsideCorp" 的子网列表中, 则将其视为*内部*。 如果尚未上载生成信息, 则内部测试将始终将流分类为*外部*。 请注意, 内部测试服务器-客户端方案仅考虑客户端终结点。 由于服务器始终来自用户的视角, 因此不会在测试中考虑。
  
#### <a name="wired-vs-wifi"></a>有线与 wifi

根据名称指示, 这是基于客户端连接类型的分类标准。 同样, 服务器始终是有线的, 并且不会包含在计算中。
  
> [!NOTE]
> 如果有一个流, 则如果两个终结点中的一个终结点连接到 Wifi 网络, 则会在 CQD 中将其分类为 Wifi。 
  
## <a name="selecting-product-data-to-see-in-reports"></a>选择要在报表中查看的产品数据
<a name="BKMKProductFilter"></a>

在摘要和位置增强的报表中, 你可以使用 "**产品筛选器**" 下拉列表显示所有产品数据、仅 Microsoft 团队数据或仅 Skype For business Online 数据。
  
![屏幕截图显示 "产品" 筛选器控件, 其中包含 "所有"、"Microsoft 团队" 和 "Skype for business" 选项。](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
在 "详细报告" 中, 你可以使用 "**属于团队**" 维度在定义报表的过程中将数据筛选到 Microsoft 团队或 Skype For business Online 数据。
  
## <a name="upload-tenant-data-information"></a>上载租户数据信息
<a name="BKMKTenantDataInformationUpload"></a>

CQD 摘要报告仪表板包括**租户数据上载**页面, 该页面从右上角的 "设置" 菜单中选择 "**租户数据上载**"。 此页面用于管理员上载其自己的信息, 例如 IP 地址和地理信息的映射、映射每个无线 AP 及其 MAC 地址、将终结点映射到终结点的映射以及模型/类型等。
  
![CQD 仪表板](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. 在 "**租户数据上载**" 页面上, 使用下拉菜单选择要上载的数据文件类型。 "文件" 数据类型表示文件的内容 (例如, "建筑物" 指的是 IP 地址和建筑物的映射以及其他地理信息, "终结点" 指的是将终结点名称映射到终结点 "生成/模型/类型 ..."。信息)。 目前, 我们支持 cqd 的 "建筑物" 和 "终结点" 数据类型 (在预览阶段和尚未正式提供) 中, cqd.lync.com 仅支持上载 "生成" 数据类型。 后续版本中将添加更多数据类型。
    
2. 选择文件数据类型后, 单击 "**浏览**" 以选择数据文件。
    
   - 数据文件必须为 tsv (以制表符分隔的值) 文件或 .csv (以逗号分隔的值) 文件。 如果使用 .csv 文件, 则包含逗号的任何字段都必须用引号引起来, 或者删除了逗号。 例如, 如果你的建筑物名称是纽约州, 则在 .csv 文件中, 它应输入为 "纽约州, NY"。
    
   - 数据文件的大小不应大于50MB。

   - 已上载到 cqd.teams.microsoft.com 的文件已展开行限制1000000以提高查询性能。 我们也可能对 cqd.lync.com 施加该限制。
    
   - 对于每个数据文件, 文件中的每一列都必须与本主题后面部分所述的预定义数据类型匹配。
    
3. 选择数据文件后, 指定 "**开始日期**", (可选)**指定结束日期**。
    
4. 选择 "**开始日期**" 后, 选择 "**上传**" 将文件上传到 CQD 服务器。
    
    上载文件之前, 首先验证该文件。 验证后, 它将存储在 Azure blob 中。 如果验证失败或文件无法存储在 Azure blob 中, 则会显示一条错误消息, 要求对文件进行更正。 下图显示了当数据文件中的列数不正确时出现的错误。
    
     ![CQD 示例上载验证错误](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. 如果验证期间没有出现错误, 文件上载将成功。 然后, 你可以在 "我的上**传**" 表中看到上载的数据文件, 其中显示了当前租户在该页面底部的所有上载文件的完整列表。
    
    每个记录显示一个上载的租户数据文件, 其中包含文件类型、上次更新时间、时间段、说明、删除图标和下载图标。 若要删除文件, 请选择表格中的垃圾桶图标。 若要下载文件, 请选择表格的 "**下载**" 列中的 "下载" 图标。
    
     ![CQD 我的上传表](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### <a name="tenant-data-file-format-and-structure"></a>租户数据文件格式和结构
<a name="BKMKTenantDataFile"> </a>

### <a name="building-data-file"></a>生成数据文件
CQD 使用首先从 "展开网络 + NetworkRange" 列中派生出子网的数据文件, 然后将子网列联接到呼叫记录的第一个子网/第二个子网列, 以显示建筑物/城市/国家/地区 .。。 信息. 你上载的数据文件的格式必须满足以下情况才能在上载之前通过验证检查。
  
- 文件必须是 tsv 文件, 这意味着在每行中, 列由选项卡或 .csv 文件分隔, 每个列由逗号分隔。
    
- 数据文件的内容不包含表格标题。 这意味着数据文件的第一行应该是真实数据, 而不是像 "Network" 之类的标题。
    
- 对于每个列, 数据类型只能是 String、Number 或 Bool。 如果是数字, 则该值必须是一个数值;如果是 Bool, 则该值必须是0或1。
    
- 对于每一列, 如果数据类型为 string, 则数据可以为空 (但必须用适当的分隔符 (即制表符或逗号) 分隔。 这只是将该字段分配为空字符串值。
    
- 每一行必须有14列, 每一列必须具有以下数据类型, 并且列必须遵循下表中列出的顺序:
    
|**列名称**|**数据类型**|**示例**|
|:-----|:-----|:-----|
|网络  <br/> |String  <br/> |192.168.1.0  <br/> |
|NetworkName  <br/> |String  <br/> |美国/西雅图/西雅图-海-1  <br/> |
|NetworkRange  <br/> |数字  <br/> |个  <br/> |
|BuildingName  <br/> |String  <br/> |西雅图-海-1  <br/> |
|OwnershipType  <br/> |String  <br/> |制定  <br/> |
|BuildingType  <br/> |String  <br/> |终止  <br/> |
|BuildingOfficeType  <br/> |String  <br/> |技术  <br/> |
|城市  <br/> |String  <br/> |西雅图  <br/> |
|ZipCode  <br/> |String  <br/> |98001  <br/> |
|该国  <br/> |String  <br/> |我们  <br/> |
|省/市/自治区  <br/> |String  <br/> |WA  <br/> |
|区域  <br/> |String  <br/> |MSUS  <br/> |
|InsideCorp  <br/> |Bool  <br/> |1  <br/> |
|ExpressRoute  <br/> |Bool  <br/> |0  <br/> |
   
> [!IMPORTANT]
> 网络范围可用于表示 supernet (具有单个路由前缀的若干子网的组合)。 将检查所有新的生成上载, 查找任何重叠区域。 如果你以前上载了一个生成文件, 则应下载当前文件, 然后重新上载它以标识任何重叠, 并在再次上载之前修复该问题。 以前上载的文件中的任何重叠都可能会导致向报表中的建筑物进行错误的子网映射。 某些 VPN 实现不能准确报告子网信息。 建议将 VPN 子网添加到生成文件, 而不是子网的一个条目时, 将 VPN 子网中每个地址的单独条目添加为单独的32位网络。 每一行可以有相同的建筑物元数据。 例如, 对于 172.16.18.0/24, 而不是一行, 您应该有256行, 每个地址对应于 172.16.18.0/32 和 172.16.18.255/32 之间 (包括这两个地址) 的一行。 

### <a name="endpoint-data-file"></a>终结点数据文件
CQD 通过将终结点数据文件联接到调用记录的第一个客户端终结点名称/第二个客户端终结点名称列来显示终结点生成/模型/类型信息, 从而使用终结点数据文件。 你上载的数据文件的格式必须满足以下情况才能在上载之前通过验证检查。

- 文件必须是 tsv 文件, 这意味着在每行中, 列由选项卡或 .csv 文件分隔, 每个列由逗号分隔。

- 数据文件的内容不包含表格标题。 这意味着数据文件的第一行应该是真实数据, 而不是像 "终结点" 等标题。

- 对于每个列, 数据类型只能是字符串, 并且长度不应超过64个字符, 这是允许的最大长度。

- 对于每个列, 数据可以是空的 (但仍须使用适当的分隔符 (即制表符或逗号) 分隔。 这只是将该字段分配为空字符串值。

- 每行必须有7列, 并且列必须按照下表中列出的顺序排列。

- 终结点必须是唯一的, 否则上传将因重复行而失败, 因为它会导致不正确的联接。

-  EndpointLabel1、EndpointLabel2、EndpointLable3 是用户可自定义的标签, 它们可以是空字符串或用户喜欢的值, 如 "IT 部门指定的2018笔记本电脑"、"资产标签 5678" .。。如此.

|**列名称**|**数据类型**|**示例**|
|:-----|:-----|:-----|
|点  <br/> |String  <br/> |1409W3534  <br/> |
|EndpointMake  <br/> |String  <br/> |Fabrikam Inc。  <br/> |
|EndpointModel  <br/> |String  <br/> |Fabrikam 模型123  <br/> |
|EndpointType   <br/> |String  <br/> |着  <br/> |
|EndpointLabel1  <br/> |String  <br/> |它指定了2018笔记本电脑  <br/> |
|EndpointLabel2  <br/> |String  <br/> |资产标签5678  <br/> |
|EndpointLabel3  <br/> |String  <br/> |购买2018   <br/> |


## <a name="selecting-media-type-in-detailed-reports"></a>在 "详细报告" 中选择媒体类型
<a name="BKMKMediaType"></a>

详细报告支持查看音频、视频、应用程序共享和基于视频的屏幕共享媒体类型的质量和媒体可靠性。 特定于单个媒体类型的维度、度量值和筛选器具有 "音频"、"视频"、"应用共享" 或 "VBSS" 作为前缀。
  
![通话质量仪表板尺寸。](media/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
如果要查看单个媒体类型的维度和度量值, 可能需要新的媒体类型维度和筛选器。 例如, 若要使用显示不同媒体类型的总会话计数的报表, 请包括 "媒体类型" 维度。
  
![通话质量仪表板总流计数。](media/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a>相关主题
[设置 Skype for Business 通话分析](set-up-call-analytics.md)

[使用呼叫分析解决较差的通话质量](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通话分析和通话质量仪表板](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
