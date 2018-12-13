---
title: 将用户从内部部署移动到团队
ms.author: crowe
author: CarolynRowe
manager: serdars--
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 摘要： 了解如何迁移用户设置并将用户移动到团队。
ms.openlocfilehash: 6bee0562b38ce3119306e23b11ea50ebdb8ac3e9
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2018
ms.locfileid: "27244030"
---
# <a name="move-users-from-on-premises-to-teams"></a>将用户从内部部署移动到团队

当用户移从本地至仅团队时，用户的 Skype 商业主页移从本地至联机和该用户分配 TeamsUpgradePolicy 与 mode = TeamsOnly。  用户移动后从内部部署到 TeamsOnly 模式：

- 所有传入呼叫和 （是否从 Skype 发送适用于商务或团队） 聊天从其他用户，将位于用户的工作组客户端中。
- 用户将能够与其他用户 （是否联机或本地） for Business 使用 Skype 的互操作。 
- 用户将能够与联盟组织中的用户进行通信。
- 该用户安排的新会议是团队会议。
- 用户仍可以加入任何 Skype 业务会议。
- 安排为将来的用户的前现有会议将业务 online 中的内部部署迁移到 Skype。
- 在用户首次登录后立即中团队, 提供了在本地存在的联系人。
- 用户不能发起呼叫或从业务的 Skype 聊天也不能可以安排 Skype for Business 中的新会议。 如果他们尝试打开 Skype 业务客户端，他们将被重定向使用团队，如下所示。 如果未安装团队客户端，他们将被导向团队使用其浏览器的 web 版本。<br><br>
    ![将用户重定向到团队的消息](../media/go-to-teams-page.png)

任何用户之前，请确保查看[先决条件](move-users-between-on-premises-and-cloud.md#prerequisites)将用户移动到云。 此外请务必查看[迁移和组织使用团队一起 for Business 的 Skype 的互操作性指南](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。

有两种方法将用户从本地移动到团队：

- 如果您正在使用版本早于 Skype 业务服务器 2015 CU8，移动需要两个步骤 （其中均可编制脚本完成一起作为单独的步骤，如果需要）：
    - [将用户从业务业务 online Skype （本地） 服务器的 Skype 移动](move-users-from-on-premises-to-skype-for-business-online.md)。
    - 一旦用户驻留在 Skype 的在线，业务分配模式的用户 TeamsUpgradePolicy = TeamsOnly。 若要授予 TeamsOnly 模式，请从业务 Online PowerShell 窗口 Skype 运行以下 cmdlet:`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- 如果您有从 Skype 的业务服务器 2015 CU8 或更高版本的管理工具，您可以使用上面的方法或可以如下所述的一个步骤中此移动。 此外，您可以选择提供内业务客户端之前将其移至仅团队 Skype 通知以及 （可选） 已由业务客户端 Skype 以无提示方式下载团队客户。

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>将直接从 for Business 的 Skype 本地用户移至仅团队

内部部署管理工具中的业务服务器 2015 CU8，与 Skype 以及中的业务服务器 2019 Skype 使您能够将用户从本地移动到团队仅模式下一步是在 PowerShell Move-csuser cmdlet 或 Skype 用于业务 Se进行服务器控制面板，如下所述。

### <a name="move-to-teams-using-move-csuser"></a>将移动到团队使用 Move-csuser

可从业务管理命令行管理程序 PowerShell 窗口本地 Skype Move-csuser。 下面的步骤和所需权限的相同用户移动到 Skype 业务 online，除了之外，还必须指定 MoveToTeams 开关必须确保，也已授予用户许可证 （除了 for Business 的 Skype 的团队Online)。

您必须具有足够的权限，在本地环境和 Office 365 租户，[所需的管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。 您可以使用一个帐户的具有权限在这两个环境中，也可以开始业务 Server 命令行管理程序窗口的本地 Skype 与内部部署凭据，并使用`-Credential`参数指定的 Office 365 的凭据与所需的 Office 365 管理角色的帐户。

若要将用户移动到团队仅模式下使用 Move-csuser:

- 指定的用户将使用`Identity`参数。
- 指定-Target 参数的值"sipfed.online.lync。<span>com"。
- 指定`MoveToTeams`切换。
- 如果两上部署和 Office 365 中没有足够的权限与一个帐户，使用`-credential`参数来提供与 Office 365 中的足够权限的帐户。
- 如果在 Office 365 中权限帐户不是以"on.microsoft 结尾。<span>com"，则必须指定`-HostedMigrationOverrideUrl`参数，[所需的管理凭据](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述为正确值。

以下 cmdlet 序列可用于将用户移至 TeamsOnly，并假定的 Office 365 凭据是单独的帐户，并提供作为 Get-credential 提示输入。

    ```
    $cred=Get-Credential
    $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
    ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>将移动到团队 Skype 用于业务 Server Control Panel

1.  打开业务服务器控件 Skype 面板应用程序。
2.  在左侧导航窗格中，选择**用户**。
3.  使用**查找**来查找您想要将移动到团队的用户。
4.  选择的用户，，然后，从列表上方的**操作**下拉列表中选择**移动到团队的所选的用户**。
5.  在向导中，单击**下一步**。
6.  如果出现提示，登录到 Office 365 帐户以。 onmicrosoft.com 和具有足够的权限。
7.  单击**下一步**，然后**下**一次将用户移动。
8. 请注意，顶部的主要控制面板中的应用程序，不向导提供了有关成功或失败状态邮件。

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>通知您 Skype 业务内部部署用户的即将开始移动到团队

内部部署管理工具中的业务服务器 2015 CU8，与 Skype 以及中的业务服务器 2019 Skype 允许您将通知的其即将移动到团队的业务用户的内部部署 Skype。 启用这些通知时，用户会看到其 Skype 业务客户端 （Win32、 Mac、 web 和移动） 的通知，如下所示。 如果安装; 如果用户单击**试用**按钮，将启动团队客户端否则，用户将导航到工作组的 web 版本在其浏览器中。 默认情况下，如果启用了通知，业务客户端的 Win32 Skype 以无提示方式下载团队客户端，这样可将用户移至仅团队模式，则之前的富客户端但是，您还可以禁用此行为。  配置通知使用内部部署版本中的`TeamsUpgradePolicy`，Win32 客户端的无提示下载控制通过内部部署和`TeamsUpgradeConfiguration`cmdlet。

![即将发布移动到团队的通知](../media/teams-upgrade-notification.png)

若要通知他们会很快将升级到团队的内部部署用户，请创建 TeamsUpgradePolicy 的新实例与 NotifySfBUsers = true。 然后将该策略分配给您想要通知，通过直接向用户分配策略或通过策略设置在站点、 池或全局级别的用户。 以下 cmdlet 创建并授予用户级别策略：

```
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

自动下载通过业务 Win32 客户端 Skype 团队通过内部部署 TeamsUpgradeConfiguration cmdlet 与 DownloadTeams 参数控制。 您创建此配置的全局、 站点和池级别。 例如，以下命令创建站点 Redmond1 的配置：

`New-CsTeamsUpgradeConfiguration -Identity “site:redmond1”`

默认情况下 DownloadTeams 的值为 True;但是，就*只*适用如果 NotifySfbUser 给定用户 = True。


## <a name="see-also"></a>另请参阅

[Move-csuser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)

[授予 CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy
)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[与 Skype for Business 共存](/microsoftteams/coexistence-chat-calls-presence)
