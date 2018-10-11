---
title: 开启或关闭对 Microsoft Teams 的来宾访问
author: LaithAlShamri
ms.author: lolaj
manager: serdars
ms.date: 10/11/2018
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
ms.openlocfilehash: 3ab67b3fa9ad58c1aa3e8fdd254e3b3515743b4c
ms.sourcegitcommit: 9dd5d8fe6888f0c7d2df1e40fdd8b4c80512f8f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2018
ms.locfileid: "25498118"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a>开启或关闭对 Microsoft Teams 的来宾访问
======================================

作为 Office 365 管理员，你必须先启用来宾功能，你或贵组织的用户（具体来说是团队所有者）才能添加来宾。 

在 Azure Active Directory 中设置来宾设置后， 更改在 Office 365 组织中生效需要 2 小时到 24 小时。 如果用户尝试向其团队添加来宾时看到“请与管理员联系”消息，很可能是尚未启用来宾功能，或设置尚未生效。


> [!IMPORTANT]
> 要启用来宾访问功能的完全体验，非常重要的一点是理解 Microsoft Teams、Azure Active Directory 和 Office 365 之间的核心授权相关性。 有关详细信息，请参阅[在 Microsoft Teams 中授权来宾访问](Teams-dependencies.md)。

## <a name="configure-guest-access-in-the-teams--skype-for-business-admin-center"></a>为业务管理中心中团队 Skype 配置来宾访问

1.  业务管理中心的登录到团队和 Skype。

2.  选择**组织范围设置** > **来宾访问**。

3. 设置为**上**的**Microsoft 团队中的允许来宾访问**切换开关。

    ![允许来宾访问开关设置为 ](media/set-up-guests-image1.png)

4.  设置为**呼叫**、**会议**和**消息**到**打开**或**关闭**，具体取决于您要允许访问切换。

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
