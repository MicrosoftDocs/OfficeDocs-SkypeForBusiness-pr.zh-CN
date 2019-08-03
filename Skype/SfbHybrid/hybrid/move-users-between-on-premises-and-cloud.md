---
title: 在内部部署和云之间移动用户
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
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
description: '摘要: 在启用了混合的 Skype for Business Server 的本地部署中, 可以在本地环境和云 (无论是 Microsoft 团队还是 Skype for Business Online) 之间移动用户。。'
ms.openlocfilehash: b7e3ecc46af5a3043848d9291394c0bff7835883
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160438"
---
# <a name="move-users-between-on-premises-and-cloud"></a>在内部部署和云之间移动用户

在启用了混合使用的 Skype for business Server 的本地部署中, 可以在本地环境和云 (无论是 Microsoft 团队还是 Skype for business Online) 之间移动用户。 用户是否位于本地或在云中称为用户的 Skype for Business 主页:

- 驻留在本地的用户与本地 Skype for Business 服务器交互。
- 联机托管的用户可能与 Skype for Business Online 服务进行交互。

*团队用户本身拥有 Skype for business 主页, 无论他们使用的是 Skype for Business 还是不是。* 如果您有本地 Skype for Business 用户, 并且这些用户也使用团队 (并排), 这些用户将驻留在本地。 在本地使用 Skype for business 的团队用户不能与来自团队客户端的 Skype for business 用户进行互操作, 也不能与联合组织中的用户在团队之间进行通信。 此类功能仅在用户从 Skype for Business 从本地迁移到联机后才可用。 当您将用户移动到联机状态时, 您可以允许他们使用 Skype for Business Online (也可以是团队), 也可以仅使其成为团队。 如果您的组织已在使用团队, 则强烈建议您将其移动到 "仅团队" 模式, 这将确保将所有传入聊天和呼叫的路由放在其团队客户端中。 有关更多详细信息, 请参阅与 skype for Business 共存的团队以及与 Skype for business 一起使用团队的组织与[skype For business](/microsoftteams/coexistence-chat-calls-presence)的[迁移和互操作性指导](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。

## <a name="prerequisites"></a>先决条件

将用户迁移到云的先决条件 (是仅适用于 Skype for business 还是仅限团队模式):

- 组织必须正确配置 Azure AD Connect, 并按照[Configure AZURE AD Connect](configure-azure-ad-connect.md)中所述, 同步用户的所有相关属性。
- 必须配置 skype for Business 混合, 如[配置 skype For business 混合](configure-federation-with-skype-for-business-online.md)中所述。
- 必须为用户分配 Skype for business Online 的许可证 (计划 2), 如果他们使用的是团队, 则还必须具有团队许可证。  此外：
    - 如果用户在本地启用了电话拨入式会议, 默认情况下, 在运行 "移动用户" 联机之前, 用户还必须具有在 Office 365 中分配的音频会议许可证。 迁移到云后, 用户将在云中为音频会议进行预配。 如果由于某种原因需要将用户移动到云, 但不使用音频会议功能, 则可以通过在中`BypassAudioConferencingCheck` `Move-CsUser`指定参数来覆盖此检查。
    - 如果用户在本地启用了企业语音, 则默认情况下, 用户必须具有在 Office 365 中分配的电话系统许可证, 然后才能将用户联机。 迁移到云后, 用户将为云中的电话系统进行预配。 如果出于某种原因您想要将用户移动到云, 但不使用电话系统功能, 则可以通过在中`BypassEnterpriseVoiceCheck` `Move-CsUser`指定参数来覆盖此检查。


## <a name="moving-users"></a>移动用户

将用户从本地移动到云时:

- 用户开始使用云中的 Skype for Business Online 服务获取任何 Skype for Business 功能。
- 团队用户将启用与 Skype for Business 用户的互操作性, 也可以与其他组织联盟。
- 来自本地的联系人将移至云 (Skype for Business 或团队)。
- 将将来安排的现有会议迁移到 "联机": 如果用户直接移动到 TeamsOnly (如下所示), 则会议将转换为团队会议, 否则会议仍保持 Skype for Business, 但会进行迁移, 以供托管在线而不是本地部署。  会议的迁移异步发生, 并在移动用户大约90分钟后开始。  若要确定会议迁移的状态, 您可以使用[csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)。 请注意, 会议提前上传的任何内容都不会移动。

若要在内部部署和云 (无论是团队还是 Skype for business Online) 之间移动用户, 请使用 Get-csuser cmdlet 或 Skype for business 管理控制面板, 这两个都是本地工具。 这些工具支持三种不同的移动路径:

- [从 skype For Business Server (本地) 到 skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md)。
- [从 Skype For Business Server (仅限内部部署) 直接向团队成员](move-users-from-on-premises-to-teams.md)(这也会将它们移动到 Skype for Business Online)。  在 Skype for business Server 2019 和 Skype for business Server 2015 的累积更新8中, 直接从本地移动到团队的选项是可用的。 使用早期版本的 Skype for Business Server 的组织仅可以通过先将用户移动到 Skype for Business Online, 然后在这些用户联机时应用 TeamsOnly 模式, 从而将用户移动到这些团队。
- [从联机 (只是团队) 到本地](move-users-from-the-cloud-to-on-premises.md)。

## <a name="required-administrative-credentials"></a>所需的管理凭据

若要在本地和云之间移动用户, 必须在本地 Skype for Business Server 环境以及 Office 365 租户中使用具有足够权限的帐户。 您可以使用一个具有所有必要权限的帐户, 也可以使用两个帐户, 在这种情况下, 您将使用本地凭据访问本地工具, 然后在这些工具中, 将为 Office 365 提供其他凭据管理帐户。  

- 在本地环境中, 执行移动的用户必须具有 Skype for Business Server 中的 CSServerAdminstrator 角色。
- 在 Office 365 中, 执行移动的用户必须是全局管理员, 或者必须具有 Skype for Business 管理员和用户管理员角色。  

    > [!Important]
    > - 如果使用的是 Skype for Business 管理员控制面板, 系统将提示你提供具有适当角色的 Office 365 帐户凭据, 如上文所述。 您必须提供以. onmicrosoft.com 结尾的帐户。 如果不可能, 请使用 Get-csuser cmdlet。
    >- 如果您在 PowerShell 中使用 Get-csuser, 则可以使用以. onmicrosoft.com 结尾的帐户, 也可以使用任何已同步到 Azure AD 的内部部署帐户, 前提是您还在 cmdlet 中指定 HostedMigrationOverrideUrl 参数. 托管迁移替代 URL 的值是以下 URL 的变体:https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>在上面的 URL 中, 将 XX 替换为两个或三个字符, 按如下所示进行确定:
    >   - 在 Skype for Business Online PowerShell 会话中, 运行以下 cmdlet:<br>`Get-CsTenant|ft identity`
    >    - 结果值将采用以下格式:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - 两位或三位代码是包含在内容 DC = lyncXX001 中的 XX。 如果它是一个双字符代码, 则它将是一个数字, 后跟一个数字 (如 0a)。 如果是由三个字符组成的代码, 则它将是两个字母后跟一个数字 (如 jp1)。 在所有情况下, 都将在 XX 代码之后立即看到001。


## <a name="voice-configuration-requirements"></a>语音配置要求

如果在内部部署中为用户配置了企业语音, 则需要在将其移动到联机时协调更新其语音配置, 或者, 或者, 也可以在没有电话功能的情况下迁移这些用户。 可用的选项取决于用户在线时使用的是团队还是 Skype for business 客户端:

- 您可以更新用户的电话服务提供商, 以使用[Microsoft 通话套餐](/microsoftteams/calling-plans-for-office-365)。 无论用户是使用团队还是 Skype for Business 客户端, 都可以选择此选项。
- 您可以继续使用本地 PSTN 提供程序:
  - 必须为要使用团队的语音用户配置[直接路由](/microsoftteams/direct-routing-plan)。 仅在用户从本地移动到联机状态后, 直接路由才可用。
  - 在联机移动后将使用 Skype for business 客户端的语音用户必须为 Skype for business 混合语音功能进行配置。

有关混合环境中的电话服务选项以及可支持性矩阵的更多详细信息, 请参阅[具有 PSTN 连接的混合环境中的用户帐户](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)。

## <a name="other-considerations"></a>其他注意事项

内部部署和联机环境中的策略 (例如控制邮件、会议和呼叫行为) 是独立的。 您可能需要考虑在环境中配置任何策略并将其分配给用户, 然后再将该用户从本地迁移到云, 这样在将其迁移到联机状态时, 他们就可以正确配置它们。

## <a name="see-also"></a>另请参阅

[将用户从本地迁移到 Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md)

[将用户从本地移动到团队](move-users-from-on-premises-to-teams.md)

[设置会议迁移服务 (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[规划直接路由](/microsoftteams/direct-routing-plan)

[移动-Get-csuser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
