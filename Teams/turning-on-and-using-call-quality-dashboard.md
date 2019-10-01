---
title: 打开和使用呼叫质量仪表板
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
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
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
ms.custom:
- Reporting
description: '了解如何打开和使用呼叫质量仪表板，获取通话质量的摘要报告。 '
ms.openlocfilehash: 25f141f30691700414c3a24e705c7d8b490fd265
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328349"
---
# <a name="turn-on-and-use-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>打开和使用 Microsoft 团队和 Skype for business Online 的通话质量仪表板

了解如何配置 Office 365 组织以使用呼叫质量仪表板来监控通话质量。
  
通话质量仪表板（CQD）可深入了解使用 Microsoft 团队和 Skype for business Online 服务进行的通话的质量。 本主题介绍了开始收集可用于解决通话质量问题的数据的步骤。

目前，CQD 版本3和 CQD 版本2都可供使用。 CQD v3 可在<span>https://cqd.teams.microsoft.com</span>。 用您的 Microsoft 团队管理员凭据登录。

## <a name="latest-changes-and-updates"></a>最新更改和更新

CQD 版本3提供接近实时的 CQD 仪表板（延迟接近30分钟），并使用最终用户可识别信息（EUII），从而使管理员能够放大到用户级别。 此外，还可通过报表交互来支持新方案，例如：

- 按地区呼叫质量：
  - 按区域日期
  - 按区域聚合到每个小时
  - 特定位置
  - 特定子网
  - 受影响的用户或用户

- 按地区呼叫可靠性/失败：
  - 按区域日期
  - 按区域聚合到每个小时
  - 特定位置
  - 特定子网
  - 受影响的用户或用户

- 按区域对我的呼叫（RMC）进行评级：从按区域聚合到特定位置的特定位置到提供低 RMC 等级的用户。 CQD v3 还包括逐字反馈。
- 帮助者：可用于 P2P 呼叫或会议的特定用户或所有参与者和通话详细信息。 帮助识别基于网络位置、设备或固件的可能系统问题。  
- 客户端版本：查看每个客户端版本的会话和用户计数，或向下钻取以查看每个客户端版本的用户名。 产品和客户端类型的预生成筛选器帮助将版本集中到特定客户端。
- 终结点：显示映射到电脑/Mac 的 "生成/模型" 的计算机终结点。 按 "生成/模型" 显示聚合质量。 映射数据的上载类似于生成数据。

如果 EUII 访问不可用，则版本3还提供 RBAC 支持。  

管理员可通过 CQD 版本3管理 Skype for business Server 2019 （不仅仅是 Skype for business Online 和 Microsoft 团队）。 这需要混合实现和使用 "调用数据" 连接器。 有关详细信息，请参阅[计划通话数据连接器](/SkypeForBusiness/hybrid/plan-call-data-connector)。

已添加 CQD 版本2：

- Microsoft 团队和 Skype for business Online 的数据
- 摘要报告包括一个用于选择所有数据、Microsoft 团队数据或 Skype for Business Online 数据的产品筛选器
- 更新了视频和 VBSS 流质量分类逻辑。 请参阅用于分类器定义的[通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)。

有关[通话质量仪表板中可用的维度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)的列表，请参阅本文。
  
> [!NOTE]
> 若要查看有关仪表板的更新和更改的信息，请单击 "**好消息**" 中的链接！ 在仪表板上显示时横幅。

CQD 版本1已提供 Skype for Business Server 2015 管理员以下功能：

- 访问缓存的报表数据以快速访问
- 指向用于共享和发布信息的报表页面的深层链接
- 简化的报表编辑和创建以及报表说明的可编辑元数据
- 为在自定义仪表板中使用而提供对多维数据集数据的编程访问的 Web Api

## <a name="cqd-near-real-time-nrt-data"></a>CQD 近实时（NRT）数据

