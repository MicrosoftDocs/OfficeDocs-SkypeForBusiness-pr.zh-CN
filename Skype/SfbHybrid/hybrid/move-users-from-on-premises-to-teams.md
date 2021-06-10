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
description: 摘要：了解如何迁移用户设置以及将用户移动到Teams。
ms.openlocfilehash: b9b21dafc2290dfff5522f5d54c0872121294dd9
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856301"
---
# <a name="move-users-from-on-premises-to-teams"></a>将用户从本地移至团队

当用户从本地移动到 Teams Only 时，用户的 Skype for Business 家庭版从本地移动到联机，并且为该用户分配 TeamsUpgradePolicy mode=TeamsOnly。  将用户从本地移动到 TeamsOnly 模式后：

- 来自其他用户的所有传入呼叫 (无论是从 Skype for Business 还是 Teams) 发送，都将进入用户的 Teams 客户端。
- 用户将能够与联机或本地部署Skype for Business (其他用户进行) 。
- 用户将能够与联盟组织的用户通信。
- 该用户安排的新会议将Teams会议。
- 用户仍可加入任何Skype for Business会议。
- 为将来安排的用户预先存在的会议将从本地迁移到Teams。
- 本地存在的联系人在用户首次登录Teams在用户登录后的不久内可用。
- 用户无法从会议发起Skype for Business聊天，也无法在 Skype for Business 中安排新Skype for Business。 如果他们尝试打开 Skype for Business 客户端，他们将被重定向以使用Teams如下所示。 如果未Teams客户端，它们将被定向到 web 版本的 Teams使用其浏览器。<br><br>
    ![将用户重定向到用户Teams](../media/go-to-teams-page.png)

