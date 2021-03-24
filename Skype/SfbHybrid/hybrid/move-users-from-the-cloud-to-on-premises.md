---
title: 将用户从云移动到本地
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
description: 了解如何将用户从 Skype for Business Online 移动到本地。
ms.openlocfilehash: fdc8a8fb4e8e6cb1e2426b067aefbfa25e808171
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110608"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>将用户从云移动到本地 

如果需要，可以将之前从本地迁移的用户移动到云 (无论是使用 Skype for Business Online 还是仅 Teams) 迁移到本地。 若要将用户从 Skype for Business Online 或 TeamsOnly 模式移回 Skype for Business Server 本地部署，请使用 Move-CsUser cmdlet 或 Skype for Business Server 控制面板，这两者都是本地工具。 将用户移回本地部署时，必须决定将用户移动到哪个池。

> [!Important]
> 如果用户之前使用的是 TeamsOnly 模式，并且你使用的是低于 Skype for Business Server 2015 CU8 的早期版本，则还必须删除该用户的 TeamsUpgradePolicy 的 TeamsOnly 模式分配。 本地用户不能具有 mode= TeamsOnly。  后续版本的 Skype for Business Server 会自动删除此分配。 有关详细信息，请参阅 [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)。

## <a name="prerequisites"></a>先决条件

- 组织必须正确配置 Azure AD Connect，并同步用户的所有相关属性，如配置 [Azure AD Connect 中所述](configure-azure-ad-connect.md)。
- 从联机移回本地的用户必须已存在于本地 Active Directory 中。
- 必须配置 Skype for Business 混合，如配置 [Skype for Business 混合中所述](configure-federation-with-skype-for-business-online.md)。

## <a name="moving-users-back-to-on-premises"></a>将用户移回本地

将用户从云移回本地后：

- 用户与其功能的 Skype for Business Server 部署交互。 
- Skype for Business Online 或 Teams 中存在的任何联系人都迁移到 Skype for Business Server。 合并这两组联系人，然后迁移回本地。  此外，Teams 中预先存在的联系人仍保留在 Teams 中。
- 如果用户还使用 Teams，他们将不能与 Skype for Business 用户进行互操作，也无法与联盟组织的用户通信。
- Skype for Business Online 中的会议 *不会自动* 迁移回本地。 用户应重新安排其会议，或者使用会议迁移 [工具（如果需要](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)）。

### <a name="move-users-with-move-csuser"></a>使用迁移功能Move-CsUser

Move-CsUser本地 Skype for Business 命令行管理程序 PowerShell 窗口提供。 您必须在本地环境和云服务组织 (Microsoft 365 或 Office 365) 中拥有足够的权限，如所需的管理凭据[中所述。](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) 可以在两个环境中使用具有特权的单个帐户，或者可以使用本地凭据启动本地 Skype for Business Server 命令行管理程序窗口，并使用 参数指定具有所需 管理角色 的 `-Credential` Microsoft 365 或 Office 365 帐户的凭据。

若要使用 Move-CsUser 将用户移动到本地：

- 使用 Identity 参数指定要移动的用户。
- 使用将承载用户的所需本地池的完全限定域名指定 -Target 参数。
- 如果您没有一个在本地和云服务 (Microsoft 365 或 Office 365) 中具有足够权限的帐户，请使用 -credential 参数在 Microsoft 365 或 Office 365 中向帐户提供足够权限。
- 如果在 Microsoft 365 或 Office 365 中具有权限的帐户没有以"on.microsoft.com"结尾，则必须指定 -HostedMigrationOverrideUrl 参数，并指定正确的值，如[](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)所需的管理凭据中所述。

以下 cmdlet 序列可用于将用户移动到 Skype for Business Server，并假定 Microsoft 365 或 Office 365 凭据是一个单独的帐户，并作为 Get-Credential 提示的输入提供。

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板移动用户

1. 打开 Skype for Business Server 控制面板应用。
2. 在左侧导航栏中，选择"**用户"。**
3. 使用 **"** 查找"查找 (要) 回本地部署的用户。
4. Select the user (s) ， and then from the **Action** dropdown above the list， choose **Move selected users to on-premises**.
5. 在向导中，选择将承载用户的用户池，然后单击"下一步 **"。**
6. 如果系统提示，使用以 .onmicrosoft.com 结尾且具有足够权限的帐户登录到 Microsoft 365 或 Office 365。
7. 单击 **"下****一步**"，再单击"下一步"以移动用户。
8. 请注意，有关成功或失败的状态消息在主"控制面板"应用的顶部提供，而不是在向导中提供。

### <a name="removing-teamsonly-mode"></a>删除 TeamsOnly 模式

如果你使用的是早于 Skype for Business 2015 CU8 的版本，并且用户正在 TeamsOnly 模式下移回本地，则必须删除 的 UpgradeToTeams 实例，然后才能在本地移动 `TeamsUpgradePolicy` 用户。 你可以显式授予采用不同模式的策略，或者只需删除该用户的现有策略分配，以使用全局策略 (只要租户的全局策略不是 UpgradeToTeams) 。

若要删除用户的 TeamsUpgradePolicy 分配，请从 Skype for Business Online PowerShell 窗口运行以下 cmdlet：

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

或者，若要分配另一个没有 mode=TeamsOnly 的 TeamsUpgradePolicy 实例，可以在 cmdlet 中将所需实例的名称指定为 PolicyName 参数的值。 若要查看 TeamsUpgradePolicy 的可用实例列表，请运行 Get-CsTeamsUpgradePolicy。


## <a name="see-also"></a>另请参阅

[Move-CsUser](/powershell/module/skype/move-csuser)