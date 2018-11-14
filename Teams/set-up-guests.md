---
title: 开启或关闭对 Microsoft Teams 的来宾访问
author: LaithAlShamri
ms.author: lolaj
manager: serdars
ms.date: 10/18/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: 开启或关闭 Microsoft Teams 中的来宾访问功能。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 436dc26e9ef9b75849fb6aac0383ed40bc5e581b
ms.sourcegitcommit: 5d8b5dee1dea84494aea92bbce568dea10752af9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2018
ms.locfileid: "26510557"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a>开启或关闭对 Microsoft Teams 的来宾访问
======================================

作为 Office 365 管理员，你必须先启用来宾功能，你或贵组织的用户（具体来说是团队所有者）才能添加来宾。 

在 Azure Active Directory 中设置来宾设置后， 更改在 Office 365 组织中生效需要 2 小时到 24 小时。 如果用户会看到"请与管理员联系"的邮件如果他们尝试将来宾添加到其工作组，，则可能的来宾功能尚未启用或设置尚未有效。


> [!IMPORTANT]
> 要启用来宾访问功能的完全体验，非常重要的一点是理解 Microsoft Teams、Azure Active Directory 和 Office 365 之间的核心授权相关性。 有关详细信息，请参阅[在 Microsoft Teams 中授权来宾访问](Teams-dependencies.md)。

## <a name="configure-guest-access-in-the-teams--skype-for-business-admin-center"></a>为业务管理中心中团队 Skype 配置来宾访问

1.  业务管理中心的登录到团队和 Skype。

2.  选择**组织范围设置** > **来宾访问**。

3. 设置为**上**的**Microsoft 团队中的允许来宾访问**切换开关。

    ![允许来宾访问开关设置为 ](media/set-up-guests-image1.png)

4.  设置在**调用**、**会议**和**消息**下的切换为**打开**或**关闭**，具体取决于您希望允许为来宾用户功能。

    - **使接听私人电话**– 启用此设置**在**允许来宾进行对等呼叫。
    - **允许的 IP 视频**-启用此设置**在**允许来宾使用其呼叫和会议的视频。
    - **屏幕共享模式**– 此设置控制屏幕共享来宾用户的可用性。 
       - 启用此设置来**禁用**删除来宾共享其屏幕团队中的功能。 
       - 启用此设置**单个应用程序**允许的单独的应用程序共享。 
       - 打开到**整个屏幕**，确定允许完成的屏幕共享此设置。
    - **立即允许开会**– 启用此设置**在**允许来宾中的 Microsoft 团队使用立即开会功能。
    - **编辑发送的邮件**-启用此设置**在**允许来宾编辑消息它们以前发送。
    - **来宾可以删除已发送的邮件**– 此设置**在**允许来宾删除消息他们打开以前发送。
    - **聊天**– 启用此设置**在**授予携带团队中使用聊天功能。
    - **在对话中使用 Giphys** – 启用此设置**在**允许来宾用于 Giphys 对话中。 Giphy 是联机数据库和搜索引擎，使用户可以搜索和共享动态的 GIF 文件。 每个 Giphy 分配内容评级。
    - **Giphy 内容评级**– 选择下拉列表中选择一个评级：
       - **允许的所有内容**-来宾都将能够在聊天，而不考虑内容评级中插入所有 Giphys。
       - **中等**-来宾都将能够在聊天室中插入 Giphys，但将从成人内容适度限制。
       - **严格**– 来宾都将能够在聊天室中插入 Giphys，但将从插入成人内容严格限制。
    - **在对话中使用 Memes** -启用此设置**在**允许来宾用于 Memes 对话中。
    - **在对话中使用标签**– 启用此设置**在**允许来宾对话中使用标签。 


5.  单击“**保存**”。

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>使用 PowerShell 打开或关闭来宾访问

1.  下载业务 Online PowerShell 模块 Skypehttps://www.microsoft.com/en-us/download/details.aspx?id=39366
 
2.  连接到业务联机终结点的 Skype PowerShell 会话。

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  检查您的配置和如果`AllowGuestUser`是`$False`，使用[集 CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet 可将其设置为`$True`。

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    AllowTBotProactiveMessaging      : False
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
您现在可以来宾用户中团队为您的组织。

## <a name="more-information"></a>更多信息

观看以下视频有关来宾访问的详细信息。

|  |  |
|---------|---------|
| 在 Microsoft Teams 中添加来宾   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
