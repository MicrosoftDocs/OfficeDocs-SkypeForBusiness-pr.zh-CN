---
title: Microsoft Teams 中的会议
ms.reviewer: ''
description: 使用这些部署资源帮助你在 Microsoft Teams 中部署会议。
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/28/2019
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a0f712b2eb753f3444b43a714d5f77fbd8b3f1a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240831"
---
# <a name="meetings--conferencing-in-microsoft-teams"></a>Microsoft Teams 中的会议

你已完成了[入门](get-started-with-teams-quick-start.md)。 你已在整个组织中部署了具有[聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)的 Teams。 现在你准备添加会议工作负载，其中包括[音频会议](deploy-audio-conferencing-teams-landing-page.md)、视频和分享。 方法如下。 


## <a name="meetings--conferencing-deployment-decisions"></a>会议部署决策

Teams 为组织提供了现成的出色体验，并且大多数组织发现默认设置即适合它们。 本文可帮助你决定是否要根据组织的情况和业务需求更改任何默认设置，然后引导你完成每项更改。 我们将这些设置分为两组：首先是[你更有可能更改的一组核心设置](#core-deployment-decisions)。 第二组包括你可能希望根据组织的需求配置的[其他设置](#additional-deployment-decisions)。

> [!Tip]
> 观看下面的课程来详细了解会议：[Microsoft Teams 中的会议：面向 IT 专业人员的简介](https://aka.ms/teams-meetings-intro)


## <a name="meetings--conferencing-prerequisites"></a>会议先决条件 

在整个组织中大规模部署会议之前，请花时间检查并确认你的环境已准备好为用户提供最佳体验。 查看以下信息，并根据需要对你的环境进行任何必需的更改。

若要获得最佳 Teams 体验，你的组织必须部署了 Exchange Online 和 SharePoint Online，并且你必须有适用于 O365 的已验证域（例如，*contoso.com*）。

为了在整个组织中大规模部署会议，你应确保所有用户地点都有权访问 Internet，以便连接到 Office 365 服务。 你至少应确保以下常用端口在用户地点已向 Internet 开放：

- 将使用 Teams 的客户端上用于传出连接的 TCP 端口 80 和 443。
- 将使用 Teams 的客户端上用于传出连接的 UDP 端口 3478 到 3481。

可以使用[网络测试配套工具](https://www.powershellgallery.com/packages/NetworkTestingCompanion/1.5.2)，确认网络位置已做好准备应对支持你的会议体验的语音和视频流量。

| 询问你自己 | 操作 |
|--------------|--------|
|我的网络是否已准备好进行 Teams 会议部署？ | 若要验证网络是否准备就绪，请参阅：<ul><li>
  [为 Microsoft Teams 准备组织的网络](https://docs.microsoft.com/zh-CN/MicrosoftTeams/prepare-network)</li><li>
  [Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/zh-CN/MicrosoftTeams/office-365-urls-ip-address-ranges)</li></ul> |
|||

## <a name="core-deployment-decisions"></a>核心部署决策

以下是大多数组织在默认设置不适合的情况下想要更改的设置。

### <a name="teams-administrators"></a>Teams 管理员

Teams 提供了一组可用于为组织管理 Teams 的自定义管理员角色。 这些角色为管理员提供各种能力。 

| 询问你自己 | 操作 |
|--------------|--------|
|将为谁分配 Teams 通信管理员角色？|若要详细了解 Teams 管理员角色，请参阅[使用 Microsoft Teams 管理员角色来管理 Teams](using-admin-roles.md)。|
|将为谁分配 Teams 通信支持工程师角色？|若要分配管理员角色，请参阅[使用 Active Directory 为用户分配管理员和非管理员角色](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。|
|将为谁分配 Teams 通信支持专家角色？||
|||

### <a name="meetings-settings"></a>会议设置 

会议设置用于控制匿名用户是否可加入 Teams 会议、设置会议邀请，并在想要启用服务质量 (QoS) 的情况下设置实时流量端口。 这些设置将用于用户在组织中安排的所有 Teams 会议。 

| 询问你自己 | 操作 |
|--------------|--------|
|是否要自定义初始会议设置？ |请参阅 [Teams 中的会议教程](tutorial-meetings-in-teams.yml)，详细了解会议设置。|
|是否要实施 QoS？|有关 QoS 概念的详细信息，请参阅 [Microsoft Teams 中的服务质量](qos-in-teams.md)。 方案和实施。|
|||

### <a name="meeting-policies"></a>会议策略

会议策略用于控制在用户加入 Teams 会议时可以使用哪些功能。 你可以使用默认策略，或者为组织中主持会议的人员创建一个或多个自定义会议策略。 若要了解详细信息，请参阅 [Microsoft Team 中的会议教程](tutorial-meetings-in-teams.yml)。

| 询问你自己 | 操作 |
|--------------|--------|
|<ul><li>是否要自定义初始会议策略？</li><li>是否需要多个会议策略？</li><li>如何确定向哪些用户组应用哪些会议策略？</li></ul>|<br>请阅读 [Teams 中的会议策略](meeting-policies-in-teams.md)。|
|||

### <a name="audio-conferencing"></a>音频会议

音频会议允许会议参与者使用传统陆上线路、专用分组交换机 (PBX) 或移动电话通过公共交换电话网 (PSTN) 拨入来加入会议，从而为组织提供了另一个进入任何会议的入口点。 

准备好部署音频会议时，请参阅深入的[音频会议部署](deploy-audio-conferencing-teams-landing-page.md)指引。

### <a name="meeting-room-and-personal-devices"></a>会议室和个人设备

为了在 Teams 实现最佳会议体验，请考虑使用 Teams 设备，例如会议室系统、手机、耳机和相机。 若要了解详细信息，请参阅[用于智能通信的 Teams 设备](https://products.office.com/microsoft-teams/across-devices)。

| 询问你自己 | 操作 |
|--------------|--------|
|是否要为我的用户购买个人设备？ |请阅读[在 Microsoft Teams 中管理设备](device-management.md)。 |
|是否要为我的会议室购买和部署会议室系统设备？|请阅读[会议室设备和解决方案](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)。|
|||

### <a name="reporting"></a>报告

使用活动报告来查看组织中的用户使用 Teams 的情况。 例如，如果某些用户尚未使用 Teams，他们可能不知道如何开始使用或了解如何使用 Teams 提高效率和改善协作。 组织可以使用活动报告来决定在何处优先安排培训和沟通工作。 


| 询问你自己 | 操作 |
|--------------|--------|
|谁将负责报告？|请阅读[使用 Teams 活动报告](teams-activity-reports.md)。  |
|谁将负责监视使用情况？|请阅读[在 Teams 中监视使用情况和反馈](get-started-with-teams-monitor-usage-and-feedback.md)。|
|||

## <a name="additional-deployment-decisions"></a>其他部署决策

你可能需要根据组织的需求和配置更改这些设置。

### <a name="bandwidth-planning"></a>带宽规划 

带宽规划允许组织对跨广域网和 Internet 链路举行会议所需的带宽进行预估，这样他们就可以确认网络得到正确配置，可以支持横向扩展的会议服务。 

| 询问你自己 | 操作 |
|--------------|--------|
| 是否需要在会议部署之前和部署期间进行带宽规划？ |请参阅[网络准备情况](3-envision-evaluate-my-environment.md#network-readiness)了解详细信息，并获取用于简化规划过程的工具链接。|
|||

### <a name="meeting-recording-and-archiving"></a>会议录制和存档

用户可以录制其会议和组内呼叫，以便捕获音频、视频和屏幕共享活动。 还有一个用于为录像添加自动转录功能的选项，这样用户就能够回放包含隐藏式字幕的会议录像，并在转录文本中搜索重要的讨论事项。 录制在云中进行，并保存在 Microsoft Stream 中，因此用户可以安全地在组织中共享录像。 若要查找会议录像，请转到会议对话。

若要了解详细信息，请参阅 [Teams 云会议录制](cloud-recording.md)。

| 询问你自己 | 操作 |
|--------------|--------|
| 是否要开启会议转录服务？|请参阅[开启或关闭录制转录](cloud-recording.md#turn-on-or-turn-off-recording-transcription)|
|||


### <a name="live-events-policies"></a>实时事件策略

Teams 实时事件策略用于管理用户组的事件设置。 可以使用默认策略，或创建可分配给在组织内主持实时事件的用户的其他策略。 

| 询问你自己 | 操作 |
|--------------|--------|
| 我的组织是否将使用 Teams 实时事件？| 有关规划、设置和配置 Teams 实时事件的详细信息，请参阅[实时事件文章](teams-live-events/what-are-teams-live-events.md)。|
|||

### <a name="conference-room-systems-rollout"></a>会议室系统部署

拥有许多会议室的组织可能需要考虑采用一种结构化方法来清点其会议室、识别相应的设备，然后进行部署。 



| 询问你自己 | 操作 |
|--------------|--------|
| 我需要进行操作什么来部署会议室系统？|请参阅[规划 Microsoft Teams 会议室](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)的相关文章。|
|||

### <a name="cloud-video-interop"></a>云视频互操作性

云视频互操作性使第三方会议室设备能够加入 Teams 会议。 

包含内容协作的视频电话会议可让你发挥会议的最大作用。 但是，会议室系统和设备的升级费用非常昂贵。 Teams 的云视频互操作性可与第三方系统配合工作，并能为所有参与者提供本机会议体验 - 无论是在会议室中还是在 Teams 客户端内。 

| 询问你自己 | 操作 |
|--------------|--------|
| 是否要在我的会议室系统部署过程中使用云视频互操作性解决方案？ | 请阅读 [Teams 的云视频互操作性](cloud-video-interop.md)。|
|||


### <a name="personal-device-rollout"></a>个人设备部署

在为支持会议和语音部署规划更大规模的个人设备部署时，请考虑使用可重复的逐站点部署流程，这种流程可提供稳定可靠的质量。

| 询问你自己 | 操作 |
|--------------|--------|
|是否要使用逐站点方法来部署会议？ |  [Teams 站点实现设置方案](3-onboard-deploy-my-service.md#site-enablement-playbook-for-microsoft-teams-voice-workloads)提供了良好的基础，你可将其用于自己的部署。 该指南侧重于语音，但有关设备交付、帐户准备、采用和培训的一般原则适用于大型会议部署。 |
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>会议和通话质量疑难解答 

Teams 提供两种用于监视和排除通话质量问题的方法：[通话分析和通话质量仪表板](difference-between-call-analytics-and-call-quality-dashboard.md)。 通话分析显示有关与每个用户的特定通话和会议相关的设备、网络和连接的详细信息。 通话分析旨在帮助管理员和技术支持人员解决特定通话的通话质量问题，而通话质量仪表板旨在帮助管理员和网络工程师优化网络。 通话质量仪表板关注的不是特定用户，而是整个 Teams 组织的聚合信息。 

|询问你自己|操作 |
|------------|-------|
| 谁将负责监视和排查通话质量问题？ | 请阅读[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)，了解排查通话质量问题所需的权限级别。|
|||

### <a name="operate-your-meetings-service"></a>操作会议服务

请务必了解 Teams 服务的整体运行状况，以便能够在发生影响服务的任何事件时主动提醒组织中的其他人。 [操作我的服务](1-drive-value-operate-my-service.md)文章提供了有关服务操作的深入指引。

|询问你自己|操作 |
|------------|-------|
|谁将在我的组织中负责管理会议服务？ | 请确保此人员具有管理会议服务所需的 Teams 管理员权限。 若要详细了解 Teams 管理员角色，请参阅[使用 Microsoft Teams 管理员角色来管理 Teams](using-admin-roles.md)。|
|||


## <a name="next-steps"></a>后续步骤
- 在整个组织中[推动采用](adopt-microsoft-teams-landing-page.md)会议。
- [添加音频会议](deploy-audio-conferencing-teams-landing-page.md)
- [部署云语音](cloud-voice-landing-page.md)
- 在 Teams 的初步部署中加入特别推荐的应用 - 例如 Planner。 在推动 Teams 采用的过程中添加其他[应用、聊天机器人和连接器](deploy-apps-microsoft-teams-landing-page.md)。
