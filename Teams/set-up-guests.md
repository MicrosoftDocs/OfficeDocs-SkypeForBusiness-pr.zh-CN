---
title: 开启或关闭对 Microsoft Teams 的来宾访问
author: somakbhattacharyya
ms.author: sbhatta
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
ms.openlocfilehash: 42fead56b8064d2697ca4e8b115eefd0116a5e36
ms.sourcegitcommit: 454ded73af5854d7b81a3b996702a6464b3fc313
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "27772758"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="f5576-103">开启或关闭对 Microsoft Teams 的来宾访问</span><span class="sxs-lookup"><span data-stu-id="f5576-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="f5576-104">作为 Office 365 管理员，你必须先启用来宾功能，你或贵组织的用户（具体来说是团队所有者）才能添加来宾。</span><span class="sxs-lookup"><span data-stu-id="f5576-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="f5576-105">在 Azure Active Directory 中设置来宾设置后，</span><span class="sxs-lookup"><span data-stu-id="f5576-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="f5576-106">更改在 Office 365 组织中生效需要 2 小时到 24 小时。</span><span class="sxs-lookup"><span data-stu-id="f5576-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="f5576-107">如果用户会看到"请与管理员联系"的邮件如果他们尝试将来宾添加到其工作组，，则可能的来宾功能尚未启用或设置尚未有效。</span><span class="sxs-lookup"><span data-stu-id="f5576-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="f5576-108">要启用来宾访问功能的完全体验，非常重要的一点是理解 Microsoft Teams、Azure Active Directory 和 Office 365 之间的核心授权相关性。</span><span class="sxs-lookup"><span data-stu-id="f5576-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="f5576-109">有关详细信息，请参阅[在 Microsoft Teams 中授权来宾访问](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="f5576-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="configure-guest-access-in-the-teams--skype-for-business-admin-center"></a><span data-ttu-id="f5576-110">为业务管理中心中团队 Skype 配置来宾访问</span><span class="sxs-lookup"><span data-stu-id="f5576-110">Configure guest access in the Teams & Skype for Business admin center</span></span>

1.  <span data-ttu-id="f5576-111">业务管理中心的登录到团队和 Skype。</span><span class="sxs-lookup"><span data-stu-id="f5576-111">Sign in to the Teams & Skype for Business admin center.</span></span>

2.  <span data-ttu-id="f5576-112">选择**组织范围设置** > **来宾访问**。</span><span class="sxs-lookup"><span data-stu-id="f5576-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="f5576-113">设置为**上**的**Microsoft 团队中的允许来宾访问**切换开关。</span><span class="sxs-lookup"><span data-stu-id="f5576-113">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="f5576-114">允许来宾访问开关设置为</span><span class="sxs-lookup"><span data-stu-id="f5576-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="f5576-115">设置在**调用**、**会议**和**消息**下的切换为**打开**或**关闭**，具体取决于您希望允许为来宾用户功能。</span><span class="sxs-lookup"><span data-stu-id="f5576-115">Set the toggles under **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the capabilities you want to allow for guest users.</span></span>

    - <span data-ttu-id="f5576-116">**使接听私人电话**– 启用此设置**在**允许来宾进行对等呼叫。</span><span class="sxs-lookup"><span data-stu-id="f5576-116">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="f5576-117">**允许的 IP 视频**-启用此设置**在**允许来宾使用其呼叫和会议的视频。</span><span class="sxs-lookup"><span data-stu-id="f5576-117">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="f5576-118">**屏幕共享模式**– 此设置控制屏幕共享来宾用户的可用性。</span><span class="sxs-lookup"><span data-stu-id="f5576-118">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="f5576-119">启用此设置来**禁用**删除来宾共享其屏幕团队中的功能。</span><span class="sxs-lookup"><span data-stu-id="f5576-119">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="f5576-120">启用此设置**单个应用程序**允许的单独的应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="f5576-120">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="f5576-121">打开到**整个屏幕**，确定允许完成的屏幕共享此设置。</span><span class="sxs-lookup"><span data-stu-id="f5576-121">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="f5576-122">**立即允许开会**– 启用此设置**在**允许来宾中的 Microsoft 团队使用立即开会功能。</span><span class="sxs-lookup"><span data-stu-id="f5576-122">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="f5576-123">**编辑发送的邮件**-启用此设置**在**允许来宾编辑消息它们以前发送。</span><span class="sxs-lookup"><span data-stu-id="f5576-123">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="f5576-124">**来宾可以删除已发送的邮件**– 此设置**在**允许来宾删除消息他们打开以前发送。</span><span class="sxs-lookup"><span data-stu-id="f5576-124">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="f5576-125">**聊天**– 启用此设置**在**授予携带团队中使用聊天功能。</span><span class="sxs-lookup"><span data-stu-id="f5576-125">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="f5576-126">**在对话中使用 Giphys** – 启用此设置**在**允许来宾用于 Giphys 对话中。</span><span class="sxs-lookup"><span data-stu-id="f5576-126">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="f5576-127">Giphy 是联机数据库和搜索引擎，使用户可以搜索和共享动态的 GIF 文件。</span><span class="sxs-lookup"><span data-stu-id="f5576-127">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="f5576-128">每个 Giphy 分配内容评级。</span><span class="sxs-lookup"><span data-stu-id="f5576-128">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="f5576-129">**Giphy 内容评级**– 选择下拉列表中选择一个评级：</span><span class="sxs-lookup"><span data-stu-id="f5576-129">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="f5576-130">**允许的所有内容**-来宾都将能够在聊天，而不考虑内容评级中插入所有 Giphys。</span><span class="sxs-lookup"><span data-stu-id="f5576-130">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="f5576-131">**中等**-来宾都将能够在聊天室中插入 Giphys，但将从成人内容适度限制。</span><span class="sxs-lookup"><span data-stu-id="f5576-131">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="f5576-132">**严格**– 来宾都将能够在聊天室中插入 Giphys，但将从插入成人内容严格限制。</span><span class="sxs-lookup"><span data-stu-id="f5576-132">**Strict** – Guests will be able to insert Giphys in chats, but will be strictly restricted from inserting adult content.</span></span>
    - <span data-ttu-id="f5576-133">**在对话中使用 Memes** -启用此设置**在**允许来宾用于 Memes 对话中。</span><span class="sxs-lookup"><span data-stu-id="f5576-133">**Use Memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="f5576-134">**在对话中使用标签**– 启用此设置**在**允许来宾对话中使用标签。</span><span class="sxs-lookup"><span data-stu-id="f5576-134">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="f5576-135">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="f5576-135">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="f5576-136">使用 PowerShell 打开或关闭来宾访问</span><span class="sxs-lookup"><span data-stu-id="f5576-136">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="f5576-137">下载业务 Online PowerShell 模块 Skypehttps://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="f5576-137">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="f5576-138">连接到业务联机终结点的 Skype PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="f5576-138">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="f5576-139">检查您的配置和如果`AllowGuestUser`是`$False`，使用[集 CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet 可将其设置为`$True`。</span><span class="sxs-lookup"><span data-stu-id="f5576-139">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

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
<span data-ttu-id="f5576-140">您现在可以来宾用户中团队为您的组织。</span><span class="sxs-lookup"><span data-stu-id="f5576-140">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="f5576-141">更多信息</span><span class="sxs-lookup"><span data-stu-id="f5576-141">More information</span></span>

<span data-ttu-id="f5576-142">观看以下视频有关来宾访问的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f5576-142">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="f5576-143">在 Microsoft Teams 中添加来宾</span><span class="sxs-lookup"><span data-stu-id="f5576-143">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
