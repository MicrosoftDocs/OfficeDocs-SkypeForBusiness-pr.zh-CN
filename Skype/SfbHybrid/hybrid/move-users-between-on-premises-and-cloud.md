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
description: 摘要：在启用了混合的 Skype for Business Server 本地部署中，可以在本地环境和云之间移动用户 (在停用) 之前是 Microsoft Teams 还是 Skype for Business Online。
ms.openlocfilehash: 9a8099d5825eda6820bb8746d543e955524111be
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510773"
---
# <a name="move-users-between-on-premises-and-cloud"></a>在本地与云之间移动用户

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

在启用了混合部署的 Skype for Business Server 本地部署中，可以在本地环境和云 (在停用) 之前在 Microsoft Teams 或 Skype for Business Online 之间移动用户。 无论用户位于本地还是在云中，均称为用户的 Skype for Business 主页：

- 本地用户与本地服务器交互Skype for Business服务器。
- 联机用户可与 Skype for Business Online 服务交互。

*Teams用户本身拥有Skype for Business，无论他们是否Skype for Business家庭。* 如果你拥有本地Skype for Business用户也使用并行Teams (，) 本地。 Teams本地 Skype for Business 的用户无法从 Teams 客户端与 Skype for Business 用户进行互操作，也无法从 Teams 与联盟组织的用户通信。 只有在将用户从本地环境移动到联机并Skype for Business TeamsOnly 后，此功能才完全可用。 将用户移动到联机时，可以允许他们使用 Skype for Business Online（也可以选择使用 Teams），也可以仅使其成为 Teams 成员。 强烈建议将用户移动到"仅Teams模式，这将确保所有传入聊天和呼叫的路由都到达其 Teams 客户端。 有关更多详细信息，请参阅[Teams](/microsoftteams/coexistence-chat-calls-presence)与 Skype for Business 共存和迁移和互操作性指南，以指导组织将 Teams 与[Skype for Business。](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="prerequisites"></a>先决条件

将用户移动到云的先决条件 (在停用之前Teams仅模式Skype for Business或联机) ：

- 组织必须正确配置 Azure AD 连接并同步用户的所有相关属性，如配置[Azure AD 连接](configure-azure-ad-connect.md)中所述。
- Skype for Business配置混合，如配置混合Skype for Business[中所述](configure-federation-with-skype-for-business-online.md)。
- 必须在计划 2 中为用户分配 Teams Skype for Business Online (许可证) 。 即使停用 Skype for Business Online，Skype for Business仍需要联机许可证。  此外：
    - 如果用户在本地启用了电话拨入式会议，则默认情况下，用户还必须在 Teams 中分配音频会议许可证，然后才能将用户联机。 迁移到云后，将在云中为用户预配音频会议。 如果出于某种原因，需要把用户转移到云端，但不使用音频会议功能，则可以通过在 `Move-CsUser` 中指定 `BypassAudioConferencingCheck` 参数来覆盖该检查。
    - 如果在本地为用户企业语音用户，则默认情况下，用户必须在 电话系统 中分配一个 Teams 许可证，然后才能将用户联机。 迁移到云后，将在云中为用户预配手机系统。 如果出于某种原因你想要将用户移动到云，但不使用电话系统功能，可以通过在 中指定 参数来替代此 `BypassEnterpriseVoiceCheck` 检查 `Move-CsUser` 。


## <a name="moving-users"></a>移动用户

将用户从本地移动到云时：

- Teams用户能够与 Skype for Business 进行互操作，如果他们是 TeamsOnly，则还可以与其他组织联盟。
- 用户开始在云中使用 Skype for Business Online 服务以使用任何 Skype for Business 功能。
- 来自本地的联系人将移动到云 (，Teams或Skype for Business Online) 。
- 他们安排在以后安排的现有会议将迁移到联机：如果用户直接移至 TeamsOnly (请参阅下面的) ，会议将转换为 Teams 会议，否则会议将保留为 Skype for Business 但会进行迁移，以便联机而不是本地托管。  会议迁移异步进行，大约在移动用户 90 分钟后开始。  若要确定会议迁移的状态，可使用 [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)。 请注意，会议之前上传的任何内容都不会移动。

