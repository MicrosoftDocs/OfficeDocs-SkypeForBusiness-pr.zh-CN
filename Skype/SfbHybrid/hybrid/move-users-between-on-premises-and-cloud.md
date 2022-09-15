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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 摘要：在为混合启用Skype for Business Server的本地部署中，可以在本地环境和云之间移动用户。
ms.openlocfilehash: ac32c4037cf275d9a6a7545701c1899742d8fd12
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705871"
---
# <a name="move-users-between-on-premises-and-cloud"></a>在本地与云之间移动用户

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

在本地部署Skype for Business Server中，Skype for Business用户也可以使用 Teams，但并非所有 Teams 功能都可供此类用户使用，只要这些用户配置为使用本地Skype for Business Server部署。 这些用户据说是本地的“主页”，某些 Teams 功能在本地托运时不可用，例如：
- 通过用户的 Teams 客户端与其他组织中的用户进行联合呼叫和聊天不可用
- 通过用户的 Teams 客户端与组织中使用Skype for Business客户端的其他用户进行互操作通信。
- 如果为用户分配了电话系统许可证) ，则 PSTN 呼叫功能 (。

若要获得完整的 Teams 功能，必须将这些用户从本地Skype for Business移动到云，此时用户将变为 TeamsOnly。 将用户从本地移动到云的行为会将用户的共存模式设置为 TeamsOnly。 将用户移动到云后，他们即是 TeamsOnly，这意味着所有传入的聊天和呼叫都位于其 Teams 客户端中。 有关详细信息，请参阅 [Teams 共存与Skype for Business](/microsoftteams/coexistence-chat-calls-presence)和[迁移以及组织使用 Teams 和Skype for Business的互操作性指南](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。

若要将用户从本地Skype for Business Server部署移动到云，需要[配置Skype for Business混合](/skypeforbusiness/hybrid/plan-hybrid-connectivity)。  为混合部署启用部署后，可以将用户从本地环境移动到云，使其成为 TeamsOnly，如下所述。 如有必要，还可以将 TeamsOnly 用户移回本地 Skype for Bsuiness 部署。 



## <a name="prerequisites"></a>先决条件

将用户移到 TeamsOnly 模式的先决条件：

- 组织必须正确配置 Azure AD Connect，并按照配置 [Azure AD Connect](configure-azure-ad-connect.md) 中所述同步用户的所有相关属性。
- Skype for Business必须配置混合，如配置[混合](configure-federation-with-skype-for-business-online.md)Skype for Business中所述。
- 必须为用户分配 Teams 和 Skype for Business Online (计划 2) 的许可证。 即使在 Skype for Business Online 停用后，仍需要 Skype for Business Online 许可证。  此外：
    - 如果用户已启用本地电话拨入式会议，则在联机移动用户之前，用户还必须在 Teams 中分配音频会议许可证。 迁移到云后，将在云中为用户预配音频会议。 
    - 如果用户已启用本地企业语音，则用户必须在 Teams 中分配 Teams 电话许可证，然后才能将用户联机移动。 迁移到云后，将为云中的电话系统预配用户。 
  
从 2022 年 7 月 31 日起，若要在本地部署和云之间移动用户，必须使用以下最低版本的 Skype for Business Server 或 Lync Server：

</br>
</br>

|本地产品|所需的最低版本|所需的最小版本|
|---|---|---|
|Skype for Business Server 2019| CU6 |7.0.2046.385|
|Skype for Business Server 2015| CU12|6.0.9319.619|
|Lync Server 2013| 带有修补程序 7 的 CU10|5.0.8308.1182|

</br>
</br>

## <a name="moving-users"></a>移动用户

将用户从本地移动到云时：

- 用户将成为 TeamsOnly 用户，这意味着用户：
   -  接收并启动 Teams 客户端中的所有聊天和呼叫。
   -  在 Teams 中安排所有会议。
   -  无法在Skype for Business中启动聊天或呼叫或安排会议。
   -  可以加入他们已拥有或将来接收的Skype for Business会议。 但是，在 Microsoft 删除给定 TeamsOnly 用户的 Skype for Business Online 基础结构后，TeamsOnly 用户只能匿名加入Skype for Business会议。 从 2022 年 10 月开始，仅在混合组织中从本地迁移到 Teams 的用户将不再使用 Skype for Business Online 基础结构进行预配。 如果邀请这些用户参加Skype for Business会议，则需要匿名加入。 有关详细信息，请参阅[具有本地部署Skype for Business Server的组织指南](/MicrosoftTeams/skype-for-business-online-retirement.md#guidance-for-organizations-with-on-premises-deployments-of-skype-for-business-server)。

- 用户已启用以实现与Skype for Business用户的互操作性，还可以与其他组织联合。
- 本地联系人将移动到 Teams。
- 他们今后安排的现有会议将转换为 Teams 会议。 会议迁移异步进行，大约在移动用户 90 分钟后开始。  若要确定会议迁移的状态，可使用 [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)。 不会移动在会议之前上传的任何内容。
- 分配有 Teams 电话许可证的用户在正确配置后可以访问 PSTN 功能。
 
若要将用户移动到 Teams，请使用Move-CsUser cmdlet 或Skype for Business 管理员 لوحة التحكم，这两者都是本地工具。 这些工具支持以下移动路径：

- [从本地Skype for Business Server () 到仅 Teams](move-users-from-on-premises-to-teams.md)。
- [从联机 (是否仅) Teams 到本地](move-users-from-the-cloud-to-on-premises.md)。


> [!NOTE] 
>  直接从本地移动到仅 Teams 的行为是自动的，无论使用哪个版本的 Skype for Business Server 或 Lync Server。 不再需要指定 `-MoveToTeams` 开关 `Move-CsUser` 才能将用户直接从本地移动到 TeamsOnly。 以前，如果未指定此开关，则用户将从本地Skype for Business Server主机转换为 Skype for Business Online，并且其模式保持不变。 现在，当用户从本地移动到云 `Move-CsUser`时，用户会自动分配 TeamsOnly 模式，并且他们的会议从本地自动转换为 Teams 会议，就像已指定交换机一样 `-MoveToTeams` ，而不管是否实际指定了开关。 


## <a name="required-administrative-credentials"></a>所需管理凭据

若要在本地和云之间移动用户，必须在本地Skype for Business Server环境中和 Teams 组织中使用具有足够权限的帐户。 可以使用一个具有所有必要权限的帐户，也可以使用两个帐户。 如果使用两个帐户，则使用本地凭据访问本地工具，然后在这些工具中，你将提供 Teams 管理帐户的其他凭据。  

- 在本地环境中，执行移动的用户必须在Skype for Business Server中具有 CSServerAdministrator、CsUserAdministrator 和 RTCUniversalUserAdmins 角色。
- 在 Teams 中，执行移动的用户必须至少是以下角色之一的成员：
  - 全局管理员角色
  - Teams 管理员角色
  - Skype for Business管理员角色。  

    > [!Important]
    > - 如果使用的是Skype for Business 管理员 لوحة التحكم，系统会提示你为具有相应角色的 Microsoft 365 帐户提供凭据，如上所述。 必须提供以 .onmicrosoft.com 结尾的帐户。 如果不可行，请使用Move-CsUser cmdlet。
    >- 如果在 PowerShell 中使用Move-CsUser，可以使用以 .onmicrosoft.com 结尾的帐户，也可以使用任何同步到 Azure AD 的本地帐户，前提是还可在 cmdlet 中指定 HostedMigrationOverrideUrl 参数。 托管迁移替代 URL 的值是以下 URL 的变体： https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>在上述 URL 中，将 XX 替换为两个或三个字符，确定如下所示：
    >   - 在 Teams PowerShell 会话中，运行以下 cmdlet：<br>`Get-CsTenant | ft ServiceInstance`
    >   - 生成的值将采用以下格式：<br>`MicrosoftCommunicationsOnline/YYYY-XX-ZZ`
    >   - 两个或三个字符的代码是 YYYY-XX-ZZ 部分中包含的 XX。 如果它是两个字符的代码，它将是一个数字，后跟数字 (如 4A) 。 如果是三个字符的代码，则为两个字母，后跟一个数字 (，如 JP1) 。 例如 NOAM-4A-S7。


## <a name="voice-configuration-requirements"></a>语音配置要求

如果在本地为企业语音配置了用户，则在将用户移动到联机时，需要协调更新其语音配置。 或者，可以迁移它们，而无需电话功能。 
- 可以更新用户的电话提供商以使用 [Microsoft 呼叫计划](/microsoftteams/calling-plans-for-office-365)。 这是一个选项，无论用户是使用 Teams 还是Skype for Business客户端。
- 可以继续使用本地 PSTN 提供程序：
  - 必须为将使用 Teams 的语音用户配置为 [直接路由](/microsoftteams/direct-routing-plan)。 直接路由仅在用户从本地移动到联机后才可用。

有关混合环境中的电话选项（包括可支持性矩阵）的详细信息，请参阅 [具有 PSTN 连接的混合环境中的用户帐户](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)。

## <a name="other-considerations"></a>其他注意事项

本地和联机环境中的策略（例如控制邮件、会议和呼叫行为）是各自独立的。 在将该用户从本地移动到云之前，可能需要考虑在环境中配置任何策略并将其分配给用户，以便在迁移到联机后立即获得正确的配置。

## <a name="see-also"></a>另请参阅

[将用户从本地移至团队](move-users-from-on-premises-to-teams.md)

[设置会议迁移服务 (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[规划直接路由](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
