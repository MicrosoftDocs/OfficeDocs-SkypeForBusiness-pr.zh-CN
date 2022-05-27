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
description: 使用载入清单为Teams准备Microsoft 365或Office 365，并配置Teams核心功能、网络和云语音工作负荷。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a91a57a077db38675a62238289ad2c204040a9cd
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675434"
---
# <a name="prepare-my-service"></a>准备服务

本文概述了为组织准备云语音服务的要求。 通过正确准备，可以确保已准备好向组织提供云语音功能。

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>加入Microsoft Teams语音工作负荷的清单

以下清单将指导你完成实施音频会议、电话系统通话套餐 (“呼叫计划”) 以及电话系统直接路由 (“直接路由”) Microsoft Teams功能的步骤。

*  [为Teams准备Microsoft 365或Office 365](onboarding-checklist-enable-office-365.md)

*  [配置Teams核心功能](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [准备网络](prepare-network.md)

*  [在 Teams 中配置云语音工作负荷](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [在Teams中配置直接路由](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

这些清单中的任务和活动是核心“操作”项，这些项目适用于使用Teams的云语音功能的每个部署。 可以自定义清单，以包含特定于你自己的Teams旅程的活动和任务。

>[!NOTE]
>本指南仅侧重于通话套餐、音频会议和直接路由。 如果你不Teams，请查看[Microsoft Teams概述](teams-overview.md)。 有关规划Teams部署的一般指南，请从[Microsoft Teams中部署聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)开始。

使用提供的清单跟踪每个活动和任务的状态，并确保未跳过任何关键步骤。 每个活动包括所需操作的详细说明和对可用于完成该活动的其他信息的引用。

尽管我们建议按顺序遵循清单，但确切的顺序取决于部署范围以及环境的配置和复杂性。 他们组织起来支持“绿地”Teams部署 (以前没有Skype for Business联机状态的部署) 或从 Skype for Business Online 迁移到Teams。 如果要从 Skype for Business Online 迁移，则可能已完成其中一些活动，现在可以忽略它们。

在按站点载入用户时，强烈建议使用 [“语音” (Playbook) 网站启用 Playbook ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 作为这些清单的补充指南。

>[!NOTE]
>大多数配置设置在 Teams 和 Skype for Business Online 之间很常见。 使用Microsoft 365 管理中心和Microsoft Teams管理中心来配置这些设置。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>Who将负责监督加入清单的完成情况？</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>下载载入清单。</li><li>根据组织的部署计划逐步完成载入清单项。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>继续载入

完成这些清单后，你将成功向Teams部署添加语音功能。

下一步，请使用 [“语音 (Playbook 网站启用 Playbook) ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 来帮助你在每个网站上载入用户，并帮助确保规划和执行特定于网站的重要活动。

-   就绪站点按站点推出计划

-   建立服务管理流程

-   执行测试和修正

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>在 Teams 中测试云语音工作负荷

在构想阶段定义并记录Teams云语音业务成功和技术实施计划并在管理中心执行所需的配置后，下一步是通过功能、功能和可用性验证组织的期望和要求。 在生产环境中部署试点或最终部署之前，应先执行此验证步骤。

可以利用在构想阶段定义的业务成功计划，作为确定要在测试阶段评估的活动、期望、功能/功能测试用例和总体范围的基础。

## <a name="define-your-testing-approach"></a>定义测试方法

在最简单的形式中，测试方法基于查看音频会议、呼叫计划或直接路由服务的功能功能，并开发测试计划，以验证范围内的用户是否满足功能要求。 下面是音频会议实现的载入阶段的示例测试计划。


| 要测试的音频会议功能 | 结果摘要 | 其他说明 |
|------------|-----------------|------------------|
| 安排包含音频会议拨入信息的临时Teams会议 | 传递/失败   | 待定 |
| 通过从 PSTN 拨入会议，并提供拨入信息，使用电话进行会议音频 | 传递/失败 | 待定 |
| 通过 PSTN 拨出，将其他人加入现有会议 | 传递/失败 | 待定 |



| 要测试的呼叫计划或直接路由功能 | 结果摘要 | 其他说明 |
|----------------------------------------------------|-----------------|------------------|
| 通过拨打 PSTN 号码进行 PSTN 呼叫       | 传递/失败       | 待定 |
| 通过从移动座机 (外部线路拨打 PSTN 号码来接收 PSTN 呼叫)  | 传递/失败 | 待定|
| 将 PSTN 呼叫从一个Teams用户传输到另一个用户 | 传递/失败 | 待定 |


>[!TIP]
>若要帮助创建测试用例作为起点，请参阅[Teams会议和呼叫](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)中提供的用户指南列表。

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>为Teams设置云语音工作负荷

定义测试方法后，下一步是在Teams云语音功能范围内配置服务环境和用户。

有关其他信息，请参阅：

- [音频会议技术规划](./cloud-voice-landing-page.md)

- [设置 Microsoft Teams 的音频会议](set-up-audio-conferencing-in-teams.md)

- [使用呼叫计划电话系统的技术规划](calling-plan-landing-page.md)

- [为Skype for Business和Microsoft Teams设置呼叫计划](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [规划直接路由](./direct-routing-plan.md)

- [配置直接路由](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a>执行测试计划

[//]: # (编辑是否正常？“用户”对我来说似乎有点歧义。)
配置用户环境和服务后，测试的最后一步包括测试计划执行，重点是功能和功能验证。 

**音频会议测试范围内用户和网站的先决条件和假设：**

-   已完成音频会议服务的业务用例定义。

-   音频会议所需的许可可用且已分配。

-   已标识组织网站和用户组的列表。

-   已标识并配置具有语言首选项的专用和共享音频会议拨号列表。

-   如果需要，[通信额度](what-are-communications-credits.md) () 已为组织设置。

-   音频会议会议网桥设置已确定并配置 (PIN 长度、进出通知、启用通知首选项) 。

-   已识别、配置和应用支持音频会议拨出方案的租户会议策略和拨号计划设置。

-   音频会议已确定和配置符合性要求。

**调用计划测试范围内用户和网站的先决条件和假设：**

-   通话套餐服务的业务用例定义已完成。

-   通话套餐所需的许可可用且已分配。

-   已标识组织网站和用户组的列表。

-   要分配给用户的电话个号码已获取或移植到 Microsoft，并且可在租户门户中使用。

-   如果需要，[通信额度](what-are-communications-credits.md) () 已为组织设置。

-   已识别、配置和应用支持通话套餐方案的租户用户策略和拨号计划设置。

-   已确定和配置通话套餐符合性要求。

**范围内用户和站点的直接路由测试先决条件和假设：**

-   直接路由服务的业务用例定义已完成。

-   直接路由所需的许可可用且已分配。

-   已标识组织网站和用户组的列表。

-   已部署、配置和配对 [SBC)  (认证的会话边框控制器](./direct-routing-plan.md#supported-session-border-controllers-sbcs)，并与电话系统配对。

-   已启用Enterprise语音，并已分配电话号码。

-   已识别、配置和分配语音路由策略。

-   Microsoft Teams已设置为范围内用户的首选呼叫客户端。
 
-   已确定并配置直接路由符合性要求。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>确定哪些音频会议功能功能将部署 (服务决策) 。</li><li>确定音频会议的用户功能要求。</li><li>确定音频会议的服务配置要求。</li><br><li>确定是否部署和配置直接路由或呼叫计划。<li>确定哪些电话系统功能将部署 (服务决策) 。</li><li>确定通话套餐或直接路由的用户功能要求。</li><li>确定通话套餐或直接路由的服务配置要求。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>开发并记录测试计划方法。</li><li>在音频会议功能范围内准备服务环境和用户。</li><li>在通话套餐或直接路由功能范围内准备服务环境和用户。</li><li>对要启用的音频会议功能执行测试验证。</li><li>对要启用的通话套餐或直接路由功能执行测试验证。</li><li>对于任何测试失败，请确认配置正确，查看社区文章，并（如果需要）提出支持案例。</li></ul></td></tr>
</table>


有关如何在Teams中对音频会议执行测试的其他详细指南，请参阅[有关音频会议的详细测试指南](./deploy-audio-conferencing-teams-landing-page.md)。

有关如何在Teams中对通话套餐执行测试的其他详细指南，请参阅[有关电话系统的详细测试指南](./cloud-voice-landing-page.md)。

<!--ENDOFSECTION-->