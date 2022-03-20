---
title: 会议、网络研讨会和直播活动
ms.reviewer: ''
description: 管理员在 Microsoft Teams 中推出和配置会议、网络研讨会和直播活动的指南。
ms.topic: article
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: ffd0ad9f9b765839a4543dd8600b558000fa164f
ms.sourcegitcommit: abe942c294ed5fca70efdf039d38d611b9c21fe9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2022
ms.locfileid: "63564734"
---
# <a name="meetings-webinars-and-live-events"></a>会议、网络研讨会和直播活动 

在 Microsoft Teams 中有多种开会方式：会议、网络研讨会和直播活动。 

本文面向管理员和 IT 专业人员介绍了会议、网络研讨会和直播活动之间的差异。 然后提供了指向快速向用户推出此功能所需信息的链接。

> [!Note]
> 有关在不同平台上快速配置 Teams 会议和活动的详细信息，请参阅 [Teams 功能（按平台）](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。


[会议](#meetings)、[网络研讨会](#webinars) 和 [直播活动](#live-events) 是会议的全部三种类型，但网络研讨会和直播活动为组织者提供了对于对话和参与者的其他控制。网络研讨会提供双向交互，而直播活动提供托管的问答体验。 

不同类型的会议还具有不同的参与者限制和参与者功能。 

下表简要总结了三种类型的会议、建议的参与者数量以及参与者在会议中的交互方式。 有关每种类型会议的详细信息，请参阅表格下面的部分。 本文还包括有关 [大型会议的最佳做法](#best-practices-for-large-meetings) 部分。
<br><br>

| 会议类型 | 参与者人数 | 交互 | 支持注册 |
|----------|--------|--------|-----|
| 会议  | 最多 20,000 人* <br> | - 最多 1,000 名参与者具有完全交互式平等会议功能。 <br> - 超过 1,000 名参与者（最多 20,000 人）具有“[仅供查看](view-only-meeting-experience.md)”功能。  | 弱 |
| 网络研讨会 | -最多 1,000 个<br>- 即将推出的“[仅供查看](view-only-meeting-experience.md)”功能增加了限制。 |- 最多 1,000 名参与者具有完全交互式功能。 <br> - 受众交互可配置。 <br> - 可以指定演示者。 | 是 |
| 直播活动 | 最多 20，000 人** |- 向大量受众广播。 <br>- 针对受众交互的审核问答。 <br> - 可以指定制作者和演示者，包括外部演示者。<br>- 支持更高级的生产功能。 | 弱 |
||||

*由通常的 10,000 人增加到 2022 年 6 月 30 日的 20,000 人。<br>

**由通常的 10,000 人增加到 2022 年 6 月 30 日的 20,000 人。 在 Yammer 和/或 Microsoft Stream 中，可以安排人数更为庞大的直播活动。 有关详细信息，请参阅 [跨 Microsoft 365 的直播活动](/stream/live-event-m365)。 请注意，如果与会者人数超过 20,000 人，则活动需要 [直播活动协助计划](/stream/live-events-assistance)。 

请注意，NDI 在会议、网络研讨会和直播活动中完全受支持，从而允许使用 OBS 和 Wirecast 等工具生成广播。有关详细信息，请参阅 [在 Microsoft Teams 中使用 NDI® 技术](use-ndi-in-meetings.md)。

## <a name="meetings"></a>会议

Teams 中的 **会议** 包括最多 1,000 人的音频、视频和屏幕共享，以及参与者人数超过 1,000 人时的 [仅供查看功能](view-only-meeting-experience.md)。 参与者无需是组织的成员（或拥有 Teams 帐户）即可加入 Teams 会议。 他们可以通过“加入会议”链接直接从日历邀请加入，也可以通过音频来电加入会议（如果适用）。  

作为管理员，你将通过指定会议策略来配置会议设置并控制为组织启用哪些会议功能。  

除了定期安排的会议外，用户还可以创建频道会议。 通过频道会议，团队中的每个人都可以看到会议、加入会议以及使用会议聊天。 频道会议是快速邀请团队中的每个人参加会议的一种方式。 有关最终用户如何安排会议的详细信息，请参阅 [安排会议](https://support.microsoft.com/office/schedule-a-meeting-in-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5)。

有关仅供查看会议体验的信息，请参阅 [Teams 仅供查看会议体验](view-only-meeting-experience.md)。

### <a name="articles-for-administrators"></a>面向管理员的文章

下表突出显示了你希望查看的关键文章：

| 文章 | 说明 | 
|----------|--------|
| [会议设置](meeting-settings-in-teams.md) |  介绍如何为匿名用户、会议邀请和媒体流量配置会议设置。  |
| [会议策略](meeting-policies-overview.md)  | 介绍如何创建和管理策略，以确定哪些功能可供会议参与者使用。 | 
| [管理 Teams 云会议录制](cloud-recording.md) | 介绍如何管理会议录制。 |
| [管理组织的设备](device-management.md)。| 介绍如何管理组织的设备，例如手机和 Teams 会议室。 |
| [使用实时遥测来解决会议质量不佳的问题](use-real-time-telemetry-to-troubleshoot-poor-meeting-quality.md) | 介绍如何使用实时分析 (RTA) 对个别用户的 Microsoft Teams 会议质量不佳进行故障排除。 
|||

### <a name="key-training-for-end-users"></a>面向最终用户的关键培训

下表列出了组织中最终用户可用的培训：

| 培训 | 说明 | 
|----------|--------|
| [管理会议](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) | 面向不熟悉 Teams 会议的用户的快速培训视频。 |
| [安排会议](https://support.microsoft.com/office/schedule-a-meeting-in-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5) | 介绍如何安排不同类型会议的文章。 |
| [使用 Teams 举行高效会议](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings) | 关于如何让会议更具吸引力、更有成效和更有意义的免费讲师指导课程。 |
| [更改 Teams 会议的参与者设置](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) | 有关管理会议选项的文章。
||


## <a name="webinars"></a>网络研讨会

**网络研讨会** 是结构化会议，演示者和参与者在其中具有明确的角色。 网络研讨会和 Teams 会议之间的一个关键区别是网络研讨会支持注册并提供与会者参与数据。 要在组织中启用网络研讨会，请参阅 [在 Teams 中设置网络研讨会](set-up-webinars.md)。 


### <a name="key-training-for-end-users"></a>面向最终用户的关键培训

下表列出了组织中最终用户可用的培训：

| 培训 | 说明 | 
|----------|--------|
| [Teams 网络研讨会入门](https://support.microsoft.com/office/get-started-with-teams-webinars-42f3f874-22dc-4289-b53f-bbc1a69013e3) | 面向不熟悉 Teams 网络研讨会的用户的快速培训视频。 |
| [视频快速入门指南](https://adoption.microsoft.com/files/assets/TeamsWebinarsGetStartedGuide.pdf) | 描述如何开始安排网络研讨会的可下载视频指南。  |
||


## <a name="live-events"></a>直播活动

**直播活动** 是结构化会议，组织能够安排和制作活动，将其流式传输给&mdash;多达 20,000 人的大规模在线受众。 在直播活动中，受众交互是一种托管的问答体验。

### <a name="articles-for-administrators"></a>面向管理员的文章

下表突出显示了你希望查看的关键文章：

| 文章 | 说明 | 
|----------|--------|
| [什么是 Teams 直播活动？](teams-live-events/what-are-teams-live-events.md)  | 直播活动的快速简介。 |
| [规划 Teams 直播活动](teams-live-events/plan-for-teams-live-events.md) | 配置直播活动之前需要了解的内容。 |
| [设置 Teams 直播活动](teams-live-events/set-up-for-teams-live-events.md) | 描述网络规划等先决条件。 |
| [配置直播活动](teams-live-events/configure-teams-live-events.md) | 配置直播活动的步骤。
||

### <a name="key-training-for-end-users"></a>面向最终用户的关键培训

下表列出了组织中最终用户可用的培训：

| 培训 | 说明 | 
|----------|--------|
| [直播活动入门](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a) | 直播活动简介以及如何开始使用。 |
| [Teams 直播活动视频培训](https://support.microsoft.com/en-us/office/plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502?ui=en-US&rs=en-US&ad=US) | 介绍如何计划和安排直播活动的视频。  |
||

要生成更大规模的虚拟活动，请查看 [虚拟活动指南](https://adoption.microsoft.com/virtual-event-guidance/)，该指南提供了面向活动组织者、技术制作者、IT 专业人员和内容创建者的指导。 

## <a name="apps-for-meetings"></a>会议应用

通过 Microsoft，可以通过集成和使用会议应用来增强会议体验。例如，Teams 会议中的 Whiteboard 集成由 Whiteboard Web 应用提供支持，允许 Teams 会议参与者在共享数字画布上一起绘制、速记和书写。

可以通过使用 Teams 提供的应用、使用经过认证的第三方应用和模板，以及创建自己的自定义应用将会议应用添加到 Teams 部署中。 

下表列出了有关详细信息的文章：

| 文章 | 说明 | 
|----------|--------|
| [应用、机器人和连接器](deploy-apps-microsoft-teams-landing-page.md) | 应用简介以及如何为组织部署应用。 |
| [Teams 会议应用](/microsoftteams/platform/apps-in-teams-meetings/teams-apps-in-meetings) | 会议应用扩展性、API 参考，以及如何为会议启用和配置应用的概述。 |
| [在 Teams 中管理 Whiteboard](manage-whiteboard.md) | 介绍 Whiteboard 功能以及如何为组织启用和禁用。 |
||

## <a name="license-requirements-for-meetings-webinars-and-live-events"></a>会议、网络研讨会和直播活动的许可证要求

任何人都可以免费参加 Teams 会议、网络研讨会或公共直播活动&mdash;无需任何许可证。 

对于组织、安排和主持会议、网络研讨会或直播活动的人员，他们需要具有 [Microsoft Teams 服务说明](/office365/servicedescriptions/teams-service-description) 中列出的 Microsoft 365 许可证之一。 如果你已在使用 Teams，则你可能拥有组织和主持会议和直播活动所需的许可证。

要允许用户通过电话拨入会议，你需要设置音频会议。 有关音频会议的详细信息，请参阅 [Teams 中的音频会议](deploy-audio-conferencing-teams-landing-page.md)。

## <a name="best-practices-for-large-meetings"></a>大型会议的最佳做法

本部分为管理员提供了指导，以及管理员可以与其演示者和组织者共享的提示。

如果要运行成功的活动，请遵循下面概述的做法：

- 为了在大型会议、网络研讨会和直播活动中获得最佳体验，Microsoft 建议使用最新版本的 Teams 桌面客户端或 Teams 移动客户端。 

- 确保本地和远程用户都遵循所有 Microsoft [网络连接原则](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)。
- 使用 [实时数据遥测](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-real-time-call-quality-analytics/ba-p/2912146) 监视活动并确定任何可能的问题及其来源。
  - 指定会议监视器来 [分析](use-real-time-telemetry-to-troubleshoot-poor-meeting-quality.md) 因指标超出阈值而体验不佳的用户的遥测。
  - 将会议监视器设置为演示者，以禁用恶意视频流、静音意外的实时麦克风，并根据需要删除与会者。

### <a name="guidelines-for-your-end-users"></a>最终用户指南

组织者和演示者应实施以下建议：

- 为了创建流畅的会议，活动组织者可以设置预定义的演示者。 会议开始后，演示者还可以将其他与会者提升为演示者角色。

- 通过会议选项定义共同组织者（公共预览版）

- 预配置视频和麦克风设置，以控制与会者经验。
  - 禁用与会者麦克风，以避免产生干扰。 如果有人需要在会议期间交互，请允许他们在举手时取消静音。
  - 禁用与会者视频，以避免视觉干扰。 在会议的适当时间内，可以允许所有与会者或特定个人使用视频。

- 在会议期间使用投票和问答。

- 使用大厅控件来控制会议进入或大厅暂留。

- 运行 [Microsoft 365网络连接测试](https://connectivity.office.com/) 以在活动举行前和当天验证网络适用性。

- 如果从家中进行演示，请验证其他设备未使用高带宽（流式处理服务、在线游戏、大型下载）。

- 从具有有线连接的终结点进行演示，以实现更可靠的音频、视频和屏幕共享。

- 确保用户在桌面或移动设备上使用最新的 Teams 应用。

- 使用笔记本电脑时，请检查网络连接性是否良好和电源是否足够。

- 在活动之前安排演练以识别设备、照明或网络问题。 这还将确保组织者/演示者熟悉他们将使用的功能。
  - 如果遇到问题，请安排额外的演练运行，以确保修正措施取得成功。
  
- 利用聚焦、PowerPoint Live、会议录制、字幕和听录等功能提升参与度和有效性。

- 演示者和参与者应使用 Teams 桌面应用来提供最佳体验。

- 参与者应在大型会议期间禁用聊天通知，以避免干扰。

- 有关托管大型会议的更多提示，请参阅 [大型 Teams 会议最佳做法](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16)。





## <a name="related-topics"></a>相关主题

[Teams 中的会议和电话会议](deploy-meetings-microsoft-teams-landing-page.md)

[在 Teams 中设置网络研讨会](set-up-webinars.md)

[Teams 中的直播活动](teams-live-events/what-are-teams-live-events.md)

[Teams 仅供查看会议体验](view-only-meeting-experience.md)

[Teams 限制和规范](limits-specifications-teams.md)

[Microsoft 技术社区： Microsoft 365 中的实时事件](https://resources.techcommunity.microsoft.com/live-events/)
