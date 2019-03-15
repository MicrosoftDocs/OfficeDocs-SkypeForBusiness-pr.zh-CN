---
title: 准备部署 Microsoft Teams 云语音服务
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 09/11/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 使用入职培训清单团队准备 Office 365 和配置团队的核心功能，网络，和云语音工作负荷。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8ede6bb8d63a53ccd636bb9881d60e521492afb8
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "30568453"
---
# <a name="prepare-my-service"></a>准备服务

本文概述了准备云的组织的语音服务的要求。 通过正确准备，您可以确保您已准备好提供语音功能延伸到您的组织的云。

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Microsoft 团队入职培训清单语音工作负荷

以下清单可指导您完成 Microsoft 团队中实现音频会议，调用计划 （"调用计划"），与电话系统直接路由 （"直接路由"） 的功能电话系统的步骤。

*  [Office 365 准备团队](onboarding-checklist-enable-office-365.md)

*  [配置团队的核心功能](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [配置网络](onboarding-checklist-configure-networking.md)

*  [在工作组中配置云语音工作负荷](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [配置直接路由团队](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

任务和这些清单中的活动是"核心待办事项"适用于云与团队的语音功能的每个部署。 您可以自定义要包含的活动和特定于您自己团队旅程的任务的清单。

>[!NOTE]
>本指南重点在于调用计划、 音频会议和直接路由。 如果您熟悉向工作组，请查看[Microsoft 团队概述](teams-overview.md)。 有关规划团队部署的一般指南，从开始[部署聊天、 团队、 通道和 Microsoft 团队中的应用程序](deploy-chat-teams-channels-microsoft-teams-landing-page.md)。

使用提供的清单来跟踪的每个单独的活动和任务，状态，以确保您没有跳过任何关键的步骤。 每个活动包括所需的操作和可用于完成了该活动的其他信息的引用的详细的说明。

虽然我们建议您按照顺序清单，准确的顺序将取决于您的部署和配置的范围和您的环境的复杂性。 它们组织以支持"全新"工作组 （一个业务联机状态的任何以前 Skype） 部署或从 Skype 业务 online 迁移到团队。 如果您正在从 Skype 业务 online 迁移内容，您可能已经完成一些这些活动，并可以忽略它们现在。

按每个站点的入职培训用户时，我们强烈建议[语音设置 （方案） 的网站启用设置方案](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)使用这些清单的补充指南作为。

>[!NOTE]
>常见团队和 Skype 业务 online 之间了大部分的配置设置。 您可以使用 Office 365 管理中心和 Microsoft 团队管理中心配置这些设置。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>决策点</td><td><ul><li>谁将负责监督入职培训清单完成？</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>后续步骤</td><td><ul><li>下载入职培训清单。</li><li>通过按照贵组织的部署计划分步入职培训清单项目工作。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>继续入职培训

完成这些清单后，将已成功添加语音功能延伸到您的团队部署。

在下一步，使用[语音设置 （方案） 的网站启用设置方案](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)可帮助您加载您的用户在每个站点，并帮助确保您规划和执行特定于网站的重要活动。

-   准备网站由网站推出计划

-   建立服务管理流程

-   执行测试和修正

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>团队中的测试云语音工作负荷

已定义和作为构想阶段的一部分中记录您的团队云语音业务成功和技术实现规划和执行所需在管理中心的配置后下, 一步是验证您的组织通过功能、 功能和可用性满足期望和要求。 在生产环境中部署的试验或最终部署之前，应执行以下验证步骤。

您可以利用您定义的阶段构想用作确定活动、 期望、 功能/功能测试用例和总体范围测试阶段进行求值的基础业务成功计划。

## <a name="define-your-testing-approach"></a>定义您的测试方法

简单的形式，测试方法根据您查看的音频会议，调用计划的功能或直接路由服务和开发测试计划验证功能要求满足范围中的用户。 下面是针对音频会议实现的板载阶段的示例测试计划。


| 要测试的音频会议功能 | 结果摘要 | 其他注释 |
|------------|-----------------|------------------|
| 包含信息电话拨入式音频会议的安排即席团队会议 | 通过/失败   | TBD |
| 用于电话拨入从 PSTN 会议音频会议提供的电话拨入式信息 | 通过/失败 | TBD |
| 通过 PSTN 拨出其他人加入现有会议 | 通过/失败 | TBD |



| 呼叫计划或直接路由功能测试 | 结果摘要 | 其他注释 |
|----------------------------------------------------|-----------------|------------------|
| 拨入 PSTN 号码发起 PSTN 呼叫       | 通过/失败       | TBD |
| 通过拨打您从外部行 （移动固定电话） 的 PSTN 号码收到 PSTN 呼叫 | 通过/失败 | TBD|
| 转接到另一个团队用户从 PSTN 呼叫 | 通过/失败 | TBD |


>[!TIP]
>为了帮助作为起点的测试用例创建，请参阅的用户指南 》[团队会议和呼叫](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)列表。

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>设置团队云语音工作负荷

既然已定义测试方法下, 一步配置您的服务环境和用户团队云语音功能的范围内。

有关其他信息，请参阅：

- [技术规划音频会议](audio-conferencing.md#technical-planning-for-audio-conferencing)

- [设置 Microsoft 团队的音频会议](set-up-audio-conferencing-in-teams.md)

- [技术规划调用计划的电话系统](calling-plan-landing-page.md)

- [调用计划为设置 Skype 业务和 Microsoft 团队](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [规划直接路由](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [配置直接路由](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a>执行测试计划

[//]: # (好了编辑？"User"看起来有点不明确给我。)
已配置的用户环境和服务后，测试的最后一步将包括具有焦点的功能及功能验证测试计划执行。 

**测试先决条件和假设条件的用户和网站范围内的音频会议：**

-   业务案例定义用于音频会议服务已完成。

-   许可音频会议所需的可用且已分配。

-   已发现的组织的站点和用户组列表。

-   已标识并配置专用和共享的音频会议电话拨入式号码语言首选项的列表。

-   [Communications 字幕式](what-are-communications-credits.md)（如果需要） 已为组织设置。

-   音频会议的会议桥设置已标识和配置 （PIN 长度、 条目/退出通知启用通知首选项）。

-   租户会议策略和拨号计划支持音频会议拨出方案具有标识、 配置和应用的设置。

-   已标识和配置音频会议合规性要求。

**调用测试先决条件和假设条件的用户和网站范围内的计划：**

-   商业调用计划已完成服务的使用案例定义。

-   许可所需的调用计划可用且已分配。

-   已发现的组织的站点和用户组列表。

-   已获得或移植到 Microsoft 和租户门户中提供有要分配给用户的电话号码。

-   [Communications 字幕式](what-are-communications-credits.md)（如果需要） 已为组织设置。

-   租户用户策略和拨号计划设置支持调用计划方案具有已标识、 配置，并应用。

-   调用计划已标识和配置合规性要求。

**测试先决条件和假设条件的用户和网站范围内的直接路由：**

-   业务直接路由服务已完成的使用案例定义。

-   许可所需的直接路由中可用，并已分配。

-   已发现的组织的站点和用户组列表。

-   [认证的会话边界控制器 (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)已部署、 配置并与电话系统配对。

-   已启用企业语音，且已分配的电话号码。

-   语音路由策略已标识、 配置和分配。

-   在范围内，Microsoft 团队已被设为首选调用客户端的用户。
 
-   已标识和配置直接路由合规性要求。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>决策点</td><td><ul><li>决定将部署的音频会议功能 （服务决策）。</li><li>确定用户音频会议功能要求。</li><li>确定要进行音频会议服务配置要求。</li><br><li>决定是否将部署并配置了直接路由或调用计划。<li>决定将部署哪些电话系统的功能 （服务决策）。</li><li>确定用户调用计划或直接路由的功能要求。</li><li>标识调用计划或直接路由服务配置要求。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>后续步骤</td><td><ul><li>开发和测试计划方法的文档。</li><li>准备您的服务环境和音频会议功能的范围内的用户。</li><li>准备您的服务环境和调用计划或直接路由功能范围中的用户。</li><li>执行测试验证您想要启用的音频会议功能。</li><li>执行测试验证您想要启用的调用计划或直接路由功能。</li><li>出于测试故障，确认您的配置是否正确，请查看社区文章和 — 如果需要 — 引发支持案例。</li></ul></td></tr>
</table>


有关如何执行测试团队中的音频会议的其他详细指导信息，请参阅[详细测试音频会议的指南](onboarding-test-plan-for-enterprises-Audio-Conferencing.md)。

有关如何执行测试呼叫的团队中计划的其他详细指导信息，请参阅[详细测试的电话系统的指南](onboarding-test-plan-for-enterprises-Phone-System.md)。

<!--ENDOFSECTION-->