CQD v3 利用近乎实时的数据馈送。 通话记录在通话结束后的30分钟内将在 CQD 门户中可用。 从 NRT 管道中调用记录仅在从数据集内删除几个月后才可用。 CQD v3 将当前 v2 管道中的数据与 v3 管道中的 NRT 数据合并。 来自存档周期的数据的 v2 和 v3 门户查询将产生相同的结果。 NRT 数据的 V2 和 v3 数据查询和 NRT Data + PII 期间将有所不同。

### <a name="piieuii-data"></a>PII/EUII 数据

PII 或 EUII 数据仅来自 v3 管道。 由于合规性原因，PII/EUII 数据仅保留30天。 由于 NRT 数据超过30天的标记，将清除 PII/EUII 字段，从而导致 PII NRT 数据。 PII/EUII 字段是：

- 完整 IP 地址
- 媒体访问控制（MAC）地址
- 基本服务集标识符（BSSID）
- 会话初始协议（SIP） URI （仅 Skype for business）
- 用户主体名称 (UPN)
- 计算机终结点名称
- 用户逐字反馈
- 对象 ID （终结点用户的 Active Directory 对象 ID）

### <a name="date-controls"></a>日期控件

CQD v3 将添加以下新的滚动趋势类型：

- 5天
- 7天
- 30天
- 60-day
- 90-day

URL 日期参数现在可接受 "天" 字段。 "滚动日期" 报告将 "YYYY-MM-DD 格式" 中指定的日期用作趋势的最后一天。  URL 日期参数 "00" 表示 "今日"。

|URL| 滚动日趋势的结束日期|
|:---|:---|
|<span>https://<cqdv3>/Spd/#/Dashboard/<reportid>/2019-02/</span>   |2019年2月的当前日期|
|<span>https://<cqdv3>/Spd/#/Dashboard/<reportid>/2019-02-15/</span>|2019年2月15日|
|<span>https://<cqdv3>/Spd/#/Dashboard/<reportid>/00/</span>        |当前日期|
|||

默认情况下，该月的当前日期用作滚动日期趋势的最后一天。

### <a name="drill-thru-functionality"></a>钻取功能

CQD v3 支持使用 SPD 报表中的钻取或向下钻取字段。 如果选择这些维度字段，报表将自动打开不同的 "报表" 选项卡，并筛选所选值。 将鼠标悬停在其上方时，具有分配的钻取筛选器的字段将由不同的光标图标（指针）进行区分。

选中 "钻取" 字段时，仪表板将自动导航到新的指定选项卡，并应用具有所选值的筛选器。 如果该选项卡具有自己的钻取字段，并且选择了一个，则以前的钻取筛选器和新的钻取筛选器以及新的钻取。 这允许你构建可逐渐缩小结果数据集的报表。

例如，在通话质量的钻取报表中，用户可以单击想要 "钻取" 的日期，这将导致 "位置" 选项卡。

    ![Screenshot: shows the drill thru report](media/CQD-drill-thru-report.png)

可以从 "位置" 选项卡添加多个日期，例如将2019-09-22 添加到日期：2019-09-24： 

    ![Screenshot: add a date to the drill thru report](media/CQD-add-date.png)

> [!NOTE]
> 不要直接跳转到最后一个选项卡。没有从以前的钻取中选择的筛选器，结果将太大，无法在表格上显示。

## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a>激活 Microsoft 通话质量仪表板（CQD）摘要报告

