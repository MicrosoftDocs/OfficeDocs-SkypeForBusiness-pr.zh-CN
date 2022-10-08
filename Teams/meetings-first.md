---
title: 会议第一 - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: 了解“会议第一”，用户可在 Teams 中创建会议，同时继续使用Skype for Business进行聊天、呼叫和状态。
ms.localizationpriority: medium
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
ms.openlocfilehash: 88be8ef1e43cc9d17fb541f6c56186959aeeb8a4
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999337"
---
# <a name="meetings-first"></a>会议优先

“会议第一”针对需要尽快开始使用 Teams 会议的本地企业语音的Skype for Business Server组织进行定位和优化。 对于这些组织，会议第一是使用将 Teams 会议体验设置为优先级的 **Islands** 模式的替代方法。

## <a name="what-is-meetings-first"></a>什么是会议第一？

会议优先基于 **SfBWithTeamsCollabAndMeetings** 共存模式。 会议优先不是产品或功能，它是一种使用 Teams 功能和功能的配置，Skype for Business提供独特的定制共存体验。

在“会议第一”中，用户在 Teams 中创建会议，同时继续使用Skype for Business进行聊天、呼叫和状态。 Teams 和 Skype for Business 之间没有重叠的模式。 在 Teams 中，聊天、呼叫和状态处于Skype for Business和关闭状态。 此配置可在 Skype for Business 和 Teams 之间实现独特的“更好的结合”方案，从而增强用户在共存期间的体验，以及 **与仅限 Teams** 用户的互操作性方案。

