---
title: 会议第一个 - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: 了解会议第一，用户可以在会议中创建Teams，同时继续使用Skype for Business聊天、呼叫和状态。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b75f9bf5328b25a1ce1fd695a90163f63a61f823
ms.sourcegitcommit: bd7847de9d1402476f8faaeae2ff97ec60d86a1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51262579"
---
# <a name="meetings-first"></a>会议优先

"会议第一"面向Skype for Business Server组织，企业语音希望尽快开始使用会议Teams本地组织。 对于这些组织，"会议优先"是使用 **"** 岛屿模式"的替代方法，该模式Teams会议体验。

## <a name="what-is-meetings-first"></a>什么是会议第一？

会议第一基于 **SfBWithTeamsCollabAndMeetings** 共存模式。 "会议第一"不是产品或功能，而是一种配置，它使用会议和会议的功能Teams Skype for Business提供定制的独特共存体验。

在"会议第一"中，用户Teams会议，同时继续使用Skype for Business聊天、呼叫和状态。 两者之间不存在形式Teams Skype for Business。 聊天、通话和状态在Skype for Business中打开Teams。 这样，Skype for Business 和 Teams 之间可实现独特的"更好地协作"方案，从而增强共存期间用户体验，以及仅与 Teams 用户 **互操作方案**。

