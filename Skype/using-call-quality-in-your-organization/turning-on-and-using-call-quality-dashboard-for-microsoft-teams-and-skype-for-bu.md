---
title: "打开并使用 Microsoft 团队和 Skype for Business Online 的呼叫质量仪表板"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.ToolsCallQualityDashboard
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
description: "See how to turn on and use the Skype for Business Online Call Quality Dashboard and get summary reports of quality of calls. "
---

# 打开并使用 Microsoft 团队和 Skype for Business Online 的呼叫质量仪表板

了解如何配置Office 365组织使用呼叫质量仪表板监视呼叫质量。
  
> [!重要信息]
> 本文是由机器翻译的，请参阅[免责声明](553fa13c-92d2-4d5c-a3d5-41a073cb047c.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/553fa13c-92d2-4d5c-a3d5-41a073cb047c) 中查找本文的英文版本以便参考。
  
呼叫质量仪表板 (CQD) Microsoft Teams和Skype for Business Online让您能够使用Microsoft Teams和Skype for Business服务进行呼叫的质量的见解。本主题介绍您需要完成以开始收集数据的步骤。
  
> [!注释]
> CQD 详细报告目前作为技术预览版提供给所有客户。 
  
## 最新更改和更新

对 CQD 的最新更改如下所示：
  
- 包括Microsoft Teams除了Skype for Business Online数据的数据。
    
- 摘要报表包括产品筛选器以选择所有数据、 Microsoft Teams数据或Skype for Business Online数据。
    
请参阅这篇文章的列表的[维度和度量值提供为 Microsoft 团队呼叫质量仪表板和 Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard-for-microsoft-teams.md)。
  
