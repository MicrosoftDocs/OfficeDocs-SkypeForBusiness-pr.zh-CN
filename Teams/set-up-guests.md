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
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="333c1-103">开启或关闭对 Microsoft Teams 的来宾访问</span><span class="sxs-lookup"><span data-stu-id="333c1-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="333c1-104">作为 Office 365 管理员，你必须先启用来宾功能，你或贵组织的用户（具体来说是团队所有者）才能添加来宾。</span><span class="sxs-lookup"><span data-stu-id="333c1-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="333c1-105">在 Azure Active Directory 中设置来宾设置后，</span><span class="sxs-lookup"><span data-stu-id="333c1-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="333c1-106">更改在 Office 365 组织中生效需要 2 小时到 24 小时。</span><span class="sxs-lookup"><span data-stu-id="333c1-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="333c1-107">如果用户尝试向其团队添加来宾时看到“请与管理员联系”消息，很可能是尚未启用来宾功能，或设置尚未生效。</span><span class="sxs-lookup"><span data-stu-id="333c1-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="333c1-108">要启用来宾访问功能的完全体验，非常重要的一点是理解 Microsoft Teams、Azure Active Directory 和 Office 365 之间的核心授权相关性。</span><span class="sxs-lookup"><span data-stu-id="333c1-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="333c1-109">有关详细信息，请参阅[在 Microsoft Teams 中授权来宾访问](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="333c1-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="configure-guest-access-in-the-teams--skype-for-business-admin-center"></a><span data-ttu-id="333c1-110">为业务管理中心中团队 Skype 配置来宾访问</span><span class="sxs-lookup"><span data-stu-id="333c1-110">Configure guest access in the Teams & Skype for Business admin center</span></span>

1.  <span data-ttu-id="333c1-111">业务管理中心的登录到团队和 Skype。</span><span class="sxs-lookup"><span data-stu-id="333c1-111">Sign in to the Teams & Skype for Business admin center.</span></span>

2.  <span data-ttu-id="333c1-112">选择**组织范围设置** > **来宾访问**。</span><span class="sxs-lookup"><span data-stu-id="333c1-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="333c1-113">设置为**上**的**Microsoft 团队中的允许来宾访问**切换开关。</span><span class="sxs-lookup"><span data-stu-id="333c1-113">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="333c1-114">允许来宾访问开关设置为</span><span class="sxs-lookup"><span data-stu-id="333c1-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="333c1-115">设置为**呼叫**、**会议**和**消息**到**打开**或**关闭**，具体取决于您要允许访问切换。</span><span class="sxs-lookup"><span data-stu-id="333c1-115">Set the toggles for **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the access you want to allow.</span></span>

5.  <span data-ttu-id="333c1-116">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="333c1-116">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="333c1-117">使用 PowerShell 打开或关闭来宾访问</span><span class="sxs-lookup"><span data-stu-id="333c1-117">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="333c1-118">下载业务 Online PowerShell 模块 Skypehttps://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="333c1-118">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="333c1-119">连接到业务联机终结点的 Skype PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="333c1-119">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="333c1-120">检查您的配置和如果`AllowGuestUser`是`$False`，使用[集 CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet 可将其设置为`$True`。</span><span class="sxs-lookup"><span data-stu-id="333c1-120">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

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
<span data-ttu-id="333c1-121">您现在可以来宾用户中团队为您的组织。</span><span class="sxs-lookup"><span data-stu-id="333c1-121">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="333c1-122">更多信息</span><span class="sxs-lookup"><span data-stu-id="333c1-122">More information</span></span>

<span data-ttu-id="333c1-123">观看以下视频有关来宾访问的详细信息。</span><span class="sxs-lookup"><span data-stu-id="333c1-123">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="333c1-124">在 Microsoft Teams 中添加来宾</span><span class="sxs-lookup"><span data-stu-id="333c1-124">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
