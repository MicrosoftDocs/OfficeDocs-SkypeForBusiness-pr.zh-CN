---
title: 在本地与云之间移动用户
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 摘要：在启用了混合部署的 Skype for Business Server 本地部署中，可以在本地环境和云之间移动用户 (无论是 Microsoft Teams 还是 Skype for Business Online) 。
ms.openlocfilehash: b4b354a6a43ab58740a053f86d9b7da1faaeb0da
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110668"
---
# <a name="move-users-between-on-premises-and-cloud"></a>在本地与云之间移动用户

在启用了混合的 Skype for Business Server 的本地部署中，你可以在本地环境和云之间移动用户（无论是移动到 Microsoft Teams 还是移动到 Skype for Business Online）。 无论用户位于本地还是在云中，均称为用户的 Skype for Business 主页：

- 本地用户与本地 Skype for Business 服务器交互。
- 联机用户可与 Skype for Business Online 服务交互。

*Teams 用户原本拥有 Skype for Business 主页，无论他们是否使用 Skype for Business。* 如果你拥有同时使用 Teams 本地 Skype for Business (，) 本地用户。 本地 Skype for Business 的 Teams 用户无法从 Teams 客户端与 Skype for Business 用户进行互操作，也无法从 Teams 与联盟组织的用户通信。 只有在将用户从本地 Skype for Business 移动到联机之后，才提供此类功能。 将用户移动到联机时，可以允许他们使用 Skype for Business Online（也可以选择使用 Teams），也可以仅使其成为 Teams 成员。 如果你的组织已在使用 Teams，强烈建议将用户移动到 Teams Only 模式，这将确保所有传入聊天和通话路由都抵达 Teams 客户端。 有关更多详细信息，请参阅 [Teams 与 Skype for Business](/microsoftteams/coexistence-chat-calls-presence) 共存和迁移以及将 Teams 与 Skype for Business 一同使用的组织互操作性 [指南](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。

## <a name="prerequisites"></a>先决条件

将用户移动到云的先决条件 (Skype for Business Only 还是 Teams Only 模式) ：

- 组织必须正确配置 Azure AD Connect，并同步用户的所有相关属性，如配置 [Azure AD Connect 中所述](configure-azure-ad-connect.md)。
- 必须配置 Skype for Business 混合，如配置 [Skype for Business 混合中所述](configure-federation-with-skype-for-business-online.md)。
- 必须为用户分配 Skype for Business Online（计划 2）许可证，如果他们将使用 Teams，还必须具有 Teams 许可证。  此外：
    - 如果在本地为用户启用了电话拨入式会议，则默认情况下，用户还必须在 Microsoft 365 或 Office 365 中分配音频会议许可证，然后才能将用户联机运行。 迁移到云后，将在云中为用户预配音频会议。 如果出于某种原因你想要将用户移动到云，但不使用音频会议功能，可以通过在 中指定 参数来覆盖此 `BypassAudioConferencingCheck` 检查 `Move-CsUser` 。
    - 如果用户在本地启用了 企业语音，则默认情况下，用户必须在 Microsoft 365 或 Office 365 中分配电话系统许可证，然后才能将用户联机。 迁移到云后，将在云中为用户预配手机系统。 如果出于某种原因你想要将用户移动到云，但不使用电话系统功能，可以通过在 中指定 参数来替代此 `BypassEnterpriseVoiceCheck` 检查 `Move-CsUser` 。


## <a name="moving-users"></a>移动用户

将用户从本地移动到云时：

- 用户开始在云中使用 Skype for Business Online 服务以使用任何 Skype for Business 功能。
- Teams 用户可以与 Skype for Business 用户进行互操作，他们也可与其他组织联合。
- 本地联系人将移动到云中 (Skype for Business 或 Teams) 。
- 他们安排在以后安排的现有会议将迁移到联机：如果用户直接移至 TeamsOnly (请参阅下面的) ，会议将转换为 Teams 会议，否则会议仍为 Skype for Business，但会进行迁移，以便联机而不是本地托管。  会议迁移异步进行，大约在移动用户 90 分钟后开始。  若要确定会议迁移的状态，可使用 [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)。 请注意，会议之前上传的任何内容都不会移动。

若要在本地和云之间移动用户 (无论是 Teams 还是 Skype for Business Online) ，请使用 Move-CsUser cmdlet 或 Skype for Business 管理控制面板，这两者都是本地工具。 这些工具支持三种不同的移动路径：

- [从 Skype for Business Server (本地) Skype for Business Online。](move-users-from-on-premises-to-skype-for-business-online.md)
- [从本地 Skype for Business Server](move-users-from-on-premises-to-teams.md) (直接) Teams Only (还会将其移动到 Skype for Business Online) 。  Skype for Business Server 2019 以及 Skype for Business Server 2015 累积更新 8 中提供直接从本地移动到 Teams Only 的选项。 使用早期版本的 Skype for Business Server 的组织可以将用户移至 Teams Only，具体做法是先将用户移动到 Skype for Business Online，然后在这些用户联机后向其应用 TeamsOnly 模式。
- [从联机 (Teams 是否) ，到本地](move-users-from-the-cloud-to-on-premises.md)。

## <a name="required-administrative-credentials"></a>所需管理凭据

若要在本地和云之间移动用户，必须在本地 Skype for Business Server 环境以及 Microsoft 365 或 Office 365 组织中使用具有足够权限的帐户。 您可以使用一个拥有所有必要权限的帐户，或者可以使用两个帐户，在这种情况下，您将使用本地凭据访问本地工具，然后在这些工具中，您将为 Microsoft 365 或 Office 365 管理帐户提供其他凭据。  

- 在本地环境中，执行移动的用户必须具有 Skype for Business Server 中的 CSServerAdminstrator 角色。
- 在 Microsoft 365 和 Office 365 中，执行移动的用户必须是全局管理员或同时具有 Skype for Business 管理员和用户管理员角色。  

    > [!Important]
    > - 如果你使用的是 Skype for Business 管理控制面板，系统将提示你提供具有适当角色的 Microsoft 365 或 Office 365 帐户的凭据，如上所述。 必须提供以 .onmicrosoft.com 结尾的帐户。 如果不可能，请使用 Move-CsUser cmdlet。
    >- 如果在 PowerShell 中使用 Move-CsUser，可以使用以 .onmicrosoft.com 结尾的帐户，或者可以使用同步到 Azure AD 的任何本地帐户，只要还要在 cmdlet 中指定 HostedMigrationOverrideUrl 参数。 托管迁移替代 URL 的值是以下 URL 的变体： https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>在以上 URL 中，将 XX 替换为两个或三个字符，按如下方式确定：
    >   - 在 Skype for Business Online PowerShell 会话中，运行以下 cmdlet：<br>`Get-CsTenant|ft identity`
    >    - 生成的值将采用以下格式：<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - 两位或三位代码是部分 DC=lyncXX001 中包含的 XX。 如果是两个字符的代码，则它是一个数字，后跟数字 (如 0a) 。 如果是三个字符的代码，它将是两个字母后跟一个数字， (jp1) 。 在所有情况下，在 XX 代码之后会立即看到 001。


## <a name="voice-configuration-requirements"></a>语音配置要求

如果在本地为用户配置了企业语音，则需要在将用户移至联机时协调更新其语音配置，或者，您也可以迁移这些用户而不使用电话功能。 可用选项取决于用户联机后是否使用 Teams 或 Skype for Business 客户端：

- 可以将用户的电话服务提供商更新为使用 [Microsoft 通话套餐](/microsoftteams/calling-plans-for-office-365)。 此选项是用户使用 Teams 还是 Skype for Business 客户端。
- 可以继续使用本地 PSTN 提供程序：
  - 必须为将使用 Teams 的语音用户配置直接 [路由](/microsoftteams/direct-routing-plan)。 直接路由仅在用户将用户从本地移动到联机之后可用。
  - 必须在联机移动后使用 Skype for Business 客户端的语音用户配置为使用 Skype for Business 混合语音功能。

有关混合环境中电话选项以及可支持性矩阵的更多详细信息，请参阅使用 PSTN 连接的混合 [环境中用户帐户](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)。

## <a name="other-considerations"></a>其他注意事项

本地和联机环境中的策略（例如控制邮件、会议和呼叫行为）是各自独立的。 在将用户从本地迁移到云之前，你可能要考虑配置环境中的任何策略并将其分配给用户，以便他们一旦迁移到联机环境，就会获得正确的配置。

## <a name="see-also"></a>另请参阅

[将用户从本地迁移至 Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md)

[将用户从本地移至团队](move-users-from-on-premises-to-teams.md)

[设置会议迁移服务 (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[规划直接路由](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)