> [!注释]
> 通过单击仪表板中的" **好消息!**"即可获取有关仪表板更新和更改的信息。你可以转到[呼叫质量仪表板](https://aka.ms/CQDOnline)。 
  
## 激活 Microsoft 呼叫质量仪表板 (CQD) 摘要报表

您可以开始使用 CQD 之前，您需要激活它为您Office 365的组织。
  
1. 登录到您的Office 365组织使用管理员帐户，，然后选择 **管理员**磁贴以打开管理中心中。
    
2. 在左窗格中，在 **管理居中对齐**、 下选择以打开Skype for Business管理中心中的 **Skype for Business** 。
    
3. 在Skype for Business管理中心中，在左窗格中，选择 **工具**，然后选择 **Skype for Business Online 呼叫质量仪表板**。
    
     ![Skype for Business tools](../images/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. 在打开的页面，您的全局管理员帐户登录，然后当系统提示您的帐户提供的凭据。
    
     ![CQD Login](../images/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
您登录后，一次激活后, CQD 将开始收集和处理数据。
  
> [!注释]
> 可能需要几个小时才能处理足够的数据在报表中显示有意义的结果。 
  
## Skype for Business Online 呼叫质量仪表板的功能
<a name="BKMK_FeaturesOfTheCQD"> </a>

CQD 摘要报告提供计划用于详细报告的功能子集。这两个版本之间的差异概括如下：
  
|**功能**|**摘要报告**|**详细报告**|
|:-----|:-----|:-----|
|应用程序共享指标  <br/> |否  <br/> |是  <br/> |
|客户建筑物信息支持  <br/> |是  <br/> |是  <br/> |
|向下钻取分析支持  <br/> |否  <br/> |是  <br/> |
|媒体可靠性指标  <br/> |否  <br/> |支持  <br/> |
|全新的报表  <br/> |是  <br/> |是  <br/> |
|报告概述  <br/> |是  <br/> |是  <br/> |
|每个用户的报告集  <br/> |否  <br/> |是  <br/> |
|报告集自定义（添加、删除、修改报告）  <br/> |否  <br/> |是  <br/> |
|基于视频的屏幕共享指标  <br/> |否  <br/> |是  <br/> |
|视频指标  <br/> |否  <br/> |是  <br/> |
|可用数据量  <br/> |过去 6 个月  <br/> |过去 6 个月  <br/> |
|Microsoft 小组数据  <br/> |支持  <br/> |支持  <br/> |
   
### 全新的报表

CQD 这两个版本提供的-现成体验，使您可以呼叫质量标准，而无需创建任何新报表。一旦在后端中处理数据时，就可以开始看到呼叫质量数据在报表中。
  
### 报告概述

两个版本的 CQD 都提供总体呼叫质量信息的高级别入口点，但是在摘要报告中显示信息的方式与详细报告不同。
  
摘要报告提供简化的选项卡式页面报告视图，使用户可以快速浏览并了解总体呼叫质量状态和趋势。
  
四个选项卡包括：
  
- **整体呼叫质量**-提供有关流，这是服务器客户端流聚合和客户端流以及单独的服务器客户端和客户端流，每月和每日趋势的窗体中的信息。
    
- **服务器-客户端** - 提供服务器与客户端终结点之间的数据流的其他详细信息。
    
- **客户端-客户端** - 提供两个客户端终结点之间的数据流的其他详细信息。
    
- **语音质量 SLA** - 提供有关呼叫Skype for Business Online语音质量 SLA 中包含的信息。
    
### "总体呼叫质量"选项卡

使用此选项卡上的数据来评估呼叫质量状态和趋势查看流计数和较差的百分比。在右上角中的图例显示的颜色和视觉元素表示这些指标。
  
![CQD Data key](../images/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
流分为三组： 良好、 较差，并且未分类。那里还计算 *不佳的百分比*  值该授予您流的比例划分为 *较差*  了总保密的流计数。由于 *较差 %= 较差流 / （较差流 + 良好流） * 100*  ，这使得 *较差 %*  通过使用多个 *自解除保密*  流状态不会受到影响。什么用于分类为较差或良好流，请参阅[https://aka.ms/cqd_quality_thresholds](https://aka.ms/cqd_quality_thresholds)。
  
使用左侧的刻度可衡量呼叫计数值。
  
![CQD data count](../images/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
使用右侧的刻度可衡量较差百分比值。
  
![CQD data per cent](../images/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
将鼠标悬停在条上，你也可以获取实际数值。
  
> [!注释]
> 下面的示例是从一组的很小的示例数据，并值不适合实际部署。 
  
![CQD Data numeric](../images/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
总体数据流量是用于确定计算的较差百分比有多相关的一个重要因素。总体数据流越小，报告的较差百分比值越不可靠。
  
### 服务器端选项卡上和客户选项卡

这两个选项卡都提供发生在其终结点至终结点方案中的数据流的其他详细信息。这两个选项卡都有四个可折叠的部分，表示媒体数据流的四种传输方案。
  
- 内部有线
    
- 外部有线
    
- 内部 Wifi
    
- 外部 Wifi
    
#### 内部测试

在处理期间，CQD 后端分类为 *内部*  或 *外部*  使用构建信息流，如果存在。终结点的每个流都有子网地址相关联。如果子网的上载的构建信息中的子网列表中，将其视为内。如果在构建信息具有尚未上载内, 测试将始终为 *外部*  分类流。请注意，内部服务器客户端方案检验只考虑客户端终结点。因为服务器始终外部从用户的角度来看，这不占测试中。
  
#### 与 wifi 有线

顾名思义，此分类条件以客户端连接的类型为基础。此外，服务器始终是有线的，不包括在计算中。
  
> [!注释]
> 如果两个终结点的其中一个已连接到 Wifi 网络给定流、，然后归为 Wifi CQD 中。 
  
## 选择要在报表中查看的产品数据
<a name="BKMK_FeaturesOfTheCQD"> </a>

在摘要和位置增强报表中，您可以使用 **产品筛选器** 下拉列表以显示所有产品数据，仅Microsoft Teams数据或仅Skype for Business Online数据。
  
![Screenshot shows the Product Filter control with options for All, Microsoft Teams, and Skype for Business.](../images/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
详细的报表中可以使用工作组维度到Microsoft Teams或Skype for Business Online定义报表的数据的数据进行筛选。
  
## 上载建筑物信息
<a name="BKMK_FeaturesOfTheCQD"> </a>

CQD 摘要报表仪表板中包含一个 **租户数据上载**页，通过从右上角中的设置菜单中选择 **上载租户数据**访问。此页面用于管理员上载其自己的信息，例如映射的 IP 地址和地理位置的信息，每个无线接入点和其 MAC 地址映射，等等。
  
![CQD Dashboard](../images/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. 在 **租户数据上载**页上，使用下拉菜单中选择数据文件类型可上载。文件数据类型表示该文件的内容 （例如，"构建"指的 IP 地址映射和构建以及其他地理位置的信息）。当前我们仅支持"构建"数据类型。将与后续版本添加一些更多数据类型。
    
2. 在选择文件数据类型后，单击 **浏览**以选择数据文件。
    
  - 数据文件必须.tsv （以制表符分隔的值） 文件或.csv （逗号分隔值） 文件。如果使用.csv 文件，包含逗号的任何字段必须包含引号或已删除的逗号。例如，如果构建名称为 NY，纽约州，.csv 文件中它应输入为"NY，纽约州"。
    
  - 数据文件的大小不得超过 50MB。
    
  - 对于每个数据文件，文件中的每一列都必须与本主题后面部分所述的预定义的数据类型相匹配。
    
3. 选择数据文件之后，指定 **开始日期**以及 （可选） **指定的结束日期**。
    
4. 在选择 **开始日期**后，请选择" **上载**"以将文件上载到 CQD 服务器。
    
    上载文件之前，首先验证。一旦验证，则它将存储在 Azure blob。如果验证失败或文件将无法存储在 Azure blob，将显示一条错误消息，请求对文件的更正。下图显示数据文件中的列数不正确发生错误。
    
     ![CQD Example upload validation error](../images/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. 如果在验证过程中未出现任何错误，则文件上载将会成功。然后，你可以在" **我的上载文件**"表中看到已上载的数据文件，该表在页面底部显示当前租户的所有已上载文件的完整列表。
    
    每个记录显示一个上载的租户数据文件的文件类型、 上次更新时间、 时间段、 说明、 删除和下载图标。要删除的文件，选择表格中的废纸篓图标。若要下载的文件，请表的 **下载**列中选择下载图标。
    
     ![CQD My Uploads table](../images/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### 租户数据文件格式和建筑物数据文件结构
<a name="BKMK_TenantDataFile"> </a>

你上载的数据文件的格式必须满足以下条件才能在上载之前通过验证检查。
  
- 文件必须.tsv 文件，这意味着，在每个行中，列隔开选项卡上或使用逗号分隔每个列的.csv 文件。
    
- 数据文件的内容不包括表标题。不头，表示数据文件的第一行都应实际数据，如"网络"等。
    
- 每个列的数据类型只能字符串、 数字或布尔值。如果它是数字，该值必须是数字值;如果这是布尔值，该值必须 0 或 1。
    
- 每个列的数据类型是字符串，如果数据可以为空 (但仍然必须用相应分隔分隔 （即制表符或逗号）。这只需将该字段空字符串值。
    
- 每一行必须有 14 列，每一列必须具有以下数据类型，并且列必须遵循下表中列出的顺序：
    
|**列名**|**数据类型**|**示例**|
|:-----|:-----|:-----|
|网络  <br/> |字符串  <br/> |192.168.1.0  <br/> |
|NetworkName  <br/> |字符串  <br/> |USA/Seattle/SEATTLE-SEA-1  <br/> |
|NetworkRange  <br/> |数字  <br/> |26  <br/> |
|BuildingName  <br/> |字符串  <br/> |SEATTLE-SEA-1  <br/> |
|OwnershipType  <br/> |字符串  <br/> |Contoso  <br/> |
|BuildingType  <br/> |字符串  <br/> |IT Termination  <br/> |
|BuildingOfficeType  <br/> |字符串  <br/> |工程  <br/> |
|城市  <br/> |字符串  <br/> |Seattle  <br/> |
|邮政编码  <br/> |字符串  <br/> |98001  <br/> |
|国家/地区  <br/> |字符串  <br/> |US  <br/> |
|州  <br/> |字符串  <br/> |WA  <br/> |
|Region  <br/> |字符串  <br/> |MSUS  <br/> |
|InsideCorp  <br/> |布尔值  <br/> |1  <br/> |
|ExpressRoute  <br/> |布尔值  <br/> |0  <br/> |
   
> [!重要信息]
> 网络范围可用于表示超网（多个子网的组合，具有单个路由前缀）。将在所有新建筑物上载中检查是否存在重叠范围。如果你之前已经上载一个建筑物文件，则应该下载当前文件并将其重新上载以识别任何重叠，并在再次上载之前解决此问题。以前上载的文件中的任何重叠都可能导致在报告中错误地将子网映射到建筑物。 > 某些 VPN 实现无法准确报告子网信息。添加到构建一个文件，而不是一个条目的子网的 VPN 子网时建议的单独条目添加 VPN 网中的每个地址作为单独的 32 位网络。每个行具有相同的构建元数据。例如，而不是 172.16.18.0/24 一行，应具有 256 行，通过一行 172.16.18.0/32 和 172.16.18.255/32，包括之间的每个地址。 
  
## 在详细报告中选择媒体类型
<a name="BKMK_FeaturesOfTheCQD"> </a>

详细的报表支持查看质量和媒体可靠性音频、 视频、 应用程序共享和基于视频的屏幕共享媒体类型。维度、 度量和单个媒体类型特定的筛选器具有"音频"、"视频"、"AppSharing"或"VBSS"作为前缀。
  
![Call Quality Dashboard Dimensions.](../images/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
如果您想要查看的维度和度量值为单个媒体类型，可能需要新的媒体类型维度和筛选。例如，如果希望显示总会话计算跨不同的媒体类型的报告，请包括媒体类型维度。
  
![Call Quality Dashboard Total Stream Count.](../images/21d5d0dc-2321-415e-8ef2-cea06165601c.png)
  
## 
<a name="MT_Footer"> </a>

> [!注释]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

