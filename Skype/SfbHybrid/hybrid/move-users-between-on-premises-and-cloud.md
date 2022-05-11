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
ms.openlocfilehash: 15e237fdf54854a86216bc3890ae26209449c146
ms.sourcegitcommit: d847256fca80e4e8954f767863c880dc8472ca04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2022
ms.locfileid: "65304000"
---
# <a name="move-users-between-on-premises-and-cloud"></a>在本地与云之间移动用户

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

在为混合启用Skype for Business Server的本地部署中，可以在本地环境和Teams之间移动用户。 无论用户位于本地还是在云中，均称为用户的 Skype for Business 主页：

- 本地用户与本地Skype for Business服务器交互。
- 联机用户可以与Teams服务交互。

*Teams用户本身就有一个Skype for Business家庭，无论他们是否使用Skype for Business。* 如果本地Skype for Business用户也并行使用Teams () ，则这些用户位于本地。 Teams本地有Skype for Business的用户无法与其Teams客户端中的Skype for Business用户进行互操作，也无法从Teams与联合组织中的用户进行通信。 仅当用户从本地Skype for Business移动到联机并创建 TeamsOnly 后，此类功能才完全可用。 建议将用户移动到 TeamsOnly 模式，以确保所有传入聊天和呼叫的路由都位于其Teams客户端中。 有关详细信息，请参阅[Teams与Skype for Business和迁移共存](/microsoftteams/coexistence-chat-calls-presence)，[以及组织使用Teams和Skype for Business的互操作性指南](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。

## <a name="prerequisites"></a>先决条件

将用户移到 TeamsOnly 模式的先决条件：

- 组织必须正确配置 Azure AD 连接并同步用户的所有相关属性，如配置 [Azure AD 连接](configure-azure-ad-connect.md) 中所述。
- Skype for Business必须配置混合，如配置[混合](configure-federation-with-skype-for-business-online.md)Skype for Business中所述。
- 必须为用户分配Teams和Skype for Business联机 (计划 2) 的许可证。 即使在Skype for Business联机停用后，仍需要Skype for Business联机许可证。  此外：
    - 如果用户已启用本地电话拨入式会议，则用户还必须在Teams中分配音频会议许可证，然后才能将用户联机移动。 迁移到云后，将在云中为用户预配音频会议。 
    - 如果用户已启用本地企业语音，则用户必须在Teams中分配电话系统许可证，然后才能将用户联机移动。 迁移到云后，将为用户预配云中的电话系统。 


## <a name="moving-users"></a>移动用户

将用户从本地移动到云时：

- Teams用户启用了与Skype for Business用户的互操作性，如果用户是 TeamsOnly，他们也可以与其他组织联合。

- 本地联系人将移至Teams。

- 他们今后安排的现有会议将转换为Teams会议。 会议迁移异步进行，大约在移动用户 90 分钟后开始。  若要确定会议迁移的状态，可使用 [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)。 不会移动在会议之前上传的任何内容。

若要将用户移到Teams，请使用Move-CsUser cmdlet 或Skype for Business管理员控制面板，这两者都是本地工具。 这些工具支持以下移动路径：

- [从本地Skype for Business Server (直接) 到仅Teams](move-users-from-on-premises-to-teams.md)。  直接从本地移动到Teams的行为现在是自动的，无论使用哪个版本的Skype for Business Server或 Lync Server。 不再需要指定 `-MoveToTeams` 开关来获取此行为。  
- [从联机 (是否仅Teams) ，到本地](move-users-from-the-cloud-to-on-premises.md)。

> [!NOTE] 
> 不再需要在Move-CsUser中指定 -MoveToTeams 开关，以便将用户直接从本地移动到 TeamsOnly。 以前，如果未指定此开关，则用户将从本地Skype for Business Server主机转换为 Skype for Business Online，并且其模式保持不变。 现在，当使用 Move-CsUser 将用户从本地移动到云时，用户会自动分配 TeamsOnly 模式，并且从本地的会议会自动转换为Teams会议，就像已指定开关一样`-MoveToTeams`，而不管是否实际指定了开关。 
> 

## <a name="required-administrative-credentials"></a>所需管理凭据

若要在本地和云之间移动用户，必须在本地Skype for Business Server环境中和Teams组织中使用具有足够权限的帐户。 可以使用一个具有所有必要权限的帐户，也可以使用两个帐户。 如果使用两个帐户，则可以使用本地凭据访问本地工具，然后在这些工具中，为Teams管理帐户提供其他凭据。  

- 在本地环境中，执行移动的用户必须在Skype for Business Server中具有 CSServerAdministrator、CsUserAdministrator 和 RTCUniversalUserAdmins 角色。
- 在Teams中，执行移动的用户必须至少是以下角色之一的成员：
  - 全局管理员角色
  - Teams管理员角色
  - Skype for Business管理员角色。  

    > [!Important]
    > - 如果使用Skype for Business管理员控制面板，系统将提示你为具有相应角色的Microsoft 365帐户提供凭据，如上所述。 必须提供以 .onmicrosoft.com 结尾的帐户。 如果不可行，请使用Move-CsUser cmdlet。
    >- 如果在 PowerShell 中使用Move-CsUser，可以使用以 .onmicrosoft.com 结尾的帐户，也可以使用任何同步到 Azure AD 的本地帐户，前提是还可在 cmdlet 中指定 HostedMigrationOverrideUrl 参数。 托管迁移替代 URL 的值是以下 URL 的变体： https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>在上述 URL 中，将 XX 替换为两个或三个字符，确定如下所示：
    >   - 在 Teams PowerShell 会话中，运行以下 cmdlet：<br>`Get-CsTenant | ft ServiceInstance`
    >   - 生成的值将采用以下格式：<br>`MicrosoftCommunicationsOnline/YYYY-XX-ZZ`
    >   - 两个或三个字符的代码是 YYYY-XX-ZZ 部分中包含的 XX。 如果它是两个字符的代码，它将是一个数字，后跟数字 (如 4A) 。 如果是三个字符的代码，则为两个字母，后跟一个数字 (，如 JP1) 。 例如 NOAM-4A-S7。


## <a name="voice-configuration-requirements"></a>语音配置要求

如果在本地为企业语音配置了用户，则在将用户移动到联机时，需要协调更新其语音配置。 或者，可以迁移它们，而无需电话功能。 可用选项取决于用户在联机后是使用Teams还是Skype for Business客户端：

- 可以更新用户的电话提供商以使用 [Microsoft 呼叫计划](/microsoftteams/calling-plans-for-office-365)。 这是一个选项，无论用户是使用Teams还是Skype for Business客户端。
- 可以继续使用本地 PSTN 提供程序：
  - 必须为将使用Teams的语音用户配置为[直接路由](/microsoftteams/direct-routing-plan)。 直接路由仅在用户从本地移动到联机后才可用。
  - 在将Skype for Business客户端移动到联机后将使用该客户端的语音用户必须配置为Skype for Business 混合语音功能。

有关混合环境中的电话选项（包括可支持性矩阵）的详细信息，请参阅 [具有 PSTN 连接的混合环境中的用户帐户](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)。

## <a name="other-considerations"></a>其他注意事项

本地和联机环境中的策略（例如控制邮件、会议和呼叫行为）是各自独立的。 在将该用户从本地移动到云之前，可能需要考虑在环境中配置任何策略并将其分配给用户，以便在迁移到联机后立即获得正确的配置。

## <a name="see-also"></a>另请参阅

[将用户从本地移至团队](move-users-from-on-premises-to-teams.md)

[设置会议迁移服务 (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[规划直接路由](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