在移动任何用户之前，请务必查看 [将](move-users-between-on-premises-and-cloud.md#prerequisites) 用户迁移到云的先决条件。 此外，请务必查看迁移和互操作性指南，以指导组织将 Teams 与 Skype for Business 一[Skype for Business。](/microsoftteams/migration-interop-guidance-for-teams-with-skype)


> [!NOTE]
> 应禁用统一联系人存储，以将联系人移动到统一联系人Teams。

> [!IMPORTANT]
>使用 Move-CsUser 将用户从本地迁移到云时，现在会自动为用户分配 TeamsOnly 模式，其从本地会议将自动转换为 Teams 会议，而不管是否实际指定了切换。 `-MoveToTeams`  (这包括从 Lync Server 2013 迁移，Lync Server 2013 从未具有 switch.) 如果未指定此开关，则用户从本地 Skype for Business Server 迁移到 Skype for Business Online，其模式保持不变。 `-MoveToTeams` 最近进行了更改，以准备停用 Skype for Business Online。


## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>将用户直接从本地Skype for Business移动到仅Teams

Skype for Business Server 和 Lync Server 2013 中的本地管理工具使您能够使用 PowerShell 中的 Move-CsUser cmdlet 或 Skype for Business Server 控制面板，在单个步骤中将用户从本地移动到 TeamsOnly 模式，如下所述。 不再需要指定开关以及直接从内部部署移动到 Teams 现在，无论使用哪个版本的 Skype for Business Server 或 Lync Server，都自动执行 Only `-MoveToTeams` 操作。 

您必须具有本地环境和云服务或 (Microsoft 365 或 Office 365) 的足够权限，如所需的管理[凭据 中所述](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。 您可以使用在两个环境中具有特权的单个帐户，或者可以使用本地凭据启动本地 Skype for Business Server 命令行管理程序窗口，并使用 参数指定具有所需 管理角色 Microsoft 365 的凭据。 `-Credential`

此外，必须确保用户已被授予 Teams (许可证，Skype for Business Online) 。 不要禁用 Skype for Business Online 许可证。

### <a name="move-to-teams-using-move-csuser"></a>使用Teams移动到Move-CsUser

Move-CsUser可从本地命令行管理程序 PowerShell Skype for Business Server Lync Server 命令行管理程序 PowerShell 窗口访问。 若要使用 Move-CsUser 将用户移动到 TeamsOnly 模式：
- 使用 参数指定要移动 `Identity` 的用户。
- 指定 `-Target` 值为"sipfed.online.lync"的参数。 <span>com"。
- 如果您没有一个在本地和云服务 (Microsoft 365) 中具有足够权限的帐户，请使用 参数在 Microsoft 365 中为帐户 `-credential` 提供足够权限。
- 如果具有权限的帐户Microsoft 365以"onmicrosoft"结尾。 <span>com"，必须指定 参数，并指定正确的 `-HostedMigrationOverrideUrl` 值，如所需的管理[凭据 中所述](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。

以下 cmdlet 序列可用于将用户移动到 TeamsOnly，并假定 Microsoft 365 凭据是一个单独的帐户，并作为 Get-Credential 提示的输入提供。 无论指定开关还是不 `-MoveToTeams` 指定开关，行为都是相同的。

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> 由于存在需要不同参数的不同情况，因此大多数情况下的默认命令是：

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>使用Teams控制面板Skype for Business Server移动到

1. 打开Skype for Business Server控制面板"应用。
2. 在左侧导航栏中，选择"**用户"。**
3. 使用 **"** 查找"查找 (要) 用户的位置Teams。
4. Select the user (s) ， and then， from the **Action** dropdown above the list， choose **Move selected users to Teams** or Move selected users to Skype for Business **Online**.   任一选项现在都直接将用户移动到 TeamsOnly。
5. 在向导中，单击“下一步”。
6. 如果系统提示，请Microsoft 365以 .onmicrosoft.com 结尾且具有足够权限的帐户登录。
7. 单击 **"下****一步**"，再单击"下一步"以移动用户。
8. 请注意，有关成功或失败的状态消息在主"控制面板"应用的顶部提供，而不是在向导中提供。
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>通知Skype for Business本地用户即将移动到Teams

Skype for Business Server 2015 CU8 和 Skype for Business Server 2019 中的本地管理工具让你能够通知本地 Skype for Business 用户他们即将移动到 Teams。 当你启用这些通知时，用户将看到其 Skype for Business 客户端 (Win32、Mac、Web 和移动) 通知，如下所示。 如果用户单击"**试用**"按钮，Teams客户端将启动（如果已安装）;否则，用户将在浏览器中导航到 Teams Web 版本。 默认情况下，当启用通知时，Win32 Skype for Business客户端会以静默方式下载 Teams 客户端，以便丰富客户端在将用户移动到 TeamsOnly 模式之前可用;但是，您也可以禁用此行为。  通知使用 本地版本进行配置，Win32 客户端的无提示下载通过 `TeamsUpgradePolicy` 本地 `TeamsUpgradeConfiguration` cmdlet 控制。

> [!TIP]
> 某些服务器可能需要重新启动才能在 2015 CU8 Skype for Business中工作。

![有关即将移动到 Teams](../media/teams-upgrade-notification.png)

若要通知本地用户他们即将升级到 Teams，请创建一个 NotifySfBUsers=true 的 TeamsUpgradePolicy 新实例。 然后，通过直接向用户分配策略或在站点、池或全局级别设置策略，将策略分配给要通知的用户。 以下 cmdlet 可创建并授予用户级别的策略：

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

通过 win32 Teams自动下载Skype for Business通过具有 DownloadTeams 参数的本地 TeamsUpgradeConfiguration cmdlet 进行控制。 您可以在全局、站点和池级别创建此配置。 例如，以下命令为站点 Redmond1 创建配置：

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

默认情况下，DownloadTeams 的值为 True;但是，只有当给定 *用户的* NotifySfbUser = True 时，才遵守此要求。

## <a name="see-also"></a>另请参阅

[Move-CsUser](/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy
)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[与 Skype for Business 共存](/microsoftteams/coexistence-chat-calls-presence)
