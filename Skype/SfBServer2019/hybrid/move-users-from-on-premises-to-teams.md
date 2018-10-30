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
ms.openlocfilehash: 76baa9cdc87535e68cc0bff4e9397a91d1090439
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838715"
---
# <a name="move-users-from-on-premises-to-teams"></a>将用户从内部部署移动到团队

与业务服务器 2019年的 Skype，可以将内部部署用户迁移到团队这篇文章中所述。

请注意，之后将您的用户移动到团队： 
 
- 他们的会议都将迁移到 Skype online 业务和联系人都将迁移到团队。 
- 他们可以加入 Skype 会议通过业务富客户端 （用户不会提示登录每次） 的 Skype 或 Skype 会议应用程序 （需要一次性下载和登录）。 当用户单击团队中的业务会议链接 Skype 时，将在相应的应用程序中启动会议。

- 移动，在您的用户将能够加入现有 Skype 业务会议使用本机应用程序。

> [!NOTE]
> 将用户移动到 TeamsOnly 模式后，用户在 Skype 驻留业务 online 中。

## <a name="prerequisites-for-moving-on-premises-users-to-teams"></a>将内部部署用户移动到团队的先决条件 

本节介绍用于将内部部署用户移到团队系统必备组件。 您必须：
- [设置混合连接性](#set-up-hybrid-connectivity)（如果您尚未这样)
- [通知用户的移动到团队](#notify-your-users-of-the-move-to-teams)（可选）
- [确保您的用户具有有效的许可证](#make-sure-your-users-have-a-valid-license)
- [注意的语音配置要求](#voice-configuration-requirements)
- [分配团队升级策略](#assign-a-teams-upgrade-policy)（可选）

## <a name="set-up-hybrid-connectivity"></a>设置混合连接性
如果您未迁移用户之前，必须确保您已配置您的业务服务器内部部署环境的 Skype 和 Skype 业务 online 之间的混合连接性。 混合连接需要 Active Directory 同步、 配置联合身份验证，等等。 有关详细信息，请参阅[规划混合连接性](plan-hybrid-connectivity.md)和[配置混合连接性](configure-hybrid-connectivity.md)。

## <a name="notify-your-users-of-the-move-to-teams"></a>通知用户的移动到团队 
这是一个可选步骤，但您应考虑的一个。 通知用户的待处理的团队升级，您可以使用本地 TeamsUpgradePolicy 和 TeamsUpgradeConfiguration cmdlet。 您还可以在后台之前升级 （仅 Win32 客户端） 配置的团队的无提示自动下载。 

例如，通知用户，他们正在升级到团队，使用内部部署 TeamsUpgradePolicy cmdlet-NotifySbUser 参数。 您可以在全局、 站点、 池或用户级别设置策略。 以下命令创建并授予用户级别策略：
 
```
New-CsTeamsUpgradePolicy -Identity UpgradeNotice -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity user01 -PolicyName “UpgradeNotice”
```

您可以通过使用 Get-csTeamsUpgradePolicy cmdlet 来检查此策略。

您的用户将看到即将移动到团队的通知。 该通知出现在 Win32、 Mac、 Mobile 以及 Web 客户端 （使用正确的版本中）。

您可以指定与 DownloadTeams 参数一起使用的本地 TeamsUpgradeConfiguration cmdlet 正在升级的用户自动下载团队 （对于 Win32 客户端）。 租户级别设置此策略，而且可应用于全局、 站点和池级。 例如，以下命令在网站级别设置的策略：

```
New-CsTeamsUpgradeConfiguration -Identity “site:redmond1” 
```

默认情况下 DownloadTeams 的值为 true 时，但您还必须设置为 True 可为给定的用户启用团队 NotifySfbUser。 

## <a name="make-sure-your-users-have-a-valid-license"></a>请确保您的用户具有有效的许可证  
在迁移之前的本地用户必须有有效的许可证，，如下所示：

-   用户必须拥有团队许可证。
-   如果对用户配置为使用内部部署企业语音，它们必须具有联机语音许可证，移动时。 
-   如果用户的本地电话拨入式会议配置，它们必须具有许可证的电话系统 (云 PBX)。

## <a name="voice-configuration-requirements"></a>语音配置要求

如果您在本地用户具有内部部署语音，您有两个选项：

-  **将具有电话功能的用户迁移。** 用户可以发起和接收呼叫使用团队客户端。  您可以选择 Microsoft 调用规划或直接路由连接到团队的电话服务。  

    -  规划 Microsoft 调用提供了一云语音解决方案。 有关 Microsoft 调用规划的详细信息，请参阅 （即将推出的链接）。 
    -  直接路由允许您使用几乎任何 PSTN 中继，并且您可以配置客户拥有电话设备和 Microsoft 电话系统之间的互操作性。  有关详细信息，请参阅[规划直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-plan)和[配置直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-configure)。

-  **迁移用户不带电话功能。** 如果将用户迁移而不保留电话功能，请确保用户在云中有相应的许可证。 

## <a name="assign-a-teams-upgrade-policy"></a>分配团队升级策略  
在线工具可用于管理如用户策略控制的传入邮件和呼叫路由。 有关详细信息，请参阅 （即将推出的链接）。

## <a name="move-on-premises-users-to-teams"></a>将内部部署用户移至团队

使用 PowerShell cmdlet 或使用 Skype 业务 Server 2019 控制面板，则可以移到团队内部部署用户。

### <a name="move-users-by-using-powershell"></a>使用 PowerShell 移动用户
使用 PowerShell 将用户移动到团队中，您将使用 moveToTeams 参数，如下所示使用 Move-csuser cmdlet:

```
Move-CsUser -Identity user0 -Target sipfed.online.lync.com -moveToTeams -credentials $cred. 
```

($cred = 获取凭据。 您必须提供 Office 365 管理员凭据。）

> [!NOTE]
> 此命令将 TeamsInteropPolicy 设置为团队，并将 TeamsUpgradePolicy 设置为 TeamsOnly 模式。 
 
向工作组移动成功后，业务客户端的用户的 Skype 将显示以下消息： 

![成功迁移到团队消息](../media/teams-upgrade-complete-message.png)

请注意，Skype for Business 将不再除以加入会议的用户。 

在极少数情况下，将用户移动到团队时，您可能想要重写电话拨入式会议和云语音功能。 可以使用 Move-csuser 命令具有以下参数执行此操作：
- **BypassAudioConferencingCheck:** 如果用户具有启用内部部署的电话拨入式会议，用户还必须在迁移之前分配 Office 365 中的 AudioConf 许可证。 一旦迁移到云中，将在云中的音频会议设置的用户。 如果由于某种原因，您想要将用户移动到云，但不是使用的音频会议功能，您可以通过指定此参数覆盖它。
- **ByPassEnterpriseVoice:** 如果用户具有启用内部部署企业语音，用户必须在迁移之前分配 Office 365 中的企业语音许可证。 迁移到云中之后, 将云中的语音设置的用户。 如果由于某种原因，您想要将用户移动到云，但不是使用云语音功能，您可以通过指定此参数覆盖云语音。
 
### <a name="move-users-by-using-the-skype-for-business-server-control-panel"></a>使用 Skype 业务 Server 控制面板移动用户 

若要将用户移至团队使用 Skype 业务控制面板：

1. 打开业务 Control Panel Skype 和登录到 Office 365 帐户。

2. 在左侧导航窗格中，选择**用户**，然后选择要迁移用户。 
     
3. 在**操作**菜单中，选择**移动到团队的所选的用户**。 

    ![单击下一步以确认迁移](../media/migration-confirmation.png)
    
4. 单击**下一步**以确认您的迁移。 

用户移动到团队后，您将看到类似如下的确认：

![移动用户确认](../media/move-user-confirmation.png)
<br/><br/>
![邮件已移动用户](../media/users-moved-successfully.png)

如果移动不成功，您将看到以下消息：

![邮件的用户无法移动](../media/users-not-moved.png)