![一张屏幕截图，显示了使用 Teams 和 Skype for Business](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> "会议第一"对于没有或很少活跃聊天用户的组织Teams匹配。 不应Teams聊天用户切换到会议第一模式，因为他们将失去在聊天中聊天Teams访问其聊天历史记录的能力。 这些用户应改为以 **岛屿** 模式进行授权，而"会议第一"仅授予尚未在"群岛"中聊天Teams。

## <a name="who-should-consider-meetings-first"></a>Who"会议第一"？

"会议第一"专为将 Skype for Business Server 与 企业语音 一起使用的组织所设计，这些组织希望加速移动到 Teams 会议，尤其是具有强大 IT 规则、希望采用托管、确定性的升级路径Teams。

对于复杂或大型组织，语音迁移通常按站点进行，并且可能需要很长时间，可能需要数年，从而导致延长共存方案。 如果该共存模式为 **"** 群岛"模式，则用户始终可以选择两种会议解决方案 (Skype for Business Teams) ，这可能会导致混乱或情况不最佳。 与语音迁移不同，会议迁移通常在短时间内在整个公司内完成。 希望尽快完全切换到会议Teams且无需等待语音迁移完成 (组织应考虑"会议) 会议。

"会议第一"对于没有用户参与的组织企业语音有用。 这些组织应能够升级到 **Teams，只要** 它们能够采用Teams会议。 他们应考虑跳过"会议第一"。

此外，"会议第一"对于其范围为纯游戏会议解决方案（例如，发出"仅会议"RFP）的组织很有用。

## <a name="capabilities-in-meetings-first"></a>会议第一中的功能

Meeting First 将以下功能汇集在一起：

- [使用 Skype for Business Server (音频) 预配](./tutorial-audio-conferencing.yml?tutorial-step=3)Teams[本地用户](tutorial-audio-conferencing.yml)。
- [会议迁移服务](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)：由用户组织的会议将迁移到云中，并转换为 Teams 会议，因为用户已升级为会议第一 (需要Exchange Online) 。
- 简化的 Teams 用户体验，以 Teams 会议、团队和频道为中心 (可以选择使用应用权限策略策略隐藏这些) ; [](teams-app-permission-policies.md)[Teams私人聊天](teams-client-experience-and-conformance-to-coexistence-modes.md)、通话和自我状态不会在"会议第一"中公开，因此部署和采用工作能够完全专注于会议。
- 高级[Teams会议体验](tutorial-meetings-in-teams.yml)。
- 两者之间的"Teams更好Skype for Business： 
  - 自动保留：在 Teams 中参加会议时，Skype for Business呼叫将暂停Teams会议，反之亦然。 这可以防止用户被会议参与者无意中听到其私人呼叫。
    ![一张屏幕截图，显示了使用 Teams 和 Skype for Business](media/meetings-first-better-together-hold.png)
  - 状态对帐：Teams中的活动反映在用户状态中，这是Skype for Business状态，因为聊天和Skype for Business。 具体而言，当"会议第一"用户Teams会议时，其状态将更新以反映这一点。 当他们显示屏幕时，他们的状态将更新为根据 (中的设置显示"请勿打扰"Skype for Business) 。
  - MAC) 上也提供 USB 设备 HID (对帐：TEAMS 在 Teams 会议中和在所有其他情况下Skype for Business受 HID 控件的遵守。
  - 除非另有说明，否则 Better Together 功能Windows最新的桌面客户端。

## <a name="prerequisites-for-meetings-first"></a>会议第一的先决条件

"会议第一"的唯一硬要求与使用本地 Active Directory Teams本地部署Skype for Business要求相同：

- [其他项的一Teams](upgrade-plan-journey-prerequisites.md)先决条件，包括
- [标识和身份验证在 Teams](identify-models-authentication.md)和
- [为 Azure Active Directory 和 Teams 配置Skype for Business。](/skypeforbusiness/hybrid/configure-azure-ad-connect)

不需要[Skype for Business](/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online)混合拓扑，但建议这样做。 某些功能（如会议迁移服务和互操作性）依赖于该拓扑。

会议 First 支持任何版本的 Skype for Business Server (，已知可与不再支持的 Lync Server) 。 支持的任何客户端支持Skype for Business，但 Better Together 功能需要最新的客户端。

一旦满足这些要求 (而不是在) ，用户就可以获得许可，Microsoft 365或[Office 365 Teams。](/office365/enterprise/assign-licenses-to-user-accounts)

为获得最佳"会议第一"体验，应该为用户[](exchange-teams-interact.md)启用Exchange Online、SharePoint [Online](sharepoint-onedrive-interact.md)和 OneDrive for Business，Microsoft 365组创建。 "会议第一"支持其邮箱位于Exchange，或者没有 SharePoint Online 或 OneDrive for Business，或者没有Microsoft 365组创建的用户。 但是，他们的体验不太完整。 特别是，对于在本地使用 Exchange Server 的组织， (根据 Exchange Server) 的版本，在从 Teams 客户端创建和查看会议以及合规性功能方面可能有一些限制。

用户至少必须获得使用[Teams](/microsoft-365/admin/manage/assign-licenses-to-users)的许可。 此外，如果需要，他们还可以获得 [音频会议](set-up-audio-conferencing-in-teams.md)的许可。

我们建议在向用户授予许可证时，将 [**SfBOnly** 或 **SfBWithTeamsCollab**](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)模式授予为租户默认值。 这可确保在准备好启动"会议优先Teams，用户不会在默认岛屿模式下自行开始使用会议。

会议 First 在桌面客户端和 Mac (Windows、) 客户端和移动客户端上受支持。 它还与[Microsoft Teams 会议室](/microsoftteams/room-systems/)兼容。 Better Together 需要完整的桌面客户端。

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>在"会议Teams准备会议

若要让用户在会议期间获得最佳体验，Teams应：

- 请遵循[会议中的](deploy-meetings-microsoft-teams-landing-page.md)步骤，Microsoft Teams会议。
- [评估环境](3-envision-evaluate-my-environment.md)。
- [准备组织的网络以Microsoft Teams。](prepare-network.md)
- 使用支持Teams会议室设备和解决方案升级会议室，[](/skypeforbusiness/certification/devices-meeting-rooms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)或使用[适用于 Microsoft Teams](cloud-video-interop.md)的云视频互操作，使现有第三方会议室和设备能够加入 Teams 会议。
- 为用户配置 [经过认证的 USB 音频和视频设备](/skypeforbusiness/certification/devices-usb-devices?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)。
- 准备[促进会议的认知和Teams采用](adopt-microsoft-teams-landing-page.md)。
- [规划服务管理](4-envision-plan-my-service-management.md)。
- 熟悉丰富的呼叫分析报告，解决 [通话质量不佳的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)。

可以考虑在此阶段运行中等规模的生产就绪试点。

## <a name="configure-users-for-meetings-first"></a>为"会议第一"配置用户

获得用户许可并准备好组织Teams会议后，可以先为用户启用会议。 我们已轻松实现：一项设置将全部实现！

"会议第一"中的所有功能和用户体验（包括 Teams 客户端配置和用户体验的[](teams-client-experience-and-conformance-to-coexistence-modes.md)自动一致性、会议迁移服务和 Better Together 功能）都是通过向用户 (或用户组或租户默认) 在[Microsoft Teams](manage-teams-in-modern-portal.md)管理中心中或[通过使用 PowerShell](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)的[SfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md)共存模式进行配置的。

![用于启用"会议第一"的管理员设置的屏幕截图](media/teams-meeting-admin-settings.png)

（可选）如果你希望从用户的 Teams 客户端的左侧导航中隐藏 Teams 和 Channels 应用程序，以进一步将他们的体验重点放在会议上，可以使用应用设置策略实现此目的[。](teams-app-setup-policies.md)

## <a name="reporting-and-call-analytics"></a>报告和呼叫分析

对于会议第一Teams会议的报告和呼叫分析与其他模式下的报表和呼叫分析没有变化。

## <a name="related-links"></a>相关链接

查看本文后，可能需要查阅选择升级过程、迁移[](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)和互操作性指南，以及[](migration-interop-guidance-for-teams-with-skype.md)与 Skype for Business[共存](coexistence-chat-calls-presence.md)，了解更多详细信息。
