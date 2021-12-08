---
title: 将用户从 2019 Skype for Business Server 移至 Teams
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
description: 摘要：了解如何迁移用户设置并将用户移动到Teams。
ms.openlocfilehash: 1e31ec999f15072ae46e96232360d85eb12153a9
ms.sourcegitcommit: c8951fe3504c1776d7aec14b79605aaf5d317e7f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2021
ms.locfileid: "61331083"
---
# <a name="move-users-from-on-premises-to-teams"></a>将用户从本地移至团队

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

当用户从本地移动到仅Teams时，用户的Skype for Business主服务器将从本地移动到联机，并为用户分配"团队升级策略"，模式=团队仅。  将用户从本地模式移动到团队仅模式后：

- 来自其他用户的所有来电和聊天 (无论是从Skype for Business还是Teams) 发送的，都将登陆用户的Teams客户端。
- 用户将能够与使用Skype for Business (的其他用户进行互操作，无论是联机还是在本地) 。
- 用户将能够与联盟组织中的用户进行通信。
- 该用户安排的新会议Teams会议。
- 用户仍然可以加入任何Skype for Business会议。
- 用户为将来安排的预先存在的会议将从本地迁移到Teams。
- 本地存在的联系人在用户首次登录后不久即可在Teams中可用。
- 用户无法从Skype for Business发起呼叫或聊天，也无法在Skype for Business安排新会议。 如果他们尝试打开Skype for Business客户端，则将被重定向到使用Teams，如下所示。 如果未安装Teams客户端，他们将使用浏览器定向到Teams的 Web 版本。<br><br>
    ![将用户重定向到Teams的消息。](../media/go-to-teams-page.png)

