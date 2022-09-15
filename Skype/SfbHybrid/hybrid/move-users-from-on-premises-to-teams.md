---
title: 将用户从 2019 Skype for Business Server移动到 Teams
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
search.appverid: MET150
ms.custom: ''
description: 摘要：了解如何迁移用户设置并将用户移动到 Teams。
ms.openlocfilehash: d29fa49e3521e93cb1818c70adb37cfb5019660b
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705841"
---
# <a name="move-users-from-on-premises-to-teams"></a>将用户从本地移至团队

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

当用户从本地移动到仅 Teams 时，用户的Skype for Business主页将从本地移动到联机，并且为用户分配了 TeamsUpgradePolicy 和 mode=TeamsOnly。  将用户从本地移动到 TeamsOnly 模式后：

- 来自其他用户的所有来电和聊天（无论是从 Skype for Business 还是 Teams 发送）都将进入用户的 Teams 客户端。
- 用户将能够与使用 Skype for Business（无论在线还是本地）的其他用户进行互操作。
- 用户将能够与联合组织中的用户进行通信。
- 该用户安排的新会议是 Teams 会议。
- 用户仍然可以加入任何 Skype for Business 会议。 但是，从 2022 年 10 月开始，混合组织中的 TeamsOnly 用户只能匿名加入Skype for Business会议。 有关详细信息，请参阅 [退休后会发生什么](/microsoftteams/skype-for-business-online-retirement#what-to-expect-post-retirement)情况。
- 计划将来的用户预先存在的会议将从本地迁移到 Teams。
- 用户首次登录后，Teams 中会提供本地存在的联系人。
- 用户无法从Skype for Business发起呼叫或聊天，也不能在Skype for Business中安排新会议。 如果他们尝试打开Skype for Business客户端，将重定向到使用 Teams，如下所示。 如果未安装 Teams 客户端，他们将使用浏览器定向到 Teams 的 Web 版本。<br><br>
    ![将用户重定向到 Teams 的消息。](../media/go-to-teams-page.png)

在移动任何用户之前，请务必查看将用户移动到云的 [先决条件](move-users-between-on-premises-and-cloud.md#prerequisites) 。 另请务必查看[使用 Teams 和Skype for Business的组织迁移和互操作性指南](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。


> [!NOTE]
> 应在本地 SfB 帐户上禁用统一联系人存储，以便将联系人移动到 Teams。

> [!IMPORTANT]
>
> - 使用 Move-CsUser 将用户从本地移到云时，系统会自动为用户分配 TeamsOnly 模式，无论是否实际指定了 `-MoveToTeams` 该开关，其本地会议都将自动转换为 Teams 会议。  (这包括从 Lync Server 2013 进行迁移，而 Lync Server 2013 从未使用过 `-MoveToTeams` switch.) 以前，如果未指定此开关，则用户将从Skype for Business Server本地主机转换为 Skype for Business Online，并且其模式保持不变。 这是为Skype for Business在线退休做准备而改变的。
> - 在本地部署和 Teams 之间移动用户现在 *需要* 更新本地组件的最低版本，Skype for Business Server或 Lync Server 不再依赖于 Skype for Business Online 旧版基础结构。 有关详细信息，请参阅 [先决条件](move-users-between-on-premises-and-cloud.md#prerequisites)。

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>将用户直接从本地Skype for Business移动到仅 Teams

使用 Skype for Business Server 和 Lync Server 2013 中的本地管理员工具，可以使用 PowerShell 中的 Move-CsUser cmdlet 或 Skype for Business Server لوحة التحكم，在单个步骤中将用户从本地移动到 TeamsOnly 模式，如下所述。 现在不再需要指定`-MoveToTeams`开关，直接从本地移动到 Teams 的操作是自动的，不管使用哪个版本的 Skype for Business Server 或 Lync Server。 

必须在本地环境和云服务 (Microsoft 365 或Office 365) 中拥有足够的权限，如[所需管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。 可以使用两个环境中具有权限的单个帐户，也可以使用本地凭据启动本地 Skype for Business Server Management Shell 窗口，并使用`-Credential`该参数为具有必要管理角色的 Microsoft 365 指定凭据。

此外，除了Skype for Business联机) ，还必须确保用户已获得 Teams (许可证。 请勿禁用Skype for Business联机许可证。

### <a name="move-to-teams-using-move-csuser"></a>使用 Move-CsUser 移动到 Teams

Move-CsUser 可从本地 Skype for Business Server 命令行管理程序 PowerShell 窗口或 Lync Server 命令行管理程序 PowerShell 窗口获取。 若要使用 Move-CsUser 将用户移动到 TeamsOnly 模式，请执行以下操作：
- 指定要使用参数移动的 `Identity` 用户。
- `-Target`指定值为“sipfed.online.lync”的参数。<span>com“ (或类似的值，如果你的租户是政府云) 。
- 如果在本地和云服务 (Microsoft 365) 中没有一个拥有足够权限的帐户，请使用 `-credential` 该参数在 Microsoft 365 中提供具有足够权限的帐户。
- 如果 Microsoft 365 中具有权限的帐户未以“onmicrosoft”结尾。<span>com“，必须指定 `-HostedMigrationOverrideUrl` 参数，其值正确，如 [所需管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。
- 请确保运行本地管理工具的计算机使用最新 CU 作为 Skype for Business Server 或 Lync Server 2013 版本，以确保 OAuth 用于身份验证。 

以下 cmdlet 序列可用于将用户移动到 TeamsOnly，并假定 Microsoft 365 凭据是一个单独的帐户，并作为Get-Credential提示的输入提供。 无论 `-MoveToTeams` 是否指定开关，行为都是相同的。

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> 由于存在需要不同参数的不同情况，大多数情况下的默认命令是：

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板移动到 Teams

1. 打开Skype for Business Server لوحة التحكم应用。
2. 在左侧导航栏中，选择 **“用户**”。
3. 使用“**查找**”找到要移动到 Teams 的用户。
4. 选择用户，然后从列表上方的“**操作**”下拉列表中，选择“**将所选用户移动到 Teams**”或“**将所选用户移动到 Skype for Business Online**”。   这两个选项现在都将用户直接移动到 TeamsOnly。
5. 在向导中，单击“下一步”。
6. 如果出现提示，请使用以 .onmicrosoft.com 结尾并具有足够权限的帐户登录到 Microsoft 365。
7. 单击“**下一步**”，然后再单击“**下一步**”一次以移动用户。
8. 有关成功或失败的状态消息在主控制面板应用的顶部提供，而不是在向导中提供。
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>通知Skype for Business本地用户即将迁移到 Teams

使用 CU8 Skype for Business Server 2015 和 2019 Skype for Business Server的本地管理员工具可通知本地Skype for Business用户即将迁移到 Teams。 启用这些通知时，用户将在其Skype for Business客户端 (Win32、Mac、Web 和移动) 中看到通知，如下所示。 如果用户单击“ **试用”** 按钮，将启动 Teams 客户端（如果已安装）：否则，用户将在浏览器中导航到 Teams 的 Web 版本。 默认情况下，启用通知时，Win32 Skype for Business客户端以无提示方式下载 Teams 客户端，以便在将用户移动到 TeamsOnly 模式之前，富客户端可用。 但是，也可以禁用此行为。  通知是使用本地版本配置的 `TeamsUpgradePolicy`，Win32 客户端的无提示下载通过本地 `TeamsUpgradeConfiguration` cmdlet 进行控制。


![即将移动到 Teams 的通知。](../media/teams-upgrade-notification.png)

若要通知本地用户他们即将升级到 Teams，请使用 NotifySfBUsers=true 创建 TeamsUpgradePolicy 的新实例。 然后，通过将策略直接分配给用户或在站点、池或全局级别设置策略，将该策略分配给要通知的用户。 以下 cmdlet 创建并授予用户级策略：

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

通过 Skype for Business Win32 客户端自动下载 Teams 通过具有 DownloadTeams 参数的本地 TeamsUpgradeConfiguration cmdlet 进行控制。 在全局、站点和池级别创建此配置。 例如，以下命令为 Site Redmond1 创建配置：

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

默认情况下，DownloadTeams 的值为 True;但是， *仅* 当给定用户的 NotifySfbUser = True 时，才会获得此功能。

## <a name="see-also"></a>另请参阅

[Move-CsUser](/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy
)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[与 Skype for Business 共存](/microsoftteams/coexistence-chat-calls-presence)
