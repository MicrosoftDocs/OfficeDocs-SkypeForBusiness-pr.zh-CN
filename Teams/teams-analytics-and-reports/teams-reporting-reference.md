---
title: Microsoft Teams 分析和报告
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
- ms.teamsadmincenter.analyticsandreports.overview
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 本文介绍在 Microsoft Teams 管理中心Teams报表。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6d195c90dc7e959146546dde1a75fedf0764c24a
ms.sourcegitcommit: 66e7b28ba1c0433535eb6a3e7d883851c27d9d1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "51478342"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams 分析和报告

新的分析和报告体验可在 Microsoft Teams 管理中心Microsoft Teams体验。 可以运行不同的报告来深入了解组织中用户如何使用Teams。 例如，你可以看到多少用户通过通道和聊天消息进行通信，以及他们用于连接到Teams。 组织可以使用报告中的信息更好地了解使用模式、帮助做出业务决策，以及告知培训和沟通工作。

## <a name="how-to-access-the-reports"></a>如何访问报表

若要访问报表，你必须是管理员或管理员Microsoft 365 Office 365、Teams管理员或Skype for Business管理员。若要详细了解Teams角色以及每个管理员角色可以访问哪些报告，请参阅使用 Teams[管理员角色管理Teams。](../using-admin-roles.md)

转到Microsoft Teams中心，在左侧导航栏中，选择"分析&报表"，然后在"报表"下选择要运行的报表。 

> [!NOTE]
> Microsoft Teams管理中心中的报表独立于Teams管理中心中Microsoft 365活动Microsoft 365报表。 有关管理中心中的活动报告Microsoft 365，请参阅 Teams 管理中心[Microsoft 365活动报告](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Teams报告参考

下面是管理中心Teams报表的列表Microsoft Teams以及每个报告中可用的一些信息的概述。

我们正在不断改进报告体验Teams添加特性和功能。 随着时间的过去，我们将向报表构建其他功能，并添加新报表，Microsoft Teams管理中心。

|报告  |测量什么？ |
|---------|---------|
|[Teams 使用情况报告](teams-usage-report.md)  |  活动用户<br/>团队和频道中的活跃用户<br/>活动频道<br/>消息<br/>团队的隐私设置<br/>团队中的来宾   |
|[Teams 用户活动报告](user-activity-report.md)  | 用户在团队聊天中发布的消息<br/>用户在私人聊天中发布的消息<br/>  1：1 呼叫参与的用户<br/> 组织的会议用户数 <br/>参与会议的用户数<br/>会议音频、视频和屏幕共享时间<br/>   用户的上次活动日期     |
|[Teams 设备使用报告](device-usage-report.md)   |  Windows 用户<br/>Mac 用户<br/>iOS 用户<br/>Android 手机用户     |
|[Teams 实时事件使用情况报表](teams-live-event-usage-report.md)   |  总视图<br>开始时间<br>事件状态<br>组织者<br>演示者<br>生成者<br>录制设置<br>生产类型    |
|[TeamsPSTN 阻止的用户报告](pstn-blocked-users-report.md)   |  显示名称<br>电话数字<br>原因<br>操作类型<br>操作日期和时间   |
|[TeamsPSTN 分钟池报告](pstn-minute-pools-report.md) |  国家或地区<br>功能 (许可证)  <br>总分钟数<br>使用的分钟数<br>可用分钟数|
|[TeamsPSTN 使用情况报告 - 呼叫计划](pstn-usage-report.md#calling-plans)|  时间戳<br>用户名<br>电话数字<br>呼叫类型 <br>调用到<br>到国家/地区 <br>从 调用 <br>从国家/地区<br>费用<br>货币<br>持续时间<br>国内/国际<br>呼叫 ID<br>数字类型<br>国家或地区<br>会议 ID<br>功能 (许可证) |
|[TeamsPSTN 使用情况报告 - 直接路由](pstn-usage-report.md#direct-routing)  |  时间戳<br>显示名称<br>SIP 地址<br>电话数字 <br>呼叫类型<br>调用到<br>开始时间<br>邀请时间<br>故障时间<br>结束时间<br>持续时间<br>数字类型<br>媒体旁路<br>SBC FQDN<br>Azure 区域<br>事件类型<br>最终 SIP 代码<br>最终 Microsoft 子代码<br>最终 SIP 短语<br>关联 ID  |

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>使用户特定的数据匿名

若要使用户活动Teams设备使用情况报告匿名Teams，您必须是全局管理员。 这会在报表及其导出中隐藏显示名称、电子邮件和 AAD ID 等可识别信息。

1. 在Microsoft 365管理中心，转到"设置 Org设置"，在"服务" \> **选项卡** 下，选择"报表 **"。**
    
2. 选择 **"报告**"，然后选择"**显示匿名标识符"。** 此设置既应用于管理中心中的使用情况Microsoft 365，也适用于Teams中心。
  
3. 选择"**保存更改"。**

> [!NOTE]
> 启用此设置将取消标识用户Teams[报告](user-activity-report.md)和设备Teams[报告的信息](device-usage-report.md)。 它不会影响管理中心内提供的其他Teams报告。
