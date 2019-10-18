---
title: 打开或关闭对 Microsoft 团队的来宾访问
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: 开启或关闭 Microsoft Teams 中的来宾访问功能。
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 186c83b82c396a21fe0098a561bcd4db13370140
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37566031"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="a185a-103">打开或关闭对 Microsoft 团队的来宾访问</span><span class="sxs-lookup"><span data-stu-id="a185a-103">Turn on or turn off guest access to Microsoft Teams</span></span>
===================================================

<span data-ttu-id="a185a-104">作为 Office 365 管理员，你必须先启用来宾功能，你或贵组织的用户（具体来说是团队所有者）才能添加来宾。</span><span class="sxs-lookup"><span data-stu-id="a185a-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span>

<span data-ttu-id="a185a-105">在 Azure Active Directory 中设置来宾设置后，</span><span class="sxs-lookup"><span data-stu-id="a185a-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="a185a-106">更改在 Office 365 组织中生效需要 2 小时到 24 小时。</span><span class="sxs-lookup"><span data-stu-id="a185a-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="a185a-107">如果用户尝试向其团队中添加来宾时看到消息 "请联系你的管理员"，则很可能是来宾功能尚未启用或设置尚未生效。</span><span class="sxs-lookup"><span data-stu-id="a185a-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a185a-108">要启用来宾访问功能的完全体验，非常重要的一点是理解 Microsoft Teams、Azure Active Directory 和 Office 365 之间的核心授权相关性。</span><span class="sxs-lookup"><span data-stu-id="a185a-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="a185a-109">有关详细信息，请参阅[在 Microsoft Teams 中授权来宾访问](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="a185a-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="a185a-110">来宾访问与外部访问（联合身份验证）</span><span class="sxs-lookup"><span data-stu-id="a185a-110">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="a185a-111">在 Microsoft 团队管理中心配置来宾访问</span><span class="sxs-lookup"><span data-stu-id="a185a-111">Configure guest access in the Microsoft Teams admin center</span></span>

1.  <span data-ttu-id="a185a-112">登录到 Microsoft 团队管理中心。</span><span class="sxs-lookup"><span data-stu-id="a185a-112">Sign in to the Microsoft Teams admin center.</span></span>

2.  <span data-ttu-id="a185a-113">选择 "**组织范围设置** > "**来宾访问**。</span><span class="sxs-lookup"><span data-stu-id="a185a-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="a185a-114">将 "**允许 Microsoft 团队中的来宾访问**" 设置切换为 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="a185a-114">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="a185a-115">允许来宾访问开关设置为 "开"</span><span class="sxs-lookup"><span data-stu-id="a185a-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="a185a-116">将 "**呼叫**"、"**会议**" 和 "**消息传递**" 下的开关设置为 **"打开**" 或 "**关闭**"，具体取决于你希望来宾用户允许的功能。</span><span class="sxs-lookup"><span data-stu-id="a185a-116">Set the toggles under **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the capabilities you want to allow for guest users.</span></span>

    - <span data-ttu-id="a185a-117">**进行专用通话**–打开此设置可允许来宾**进行对等**呼叫。</span><span class="sxs-lookup"><span data-stu-id="a185a-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="a185a-118">**允许使用 IP 视频**-打开此**设置可允许来宾在其**呼叫和会议中使用视频。</span><span class="sxs-lookup"><span data-stu-id="a185a-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="a185a-119">**屏幕共享模式**-此设置控制来宾用户的屏幕共享的可用性。</span><span class="sxs-lookup"><span data-stu-id="a185a-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="a185a-120">将此设置启用为 "**已禁用**"，以删除来宾在团队中共享其屏幕的功能。</span><span class="sxs-lookup"><span data-stu-id="a185a-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="a185a-121">将此设置转换为 "**单应用程序**" 以允许共享单个应用程序。</span><span class="sxs-lookup"><span data-stu-id="a185a-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="a185a-122">将此设置转换为**整个屏幕**，以允许完成屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="a185a-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="a185a-123">**允许立即开会**–打开**此设置可允许来宾在 Microsoft**团队中使用 "立即开会" 功能。</span><span class="sxs-lookup"><span data-stu-id="a185a-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="a185a-124">**编辑已发送的邮件**-打开**此设置可**允许来宾编辑以前发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="a185a-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="a185a-125">**来宾可以删除已发送的邮件**-打开**此设置可**允许来宾删除以前发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="a185a-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="a185a-126">**聊天**-启用**此设置，让来宾能够在**团队中使用聊天功能。</span><span class="sxs-lookup"><span data-stu-id="a185a-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="a185a-127">**在对话中使用 giphy** -打开此**设置可允许来宾在对话**中使用 giphy。</span><span class="sxs-lookup"><span data-stu-id="a185a-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="a185a-128">Giphy 是一个联机数据库和搜索引擎，允许用户搜索和共享动态 GIF 文件。</span><span class="sxs-lookup"><span data-stu-id="a185a-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="a185a-129">每个 Giphy 都分配有一个内容分级。</span><span class="sxs-lookup"><span data-stu-id="a185a-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="a185a-130">**Giphy 内容分级**-从下拉列表中选择分级：</span><span class="sxs-lookup"><span data-stu-id="a185a-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="a185a-131">**允许所有内容**-无论内容分级如何，来宾都能够插入聊天中的所有 giphy。</span><span class="sxs-lookup"><span data-stu-id="a185a-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="a185a-132">"**中等**"-来宾将能够在聊天中插入 giphy，但将按成人内容适度限制。</span><span class="sxs-lookup"><span data-stu-id="a185a-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="a185a-133">**严格**-来宾将能够在聊天中插入 giphy，但将受到限制，无法插入成人内容。</span><span class="sxs-lookup"><span data-stu-id="a185a-133">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
    - <span data-ttu-id="a185a-134">**在对话中使用 meme** -打开此**设置可允许来宾在对话**中使用 meme。</span><span class="sxs-lookup"><span data-stu-id="a185a-134">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="a185a-135">**在对话中使用贴纸**-启用**此设置可允许来宾在对话**中使用贴纸。</span><span class="sxs-lookup"><span data-stu-id="a185a-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="a185a-136">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a185a-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="a185a-137">使用 PowerShell 打开或关闭来宾访问</span><span class="sxs-lookup"><span data-stu-id="a185a-137">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="a185a-138">从下载 Skype for Business Online PowerShell 模块https://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="a185a-138">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="a185a-139">将 PowerShell 会话连接到 Skype for Business Online 终结点。</span><span class="sxs-lookup"><span data-stu-id="a185a-139">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="a185a-140">检查您的配置， `AllowGuestUser`如果`$False`是，请使用[CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet 将其设置为`$True`。</span><span class="sxs-lookup"><span data-stu-id="a185a-140">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

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
<span data-ttu-id="a185a-141">您现在可以在组织的工作组中拥有来宾用户。</span><span class="sxs-lookup"><span data-stu-id="a185a-141">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="a185a-142">更多信息</span><span class="sxs-lookup"><span data-stu-id="a185a-142">More information</span></span>

<span data-ttu-id="a185a-143">观看以下视频，了解有关来宾访问的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="a185a-143">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="a185a-144">在 Microsoft Teams 中添加来宾</span><span class="sxs-lookup"><span data-stu-id="a185a-144">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
