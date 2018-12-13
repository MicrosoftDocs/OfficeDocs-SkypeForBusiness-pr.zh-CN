---
title: 内部部署和云之间移动用户
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 摘要： 在业务服务器为混合启用的 Skype 的本地部署中，您可以将用户移动之间的内部部署环境和云 （是否向 Microsoft 工作组或业务 online Skype）.
ms.openlocfilehash: 492a2a7d14af77bc0b90afe03f0d36de0f830129
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247626"
---
# <a name="move-users-between-on-premises-and-cloud"></a>内部部署和云之间移动用户

在启用了混合的业务服务器的 Skype 的本地部署中，可以将用户移动之间的内部部署环境和云 （是否向 Microsoft 工作组或业务 online Skype）。 指示用户是否位于内部部署或云中称为业务主页中的用户的 Skype:

- 用户驻留在本地与业务服务器的内部部署 Skype 进行交互。
- 联机驻留用户可能交互 Skype 业务联机服务。

*团队用户本质上是具有商业主页 Skype，无论他们 Skype for Business 使用。* 如果您有还使用团队 （并行） 的业务用户的内部部署 Skype，这些用户都驻留在本地。 与 Skype 的本地业务团队用户没有能够与 Skype 互操作的业务用户从其团队客户端，也可以它们沟通团队与联盟组织中的用户。 移动该用户是从 for Business 的 Skype 本地到 online 之后，此类功能才可用。 当用户移动到 online 时，您可以允许他们 Skype 用于业务联机 （和 （可选） 团队） 或可使其仅团队。 如果您的组织已使用团队，强烈建议您将它们移动到团队仅模式，这将确保其团队客户端中到达的所有传入的聊天和呼叫路由的。 有关详细信息，请参阅[与 for Business 的 Skype 团队共存](/microsoftteams/coexistence-chat-calls-presence)和[迁移和组织使用团队一起 for Business 的 Skype 的互操作性指南](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。

## <a name="prerequisites"></a>先决条件

若要将用户移至云 （是否仅业务或团队仅模式的 Skype） 的先决条件：

- 组织必须具有正确的 Azure AD 连接，并且同步的用户的所有相关属性[配置 Azure AD 连接](configure-azure-ad-connect.md)中所述。
- 必须配置为业务混合的 Skype，[业务混合配置 Skype](configure-federation-with-skype-for-business-online.md)中所述。
- 必须为用户分配许可证的 Skype 业务 online (计划 2)，并且如果他们将使用团队，它们必须还具有团队许可证。  另外：
    - 如果用户启用了电话拨入式会议中在本地，默认情况下，用户还必须具有运行之前分配 Office 365 中的音频会议许可证联机移动用户。 一旦迁移到云中，将在云中的音频会议设置的用户。 如果由于某种原因，您想要将用户移动到云，但不是使用音频会议功能，您可以通过指定覆盖此检查`BypassAudioConferencingCheck`中的参数`Move-CsUser`。
    - 如果在本地的企业语音启用用户，则默认情况下用户必须具有之前联机移动用户分配 Office 365 中的电话系统许可证。 一次已迁移到云中，用户将在云中的电话系统的设置。 如果由于某种原因，您想要将用户移动到云，但不要使用电话系统的功能，您可以通过指定覆盖此检查`BypassEnterpriseVoiceCheck`中的参数`Move-CsUser`。


## <a name="moving-users"></a>移动用户

当用户是从内部部署移到云中：

- 用户启动 Skype 云中的业务联机服务用于任何 Skype 业务功能。
- 团队成为为用户启用的互操作性与 Skype 业务用户，他们还可以与其他组织进行联盟。
- 从本地的联系人将移动到云 (for Business 的 Skype) 或团队。
- 这些组织的现有将来安排的会议都将迁移到 online。 会议的迁移异步发生的情况，并开始大约 90 分钟后将用户移动。  若要确定会议迁移的状态，可以使用[Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)。 请注意，也不会移动会议前已上载的任何内容。

若要在部署和云 （是否向工作组或业务 online Skype） 移动之间移动用户，用于业务管理 Control Panel Move-csuser cmdlet 或 Skype，这两种是内部部署工具。 这些工具支持三个不同的移动路径：

- [从 Skype 的业务业务 online Skype （本地） 服务器](move-users-from-on-premises-to-skype-for-business-online.md)。
- [用于业务服务器 （本地） 到团队仅直接从 Skype](move-users-from-on-premises-to-teams.md)（其中还将它们移动到 Skype 业务 online）。  在本地到团队仅直接从移动的选项位于业务服务器 2019年的 Skype 以及业务服务器 2015年的 Skype 的累积更新 8。 使用 for Business Server 的早期版本的 Skype 的组织可以将用户移动到团队仅通过第一个将其移至 Skype 业务 online 联机后，然后向这些用户应用 TeamsOnly 模式。
- [从 online (是否工作组只有或不)，以本地](move-users-from-the-cloud-to-on-premises.md)。

## <a name="required-administrative-credentials"></a>所需的管理凭据

要移动上部署和云之间移动用户，您必须使用的帐户具有足够权限在这两个本地 Skype 业务服务器环境以及 Office 365 租户。 您可以使用一个帐户具有所需的所有权限，或您可以使用两个帐户、 将访问这种情况下使用的内部部署工具部署凭据，然后这些工具中要提供其他凭据的 Office 365管理帐户。  

- 在内部部署环境中，执行移动的用户必须具有业务服务器的 Skype 的 CSServerAdminstrator 角色。
- 在 Office 365 中，执行移动用户必须是全局管理员或它必须具有两个 Skype 业务管理员和用户管理员角色。  

    > [!Important]
    > - 如果您使用 Skype 业务管理控制面板，将提示您提供凭据的 Office 365 帐户具有适当的角色，上面所述。 提供在结束的帐户必须。 onmicrosoft.com。 如果这是不可能的则使用 Move-csuser cmdlet。
    >- 如果您在 PowerShell 中使用 Move-csuser，您可以使用结束中的帐户。 onmicrosoft.com，也可以使用任何同步到 Azure AD 的本地帐户，假设您指定 cmdlet HostedMigrationOverrideUrl 参数. 托管的迁移覆盖 URL 的值是 variant 类型的以下 URL:https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>在上面的 URL 中，替换两个或三个字符，按以下方式确定 XX:
    >   - 在业务 Online PowerShell 会话 Skype，运行以下 cmdlet:<br>`Get-CsTenant|ft identity`
    >    - 生成的值将为以下格式：<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - 两个或三个数字代码是 XX 包含在部分中，DC = lyncXX001。 如果是两个字符代码，它将为跟一个数字 （例如 0a) 的数字。 如果是三个字符代码，将两个字母后跟一个以数字 （例如 jp1)。 在所有情况下，您将看到 XX 代码后立即 001。


