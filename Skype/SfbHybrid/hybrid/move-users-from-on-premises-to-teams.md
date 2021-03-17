---
title: 将用户从 Skype for Business Server 2019 移动到 Teams
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
description: 摘要：了解如何迁移用户设置和将用户移动到 Teams。
ms.openlocfilehash: c84cdbe5f91816ddfabd476540e47f3d1871a427
ms.sourcegitcommit: 360c78c66386fe00afe535681f51254eda886edf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2021
ms.locfileid: "50836979"
---
# <a name="move-users-from-on-premises-to-teams"></a>将用户从本地移至团队

当用户从本地移动到仅 Teams 时，用户的 Skype for Business 主页从本地移动到联机，并且该用户分配有 mode=TeamsOnly 的 TeamsUpgradePolicy。  将用户从本地移动到 TeamsOnly 模式后：

- 来自其他用户的所有传入呼叫 (无论是从 Skype for Business 还是 Teams) 发送，都将登录用户的 Teams 客户端。
- 用户将能够与使用 Skype for Business 的其他用户进行互操作， (联机或本地部署) 。
- 用户将能够与联盟组织的用户通信。
- 该用户安排的新会议是 Teams 会议。
- 用户仍可加入任何 Skype for Business 会议。
- 为将来安排的用户预先存在的会议将从本地迁移到 Teams。
- 在用户首次登录后，Teams 中将可以使用本地存在的联系人。
- 用户无法从 Skype for Business 发起呼叫或聊天，也不能在 Skype for Business 中安排新会议。 如果他们尝试打开 Skype for Business 客户端，他们将被重定向为使用 Teams，如下所示。 如果未安装 Teams 客户端，他们将使用浏览器定向到 Teams 的 Web 版本。<br><br>
    ![将用户重定向到 Teams 的消息](../media/go-to-teams-page.png)