若要在本地和云 (之间移动用户 (无论是 Teams 还是 Skype for Business Online) ，请使用 Move-CsUser cmdlet 或 Skype for Business 管理控制面板，这两者都是本地工具。 这些工具支持三种不同的移动路径：

- [从Skype for Business Server (本地) 直接](move-users-from-on-premises-to-teams.md)Teams仅 (，这也会将它们移动到 Skype for Business Online) 。  无论是使用哪种版本的 Teams，从内部部署直接移动到 Lync Server 的行为现在Skype for Business Server都是自动的。 不再需要指定开关 `-MoveToTeams` 获取此行为。  
- [从Skype for Business Server (本地) 到 Skype for Business Online。](move-users-from-on-premises-to-skype-for-business-online.md) 仍然需要将用户移动到 Skype for Business Online 而不成为 TeamsOnly 的客户可以通过先使用 TeamsOnly 模式将用户移动到云，然后使用 Teams 管理中心将用户模式更新为 TeamsOnly 而非 TeamsOnly 来实现此目的。 `Grant-CsTeamsUpgradePolicy` 停用 Online 后，此选项Skype for Business不再可用。
- [从联机 (，Teams是否) ，到本地](move-users-from-the-cloud-to-on-premises.md)。

> [!NOTE] 
> 不再需要在部署中指定 -MoveToTeams Move-CsUser将用户直接从本地移动到 TeamsOnly。 以前，如果未指定此开关，则用户从本地Skype for Business Server转换为 Skype for Business Online，其模式保持不变。 现在，使用 Move-CsUser 将用户从本地移动到云时，系统会自动为用户分配 TeamsOnly 模式，其从本地会议自动转换为 Teams 会议，就像已指定交换机一样，无论是否实际指定了交换机。 `-MoveToTeams` 
> 

## <a name="required-administrative-credentials"></a>所需管理凭据

若要在本地和云之间移动用户，必须在本地部署环境以及 Skype for Business Server 组织中使用具有足够权限Teams帐户。 您可以使用一个拥有所有必要权限的帐户，或者可以使用两个帐户，在这种情况下，您将使用本地凭据访问本地工具，然后在这些工具中，您将为 Teams 管理帐户提供其他凭据。  

- 在本地环境中，执行移动的用户必须具有 CSServerAdministrator 角色Skype for Business Server。
- 在Teams中，执行移动的用户必须满足以下条件之一：
  - 用户是全局管理员角色的成员。
  - 用户是用户管理员和Teams管理员角色的成员。
  - 用户是管理员和用户Skype for Business的成员。  

    > [!Important]
    > - 如果你使用的是管理Skype for Business控制面板，系统将提示你提供具有适当角色Microsoft 365帐户的凭据，如上所述。 必须提供以 .onmicrosoft.com 结尾的帐户。 如果不可能，请使用 Move-CsUser cmdlet。
    >- 如果在 PowerShell 中使用 Move-CsUser，可以使用以 .onmicrosoft.com 结尾的帐户，或者可以使用同步到 Azure AD 的任何本地帐户，只要还要在 cmdlet 中指定 HostedMigrationOverrideUrl 参数。 托管迁移替代 URL 的值是以下 URL 的变体： https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>在以上 URL 中，将 XX 替换为两个或三个字符，按如下方式确定：
    >   - 在 PowerShell Teams中，运行以下 cmdlet：<br>`Get-CsTenant|ft identity`
    >   - 生成的值将采用以下格式：<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >   - 两位或三位代码是部分 DC=lyncXX001 中包含的 XX。 如果是两个字符的代码，则它是一个数字，后跟数字 (如 0a) 。 如果是三个字符的代码，它将是两个字母后跟一个数字， (jp1) 。 在所有情况下，在 XX 代码之后会立即看到 001。


## <a name="voice-configuration-requirements"></a>语音配置要求

如果在本地为用户配置了企业语音，则需要在将用户移至联机时协调更新其语音配置，或者，您也可以迁移这些用户而不使用电话功能。 可用选项取决于用户联机后是Teams还是Skype for Business客户端：

- 可以将用户的电话服务提供商更新为使用 [Microsoft 通话套餐](/microsoftteams/calling-plans-for-office-365)。 此选项是用户使用客户端还是Teams Skype for Business客户端。
- 可以继续使用本地 PSTN 提供程序：
  - 必须使用直接路由 配置Teams语音[用户](/microsoftteams/direct-routing-plan)。 直接路由仅在用户将用户从本地移动到联机之后可用。
  - 联机移动后Skype for Business客户端的语音用户必须配置为使用Skype for Business 混合语音功能。

有关混合环境中电话选项以及可支持性矩阵的更多详细信息，请参阅使用 PSTN 连接的混合 [环境中用户帐户](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)。

## <a name="other-considerations"></a>其他注意事项

本地和联机环境中的策略（例如控制邮件、会议和呼叫行为）是各自独立的。 在将用户从本地迁移到云之前，你可能要考虑配置环境中的任何策略并将其分配给用户，以便他们一旦迁移到联机环境，就会获得正确的配置。

## <a name="see-also"></a>另请参阅

[将用户从本地移至团队](move-users-from-on-premises-to-teams.md)

[将用户从本地迁移至 Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md)

[设置会议迁移服务 (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[规划直接路由](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
