---
title: 准备部署云语音服务
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 使用载入清单为Microsoft 365或Office 365 Teams配置Teams核心功能、网络和云语音工作负荷。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a8aa2818cb2b4be85054f8804fa6a11112c4e8a68cc171e9b9f7191e3f3a5bfd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322914"
---
# <a name="prepare-my-service"></a>准备服务

本文概述了为组织准备云语音服务的要求。 通过正确准备，你可以确保已准备好向组织提供云语音功能。

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>载入语音工作负荷Microsoft Teams清单

以下清单将引导你完成在 Microsoft Teams 中实现音频会议、电话系统 呼叫计划 ("呼叫计划") 和 电话系统 直接路由 ("直接路由") 功能的步骤。

*  [为Microsoft 365准备Office 365或Teams](onboarding-checklist-enable-office-365.md)

*  [配置Teams核心功能](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [准备网络](prepare-network.md)

*  [在云中配置云语音Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [在 Teams 中配置直接路由](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

这些清单中的任务和活动是核心的"任务"项目，适用于使用云语音功能部署Teams。 可以自定义清单，以包含特定于自己的任务旅程的活动Teams任务。

>[!NOTE]
>本指南仅侧重于通话计划、音频会议和直接路由。 如果你还不[Teams，请查看](teams-overview.md)Microsoft Teams 概述。 有关规划用户部署Teams一般指南，请从在 Microsoft Teams 中部署聊天、团队、[频道Microsoft Teams。](deploy-chat-teams-channels-microsoft-teams-landing-page.md)

使用提供的清单跟踪每个单独活动和任务的状态，并确保未跳过任何关键步骤。 每个活动包含所需操作的详细说明，并引用可用于完成该活动的其他信息。

尽管我们建议按顺序遵循清单，但确切顺序取决于部署范围和环境的配置和复杂性。 组织它们以支持"绿地"部署Teams部署 (之前没有 Skype for Business Online 状态) 或者从 Skype for Business Online 迁移到 Teams。 如果要从 Skype for Business Online 迁移，则你可能已完成其中一些活动，现在可以忽略这些活动。

当您按网站载入用户时，强烈建议使用 [适用于 Voice (Playbook ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 的站点启用 Playbook) 作为这些清单的补充指南。

>[!NOTE]
>大多数配置设置在 Teams 和 Skype for Business Online 之间很常见。 使用 Microsoft 365 管理 中心Microsoft Teams管理中心配置这些设置。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>Who将负责监督登记清单的完成情况？</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>下一步</td><td><ul><li>下载载入清单。</li><li>根据组织的部署计划逐步完成登记清单项。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>继续载入

完成这些清单后，你已成功将语音功能添加到Teams部署。

下一步，使用 [Voice (Playbook) ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 网站启用 Playbook 来帮助你在每个网站上载入用户，并帮助确保你计划和执行重要的特定于网站的活动。

-   就绪的站点按站点推出计划

-   建立服务管理流程

-   执行测试和修正

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>在云中测试云语音Teams

在"构想"阶段定义并记录 Teams 云语音业务成功和技术实施计划并采用所需的配置后，下一步是验证通过功能、功能和可用性满足组织的期望和要求。 在生产环境中部署试点或最终部署之前，应执行此验证步骤。

可以利用在"构想"阶段定义的业务成功计划，作为确定在测试阶段要评估的活动、预期、功能/功能测试用例和总体范围的基础。

## <a name="define-your-testing-approach"></a>定义测试方法

最简单的测试方法基于你查看音频会议、呼叫计划或直接路由服务的功能，并开发一个测试计划来验证你的功能要求是否满足范围内用户的要求。 下面是音频会议实现载入阶段的示例测试计划。


| 要测试的音频会议功能 | 结果摘要 | 其他说明 |
|------------|-----------------|------------------|
| 安排包含音频Teams拨入信息的临时临时会议 | 通过/失败   | TBD |
| 使用电话从 PSTN 拨入会议，并使用提供的拨入信息拨入音频 | 通过/失败 | TBD |
| 通过 PSTN 拨出将其他人加入现有会议 | 通过/失败 | TBD |



| 要测试的调用计划或直接路由功能 | 结果摘要 | 其他说明 |
|----------------------------------------------------|-----------------|------------------|
| 通过拨打 PSTN 号码进行 PSTN 呼叫       | 通过/失败       | TBD |
| 通过从外部线路拨打 PSTN 号码以接收 PSTN 呼叫 (移动、座机)  | 通过/失败 | TBD|
| 将 PSTN 呼叫从一Teams转接到另一个用户 | 通过/失败 | TBD |


>[!TIP]
>若要从创建测试用例开始，请参阅"会议"和"呼叫"Teams[提供的用户指南列表](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)。

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>为应用程序设置云语音Teams

定义测试方法后，下一步是在云语音功能范围内配置服务Teams用户。

有关其他信息，请参阅：

- [音频会议的技术规划](./cloud-voice-landing-page.md)

- [设置 Microsoft Teams 的音频会议](set-up-audio-conferencing-in-teams.md)

- [使用通话套餐电话系统技术规划](calling-plan-landing-page.md)

- [为呼叫和通话设置Skype for Business Microsoft Teams](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [规划直接路由](./direct-routing-plan.md)

- [配置直接路由](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a>执行测试计划

[//]: # (编辑好吗？"用户"似乎有点不明确。)
配置用户环境和服务后，最后一个测试步骤包括测试计划执行，并侧重于特性和功能验证。 

**音频会议测试针对范围中的用户和网站的先决条件和假设：**

-   音频会议服务的业务用例定义已完成。

-   音频会议所需的许可可用且已分配。

-   已标识组织站点和用户组的列表。

-   已标识并配置具有语言首选项的专用和共享音频会议拨入号码列表。

-   [如果需要 (，) ](what-are-communications-credits.md) 为组织设置通信信用额度。

-   音频会议会议网桥设置已识别并 (PIN 长度、进入/退出通知、启用通知首选项) 。

-   已标识、配置和应用支持音频会议拨出方案的租户会议策略和拨号计划设置。

-   已标识并配置音频会议符合性要求。

**调用计划测试范围内用户和网站的先决条件和假设：**

-   呼叫计划服务的业务用例定义已完成。

-   呼叫计划所需的许可可用且已分配。

-   已标识组织站点和用户组的列表。

-   电话分配给用户的号码已获取或移植到 Microsoft，可在租户门户中获取。

-   [如果需要 (，) ](what-are-communications-credits.md) 为组织设置通信信用额度。

-   已标识、配置和应用支持呼叫计划的租户用户策略和拨号计划设置。

-   已标识并配置调用计划符合性要求。

**用户和站点在范围内直接路由测试先决条件和假设：**

-   已完成直接路由服务的业务用例定义。

-   直接路由所需的许可可用且已分配。

-   已标识组织站点和用户组的列表。

-   已[部署、配置 (SBC](./direct-routing-plan.md#supported-session-border-controllers-sbcs)) 的经认证的会话边界控制器电话系统。

-   Enterprise语音，并且已分配电话号码。

-   已标识、配置和分配语音路由策略。

-   Microsoft Teams已设置为范围内用户的首选调用客户端。
 
-   已标识并配置直接路由符合性要求。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>确定将部署哪些音频会议功能 (服务决策) 。</li><li>确定音频会议的用户功能要求。</li><li>确定音频会议的服务配置要求。</li><br><li>确定是否部署和配置直接路由或呼叫计划。<li>确定电话系统服务决策部署哪些 (功能) 。</li><li>确定调用计划或直接路由的用户功能要求。</li><li>确定调用计划或直接路由的服务配置要求。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>下一步</td><td><ul><li>开发和记录测试计划方法。</li><li>在音频会议功能的范围内准备服务环境和用户。</li><li>在调用计划或直接路由功能的范围内准备服务环境和用户。</li><li>对要启用的音频会议功能执行测试验证。</li><li>对要启用的呼叫计划或直接路由功能执行测试验证。</li><li>对于任何测试失败，请确认配置是否正确，查看社区文章，并（如果需要）提出支持案例。</li></ul></td></tr>
</table>


有关如何在音频会议中执行音频会议测试Teams，请参阅[音频会议的详细测试指南](./deploy-audio-conferencing-teams-landing-page.md)。

有关如何在 Teams 中为调用计划执行测试的其他详细指导，请参阅适用于 电话系统 的详细[测试指南](./cloud-voice-landing-page.md)。

<!--ENDOFSECTION-->