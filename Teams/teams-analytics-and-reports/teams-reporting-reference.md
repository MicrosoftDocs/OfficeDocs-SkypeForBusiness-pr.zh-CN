---
title: Microsoft Teams 分析和报告
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
- ms.teamsadmincenter.analyticsandreports.overview
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 在本文中，你将了解 Microsoft Teams 管理中心中提供的 Teams 报表。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0a688a3356ce31dd478c35082195ace8f6be4d47
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307657"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams 分析和报告

Microsoft Teams 管理中心提供了适用于 Microsoft Teams 的新分析和报告体验。 可以运行不同的报表来深入了解组织中的用户使用 Teams 的方式。 例如，可以查看有多少用户通过频道和聊天消息进行通信，以及他们用于连接到 Teams 的设备类型。 你的组织可以使用报告中的信息来更好地了解使用模式，帮助做出业务决策，并为培训和沟通工作提供信息。

## <a name="how-to-access-the-reports"></a>如何访问报表

若要访问报表，你必须是 Microsoft 365 或 Office 365 中的全局管理员、Microsoft 365 或 Office 365 中的全局读者、Teams 服务管理员或Skype for Business管理员。若要详细了解 Teams 管理员角色以及每个管理员角色可以访问的报表，请参阅[使用 Teams 管理员角色管理 Teams](../using-admin-roles.md)。

转到 Microsoft Teams 管理中心，在左侧导航中，选择“**分析&报表**”，然后在“**查看报表**”下，选择要运行的报表。

> [!NOTE]
> Microsoft Teams 管理中心中的报表与属于Microsoft 365 管理中心Microsoft 365 报表的 Teams 的活动报告分开。 有关Microsoft 365 管理中心中的活动报告的详细信息，请参阅[管理中心中的 Microsoft 365 报告](/microsoft-365/admin/activity-reports/activity-reports)。

## <a name="teams-reporting-reference"></a>Teams 报告参考

下面是跨不同环境的 Microsoft Teams 管理中心提供的 Teams 报表列表，以及每个报表中可用的一些信息的概述。

我们正在不断改进 Teams 报告体验，并添加特性和功能。 随着时间的推移，我们将在报表中构建其他功能，并在 Microsoft Teams 管理中心添加新报表。

