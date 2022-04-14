---
title: Microsoft Teams 分析和报告
author: serdarsoysal
ms.author: serdars
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
description: 本文介绍Microsoft Teams管理中心提供的Teams报表。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6a3cbf42c65d054befac8ad4e1f25d8be65f286
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853033"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams 分析和报告

Microsoft Teams管理中心提供了适用于Microsoft Teams的新分析和报告体验。 可以运行不同的报表来深入了解组织中的用户如何使用Teams。 例如，你可以看到有多少用户通过频道和聊天消息进行通信，以及他们用于连接到Teams的设备类型。 你的组织可以使用报表中的信息来更好地了解使用模式、帮助做出业务决策，以及为培训和沟通工作提供信息。

## <a name="how-to-access-the-reports"></a>如何访问报表

若要访问报表，必须是Microsoft 365或Office 365的全局管理员、Microsoft 365或Office 365中的全局读者、Teams服务管理员或Skype for Business管理员。若要详细了解Teams管理员角色以及每个管理员角色可以访问哪些报告，请参阅[使用Teams管理员角色来管理Teams](../using-admin-roles.md)。

转到Microsoft Teams管理中心，在左侧导航栏中，选择 **“分析”&报** 表，然后在 **“查看报表**”下选择要运行的报表。

> [!NOTE]
> Microsoft Teams管理中心中的报表与作为Microsoft 365 管理中心中Microsoft 365报表一部分的Teams的活动报表是分开的。 有关Microsoft 365 管理中心中的活动报告的详细信息，请[参阅Microsoft 365 管理中心中的Teams活动报告](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Teams报告参考

下面是Microsoft Teams管理中心提供的Teams报表的列表，以及每个报表中提供的一些信息的概述。

我们正在不断改进Teams报告体验，并添加功能和功能。 随着时间的推移，我们将在报表中构建其他功能，并在Microsoft Teams管理中心添加新报表。

|报告  |测量什么？ |
|---------|---------|
|[Teams 使用情况报告](teams-usage-report.md)  |  活动用户<br/>团队和频道中的活跃用户<br/>活动通道<br/>消息<br/>团队的隐私设置<br/>团队中的来宾   |
|[Teams 用户活动报告](user-activity-report.md)  | 用户在团队聊天中发布的消息<br/>用户在私人聊天中发布的消息<br/>  用户参与的 1：1 呼叫<br/> 用户组织的会议数 <br/>用户参与的会议数<br/>会议音频、视频和屏幕共享时间<br/>   用户的最后一个活动日期     |
|[Teams 设备使用报告](device-usage-report.md)   |  Windows 用户<br/>Mac 用户<br/>iOS 用户<br/>Android 手机用户     |
|[Teams 实时事件使用情况报表](teams-live-event-usage-report.md)   |  总视图<br>开始时间<br>事件状态<br>组织者<br>主持人<br>生产者<br>录制设置<br>生产类型    |
|[Teams PSTN 阻止用户报告](pstn-blocked-users-report.md)   |  显示名称<br>电话编号<br>原因<br>操作类型<br>操作日期和时间   |
|[Teams PSTN 分钟池报表](pstn-minute-pools-report.md) |  国家或地区<br>功能 (许可证)  <br>总分钟数<br>所用分钟数<br>可用分钟数|
|[Teams PSTN 使用情况报告 - 呼叫计划](pstn-usage-report.md#calling-plans)|  时间戳<br>用户名<br>电话编号<br>呼叫类型 <br>调用到<br>到国家或地区 <br>从中调用 <br>从国家或地区<br>负责<br>货币<br>持续时间<br>国内/国际<br>呼叫 ID<br>数字类型<br>国家或地区<br>会议 ID<br>功能 (许可证) |
|[Teams PSTN 使用情况报告 - 直接路由](pstn-usage-report.md#direct-routing)  |  时间戳<br>显示名称<br>SIP 地址<br>电话编号 <br>呼叫类型<br>调用到<br>开始时间<br>邀请时间<br>失败时间<br>结束时间<br>持续时间<br>数字类型<br>媒体旁路<br>SBC FQDN<br>Azure 区域<br>事件类型<br>最终 SIP 代码<br>最终 Microsoft 子代码<br>最终 SIP 短语<br>相关 ID  |
|[Teams信息保护许可证报告](information-protection-license-report.md)  | <br>用户是否具有通过更改通知推送其消息的有效许可证</br><br>用户触发的更改通知事件总数<br><br>哪些应用正在侦听组织范围的更改通知事件<br>|
|[Teams虚拟访问使用情况报告](virtual-visits-usage-report.md)  | 虚拟约会数<br>Bookings约会数<br>Teams电子健康记录 (与 EHR) 集成的约会的数量<br>约会的平均持续时间<br>与会者的平均大厅等待时间<br>开始时间<br>会议 ID<br>大厅等待时间<br>持续时间<br>地位<br>产品类型<br>与会者<br>发送的短信
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>使用户特定的数据匿名

若要使Teams用户活动中的数据和Teams设备使用情况报告匿名，必须是全局管理员。 这会隐藏报表及其导出中的可识别信息，例如显示名称、电子邮件和Microsoft Azure Active Directory ID。

1. 在Microsoft 365 管理中心中，转到 **设置** \> **组织设置**，然后在 **“服务”** 选项卡下选择 **“报表**”。
    
2. 选择 **“报** 表”，然后选择 **在所有报表中显示隐藏的用户、组和网站名称**。 此设置同时应用于Microsoft 365 管理中心中的使用情况报表以及Teams管理中心。
  
3. 选择 **“保存更改**”。

> [!NOTE]
> 启用此设置将取消识别[Teams用户活动报表](user-activity-report.md)和[Teams设备使用情况报告](device-usage-report.md)中的信息。 它不会影响Teams管理中心中提供的其他使用情况报告。
> 此设置也适用于Microsoft 365 管理中心、Microsoft Graph 和Power BI中的Microsoft 365使用情况报告。