![Teams 和 Skype for Business 的更好结合方案的屏幕截图。](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> 对于没有或少有活动 Teams 聊天用户的组织来说，会议优先是更好的匹配项。 Active Teams 聊天用户不应切换到“会议第一”模式，因为他们将失去在 Teams 中聊天和访问其聊天历史记录的能力。 这些用户应改为采用 **Islands** 模式，而“会议第一”仅授予尚未在 Teams 聊天中处于活动状态的用户。

## <a name="who-should-consider-meetings-first"></a>谁应该考虑会议第一？

会议第一是针对与想要加速迁移到 Teams 会议的企业语音使用Skype for Business Server的组织。 第一次会议尤其适用于具有强大 IT 规则的组织，这些组织希望有 Teams 的托管升级路径。

对于复杂组织或大型组织，语音迁移通常是逐站点完成的，可能需要很长时间（可能需要几年时间）才能实现扩展共存方案。 如果这种共存处于 **Islands** 模式，用户始终可以选择两个会议解决方案 (Skype for Business和 Teams) ，这可能会导致混乱或不理想的情况。 与语音迁移不同，会议迁移通常可以在短时间内在整个公司中完成。 希望尽快完全切换到 Teams 会议的组织 (，而无需等待其语音迁移完成) 应考虑先开会。

第一次会议可能对没有企业语音用户的组织没有用处。 只有在能够采用 Teams 会议后，这些组织才能升级到 **Teams** 。 他们应该考虑先跳过会议。

此外，会议第一会对范围为纯游戏会议解决方案的组织非常有用，例如，在颁发“仅会议”RFP 时。

## <a name="capabilities-in-meetings-first"></a>会议第一中的功能

会议第一会将以下功能结合在一起：

- 使用 [Teams 音频会议](tutorial-audio-conferencing.yml)预[配Skype for Business Server (本地) 用户](./tutorial-audio-conferencing.yml?tutorial-step=3)。
- [会议迁移服务](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)：用户组织的会议将迁移到云，并转换为 Teams 会议，因为用户被提升为会议第一 (需要Exchange Online) 。
- 在 Teams 中简化了用户体验，以 Teams 会议、团队和频道为中心， (可以使用 [应用权限策略](teams-app-permission-policies.md)) 进行隐藏。 [Teams 专用聊天、通话和自我存在](teams-client-experience-and-conformance-to-coexistence-modes.md) 不会在会议第一版中公开，因此部署和采用工作可以专注于会议。
- 高级 [Teams 会议体验](tutorial-meetings-in-teams.yml)。
- Teams 和Skype for Business之间的“更好在一起”： 
  - 自动保留：在 Teams 中的会议中，接听电话Skype for Business会将 Teams 会议置于保留状态，反之亦然。 这可防止用户通过会议参与者无意中听到其私人呼叫。
    ![Teams 和 Skype for Business 的更好结合方案的屏幕截图。](media/meetings-first-better-together-hold.png)
  - 状态对帐：Teams 中的活动反映在用户的状态中，这是聊天和呼叫Skype for Business Skype for Business状态。 具体而言，当会议第一用户在 Teams 会议中时，会更新其状态以反映这一点。 当他们显示屏幕时，他们的状态将更新为根据Skype for Business) 中的设置显示“请勿打扰 (”。
  - Mac) 上也提供了 USB 设备 HID 控制对帐 (：在 Teams 会议中，Teams 会遵守 HID 控件，并在所有其他情况下Skype for Business。
  - 除非另有说明，否则“更好在一起”功能目前需要最新的 Windows 桌面客户端。

## <a name="prerequisites-for-meetings-first"></a>会议优先的先决条件

会议第一项的唯一硬性要求与具有本地 Active Directory和Skype for Business本地部署的 Teams 的要求相同：

- [Teams 的一般先决条件](upgrade-plan-journey-prerequisites.md)，包括
- [Teams 中的标识和身份验证](identify-models-authentication.md)
- [为 Teams 和 Skype for Business 配置 Azure Active Directory](/skypeforbusiness/hybrid/configure-azure-ad-connect)。

[不需要Skype for Business混合拓扑](/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online)，但建议使用它。 会议迁移服务和互操作性等某些功能依赖于该拓扑。

会议优先支持任何版本的Skype for Business Server (并且已知可以使用不再支持的 Lync Server) 。 它支持任何受支持的Skype for Business客户端，但是 Better Together 功能需要最近的客户端。

满足这些要求后， (而不是之前的) ，用户可以[获得 Microsoft 365 或 Office 365 和 Teams 的许可](/office365/enterprise/assign-licenses-to-user-accounts)。

为了获得最佳会议第一体验，应为用户启用[Exchange Online](exchange-teams-interact.md)、[SharePoint Online 和 OneDrive for Business](sharepoint-onedrive-interact.md) 以及 Microsoft 365 组创建。 对于邮箱位于本地 Exchange 的用户，或者没有 SharePoint Online 或 OneDrive For Business 或 Microsoft 365 组创建的用户，支持“会议第一”。 但是，他们的经验将不那么完整。 对于使用本地Exchange Server的组织，可能会 (取决于Exchange Server) 创建和查看 Teams 客户端会议的一些限制，以及合规性功能方面的一些限制。

用户必须至少获得 [Teams 的许可](/microsoft-365/admin/manage/assign-licenses-to-users)。 此外，它们可以根据需要获得 [音频会议](set-up-audio-conferencing-in-teams.md)许可。

建议在向用户发放许可证时 [，将 **SfBOnly** 或 **SfBWithTeamsCollab**](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) 模式作为租户默认授予。 此设置可确保在启动“会议第一”之前，用户不会在默认 **的“岛屿** ”模式下自行开始使用 Teams。

Windows 和 Mac)  (、浏览器客户端和移动客户端上的完整桌面客户端都支持会议优先。 它还与[Microsoft Teams 会议室](/microsoftteams/room-systems/)兼容。 更好的一起需要完整的桌面客户端。

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>首先在会议中准备 Teams 会议

要使用户在 Teams 会议中获得最佳体验，应：

- 具体而言，请按照 [Microsoft Teams 会议和会议](deploy-meetings-microsoft-teams-landing-page.md)中的步骤进行操作。
- [评估环境](3-envision-evaluate-my-environment.md)。
- [为 Microsoft Teams 准备组织的网络](prepare-network.md)。
- 使用支持 Teams 的 [会议室设备和解决方案](/skypeforbusiness/certification/devices-meeting-rooms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)升级会议室，或使用 [适用于 Microsoft Teams 的云视频互操作](cloud-video-interop.md) ，使现有的第三方会议室和设备能够加入 Teams 会议。
- 为用户配备 [经过认证的 USB 音频和视频设备](/skypeforbusiness/certification/devices-usb-devices?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)。
- 准备 [推动 Teams 会议的认知和采用](adopt-microsoft-teams-landing-page.md)。
- [规划服务管理](4-envision-plan-my-service-management.md)。
- 熟悉丰富的通话分析报告，以 [排查通话质量差的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)。

在此阶段，可以考虑运行中等规模生产就绪试点。

## <a name="configure-users-for-meetings-first"></a>为会议第一版配置用户

获得用户许可并准备组织参加 Teams 会议后，即可为用户启用“会议第一”。 我们简化了操作：一个设置将全部完成。

会议第一版中的所有功能和用户体验（包括 Teams 客户端配置和[用户体验的自动符合](teams-client-experience-and-conformance-to-coexistence-modes.md)性、会议迁移服务和 Better Together 功能）均通过授予用户 (或用户组进行配置，或租户默认) [Microsoft Teams 管理中心](manage-teams-in-modern-portal.md)或 [PowerShell](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) 中的 [SfBWithTeamsCollabAndMeetings 共存模式](setting-your-coexistence-and-upgrade-settings.md)。

![用于启用“会议第一”的管理员设置的屏幕截图。](media/teams-meeting-admin-settings.png)

如果要在用户 Teams 客户端的左侧导航栏中隐藏 Teams 和 Channels 应用程序，以进一步专注于会议，可以使用 [应用设置策略](teams-app-setup-policies.md)。

## <a name="reporting-and-call-analytics"></a>报告和呼叫分析

“会议第一”中 Teams 会议的报告和呼叫分析与处于其他模式的会议不一样。

## <a name="related-links"></a>相关链接

有关详细信息，请参阅[“选择升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)”、“[迁移和互操作性指南](migration-interop-guidance-for-teams-with-skype.md)”，以及[与Skype for Business共存](coexistence-chat-calls-presence.md)，了解更多详细信息。