|报告  |公共 |Gcc |GCCH |国防部 |测量什么？ |
|---------|---------|---------|---------|---------|---------|
|[Teams 使用情况报告](teams-usage-report.md)  |是|是|是|是|  活动用户<br/>团队和频道中的活动用户<br/>活动通道<br/>消息<br/>团队的隐私设置<br/>团队中的活动来宾  <br/>在共享频道) 中 (活动外部用户<br/>团队中特定于频道的详细信息 (新) |
|[Teams 用户活动报告](user-activity-report.md)  |是|是|是|是|活动内部和外部 (在共享频道) 用户<br/> 用户在团队聊天中发布的消息<br/>用户在私人聊天中发布的消息<br/>  1：1 呼叫参与的用户<br/> 用户组织的会议数 <br/>用户参与的会议数<br/>会议音频、视频和屏幕共享时间<br/>   用户的上次活动日期  <br>用户 (新) 的共享频道交互</br>   |
|[Teams 设备使用报告](device-usage-report.md)   |是|是|是|是|  Windows 用户<br/>Mac 用户<br/>iOS 用户<br/>Android 手机用户     |
|[teams 应用使用情况报告 (新) ](app-usage-report.md)   |是|是|否|否|  应用的活跃用户总数<br/>使用应用的活动团队总数<br/>新) 已安装 (应用总数<br/>非活动应用总数 <br/>新)  (1P 与 3P 与 LoB 应用的总使用情况     |
|[Teams 实时事件使用情况报表](teams-live-event-usage-report.md)   |是|是|否|否|  总视图<br>开始时间<br>事件状态<br>组织者<br>主持人<br>生产者<br>录制设置<br>生产类型    |
|[Teams PSTN 阻止的用户报告](pstn-blocked-users-report.md)   |是|是|否|否|  显示名称<br>电话号码<br>原因<br>操作类型<br>操作日期和时间   |
|[Teams PSTN 分钟池报告](pstn-minute-pools-report.md) |是|是|否|否|  国家或地区<br>功能 (许可证)  <br>总分钟数<br>使用的分钟数<br>可用分钟数|
|[Teams PSTN 使用情况报告 - 通话套餐](pstn-usage-report.md#calling-plans)|是|是|否|否|  时间戳<br>用户名<br>电话号码<br>呼叫类型 <br>调用到<br>到国家或地区 <br>从 调用 <br>来自国家或地区<br>负责<br>货币<br>持续时间<br>国内/国际<br>呼叫 ID<br>数字类型<br>国家或地区<br>会议 ID<br>功能 (许可证) |
|[Teams PSTN 使用情况报告 - 直接路由](pstn-usage-report.md#direct-routing)  |是|是|否|否|  时间戳<br>显示名称<br>SIP 地址<br>电话号码 <br>呼叫类型<br>调用到<br>开始时间<br>邀请时间<br>失败时间<br>结束时间<br>持续时间<br>数字类型<br>媒体旁路<br>SBC FQDN<br>Azure 区域<br>事件类型<br>最终 SIP 代码<br>最终Microsoft子代码<br>最终 SIP 短语<br>相关 ID  |
|[Teams 信息保护许可证报告](information-protection-license-report.md)  |是|是|否|否| <br>用户是否具有通过更改通知推送其消息的有效许可证</br><br>用户触发的更改通知事件总数<br><br>哪些应用正在侦听组织范围的更改通知事件<br>|
|[Teams 虚拟约会使用情况报告](/microsoft-365/frontline/virtual-appointments-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)|是|是|否|否| 虚拟约会数<br>预订约会数<br> (EHR) 集成约会的 Teams 电子健康记录数<br>约会的平均持续时间<br>与会者的平均大厅等待时间<br>开始时间<br>会议 ID<br>大厅等待时间<br>持续时间<br>地位<br>产品类型<br>与会者<br>部门<br>发送的短信<br>约会是否使用了高级虚拟约会功能|
|[Teams 高级虚拟约会活动报告](/microsoft-365/frontline/advanced-virtual-appointments-activity-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) |是|是|否|否|使用高级虚拟约会功能的用户数<br>使用短信通知的用户数<br>即将) 使用大厅聊天 (的用户数<br>执行按需约会的用户数|
|[Teams EHR 连接器虚拟约会报表](/microsoft-365/frontline/ehr-connector-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) |是|是|否|否| 开始时间<br>持续时间<br>会议组织者) 的主要 (名称<br>主要组织者的电子邮件 (会议组织者) 的电子邮件<br>部门<br>服务员<br>大厅等待时间<br>约会是否在分配限制内|
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>使用户特定的数据匿名

若要使 Teams 用户活动报告中的数据匿名，你必须是全局管理员。 全局管理员可以在报表及其导出中使用 MD5 哈希) 隐藏 (身份信息，例如显示名称、组名称、电子邮件和 AAD ID。

1. 在Microsoft 365 管理中心中，转到 **“设置** \> **组织设置”**，然后在“**服务**”选项卡下，选择“**报表**”。
    
2. 选择“ **报表**”，然后选择“ **在所有报表中显示隐藏的用户、组和站点名称**”。 此设置将应用于 Microsoft 365 管理中心 中的使用情况报告以及 Teams 管理中心。
  
3. 选择 **“保存更改**”。

> [!NOTE]
> 启用此设置将取消标识 [Teams 用户活动报告](user-activity-report.md)、 [Teams 设备使用情况报告](device-usage-report.md)和 [Teams 使用情况报告中](teams-usage-report.md)的用户、组和站点名称信息。 从 2021 年 9 月 1 日开始，此设置默认为每个人启用，这是我们持续承诺的一部分，以帮助保护重要信息并使公司能够支持其本地隐私法。 
>
>此设置也适用于 Microsoft 365 管理中心、Microsoft Graph 和 Power BI 中的 Microsoft 365 个使用情况报告。