在开始使用 CQD 之前，请为您的 Office 365 组织激活它，如下所示：

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 使用 Microsoft 团队服务管理员帐户登录到你的 Office 365 组织，然后选择 "**管理员**" 磁贴以打开管理中心。
2. 在左窗格中的 "**管理中心**" 下，选择 " **microsoft 团队**" 以打开 "microsoft 团队管理中心"。
3. 在 "Microsoft 团队管理中心" 中，在左窗格中选择 "**呼叫质量" 仪表板**。
4. \(在打开 https://<span>cqd.teams.microsoft.com<span/>\)的页面上，单击 "**登录**"，然后输入全局管理员帐户或 microsoft 团队服务管理员帐户信息。

    ![屏幕截图：显示凭据提示](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
登录后，一旦激活，CQD 将开始收集和处理数据。  
> [!NOTE]
> 可能需要一个或多个小时才能处理足够的数据，以在报表中显示有意义的结果。

![](media/sfb-logo-30x30.png) **使用 skype for business 旧版门户**的 skype for business 徽标的图标

1. 使用管理员帐户登录到您的 Office 365 组织，然后选择 "**管理员**" 磁贴以打开管理中心。
2. 在左窗格中的 "**管理中心**" 下，选择 " **microsoft 团队**" 以打开 "microsoft 团队管理中心"。
3. 在 Microsoft 团队管理中心中，在左窗格中选择 "**旧版门户**"，选择 "**工具**"，然后选择 " **Skype for Business Online 呼叫质量" 仪表板**。

     ![屏幕截图：选择 "呼叫质量" 仪表板](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. 在打开的页面上，用全局管理员帐户登录，然后在出现提示时提供帐户的凭据。

登录后，"呼叫质量" 仪表板将开始收集和处理数据。

## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Microsoft 团队和 Skype for business Online 的通话质量仪表板的功能

<a name="BKMKFeaturesOfTheCQD"> </a>

<!-- Siunies, this isn't very clear, it doesn't call out v1 and v2. unsure how to elaborate for v3, please comment -->
CQD 摘要报告提供为详细报告规划的功能的子集。 此处概括介绍了版本之间的差异：
  
|功能|摘要报告|详细报告|
|:--- |:--- |:--- |
|应用程序共享跃点数 | 否 | 是 |
|客户构建信息支持 | 是 | 是  |
|客户终结点信息支持 | 仅在<span>cqd.teams.microsoft.com 中<span/> | 仅在<span>cqd.teams.microsoft.com 中<span/> |
|向下钻取分析支持   | 否   | 是   |
|媒体可靠性指标   | 否   | 是   |
|现成的报表   | 是   | 是    |
|概述报表   | 是   | 是    |
|每用户报告集   | 否   | 是   |
|报表集自定义（添加、删除、修改报表）   | 否   | 是   |
|基于视频的屏幕共享指标   | 否   | 是   |
|视频指标   | 否   | 是   |
|可用数据量   | 过去6个月   | 过去6个月   |
|Microsoft 团队数据   | 是   | 是    |
| | | |

### <a name="out-of-the-box-reports"></a>现成的报表

所有版本的 CQD 都提供了一种可提供通话质量指标的体验，无需创建新报表。 在后端处理完数据后，您将在报告中看到通话质量数据。
  
### <a name="overview-reports"></a>概述报表

CQD 的所有版本都为整体通话质量信息提供高级别的入口点，但信息在摘要报告中的显示方式不同于详细的报告。  
  
摘要报告提供简化的选项卡式页面报告视图，以便你可以快速浏览和理解整体通话质量状态和趋势。

四个选项卡包括：
  
- **整体通话质量**-提供有关所有流的信息，它是显示每月和每天的趋势的聚合：
  - 服务器-客户端流
  - 客户端-客户端流
  - 单独的服务器-客户端和客户端-客户端流
- **服务器-客户端**-提供服务器和客户端终结点之间的流的详细信息。
- **客户端-客户端**-提供两个客户端终结点之间的流的详细信息。
- **语音质量 SLA** —提供有关 Skype For Business Online 语音质量 SLA 中所含通话的信息。

> [!NOTE]
> CQD 版本3适用于 Microsoft 团队、Skype for business Online 和 Skype for business 服务器。 要将 CQD 与 Skype for Business Server 2019 配合使用，您必须[配置 "呼叫数据连接器](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector)"。 请参阅在开始之前[计划通话数据连接器](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/plan-call-data-connector)。

- 按地区呼叫质量：

  - 按区域日期
  - 按区域聚合到每个小时
  - 特定位置
  - 特定子网
  - 受影响的用户或用户

- 按地区呼叫可靠性/失败：
  - 按区域日期
  - 按区域聚合到每个小时
  - 特定位置
  - 特定子网
  - 受影响的用户或用户

- 按区域对我的呼叫（RMC）进行评级：从按区域聚合到特定位置的特定位置到提供低 RMC 等级的用户。 CQD v3 还包括逐字反馈。
- 帮助者：可用于 P2P 呼叫或会议的特定用户或所有参与者和通话详细信息。 帮助识别基于网络位置、设备或固件的可能系统问题。  
- 客户端版本：查看每个客户端版本的会话和用户计数，或向下钻取以查看每个客户端版本的用户名。 产品和客户端类型的预生成筛选器帮助将版本集中到特定客户端。
- 终结点：显示映射到电脑/Mac 的 "生成/模型" 的计算机终结点。 按 "生成/模型" 显示聚合质量。 映射数据的上载类似于生成数据。

### <a name="overall-call-quality-tab"></a>"整体通话质量" 选项卡

使用此选项卡上的数据根据流计数和不良百分比评估通话质量状态和趋势。 右上角的图例将显示哪些颜色和视觉元素表示这些指标。
  
![屏幕截图：显示 "通话质量" 选项卡](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
流分为三个组： "完好"、"差" 和 "未分类"。 还计算出的*百分比*值太差，可让你将流的比率划分为*较差*的分类流计数。 由于*较差的% = 不良流/（差流 + 正常流） * 100*，*差%* 不受多个未*分类*流的存在的影响。 若要查看将流分类为差或好的内容，请参阅["呼叫质量" 仪表板中的 "流分类](stream-classification-in-call-quality-dashboard.md)"。
  
使用左侧的刻度测量流计数值。
  
![屏幕截图：显示流计数值](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
使用右侧的刻度测量差的百分比值。
  
![屏幕截图：显示差的% 值](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
也可以通过将鼠标悬停在条上来获取实际数值。
  
> [!NOTE]
> 下面的示例来自非常小的示例数据集，并且值对于实际部署不切合实际。
  
![屏幕截图：显示用于访问数据的鼠标](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
整个流卷可帮助确定计算出的较差百分比的相关程度。 总体流的数量越小，报告的百分比值越低越可靠。
  
### <a name="server-client-tab-and-client-client-tabs"></a>服务器-客户端选项卡和客户端-客户端选项卡

这两个选项卡提供了在其终结点到终结点应用场景中发生的流的详细信息。 "服务器-客户端" 选项卡具有四个可折叠的部分，表示媒体流将流经的四个方案。
  
- 内部有线
- 外部有线
- 内部 Wifi
- 外部 Wifi

同样，"客户端-客户端" 选项卡具有五个可折叠部分：

- 有线内部-有线内部
- 有线内部-有线外部
- 有线外部-有线外部
- 内部有线-内部 Wifi
- 内部有线-外部 Wifi

#### <a name="inside-test"></a>内部测试

在处理期间，CQD 后端使用建筑物信息将流分类为*内部*或*外部*流（如果存在）。 每个流的终结点与子网地址相关联。 如果子网位于上载的生成信息中标记为 "InsideCorp" 的子网列表中，则将其视为*内部*。 如果尚未上载生成信息，则内部测试始终会将流分类为*外部*流。  

> [!NOTE]
> 服务器客户端方案的内部测试仅考虑客户端终结点。 由于服务器始终来自用户的视角，因此不会在测试中考虑。
  
#### <a name="wired-vs-wifi"></a>有线与 wifi

根据名称指示，分类标准基于客户端连接的类型。 同样，服务器始终是有线的，并且不会包含在计算中。
  
> [!NOTE]
> 如果有一个流，则如果两个终结点中的一个终结点连接到 Wifi 网络，则会在 CQD 中将其分类为 Wifi。
  
## <a name="selecting-product-data-to-see-in-reports"></a>选择要在报表中查看的产品数据

<a name="BKMKProductFilter"></a>

在摘要和位置增强的报表中，你可以使用 "**产品筛选器**" 下拉列表显示所有产品数据、仅 Microsoft 团队数据或仅 Skype For business Online 数据。
  
![屏幕截图：显示产品筛选器控件选项](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
在 "详细报表" 中，可以使用 "**属于团队**" 维度将数据筛选到 Microsoft 团队或 Skype For business Online 数据。
  
## <a name="upload-tenant-data-information"></a>上载租户数据信息

<a name="BKMKTenantDataInformationUpload"></a>

CQD 摘要报告仪表板包括**租户数据上载**页面，该页面从右上角的 "设置" 菜单中选择 "**租户数据上载**"。 此页面用于管理员上载其自己的信息，例如：

- IP 地址和地理信息的地图
- 每个无线 AP 及其 MAC 地址的地图
- 终结点到终结点的映射/模型/类型等。
  
![屏幕截图：显示呼叫质量仪表板租户数据](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. 在 "**租户数据上载**" 页面上，使用下拉菜单选择要上传的数据文件类型。 "文件" 数据类型表示文件的内容（例如，"建筑物" 指的是 IP 地址和建筑物和其他地理信息的映射，"终结点" 指终结点名称和模型/类型信息的映射。 当前 CQD 支持 cqd.teams.microsoft.com 的 "建筑物" 和 "终结点" 数据类型（在预览阶段和尚未正式提供），cqd.lync.com 仅支持 "建筑物" 数据类型。
2. 选择文件数据类型后，单击 "**浏览**" 以选择数据文件。

   - 数据文件必须为 tsv （以制表符分隔的值）文件或 .csv （以逗号分隔的值）文件。 使用 .csv 文件时，包含逗号的任何字段都必须用引号引起来，或者删除逗号。 例如，如果建筑物名称为 NY，则在 .csv 文件中输入 "纽约州，NY"。
   - 数据文件不能大于 50 MB。
   - 上载到 cqd.teams.microsoft.com 的文件具有展开的行限制1000000以使查询性能更快。 此限制也适用于 CQD<span></span><span></span>上的 CQD v2。
   - 对于每个数据文件，文件中的每一列都必须与本主题后面部分所述的预定义数据类型匹配。
3. 接下来，指定**开始日期**，并根据需要**指定结束日期**。
4. 最后，选择 "**上传**" 将文件上载到 CQD 服务器。
    上载文件之前，首先验证该文件。 验证后，它将存储在 Azure blob 中。 如果验证失败或文件无法存储在 Azure blob 中，则会显示一条错误消息请求对文件的更正。 下图显示了数据文件中的列数不正确的示例错误。

     ![屏幕截图：显示上载验证错误](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. 如果验证期间未出现任何错误，则文件上载成功。 然后，您可以在 "我的上**传**" 表中看到上载的数据文件。 该页面底部还显示为当前租户上载的所有文件的完整列表。
    每个记录显示一个上载的租户数据文件，其中包含文件类型、上次更新时间、时间段、说明、删除图标和下载图标。 若要删除文件，请选择表格中的垃圾桶图标。 若要下载文件，请选择表格的 "**下载**" 列中的 "下载" 图标。

     ![屏幕截图：显示 "我的上传" 表](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)

6. 如果你选择使用多个生成数据文件或多个终结点数据文件，则某些报表的生成速度较慢。

### <a name="tenant-data-file-format-and-structure"></a>租户数据文件格式和结构

<a name="BKMKTenantDataFile"> </a>

### <a name="building-data-file"></a>生成数据文件

CQD 使用构建数据文件，这有助于提供有用的通话详细信息。 通过展开 "网络 + NetworkRange" 列，然后将 "子网" 列联接到呼叫记录的第一个子网或 "第二个子网" 列中，显示建筑物、城市、国家或地区信息，从而派生出子网列。 你上载的数据文件的格式必须满足以下条件才能在上载之前通过验证检查：
  
- 文件必须是 tsv 文件（由制表符分隔列）或 .csv 文件（列由逗号分隔）。
- 数据文件不包含表格标题行。 数据文件的第一行应为真实数据，而不是标题标签（如 "Network"）。
- 文件中的数据类型只能是 String、Integer 或 Boolean。 对于整数数据类型，值必须是一个数值。 布尔值必须是0或1。
- 如果列使用字符串数据类型，则数据字段可以为空，但仍须由制表符或逗号分隔。 空数据字段只是分配一个空字符串值。
- 每一行必须有14列，每一列必须具有相应的数据类型，并且列必须遵循下表中列出的顺序：

||||||||||||||||
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:---  |:--- |:---|
|**列字段名称**|NetworkIP  |NetworkName              |NetworkRange|BuildingName  |OwnershipType| BuildingType  |BuildingOfficeType|城市   |ZipCode|该国|省/市/自治区 |区域|InsideCorp&dagger;|ExpressRoute&Dagger;|VPN （可选）|
|**数据类型**        | String    | String                  |数字      | String       | String      | String        |String            |String |String |String |String|String|Boolean   |Boolean     |Boolean|
|**示例值**    |192.168.1.0|美国/西雅图/西雅图-海-1| 个         | 西雅图-海-1| 制定     | 终止|技术       |西雅图|98001  |我们     |WA    |MSUS  | 1        |0           | 0|
|||||||||||||||||

&dagger;此设置可用于反映子网是否位于企业网络内。 如果你决定，可以自定义其他用途的用法。

&Dagger;此设置可用于反映网络是否使用 Azure ExpressRoute。 如果你决定，可以自定义其他用途的用法。  

**示例行：**

```
192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0
```

> [!IMPORTANT]
> 网络范围可用于表示 supernet （具有单个路由前缀的若干子网的组合）。 将检查所有新的生成上载，查找任何重叠区域。 如果你以前上载了一个生成文件，则应下载当前文件，然后重新上载它以标识任何重叠，并在再次上载之前修复该问题。 以前上载的文件中的任何重叠都可能会导致向报表中的建筑物进行错误的子网映射。 某些 VPN 实现不能准确报告子网信息。 建议将 VPN 子网添加到生成文件，而不是子网的一个条目时，将 VPN 子网中每个地址的单独条目添加为单独的32位网络。 每一行可以有相同的建筑物元数据。 例如，对于 172.16.18.0/24，而不是一行，您应该有256行，每个地址对应于 172.16.18.0/32 和 172.16.18.255/32 之间（包括这两个地址）的一行。
>
> "VPN" 列是可选的，默认值为0。  如果 VPN 列的值设置为1，则该行表示的子网将完全展开，以匹配子网内的所有 IP 地址。  请谨慎使用，并且仅针对 VPN 子网，因为完全展开这些子网将对涉及生成数据的查询的查询时间产生负面影响。

### <a name="endpoint-data-file"></a>终结点数据文件

CQD 使用终结点数据文件。 在调用记录的第一个客户端终结点名称列或第二个客户端终结点名称列中使用列值来显示终结点的 "创建"、"模型" 或 "类型" 信息。 你上载的数据文件的格式必须满足以下条件才能在上载之前通过验证检查：

- 文件必须是 tsv 文件（由制表符分隔列）或 .csv 文件（列由逗号分隔）。
- 数据文件的内容不包含表格标题。 数据文件的第一行应为真实数据，而不是标题标签（如 "终结点"）。
- 所有七列仅使用字符串数据类型。 允许的最大长度为64个字符。
- 数据字段可以为空，但仍须由制表符或逗号分隔。 空数据字段只是分配一个空字符串值。
- 终结点必须是唯一的，否则上传将失败。 如果存在重复的行或两行使用同一终结点，则冲突将导致不正确的联接。
- EndpointLabel1、EndpointLabel2 和 EndpointLabel3 是可自定义的标签。 它们可以是空字符串或值，如 "IT 部门指定的2018膝上型计算机" 或 "资产标签 5678"。
- 每行必须有七列，并且列必须按以下顺序排列：

  **字段顺序：**

  终结点、EndpointModel、EndpointType、EndpointLabel1、EndpointLabel2、EndpointLabel3

  **示例行：**

  `1409W3534, Fabrikam Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018,`  

## <a name="create-custom-detailed-reports"></a>创建自定义详细报告

如果您想要创建一个特定报表，使其关注所提供的详细报表所提供的数据的维度，请创建一个自定义报表。

在 "登录\(**摘要报告**"\)屏幕上显示的屏幕顶部显示的报告下拉列表中，选择 "**详细报告**"，然后**单击**报表的 "操作" 菜单中的 "编辑"，以查看查询编辑器。 每个报告都可以通过对多维数据集进行查询得到。 报告是其查询返回的数据的可视化形式。 查询编辑器可帮助您编辑报表的这些查询和显示选项。 为新报表打开 "查询编辑器" 时，你会看到类似于以下屏幕截图的内容：

![编辑新报表](media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. 左侧窗格中选择了维度、度量和筛选器。 单击标题旁边的 "加号" 按钮以打开对话框，您可以在其中添加维度、测量或筛选，并选中相应的框。 如果您编辑现有报表，则可以取消选中现有值以将其删除。 有关详细信息，请参阅[通话质量仪表板中可用的维度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)。
2. 顶部显示了图表自定义选项。
3. 报表的预览在查询编辑器中可用。
4. 可以使用底部的 "编辑" 框创建详细的报表名称和说明。

## <a name="frequently-asked-questions"></a>常见问题

### <a name="why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data"></a>为什么 CQD v2 报表数据看起来与 CQD v3 报表数据不同？ 

如果你看到 CQD v2 和 v3 之间的数据差异，请确保在 "苹果" 和 "窄" 级别（而不是聚合级别）上执行数据比较或验证。 例如，如果你筛选 MSIT "建筑物 30" WiFi 团队桌面客户端数据的两个报表，则 v2 和 v3 的低质量百分比应该相同。

CQD v2 和 CQD v3 具有不同的总数，因为 CQD v3 具有 CQD v2 中不存在的新方案。 摘要总数或聚合的所有不带筛选器的数字均应不同。  

如果使用方案包括 Skype for Business Server 2019 调用，CQD v3 数据包括 Skype 机器人呼叫（自动助理、CVI、虚拟桌面界面）、实时事件和 PSTN 呼叫。 CQD v2 不使用此数据。 （CQD v3 需要配置了 cloud data connector 的 Skype for business Server 2019。）

例如，如果你在 CQD v2 摘要报告中看到200000音频5000流，但在5500失败时看到300000音频流是不寻常的（区别可能是由于 Skype for business 服务器2019通话、CVI 呼叫、PSTN 呼叫等）在 CQD v3 摘要报告中。

为消除意外的差异，请查看整个数据的多个细目。 通过一个或多个以下参数对数据进行筛选：

- User Agent Category Pair
- 第一产品
- 第二产品

### <a name="other-expected-differences-between-cqd-v2-and-cqd-v3"></a>CQD v2 和 CQD v3 之间的其他预期差异

团队中有多种质量和可靠性改进，而不是 Skype for business Online：

- 自动重新连接
- 快速漫游
- 改进的黑白管理

比较这两个服务的数据时：

- 选择具有紧密焦点的方案，如企业有线连接、Windows 桌面或单个区域或建筑物。
- 检查团队 MR、TR 或 MP IP 范围。 团队范围比 Skype for business Online 更新，并且可能导致与防火墙的连接问题
- 不要比较汇总或顶级数字。 这些比较将使你能够将企业有线连接上的 Skype for business Online 通话的大型通话量与 LTE 或专用网络上的一小大量团队通话进行比较。
- 注意位置偏向和人口差异：有许多比较过于不同的比较非常有用：
  - NOAM： APAC
  - 纽约州： Goa
  - 有线 : wifi
  - 公司网络：家庭网络
  


## <a name="related-topics"></a>相关主题

[通话质量仪表板中可用的维度和衡量指标](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)

[设置 Skype for Business 通话分析](set-up-call-analytics.md)

[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通话分析和通话质量仪表板](difference-between-call-analytics-and-call-quality-dashboard.md)
