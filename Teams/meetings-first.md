---
title: 会议第一 - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: 了解会议第一，用户可以在 Teams 中创建会议，同时继续使用 Skype for Business 进行聊天、通话和状态。
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
ms.openlocfilehash: c4e4eba45e7f6719b1fb3427ebd169b69a1e86c9
ms.sourcegitcommit: 4e648c3dd71d9c38cbcb81fab9e8cb9d241fe79c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "49871073"
---
# <a name="meetings-first"></a>会议优先

"会议第一"针对 Skype for Business Server 组织进行了优化，企业语音希望尽快开始使用 Teams 会议的本地用户。 对于这些组织，会议优先是使用 **以** Teams 会议体验为优先级的岛屿模式的替代方式。

## <a name="what-is-meetings-first"></a>什么是会议第一？

Meetings First 基于 **SfBWithTeamsCollabAndMeetings** 共存模式。 "会议第一"不是产品或功能，而是一种配置，它使用 Teams 和 Skype for Business 的功能来提供唯一定制共存体验。

在"会议第一"中，用户在 Teams 中创建会议，同时继续使用 Skype for Business 进行聊天、通话和状态。 Teams 和 Skype for Business 之间不存在形式重叠的情况。 聊天、通话和状态在 Skype for Business 中打开，Teams 中则关闭。 这样，Skype for Business 和 Teams 之间就可实现独特的"更好的协作"方案，从而增强用户共存期间的体验，以及与 Teams 用户之间的 **互操作性** 方案。