在移动任何用户之前，请务必查看 [将](move-users-between-on-premises-and-cloud.md#prerequisites) 用户迁移到云的先决条件。 此外，请务必查看适用于将 Teams 与 Skype for Business 一同使用的组织的 [迁移和互操作性指南](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。


> [!NOTE]
> 对于要移动到 Teams 的联系人，应禁用 On-prem SfB 帐户上的统一联系人存储。


有两种方法将用户从本地移动到 Teams：

- 如果你使用的是早于 Skype for Business Server 2015 CU8 的版本，则移动需要两个步骤 (如果需要，可以将脚本编写为一起作为单个步骤) ：
  - [将用户从本地 Skype for Business Server (移动到) Skype for Business Online。](move-users-from-on-premises-to-skype-for-business-online.md)
  - 用户位于 Skype for Business Online 中后，将用户 TeamsUpgradePolicy 与 mode= TeamsOnly 分配。 若要授予 TeamsOnly 模式，请从 Skype for Business Online PowerShell 窗口运行以下 cmdlet： `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- 如果你有来自 Skype for Business Server 2015 CU8 或更高版本的管理工具，可以使用上述方法，或者你可以执行如下所述的一个步骤中的移动。 此外，还可以选择在将 Skype for Business 客户端移动到"仅 Teams"之前在 Skype for Business 客户端中提供通知，也可以选择让 Skype for Business 客户端以静默方式下载 Teams 客户端。

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>将用户直接从本地 Skype for Business 移动到 Teams Only

Skype for Business Server 2015 CU8 以及 Skype for Business Server 2019 中的本地管理工具支持使用 PowerShell 中的 Move-CsUser cmdlet 或 Skype for Business Server 控制面板，在单个步骤中将用户从本地移动到仅 Teams 模式，如下所述。

### <a name="move-to-teams-using-move-csuser"></a>使用"迁移"功能Move-CsUser

Move-CsUser本地 Skype for Business 命令行管理程序 PowerShell 窗口提供。 以下步骤和所需的权限与将用户移动到 Skype for Business Online 相同，除了还必须指定 MoveToTeams 开关，并且必须确保除了 Skype for Business Online) 之外，用户还被授予了 Teams (的许可证。

你必须在本地环境和云服务 (Microsoft 365 或 Office 365) 拥有足够的权限，如所需的管理凭据 [中所述](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。 可以在两个环境中使用具有特权的单个帐户，或者可以使用本地凭据启动本地 Skype for Business Server 命令行管理程序窗口，并使用 参数指定具有所需 管理角色 的 `-Credential` Microsoft 365 或 Office 365 帐户的凭据。

若要使用 Move-CsUser 将用户移动到仅 Teams 模式：

- 使用 参数指定要移动 `Identity` 的用户。
- 使用值"sipfed.online.lync"指定 -Target 参数。 <span>com"。
- 指定 `MoveToTeams` 开关。
- 如果您没有一个在本地和云服务 (Microsoft 365 或 Office 365) 中具有足够权限的帐户，请使用 参数在 Office 365 中为帐户提供足够权限。 `-credential`
- 如果在 Microsoft 365 或 Office 365 中具有权限的帐户没有以"onmicrosoft"结尾。 <span>com"，必须指定 参数，并指定正确的 `-HostedMigrationOverrideUrl` 值，如所需的管理 [凭据 中所述](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。

以下 cmdlet 序列可用于将用户移动到 TeamsOnly，并假定 Microsoft 365 或 Office 365 凭据是一个单独的帐户，并作为 Get-Credential 提示的输入提供。

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> 由于存在需要不同参数的不同情况，因此大多数情况下的默认命令是：

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板移动到 Teams

1. 打开 Skype for Business Server 控制面板应用。
2. 在左侧导航栏中，选择"**用户"。**
3. 使用 **"** 查找"查找 (要) Teams 的用户。
4. Select the user (the) ， and then， from the **Action** dropdown above the list， choose **Move selected users to Teams**.
5. 在向导中，单击“下一步”。
6. 如果系统提示，使用以 .onmicrosoft.com 结尾且具有足够权限的帐户登录到 Microsoft 365 或 Office 365。
7. 单击 **"下****一步**"，再单击"下一步"以移动用户。
8. 请注意，有关成功或失败的状态消息在主"控制面板"应用的顶部提供，而不是在向导中提供。

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>通知 Skype for Business 本地用户即将移动到 Teams

Skype for Business Server 2015 CU8 以及 Skype for Business Server 2019 中的本地管理工具让你能够通知本地 Skype for Business 用户他们即将移动到 Teams。 当你启用这些通知时，用户将在 Skype for Business 客户端 (Win32、Mac、Web 和移动) 通知，如下所示。 如果用户单击" **试用"** 按钮，则 Teams 客户端将在安装后启动;否则，用户将在浏览器中导航到 Teams 的 Web 版本。 默认情况下，当启用通知时，Win32 Skype for Business 客户端会以静默方式下载 Teams 客户端，以便丰富客户端在将用户移动到"仅 Teams"模式之前可用;但是，您也可以禁用此行为。  通知使用 本地版本进行配置，Win32 客户端的无提示下载通过 `TeamsUpgradePolicy` 本地 `TeamsUpgradeConfiguration` cmdlet 控制。

> [!TIP]
> 某些服务器可能需要重新启动才能在 Skype for Business 2015 CU8 中运行。

![有关即将移动到 Teams 的通知](../media/teams-upgrade-notification.png)

若要通知本地用户他们即将升级到 Teams，请创建一个使用 NotifySfBUsers=true 的 TeamsUpgradePolicy 新实例。 然后，通过直接向用户分配策略或在站点、池或全局级别设置策略，将策略分配给要通知的用户。 以下 cmdlet 可创建并授予用户级别的策略：

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

通过 Skype for Business Win32 客户端自动下载 Teams 通过具有 DownloadTeams 参数的本地 TeamsUpgradeConfiguration cmdlet 进行控制。 您可以在全局、站点和池级别创建此配置。 例如，以下命令为站点 Redmond1 创建配置：

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

默认情况下，DownloadTeams 的值为 True;但是，只有当给定 *用户的* NotifySfbUser = True 时，才遵守此要求。

## <a name="see-also"></a>另请参阅

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[与 Skype for Business 共存](/microsoftteams/coexistence-chat-calls-presence)
