---
title: 将用户从 Skype for Business Server 2019 移动到团队
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
description: 摘要：了解如何迁移用户设置并将用户移动到团队。
ms.openlocfilehash: 07d0657017d24acbbd3961c3528056debb927a5a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779678"
---
# <a name="move-users-from-on-premises-to-teams"></a>将用户从本地移至团队

当用户仅从本地移动到团队时，用户的 Skype for Business 主页将从本地移动到联机，并向用户分配模式 = TeamsOnly 的 TeamsUpgradePolicy。  将用户从本地移动到 TeamsOnly 模式后：

- 来自其他用户（无论是从 Skype for Business 还是团队发送）的所有传入呼叫和聊天都将在用户的团队客户端中进行陆地。
- 用户将能够与使用 Skype for Business 的其他用户交互操作（无论是在线还是在本地）。
- 用户将能够与联合组织中的用户进行通信。
- 由该用户计划的新会议是团队会议。
- 用户仍可以加入任何 Skype for Business 会议。
- 为未来安排的用户的预先存在的会议将从本地迁移到团队。
- 在用户首次登录后，会立即在本地的联系人中使用已存在的联系人。
- 用户不能从 Skype for Business 发起呼叫或聊天，也不能在 Skype for Business 中安排新会议。 如果他们尝试打开 Skype for Business 客户端，它们将被重定向到使用如下所示的团队。 如果未安装团队客户端，则会使用浏览器将其定向到团队的 web 版本。<br><br>
    ![将用户重定向到团队的邮件](../media/go-to-teams-page.png)

在移动任何用户之前，请务必查看将用户移动到云的[先决条件](move-users-between-on-premises-and-cloud.md#prerequisites)。 此外，请务必查看[与 Skype For business 一起使用团队的组织的迁移和互操作性指南](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。


> [!NOTE]
> 应在本地 SfB 帐户上禁用统一联系人存储库，以便将联系人移动到团队。


有两种方法可以将用户从本地移动到团队：

- 如果使用早于 Skype for business Server 2015 CU8 的版本，则移动需要两个步骤（可以通过脚本将其作为一个步骤进行脚本，如果需要）：
  - [将用户从 skype For Business Server （本地）移动到 skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md)。
  - 一旦用户托管在 Skype for Business Online 中，请将用户 TeamsUpgradePolicy 分配为 mode = TeamsOnly。 若要授予 TeamsOnly 模式，请从 Skype for Business Online PowerShell 窗口运行以下 cmdlet：`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- 如果您具有来自 Skype for Business Server 2015 CU8 或更高版本的管理工具，则可以使用上面的方法，也可以按如下所述在一个步骤中进行移动。 此外，您可以选择在 Skype for business 客户端中提供通知，然后在将其仅移动到团队之前，也可以选择让 Skype for Business 客户端自行下载团队客户端。

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>仅将本地用户从 Skype for Business 直接移动到团队

Skype for business Server 2015 中的本地管理工具使用 CU8，以及 Skype for Business Server 2019 中的本地管理工具，您可以使用 PowerShell 中的 Get-csuser cmdlet 或 Skype for Business Server 控制面板，在一个步骤中将用户从 "仅本地" 移动到 "仅工作组" 模式（如下所述）。

### <a name="move-to-teams-using-move-csuser"></a>使用 Get-csuser 移动到团队

Get-csuser 可从本地 Skype for Business 命令行管理程序 PowerShell PowerShell PowerShell 窗口中获取。 下面的步骤和需要的权限与将用户移动到 Skype for business Online 相同，不同之处在于，您还必须指定 MoveToTeams 开关，并且必须确保用户也已为团队授予许可证（除了 Skype for Business Online）。

在本地环境和 Office 365 组织中，您必须具有足够的权限，如[所需的管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。 您可以使用在两个环境中具有权限的单个帐户，也可以使用本地凭据启动本地 Skype for Business Server Management Shell 窗口，并使用`-Credential`参数指定具有必要的 office 365 管理角色的 office 365 帐户的凭据。

使用 Get-csuser 将用户移动到仅限工作组模式的步骤：

- 使用`Identity`参数指定要移动的用户。
- 指定值为 "sipfed.online.lync.com>" 的-Target 参数。<span>com "。
- 指定`MoveToTeams`开关。
- 如果您没有一个帐户在本地和 Office 365 中具有足够的权限，请使用`-credential`参数在 Office 365 中提供具有足够权限的帐户。
- 如果在 Office 365 中具有权限的帐户不以 ".onmicrosoft" 结尾。<span>com "，必须使用正确的`-HostedMigrationOverrideUrl`值指定参数，如[所需管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。

可以使用以下 cmdlet 序列将用户移动到 TeamsOnly，并假定 Office 365 凭据是单独的帐户并作为 Get Credential 提示的输入提供。

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>移动到使用 Skype for Business Server 控制面板的团队

1. 打开 "Skype for Business Server 控制面板" 应用。
2. 在左侧导航栏中，选择 "**用户**"。
3. 使用 "**查找**" 查找要移到团队的用户。
4. 选择用户，然后从列表上方的 "**操作**" 下拉列表中选择 "**将所选用户移动到团队**"。
5. 在向导中，单击“下一步”****。
6. 如果出现提示，请使用以 onmicrosoft.com 结尾的帐户登录 Office 365 并拥有足够的权限。
7. 单击 "**下一步**"，然后再单击一次以移动用户。 **Next**
8. 请注意，有关成功或失败的状态消息是在主控制面板应用程序的顶部提供的，而不是在向导中提供的。

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>将即将推出的 Skype for business 本地用户通知给团队

Skype for business Server 2015 中的本地管理员工具使用 CU8 以及 Skype for Business Server 2019 中的本地管理员工具，您可以将即将到来的 Skype for Business 用户通知给团队。 启用这些通知后，用户将在其 Skype for Business 客户端（Win32、Mac、web 和手机）中看到通知，如下所示。 如果用户单击 "**尝试**" 按钮，则团队客户端将在已安装的情况下启动;否则，用户将在其浏览器中导航到团队的 web 版本。 默认情况下，启用通知后，Win32 Skype for Business 客户端将以无提示方式下载团队客户端，以便在用户仅将用户移动到 "仅工作组" 模式之前可以使用富客户端;但是，也可以禁用此行为。  使用内部部署版本配置通知`TeamsUpgradePolicy`，并通过内部部署`TeamsUpgradeConfiguration` cmdlet 控制 Win32 客户端的无提示下载。

> [!TIP]
> 某些服务器可能需要重新启动，这样才能在 Skype for Business 2015 with CU8 中工作。

![即将到来的转到团队的通知](../media/teams-upgrade-notification.png)

若要通知本地用户他们很快将升级到团队，请创建一个新的 TeamsUpgradePolicy 实例，并 NotifySfBUsers = true。 然后，通过将策略直接分配给用户或在站点、池或全局级别设置策略，将该策略分配给要通知的用户。 以下 cmdlet 创建并授予用户级策略：

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

通过 Skype for Business Win32 客户端自动下载团队是通过内部部署 TeamsUpgradeConfiguration cmdlet 和 DownloadTeams 参数进行控制的。 您可以在全局、站点和池级别上创建此配置。 例如，以下命令将创建网站 Redmond1 的配置：

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

默认情况下，DownloadTeams 的值为 True;但是，仅当给定用户的 NotifySfbUser = True 时*才*会生效。

## <a name="see-also"></a>另请参阅

[移动-Get-csuser](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[与 Skype for Business 共存](/microsoftteams/coexistence-chat-calls-presence)
