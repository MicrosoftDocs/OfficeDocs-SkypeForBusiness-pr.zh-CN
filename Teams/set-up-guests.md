---
title: 打开或关闭对 Microsoft 团队的来宾访问
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: 开启或关闭 Microsoft Teams 中的来宾访问功能。
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240e93d5f6329090940e6bf49cb2d6a4ee46ce2f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221448"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>打开或关闭对 Microsoft 团队的来宾访问
===================================================

作为 Office 365 管理员，你必须先启用来宾功能，你或贵组织的用户（具体来说是团队所有者）才能添加来宾。

在 Azure Active Directory 中设置来宾设置后， 更改在 Office 365 组织中生效需要 2 小时到 24 小时。 如果用户尝试向其团队中添加来宾时看到消息 "请联系你的管理员", 则很可能是来宾功能尚未启用或设置尚未生效。

> [!IMPORTANT]
> 要启用来宾访问功能的完全体验，非常重要的一点是理解 Microsoft Teams、Azure Active Directory 和 Office 365 之间的核心授权相关性。 有关详细信息，请参阅[在 Microsoft Teams 中授权来宾访问](Teams-dependencies.md)。

## <a name="guest-access-vs-external-access-federation"></a>来宾访问与外部访问（联合身份验证）

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a>在 Microsoft 团队管理中心配置来宾访问

1.  登录到 Microsoft 团队管理中心。

2.  选择 "**组织范围设置** > "**来宾访问**。

3. 将 "**允许 Microsoft 团队中的来宾访问**" 设置切换为 **"开**"。

    ![允许来宾访问开关设置为 "开" ](media/set-up-guests-image1.png)

4.  将 "**呼叫**"、"**会议**" 和 "**消息传递**" 下的开关设置为 **"打开**" 或 "**关闭**", 具体取决于你希望来宾用户允许的功能。

    - **进行专用通话**–打开此设置**** 可允许来宾进行对等呼叫。
    - **允许使用 IP 视频**-打开此**** 设置可允许来宾在其呼叫和会议中使用视频。
    - **屏幕共享模式**-此设置控制来宾用户的屏幕共享的可用性。 
       - 将此设置启用为 "**已禁用**", 以删除来宾在团队中共享其屏幕的功能。 
       - 将此设置转换为 "**单应用程序**" 以允许共享单个应用程序。 
       - 将此设置转换为**整个屏幕**, 以允许完成屏幕共享。
    - **允许立即开会**–打开此设置**** 可允许来宾在 Microsoft 团队中使用 "立即开会" 功能。
    - **编辑已发送的邮件**-打开**** 此设置可允许来宾编辑以前发送的邮件。
    - **来宾可以删除已发送的邮件**-打开**** 此设置可允许来宾删除以前发送的邮件。
    - **聊天**-启用此设置**** , 让来宾能够在团队中使用聊天功能。
    - **在对话中使用 giphy** -打开此**** 设置可允许来宾在对话中使用 giphy。 Giphy 是一个联机数据库和搜索引擎, 允许用户搜索和共享动态 GIF 文件。 每个 Giphy 都分配有一个内容分级。
    - **Giphy 内容分级**-从下拉列表中选择分级:
       - **允许所有内容**-无论内容分级如何, 来宾都能够插入聊天中的所有 giphy。
       - "**中等**"-来宾将能够在聊天中插入 giphy, 但将按成人内容适度限制。
       - **严格**-来宾将能够在聊天中插入 giphy, 但将受到限制, 无法插入成人内容。
    - **在对话中使用 meme** -打开此**** 设置可允许来宾在对话中使用 meme。
    - **在对话中使用贴纸**-启用**** 此设置可允许来宾在对话中使用贴纸。 


5.  单击“**保存**”。

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>使用 PowerShell 打开或关闭来宾访问

1.  从下载 Skype for Business Online PowerShell 模块https://www.microsoft.com/en-us/download/details.aspx?id=39366
 
2.  将 PowerShell 会话连接到 Skype for Business Online 终结点。

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  检查您的配置, `AllowGuestUser`如果`$False`是, 请使用[CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet 将其设置为`$True`。

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
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
您现在可以在组织的工作组中拥有来宾用户。

## <a name="more-information"></a>详细信息

观看以下视频, 了解有关来宾访问的更多详细信息。

|  |  |
|---------|---------|
| 在 Microsoft Teams 中添加来宾   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
