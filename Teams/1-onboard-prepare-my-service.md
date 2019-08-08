---
title: 准备部署 Microsoft Teams 云语音服务
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 使用 "加入清单" 为团队准备 Office 365 并配置团队核心功能、网络和云语音工作负荷。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63b507237cbc9a1d32dc891b99eaf6425528b559
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236195"
---
# <a name="prepare-my-service"></a>准备服务

本文概述了为组织准备云语音服务的要求。 通过正确准备, 你可以确保你已准备好向你的组织提供云语音功能。

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Microsoft 团队语音工作负荷的加入清单

以下清单将指导你完成以下步骤: 使用呼叫计划 ("呼叫计划") 实现音频会议、电话系统和 Microsoft 团队中的电话系统直接路由 ("直接路由") 功能。

*  [为团队准备 Office 365](onboarding-checklist-enable-office-365.md)

*  [配置团队核心功能](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [配置网络](onboarding-checklist-configure-networking.md)

*  [在团队中配置云语音工作负荷](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [配置团队中的直接路由](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

这些清单中的任务和活动是应用于团队的每个云语音功能部署的核心 "待办事项" 项目。 你可以自定义清单, 以包括特定于你自己的团队旅行的活动和任务。

>[!NOTE]
>本指南仅重点介绍通话计划、音频会议和直接路由。 如果您不熟悉团队, 请查看[Microsoft 团队的概述](teams-overview.md)。 有关规划团队部署的一般指南, 请从[Microsoft 团队中的 "部署聊天"、"团队"、"频道" 和 "应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)" 开始。

使用提供的清单跟踪每个单独的活动和任务的状态, 并确保未跳过任何关键步骤。 每个活动都包括所需操作的详细说明和可用于完成该活动的其他信息的参考。

尽管我们建议按顺序跟踪检查表, 但具体顺序将取决于你的部署的范围以及你的环境的配置和复杂程度。 它们被组织为支持 "全新" 团队部署 (没有以前的 Skype for Business Online 状态) 或从 Skype for business Online 迁移到团队。 如果您是从 Skype for Business Online 迁移, 您可能已经完成了这些活动中的一部分, 并且现在可以忽略它们。

如果您是在每个网站的基础上加入用户, 我们强烈建议您使用[网站支持行动手册 (如 "行动手册")](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)作为这些清单的辅助指南。

>[!NOTE]
>大多数配置设置在团队和 Skype for business Online 之间通用。 使用 Microsoft 365 管理中心和 Microsoft 团队管理中心配置这些设置。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>谁将负责监督加入核对清单的完成？</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>下载加入核对清单。</li><li>按照组织的部署计划逐步执行 "加入清单" 项目。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>继续加入

完成这些清单后, 您将向团队部署成功添加了语音功能。

下一步, 使用[网站支持行动手册 For 语音 (行动手册)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)帮助你在每个网站上为你的用户板载, 并帮助确保你规划和执行重要的特定于网站的活动。

-   按网站推出计划准备的网站

-   建立服务管理过程

-   执行测试和修正

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>在团队中测试云语音工作负载

在构思阶段中定义并记录团队云语音业务成功和技术实现计划后, 在管理中心执行所需的配置后, 下一步是验证你的组织的通过功能、功能和可用性来满足预期和要求。 在生产环境中部署试验或最终部署之前, 应执行此验证步骤。

你可以利用在 Envision 阶段中定义的业务成功计划来充当确定活动、预期、功能/功能测试用例以及测试阶段中要评估的整体范围的基础。

## <a name="define-your-testing-approach"></a>定义测试方法

在最简单的形式中, 你的测试方法基于你查看音频会议、呼叫计划或直接路由服务的功能功能, 并开发测试计划以验证你的功能要求是否满足范围内的用户。 下面是音频会议实现的板载阶段的示例测试计划。


| 要测试的音频会议功能 | 结果摘要 | 其他笔记 |
|------------|-----------------|------------------|
| 安排包含音频会议拨入信息的临时团队会议 | 通过/失败   | TBD |
| 通过使用提供的拨入信息从 PSTN 拨入会议, 使用手机进行会议音频 | 通过/失败 | TBD |
| 通过 PSTN 拨出, 将其他人加入现有会议 | 通过/失败 | TBD |



| 通话计划或直接路由功能进行测试 | 结果摘要 | 其他笔记 |
|----------------------------------------------------|-----------------|------------------|
| 通过拨打 PSTN 号码进行 PSTN 呼叫       | 通过/失败       | TBD |
| 通过从外部线路 (手机、座机) 拨您的 PSTN 号码来接收 PSTN 呼叫 | 通过/失败 | TBD|
| 将 PSTN 呼叫从一个团队用户转移到另一个团队用户 | 通过/失败 | TBD |


>[!TIP]
>若要帮助测试案例创建作为起点, 请参阅[团队会议和通话](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)中可用的用户指南列表。

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>为团队设置云语音工作负荷

现在, 你已定义测试方法, 下一步是在团队云语音功能的范围内配置你的服务环境和用户。

有关其他信息, 请参阅:

- [音频会议的技术规划](cloud-voice-deployment.md)

- [设置 Microsoft Teams 的音频会议](set-up-audio-conferencing-in-teams.md)

- [带有呼叫计划的电话系统技术规划](calling-plan-landing-page.md)

- [为 Skype for business 和 Microsoft 团队设置呼叫计划](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [规划直接路由](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [配置直接路由](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a>执行测试计划

[//]: # (编辑？"用户" 似乎对我有点不明确。)
在用户环境和服务配置完成后, 测试的最后一步包括测试计划执行, 重点在于功能和功能验证。 

**针对范围内的用户和网站的音频会议测试先决条件和假设:**

-   音频会议服务的业务使用案例定义已完成。

-   音频会议所需的许可可用且已分配。

-   已标识组织网站和用户组的列表。

-   已确定并配置了具有语言首选项的专用和共享音频会议拨入号码的列表。

-   [通讯信用点数](what-are-communications-credits.md)(如果需要) 已为你的组织设置。

-   已识别和配置音频会议网桥设置 (PIN 长度、进入/退出通知、启用通知首选项)。

-   已识别、配置和应用支持音频会议拨出方案的租户会议策略和拨号计划设置。

-   已确定和配置音频会议合规性要求。

**针对范围内的用户和网站的通话计划测试先决条件和假设:**

-   已完成通话计划服务的业务使用案例定义。

-   通话计划所需的许可可用且已分配。

-   已标识组织网站和用户组的列表。

-   要分配给用户的电话号码已获取或移植到 Microsoft, 并且在租户门户中可用。

-   [通讯信用点数](what-are-communications-credits.md)(如果需要) 已为你的组织设置。

-   已识别、配置和应用支持呼叫计划方案的租户用户策略和拨号计划设置。

-   已确定并配置了通话计划合规性要求。

**作用域中的用户和网站的直接路由测试先决条件和假设:**

-   直接路由服务的企业使用案例定义已完成。

-   直接路由所需的许可可用且已分配。

-   已标识组织网站和用户组的列表。

-   已[验证的会话边界控制器 (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)已部署、配置并与电话系统配对。

-   已启用企业语音, 并且已分配电话号码。

-   已确定、配置和分配语音路由策略。

-   Microsoft 团队已被设置为范围内用户的首选呼叫客户端。
 
-   已确定并配置直接路由合规性要求。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>确定将部署哪些音频会议功能 (服务决策)。</li><li>确定音频会议的用户功能要求。</li><li>确定音频会议的服务配置要求。</li><br><li>确定是否将部署和配置直接路由或呼叫计划。<li>确定将部署哪些电话系统功能功能 (服务决策)。</li><li>确定呼叫计划或直接路由的用户功能要求。</li><li>确定呼叫计划或直接路由的服务配置要求。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>开发并记录你的测试计划方法。</li><li>准备您的服务环境和音频会议功能范围内的用户。</li><li>在 "呼叫计划" 或 "直接路由" 功能的范围内准备服务环境和用户。</li><li>对要启用的音频会议功能执行测试验证。</li><li>为要启用的呼叫计划或直接路由功能执行测试验证。</li><li>对于任何测试失败, 请确认您的配置正确, 查看社区文章, 如果需要, 还可以提出支持案例。</li></ul></td></tr>
</table>


有关如何在团队中执行音频会议测试的更多详细指导, 请参阅[音频会议的详细测试指南](onboarding-test-plan-for-enterprises-Audio-Conferencing.md)。

有关如何针对团队中的通话计划执行测试的更多详细指导, 请参阅[电话系统的详细测试指南](onboarding-test-plan-for-enterprises-Phone-System.md)。

<!--ENDOFSECTION-->