## <a name="voice-configuration-requirements"></a>语音配置要求

如果在本地的企业语音配置用户，您需要协调更新其语音配置时将它们移动到联机状态，或者，或者，您无法将其迁移不带电话功能。 可用的选项取决于是否用户将使用的团队或 Skype for Business 客户端后联机：

- 您可以更新用户的电话服务提供程序以使用[Microsoft 调用规划](/microsoftteams/calling-plans-for-office-365)。 用户将业务客户端使用团队或 Skype 是否，这是一个选项。
- 您可以继续使用在本地 PSTN 提供商：
  - 语音用户将使用团队必须配置为[在直接路由](/microsoftteams/direct-routing-plan)。 移动该用户是从本地到 online 之后，直接路由才可用。
  - 将用于 Skype 业务客户端后联机移动语音用户必须为配置 Skype 业务混合语音功能。

有关混合环境，以及可支持性矩阵中的电话选项的详细信息，请参阅[使用 PSTN 连接的混合环境中的用户帐户](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)。

## <a name="other-considerations"></a>其他考虑事项

策略 （例如要控制消息、 会议，并调用行为） 环境中的本地和联机是独立的。 您可能要考虑环境中配置的任何策略以及将其分配给用户之前该用户从内部部署迁移到云，以便为迁移到 online 具有正确的配置。

## <a name="see-also"></a>另请参阅

[将用户从本地迁移至 Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md)

[将用户从内部部署移动到团队](move-users-from-on-premises-to-teams.md)

[设置会议迁移服务 (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[规划直接路由](/microsoftteams/direct-routing-plan)

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)