![Teams 和 Skype for Business 的更佳协作方案的屏幕截图](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> 对于没有或没有活动 Teams 聊天用户的组织，"会议第一"是更好的匹配。 活动 Teams 聊天用户不应切换到会议第一模式，因为他们将失去在 Teams 中聊天和访问其聊天历史记录的能力。 这些用户应改为以 **群岛** 模式命名，而会议第一次仅授予尚未在 Teams 中聊天的用户。

## <a name="who-should-consider-meetings-first"></a>谁应该先考虑会议？

会议第一个方案专为将 Skype for Business Server 与 企业语音 一起使用的组织所设计，这些组织希望加速他们转移到 Teams 会议，尤其是具有强 IT 规则、希望获得 Teams 的托管、确定性升级路径的组织。

对于复杂组织或大型组织，语音迁移通常按站点执行，并且可能需要很长时间，可能可能需要数年，从而导致扩展的共存方案。 如果该共存模式为 **"** 群岛"模式，则用户始终可以选择两种会议解决方案 (Skype for Business 和 Teams) ，这可能会导致混乱或情况不最佳。 与语音迁移不同，会议迁移通常可以在短时间内在整个公司内完成。 希望尽快完全切换到 Teams 会议且无需等待语音迁移完成 (的组织应考虑先) 会议。

对于没有用户或用户的组织，"会议第一企业语音有用。 这些组织应能够在能够采用 **Teams** 会议时尽快升级到 Teams。 他们应考虑跳过"会议第一"。

此外，"会议第一"对于其范围为纯会议解决方案的组织很有用，例如，当发出"仅会议"RFP 时。

## <a name="capabilities-in-meetings-first"></a>会议第一中的功能

Meeting First 将以下功能汇集在一起：

- [使用 Teams 音频 (](https://docs.microsoft.com/microsoftteams/tutorial-audio-conferencing?tutorial-step=3) 将 Skype for Business Server) 本地 [用户](tutorial-audio-conferencing.yml)。
- [会议迁移服务](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)：由用户组织的会议将迁移到云，并转换为 Teams 会议，因为用户被提升为"会议第一 (需要 Exchange Online) 。
- Teams 中以 Teams 会议和团队和频道为中心的简化用户体验 (（可选）使用应用权限策略选项隐藏) ; [](teams-app-permission-policies.md)[Teams 私人聊天、通话](teams-client-experience-and-conformance-to-coexistence-modes.md)和自我状态不会在"会议第一"中公开，从而使部署和采用工作能够完全专注于会议。
- 高级 [团队会议体验](tutorial-meetings-in-teams.yml)。
- Teams 与 Skype for Business 之间的"更好地协作"： 
  - 自动保留：在 Teams 中参加会议时，在 Skype for Business 中加入通话将暂停 Teams 会议，反之亦然。 这可以防止用户被会议参与者听到其私人呼叫。
    ![Teams 和 Skype for Business 的更佳协作方案的屏幕截图](media/meetings-first-better-together-hold.png)
  - 状态对帐：Teams 中的活动反映在用户状态中，这是 Skype for Business 状态，因为聊天和通话在 Skype for Business 中。 具体而言，当"会议第一"用户参加 Teams 会议时，其状态将更新以反映这一点。 当他们显示屏幕时，他们的状态将更新为 (Skype for Business) 中的设置显示"请勿打扰) 。
  - MAC (上也提供 USB 设备 HID 控件对帐) ：在 Teams 会议中，Teams 和 Skype for Business 在所有其他情况下都遵守 HID 控件。
  - 除非另有说明，否则 Better Together 功能目前需要最新的 Windows 桌面客户端。

## <a name="prerequisites-for-meetings-first"></a>会议第一先决条件

"会议第一"的唯一硬性要求与使用本地 Active Directory 和 Skype for Business 本地部署的 Teams 的要求相同：

- [Teams 的一般先决条件](upgrade-plan-journey-prerequisites.md)，包括
- [Teams 中的标识和身份验证](identify-models-authentication.md) 以及
- 为 Teams 和 Skype for Business 配置[Azure Active Directory。](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect)

不需要 [Skype for Business 混合](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) 拓扑，但建议这样做。 某些功能（如会议迁移服务和互操作性）依赖于该拓扑。

会议 First 支持任何版本的 Skype for Business Server (已知可与不再支持的 Lync Server) 。 支持的任何 Skype for Business 客户端都支持它，但 Better Together 功能需要最新的客户端。

一旦满足这些要求 (而不是在) ，用户就可以获得 [Microsoft 365 或 Office 365](https://docs.microsoft.com/office365/enterprise/assign-licenses-to-user-accounts)和 Teams 的许可。

为获得最佳会议第一体验，应允许用户创建 [Exchange Online、SharePoint](exchange-teams-interact.md)Online 和 [OneDrive for Business](sharepoint-onedrive-interact.md)以及 Microsoft 365 组。 邮箱位于 Exchange 本地、没有 SharePoint Online、OneDrive For Business 或 Microsoft 365 组创建的用户支持"会议第一"。 但是，他们的体验将不太完整。 特别是，对于在本地使用 Exchange Server 的组织， (根据 Exchange Server) 的版本，从 Teams 客户端创建和查看会议存在一些限制，以及合规性功能方面的限制。

用户至少必须获得 [Teams 许可](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。 此外，如果需要， [他们可以获得音频](set-up-audio-conferencing-in-teams.md)会议的许可。

我们建议在向用户授予许可证时，将 [**SfBOnly** 或 **SfBWithTeamsCollab**](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)模式授予为租户默认值。 这可确保在准备好启动"会议优先"之前，用户不会在默认岛屿模式下自行开始使用 Teams。

Windows 和 Mac (、浏览器客户端) 移动客户端上支持"会议第一"功能。 它还与 Microsoft [Teams 会议室兼容](https://docs.microsoft.com/microsoftteams/room-systems/)。 Better Together 需要完整的桌面客户端。

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>在"会议第一"中准备 Teams 会议

若要让用户在 Teams 会议中获得最佳体验，应：

- 请尤其按照 [Microsoft Teams 的会议和会议](deploy-meetings-microsoft-teams-landing-page.md)中的步骤操作。
- [评估环境](3-envision-evaluate-my-environment.md)。
- [为 Microsoft Teams 准备组织的网络](prepare-network.md)。
- 使用支持 Teams 的会议室[](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)设备和解决方案升级会议室，或使用 Microsoft [Teams](cloud-video-interop.md)的云视频互操作，使现有第三方会议室和设备能够加入 Teams 会议。
- 为用户配置 [经过认证的 USB 音频和视频设备](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)。
- 准备 [提高 Teams 会议的认知和采用率](adopt-microsoft-teams-landing-page.md)。
- [规划服务管理](4-envision-plan-my-service-management.md)。
- 熟悉丰富的呼叫分析报告，解决 [通话质量不佳的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)。

可以考虑在此阶段运行中等规模生产就绪试点。

## <a name="configure-users-for-meetings-first"></a>为"会议第一"配置用户

获得用户许可并准备好组织参加 Teams 会议后，可以先为用户启用"会议第一"。 我们让操作变得简单：一个设置将全部实现！

"会议第一"中的所有功能和用户体验（包括 Teams 客户端配置[](teams-client-experience-and-conformance-to-coexistence-modes.md)和用户体验的自动一致性、会议迁移服务和 Better Together 功能）都是通过向用户 (或用户组或租户默认) 在[Microsoft Teams](manage-teams-in-modern-portal.md)管理中心或[PowerShell](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)中授予[SfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md)共存模式来配置的。

![用于启用"会议第一"的管理员设置的屏幕截图](media/teams-meeting-admin-settings.png)

（可选）如果你希望从用户 Teams 客户端的左侧导航中隐藏 Teams 和频道应用程序，以进一步将他们的体验集中在会议上，可以使用应用权限策略实现这些 [体验](teams-app-permission-policies.md)。

## <a name="reporting-and-call-analytics"></a>报告和呼叫分析

"会议第一"中 Teams 会议的报告和呼叫分析与其他模式中的报告和呼叫分析没有变化。

## <a name="related-links"></a>相关链接

查看本文后，可能需要查阅"选择升级过程、[](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)迁移和互操作性指南"，以及与[Skype for Business](coexistence-chat-calls-presence.md)共存，了解更多详细信息。 [](migration-interop-guidance-for-teams-with-skype.md)


