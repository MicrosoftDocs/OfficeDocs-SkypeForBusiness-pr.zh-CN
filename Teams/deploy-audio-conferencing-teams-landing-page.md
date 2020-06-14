---
title: 配置音频会议设置 - Microsoft Teams
ms.reviewer: ''
description: 使用这些部署资源来帮助你部署作为 Microsoft Teams 中的会议工作负载一部分的音频会议。
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
ms.custom: seo-marvel-mar2020
f1.keywords:
- NOCSH
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: f01c95ac248d470cc0384e42b6948c45bb99c8bf
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691318"
---
# <a name="learn-how-to-deploy-audio-conferencing-in-microsoft-teams"></a>了解如何在 Microsoft Teams 中部署音频会议

音频会议是指通过普通电话加入 Teams 会议或从会议中拨出到某个电话号码的功能。 确保在组织中部署音频会议的过程中已经查看了[会议部署](deploy-meetings-microsoft-teams-landing-page.md)。

## <a name="audio-conferencing-deployment-decisions"></a>音频会议部署决策

本文根据组织的情况和业务需求来帮助你决定是否更改任何默认音频会议设置，然后引导你完成每项更改。 我们将这些设置分为两组：首先是[你更有可能更改的一组核心设置](#core-deployment-decisions)。 第二组包括你可能希望根据组织的需求配置的[其他设置](#additional-deployment-decisions)。

你只需为打算安排或主持会议的人设置音频会议。 通过拨入方式参与的与会者无需任何分配的许可证或进行任何其他设置。 对于在旅途中并且无法使用其笔记本电脑或移动设备上的 Skype for Business 或 Teams 应用参与会议的用户来说，拨入（或呼入）会议非常有用。 


## <a name="audio-conferencing-prerequisites"></a>音频会议先决条件 

在部署 Teams 的音频会议功能之前，请考虑以下各项：

|询问你自己|操作 |
|------------|-------|
|我所在的国家/地区是否可以使用音频会议功能？|若要了解你所在的国家/地区是否可使用音频会议功能，请参阅[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。|
|我的用户是否有适当的 Teams 音频会议许可？|音频会议许可证作为 Microsoft 365 或 Office 365 E5 订阅的一部分提供，或作为 Microsoft 365 商业标准版 E1 或 E3 订阅的一项附加服务提供。 <ul><li>若要获取和分配许可证，请参阅[在 Microsoft 365 或 Office 365 中试用或购买音频会议功能](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)以及[分配或移除 Microsoft 365 商业应用版许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</li><li> 若要了解详细信息，请阅读 [Microsoft Teams 附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。 </li><li>若要了解每种计划中包括哪些云功能，请参阅[基于计划的许可证选项](teams-add-on-licensing/office-365-business-premium.md)文章。</li></ul>|
|是否需要为分配有音频会议许可证的用户购买通信点数？|若要了解详情，请阅读[什么是通信点数](what-are-communications-credits.md)，然后查看下面的[通信点数](#communications-credits)部分。|
|||


## <a name="core-deployment-decisions"></a>核心部署决策

满足了音频会议先决条件后，请完成以下任务来为用户配置音频会议。


### <a name="teams-administrators"></a>Teams 管理员

Teams 提供了一组可用于为组织管理 Teams 的自定义管理员角色。 这些角色为管理员提供各种能力。 

| 询问你自己 | 操作 |
|--------------|--------|
|将为谁分配 Teams 通信管理员角色？|若要详细了解 Teams 管理员角色，请参阅[使用 Microsoft Teams 管理员角色来管理 Teams](using-admin-roles.md)。|
|将为谁分配 Teams 通信支持工程师角色？|若要分配管理员角色，请参阅[使用 Active Directory 为用户分配管理员和非管理员角色](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。|
|将为谁分配 Teams 通信支持专家角色？||
|||

### <a name="conferencing-bridges-and-phone-numbers"></a>会议网桥和电话号码

会议网桥使用户能够使用电话拨入会议。 可以使用会议网桥的默认设置，也可以更改电话号码（收费和免费）和其他设置（如 PIN 或使用的语言）。

请参阅[音频会议](audio-conferencing-in-office-365.md)了解详情。

|询问你自己|操作 |
|------------|-------|
|是否需要添加新的会议网桥号码？| 若要添加新号码，请参阅[获取服务电话号码](/microsoftteams/getting-service-phone-numbers)。|
|是否需要修改网桥设置？|若要修改网桥设置，请参阅[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。|
|是否需要移植号码以用于音频会议？|若要了解移植电话号码，请阅读[将电话号码转移到 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。|
|||


### <a name="default-and-alternate-languages"></a>默认语言和备用语言

Teams 音频会议允许你为会议网桥设置默认语言和备用语言。

|询问你自己|操作 |
|------------|-------|
| 我应为自动助理问候选择哪些语言？ | 若要选择语言，请参阅[为音频会议设置自动助理语言](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)。|
|||

### <a name="conferencing-bridge-settings"></a>会议网桥设置 

设置了会议网桥（包括默认语言和备用语言）之后，你应验证诸如进入/退出通知和 PIN 长度等默认设置是否符合你的要求。 如果不符合，你可以更改这些设置。 

|询问你自己|操作 |
|------------|-------|
| 当用户加入或退出会议时，与会者是否将听到一条通知？ | 若要更改这些设置，请参阅[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。|
|会议组织者用于开始会议的 PIN 必须设置为什么长度？||
|||

### <a name="dial-in-phone-number-settings-for-users-who-lead-meetings"></a>主持会议的用户的拨入电话号码设置

创建音频会议网桥后，需要设置主持会议的用户将使用的收费和/或免费号码。

|询问你自己|操作 |
|------------|-------|
| 为将主持会议的每名用户分配哪些会议网桥号码？ | 若要为用户分配拨入电话号码，请参阅[步骤 7：为主持会议的用户分配拨入电话号码](set-up-audio-conferencing-in-teams.md#step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings)。 |
|||

### <a name="communications-credits"></a>通信点数

为了提供免费会议网桥电话号码以及支持会议向国际电话号码拨出，你需要贵组织设置通信点数。 若要详细了解通信点数，请参阅[什么是通信点数？](what-are-communications-credits.md)。

|询问你自己|操作 |
|------------|-------|
|我的音频会议实现是否需要通信点数？ |若要了解你是否需要设置通信点数，请参阅[为你的组织设置通信点数](set-up-communications-credits-for-your-organization.md)。|
|如果需要通信点数，我应该购买多少？|若要确定通信点数数额，请参阅[推荐的资金金额](what-are-communications-credits.md#recommended-funding-amounts)。|
|是否要配置自动充值金额？|若要配置自动充值金额，请参阅[为你的组织设置通信点数](set-up-communications-credits-for-your-organization.md)。|
|||



## <a name="additional-deployment-decisions"></a>其他部署决策

你可能需要根据组织的需求和配置更改这些设置。

### <a name="outbound-calling-restriction-policies"></a>出站呼叫限制策略 

作为管理员，您可以使用出站呼叫控件来限制组织用户可以进行的音频会议和最终用户 PSTN 呼叫类型。

|询问你自己|操作 |
|------------|-------|
| 是否将限制允许的出站通话类型？ | 若要限制出站通话，请参阅[音频会议和用户 PSTN 通话的出站通话限制策略](outbound-calling-restriction-policies.md)。|
|||


### <a name="dial-plans"></a>拨号计划

作为 Microsoft 365 或 Office 365 电话系统一部分的拨号计划是一组规范化规则，用于将拨打的电话号码转换为替代格式（通常为 E.164 格式）以便进行通话授权和通话路由。

有关拨号计划的详细信息，请参阅[什么是拨号计划？](what-are-dial-plans.md)

|询问你自己|操作 |
|------------|-------|
|我的组织是否需要自定义拨号计划？|为了帮助确定你是否需要自定义拨号计划，请参阅[规划租户拨号计划](what-are-dial-plans.md#planning-for-tenant-dial-plans)。 |
|哪些用户需要自定义拨号计划，应为每个用户分配哪种租户拨号计划？|若要使用 PowerShell 将用户添加到自定义拨号计划，请参阅[创建和管理拨号计划](create-and-manage-dial-plans.md)。|
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>会议和通话质量疑难解答 

Teams 提供两种用于监视和排除通话质量问题的方法：[通话分析和通话质量仪表板](difference-between-call-analytics-and-call-quality-dashboard.md)。 通话分析显示有关与每个用户的特定通话和会议相关的设备、网络和连接的详细信息。 通话分析旨在帮助管理员和技术支持人员解决特定通话的通话质量问题，而通话质量仪表板旨在帮助管理员和网络工程师优化网络。 通话质量仪表板关注的不是特定用户，而是整个 Teams 组织的聚合信息。 

|询问你自己|操作 |
|------------|-------|
| 谁将负责监视和排查通话质量问题？ | 请参阅[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)，了解排查通话质量问题所需的权限级别。|
|||


## <a name="next-steps"></a>后续步骤
- 在组织内[推动采用](adopt-microsoft-teams-landing-page.md)音频会议。
- [部署云语音](cloud-voice-landing-page.md)
- 在 Teams 的初步部署中加入特别推荐的应用 - 例如 Planner。 在推动 Teams 采用的过程中添加其他[应用、聊天机器人和连接器](deploy-apps-microsoft-teams-landing-page.md)。
