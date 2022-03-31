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
description: 本文介绍在 Microsoft Teams 管理中心Teams报表。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b773b2d214bd105b8ca94850c0ddbc6e8c23757a
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556353"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams 分析和报告

Microsoft Teams 管理中心Microsoft Teams新的分析和报告体验。 可以运行不同的报表来深入了解组织中用户如何使用 Teams。 例如，你可以看到多少用户通过通道和聊天消息进行通信，以及他们用于连接到Teams。 组织可以使用报告中的信息更好地了解使用模式、帮助做出业务决策，以及告知培训和沟通工作。

## <a name="how-to-access-the-reports"></a>如何访问报表

若要访问报表，您必须是 Microsoft 365 或 Office 365 中的全局管理员、Microsoft 365 或 Office 365 中的全局Teams管理员或 Skype for Business 管理员。若要详细了解Teams角色以及每个管理员角色可以访问哪些报告，请参阅使用Teams[管理员角色管理Teams](../using-admin-roles.md)。

转到Microsoft Teams中心，在左侧导航栏中，选择"分析&报表"，然后在"查看报表"下，选择要运行的报表。

> [!NOTE]
> Microsoft Teams管理中心中的报表独立于 Teams 中Microsoft 365活动报告Microsoft 365 管理中心。 有关活动报告中的活动报告Microsoft 365 管理中心，请参阅Teams[中的活动Microsoft 365 管理中心](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Teams报告参考

下面是管理中心Teams报表的列表Microsoft Teams以及每个报告中提供的一些信息的概述。

我们正在不断改进报告体验Teams添加特性和功能。 随着时间的过去，我们将向报表构建其他功能，并添加新报表，Microsoft Teams管理中心。

|报告  |测量什么？ |
|---------|---------|
|[Teams 使用情况报告](teams-usage-report.md)  |  活动用户<br/>团队和频道中的活跃用户<br/>活动频道<br/>消息<br/>团队的隐私设置<br/>团队中的来宾   |
|[Teams 用户活动报告](user-activity-report.md)  | 用户在团队聊天中发布的消息<br/>用户在私人聊天中发布的消息<br/>  1：1 呼叫参与的用户<br/> 用户组织的会议数 <br/>用户参与的会议数<br/>会议音频、视频和屏幕共享时间<br/>   用户的上次活动日期     |
|[Teams 设备使用报告](device-usage-report.md)   |  Windows 用户<br/>Mac 用户<br/>iOS 用户<br/>Android 手机用户     |
|[Teams 实时事件使用情况报表](teams-live-event-usage-report.md)   |  总视图<br>开始时间<br>事件状态<br>组织者<br>演示者<br>生成者<br>录制设置<br>生产类型    |
|[Teams PSTN 阻止的用户报告](pstn-blocked-users-report.md)   |  显示名称<br>电话数字<br>原因<br>操作类型<br>操作日期和时间   |
|[Teams PSTN 分钟池报告](pstn-minute-pools-report.md) |  国家或地区<br>功能 (许可证)  <br>总分钟数<br>使用的分钟数<br>可用分钟数|
|[Teams PSTN 使用情况报告 - 呼叫计划](pstn-usage-report.md#calling-plans)|  时间戳<br>用户名<br>电话数字<br>呼叫类型 <br>调用到<br>到国家/地区 <br>从 调用 <br>从国家/地区<br>费用<br>货币<br>持续时间<br>国内/国际<br>呼叫 ID<br>数字类型<br>国家或地区<br>会议 ID<br>功能 (许可证) |
|[Teams PSTN 使用情况报告 - 直接路由](pstn-usage-report.md#direct-routing)  |  时间戳<br>显示名称<br>SIP 地址<br>电话数字 <br>呼叫类型<br>调用到<br>开始时间<br>邀请时间<br>故障时间<br>结束时间<br>持续时间<br>数字类型<br>媒体旁路<br>SBC FQDN<br>Azure 区域<br>事件类型<br>最终 SIP 代码<br>最终 Microsoft 子代码<br>最终 SIP 短语<br>关联 ID  |
|[Teams信息保护许可证报告](information-protection-license-report.md)  | <br>用户是否具有通过更改通知推送其消息的有效许可证</br><br>用户触发的更改通知事件总数<br><br>哪些应用正在侦听组织范围的更改通知事件<br>|
|[Teams虚拟访问使用情况报告](virtual-visits-usage-report.md)  | 虚拟访问数<br>访问Bookings数<br>EHR Teams电子健康记录 (集成) 访问的数量<br>平均访问持续时间<br>与会者的平均大厅等待时间<br>开始时间<br>会议 ID<br>大厅等待时间<br>持续时间<br>状态<br>产品类型<br>与会者<br>发送短信
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>使用户特定的数据匿名

若要使用户活动Teams设备使用情况Teams数据匿名，您必须是全局管理员。 这会隐藏报表及其导出显示名称、电子邮件Microsoft Azure Active Directory ID 等可识别信息。

1. 在Microsoft 365 管理中心，转到"**设置**\>组织"设置，**在"服务"选项卡下** 选择"报表 **"**。
    
2. 选择 **"** 报表"，然后选择"在所有报告中显示隐藏的用户、组 **和网站名称"**。 此设置同时应用于管理中心Microsoft 365 管理中心使用情况Teams报表。
  
3. 选择" **保存更改"**。

> [!NOTE]
> 启用此设置将取消标识用户Teams[报告](user-activity-report.md)和设备Teams[报告的信息](device-usage-report.md)。 它不会影响管理中心内提供的其他Teams报告。
> 此设置也适用于 Microsoft 365、Microsoft Microsoft 365 管理中心 和 Graph Power BI 中的Power BI。
