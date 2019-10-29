---
title: 打开或关闭对 Microsoft 团队的来宾访问
author: lanachin
ms.author: v-lanac
manager: serdars
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
ms.openlocfilehash: 20971fd985d4512e8a9bf00db23092f1a6e44702
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753347"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="82f3a-103">打开或关闭对 Microsoft 团队的来宾访问</span><span class="sxs-lookup"><span data-stu-id="82f3a-103">Turn on or turn off guest access to Microsoft Teams</span></span>
===================================================

<span data-ttu-id="82f3a-104">默认情况下，来宾访问处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="82f3a-104">By default, guest access is turned off.</span></span> <span data-ttu-id="82f3a-105">作为 Office 365 管理员，必须先为团队启用来宾访问权限，管理员或团队所有者才能添加来宾。</span><span class="sxs-lookup"><span data-stu-id="82f3a-105">As the Office 365 admin, you must turn on guest access for Teams before the admin or team owners can add guests.</span></span> <span data-ttu-id="82f3a-106">若要启用来宾访问，请使用[来宾访问清单](guest-access-checklist.md)。</span><span class="sxs-lookup"><span data-stu-id="82f3a-106">To turn on guest access, use the [Guest access checklist](guest-access-checklist.md).</span></span> 

<span data-ttu-id="82f3a-107">启用来宾访问后，更改将花费2-24 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="82f3a-107">After you turn on guest access, it takes 2-24 hours for the changes to take effect.</span></span> <span data-ttu-id="82f3a-108">如果用户尝试向其团队中添加来宾时看到消息 "请联系你的管理员"，则很可能是来宾访问尚未打开，或者设置尚未生效。</span><span class="sxs-lookup"><span data-stu-id="82f3a-108">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82f3a-109">打开来宾访问取决于 Azure Active Directory、Office 365、SharePoint Online 和团队中的设置。</span><span class="sxs-lookup"><span data-stu-id="82f3a-109">Turning on guest access depends on settings in Azure Active Directory, Office 365, SharePoint Online, and Teams.</span></span> <span data-ttu-id="82f3a-110">有关详细信息，请参阅[授权团队中的来宾访问](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="82f3a-110">For more information, see [Authorize guest access in Teams](Teams-dependencies.md).</span></span>



## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="82f3a-111">配置团队管理中心中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="82f3a-111">Configure guest access in the Teams admin center</span></span>

1.  <span data-ttu-id="82f3a-112">登录到 Microsoft 团队管理中心。</span><span class="sxs-lookup"><span data-stu-id="82f3a-112">Sign in to the Microsoft Teams admin center.</span></span>

2.  <span data-ttu-id="82f3a-113">选择 "**组织范围设置** > "**来宾访问**。</span><span class="sxs-lookup"><span data-stu-id="82f3a-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="82f3a-114">将 "**允许 Microsoft 团队中的来宾访问**" 设置为 **"打开"**。</span><span class="sxs-lookup"><span data-stu-id="82f3a-114">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="82f3a-115">允许来宾访问开关设置为 "开"</span><span class="sxs-lookup"><span data-stu-id="82f3a-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="82f3a-116">在 "**呼叫**、**会议**和**消息**" 下，为每个功能选择 **"开" 或 "** **关**"，具体取决于您希望来宾用户允许的功能。</span><span class="sxs-lookup"><span data-stu-id="82f3a-116">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

    - <span data-ttu-id="82f3a-117">**进行专用通话**–打开此设置可允许来宾**进行对等**呼叫。</span><span class="sxs-lookup"><span data-stu-id="82f3a-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="82f3a-118">**允许使用 IP 视频**-打开此**设置可允许来宾在其**呼叫和会议中使用视频。</span><span class="sxs-lookup"><span data-stu-id="82f3a-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="82f3a-119">**屏幕共享模式**-此设置控制来宾用户的屏幕共享的可用性。</span><span class="sxs-lookup"><span data-stu-id="82f3a-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="82f3a-120">将此设置启用为 "**已禁用**"，以删除来宾在团队中共享其屏幕的功能。</span><span class="sxs-lookup"><span data-stu-id="82f3a-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="82f3a-121">将此设置转换为 "**单应用程序**" 以允许共享单个应用程序。</span><span class="sxs-lookup"><span data-stu-id="82f3a-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="82f3a-122">将此设置转换为**整个屏幕**，以允许完成屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="82f3a-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="82f3a-123">**允许立即开会**–打开**此设置可允许来宾在 Microsoft**团队中使用 "立即开会" 功能。</span><span class="sxs-lookup"><span data-stu-id="82f3a-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="82f3a-124">**编辑已发送的邮件**-打开**此设置可**允许来宾编辑以前发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="82f3a-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="82f3a-125">**来宾可以删除已发送的邮件**-打开**此设置可**允许来宾删除以前发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="82f3a-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="82f3a-126">**聊天**-启用**此设置，让来宾能够在**团队中使用聊天功能。</span><span class="sxs-lookup"><span data-stu-id="82f3a-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="82f3a-127">**在对话中使用 giphy** -打开此**设置可允许来宾在对话**中使用 giphy。</span><span class="sxs-lookup"><span data-stu-id="82f3a-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="82f3a-128">Giphy 是一个联机数据库和搜索引擎，允许用户搜索和共享动态 GIF 文件。</span><span class="sxs-lookup"><span data-stu-id="82f3a-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="82f3a-129">每个 Giphy 都分配有一个内容分级。</span><span class="sxs-lookup"><span data-stu-id="82f3a-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="82f3a-130">**Giphy 内容分级**-从下拉列表中选择分级：</span><span class="sxs-lookup"><span data-stu-id="82f3a-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="82f3a-131">**允许所有内容**-无论内容分级如何，来宾都能够插入聊天中的所有 giphy。</span><span class="sxs-lookup"><span data-stu-id="82f3a-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="82f3a-132">"**中等**"-来宾将能够在聊天中插入 giphy，但将按成人内容适度限制。</span><span class="sxs-lookup"><span data-stu-id="82f3a-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="82f3a-133">**严格**-来宾将能够在聊天中插入 giphy，但将受到限制，无法插入成人内容。</span><span class="sxs-lookup"><span data-stu-id="82f3a-133">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
    - <span data-ttu-id="82f3a-134">**在对话中使用 meme** -打开此**设置可允许来宾在对话**中使用 meme。</span><span class="sxs-lookup"><span data-stu-id="82f3a-134">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="82f3a-135">**在对话中使用贴纸**-启用**此设置可允许来宾在对话**中使用贴纸。</span><span class="sxs-lookup"><span data-stu-id="82f3a-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="82f3a-136">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="82f3a-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="82f3a-137">使用 PowerShell 打开或关闭来宾访问</span><span class="sxs-lookup"><span data-stu-id="82f3a-137">Use PowerShell to turn guest access on or off</span></span>
<span data-ttu-id="82f3a-138">已阅读["使用 PowerShell" 打开或关闭来宾访问](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)</span><span class="sxs-lookup"><span data-stu-id="82f3a-138">Read [Use PowerShell to turn guest access on or off](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)</span></span>


## <a name="video-adding-guests-in-teams"></a><span data-ttu-id="82f3a-139">视频：在团队中添加来宾</span><span class="sxs-lookup"><span data-stu-id="82f3a-139">Video: Adding guests in Teams</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="82f3a-140">在 Microsoft Teams 中添加来宾</span><span class="sxs-lookup"><span data-stu-id="82f3a-140">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 


## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="82f3a-141">外部访问（联盟）与来宾访问</span><span class="sxs-lookup"><span data-stu-id="82f3a-141">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]