在移动任何用户之前，请务必查看将用户移动到云的 [先决条件](move-users-between-on-premises-and-cloud.md#prerequisites) 。 此外，请务必查看[有关将 Teams 与 Skype for Business 一起使用的组织的迁移和互操作性指南](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。


> [!NOTE]
> 应在本地 SfB 帐户上禁用统一联系人存储，以便将联系人移动到Teams。

> [!IMPORTANT]
>
> - 使用 Move-CsUser 将用户从本地移动到云时，现在会自动为用户分配 TeamsOnly 模式，并且无论是否实际指定了切换，其来自本地的会议都将自动转换为Teams会议 `-MoveToTeams` 。  (这包括从 Lync Server 2013（从未有过 `-MoveToTeams` 开关）的迁移。) 以前，如果未指定此开关，用户将从驻留在本地Skype for Business Server转换为联机Skype for Business，并且其模式保持不变。 最近，为了准备退出Skype for Business Online，这一点已经发生了变化。
> - 在本地部署和Teams之间移动用户现在 *需要* OAuth 身份验证协议。 以前建议使用 OAuth，但不是必需的。  2019 Skype for Business Server 2019 Skype for Business Server 2015 CU12 (KB 3061064) 已需要 OAuth。 如果将 Skype for Business Server 2015 与 CU8 一起使用到 CU11，则必须传递 `-UseOAuth` 开关，这样可以确保本地代码使用 OAuth 进行身份验证，或者最好升级到 CU12。 如果您使用的是 CU8 之前的 Skype for Business Server 2015 版本，则必须升级到 CU12 或更高版本。  如果您使用的是 Lync Server 2013，则必须首先升级到 Lync Server 2013 累积更新 10 修补程序 5 (KB 2809243) 或更高版本。


## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>将用户直接从本地Skype for Business移动到仅Teams

Skype for Business Server 和 Lync Server 2013 中的本地管理工具使你能够使用 PowerShell 中的 Move-CsUser cmdlet 或"Skype for Business Server控制面板"，在单个步骤中将用户从本地模式移动到 TeamsOnly 模式，如下所述。 不再需要指定 `-MoveToTeams` 开关，并且无论使用哪个版本的 Skype for Business Server 或 Lync Server，直接从本地移动到Teams的行为现在都是自动的。 

您必须在本地环境和云服务 (Microsoft 365或Office 365) 中都具有足够的权限，如[所需的管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。 可以使用在两个环境中都具有特权的单个帐户，也可以使用本地凭据启动本地Skype for Business Server命令行管理程序窗口，并使用该 `-Credential` 参数为具有必要管理角色的Microsoft 365指定凭据。

此外，除了Skype for Business联机) 之外，您还必须确保已向用户授予Teams (许可证。 请勿禁用联机Skype for Business许可证。

### <a name="move-to-teams-using-move-csuser"></a>使用Move-CsUser移动到Teams

Move-CsUser可从本地Skype for Business Server命令行管理程序 PowerShell 窗口或 Lync Server 命令行管理程序 PowerShell 窗口获得。 要使用 Move-CsUser 将用户移动到 TeamsOnly 模式，请执行以下操作：
- 使用参数指定要移动 `Identity` 的用户。
- 指定 `-Target` 值为"sipfed.online.lync. <span>com"。
- 如果在本地和云服务 (Microsoft 365) 中没有一个具有足够权限的帐户，请使用该 `-credential` 参数为Microsoft 365中具有足够权限的帐户提供该帐户。
- 如果具有Microsoft 365权限的帐户不会以"onmicrosoft. <span>com"，则必须指定 `-HostedMigrationOverrideUrl` 参数，并具有[所需的管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述的正确值。
- 确保运行本地管理工具的计算机使用适用于您的 Skype for Business Server 或 Lync Server 2013 版本的最新 CU，以确保使用 OAuth 进行身份验证。 

以下 cmdlet 序列可用于将用户移动到 TeamsOnly，并假定Microsoft 365凭据是单独的帐户，并作为Get-Credential提示的输入提供。 无论是否 `-MoveToTeams` 指定了开关，行为都是相同的。

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> 由于存在需要不同参数的不同情况，因此在大多数情况下，默认命令为：

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>使用Skype for Business Server控制面板移动到Teams

1. 打开"Skype for Business Server控制面板"应用。
2. 在左侧导航栏中，选择 **"用户"。**
3. 使用 **"查找"** 查找要移动到Teams的用户 () 。
4. 选择用户 () ，然后从列表上方的 **"操作"** 下拉列表中选择 **"将所选用户移动到Teams"** 或 **"将所选用户移动到联机Skype for Business"。**   现在，任一选项都将用户直接移动到 TeamsOnly。
5. 在向导中，单击“下一步”。
6. 如果出现提示，请使用以 .onmicrosoft.com 结尾且具有足够权限的帐户登录到Microsoft 365。
7. 单击" **下一步**"，然后单击" **下一步** "以再次移动用户。
8. 请注意，有关成功或失败的状态消息在主控制面板应用程序的顶部提供，而不是在向导中提供。
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>通知Skype for Business本地用户即将迁移到Teams

Skype for Business Server 2015 年与 CU8 以及 2019 Skype for Business Server中的本地管理工具使你能够通知本地Skype for Business用户即将迁移到Teams。 启用这些通知后，用户将在其Skype for Business客户端 (Win32、Mac、Web 和移动) 中看到通知，如下所示。 如果用户单击"**试用**"按钮，则Teams客户端（如果已安装），则将启动该客户端;否则，用户将在其浏览器中导航到 web 版本的Teams。 默认情况下，启用通知后，Win32 Skype for Business客户端以静默方式下载Teams客户端，以便在将用户移动到 TeamsOnly 模式之前可以使用胖客户端;但是，您也可以禁用此行为。  通知是使用 本地版本的 配置的 `TeamsUpgradePolicy` ，Win32 客户端的静默下载通过本地 `TeamsUpgradeConfiguration` cmdlet 进行控制。

> [!TIP]
> 某些服务器可能需要重新启动才能在 2015 Skype for Business使用 CU8 时正常工作。

![即将移至Teams的通知。](../media/teams-upgrade-notification.png)

若要通知本地用户他们即将升级到Teams，请使用 NotifySfBUsers=true 创建一个新的 TeamsUpgradePolicy 实例。 然后，通过将策略直接分配给用户或在站点、池或全局级别设置策略，将该策略分配给要通知的用户。 以下 cmdlet 创建并授予用户级策略：

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

通过 Skype for Business Win32 客户端自动下载Teams是通过具有 DownloadTeams 参数的本地 TeamsUpgrade 配置 cmdlet 控制的。 您可以在全局、站点和池级别创建此配置。 例如，以下命令为站点 Redmond1 创建配置：

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

默认情况下，下载团队的值为 True;但是，仅当 NotifySfbUser = True 对于给定用户时 *，才* 支持它。

## <a name="see-also"></a>另请参阅

[Move-CsUser](/powershell/module/skype/move-csuser)

[格兰特-CsTeams升级政策](/powershell/module/skype/grant-csteamsupgradepolicy
)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[与 Skype for Business 共存](/microsoftteams/coexistence-chat-calls-presence)
