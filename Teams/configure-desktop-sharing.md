---
title: 在 Microsoft Teams 中配置桌面共享
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解如何配置会议策略，让用户在聊天或会议中共享Teams桌面。
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 35db312d7a4530f05db3cbad59d1b2b29a4e3847
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856461"
---
# <a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="5fefb-103">在 Microsoft Teams 中配置桌面共享</span><span class="sxs-lookup"><span data-stu-id="5fefb-103">Configure desktop sharing in Microsoft Teams</span></span>

<span data-ttu-id="5fefb-104">桌面共享让用户可以在会议或聊天过程中呈现屏幕或应用。</span><span class="sxs-lookup"><span data-stu-id="5fefb-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="5fefb-105">管理员可在 Microsoft Teams 中配置屏幕共享，让用户共享整个屏幕、某个应用或文件。</span><span class="sxs-lookup"><span data-stu-id="5fefb-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="5fefb-106">你可以让用户提供或请求控制权、允许 PowerPoint 共享、添加白板以及允许共享笔记。</span><span class="sxs-lookup"><span data-stu-id="5fefb-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="5fefb-107">你还可以配置匿名或外部用户是否可以请求共享屏幕的控制权。</span><span class="sxs-lookup"><span data-stu-id="5fefb-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span> <span data-ttu-id="5fefb-108">Teams 会议的外部与会者可分为以下几类:</span><span class="sxs-lookup"><span data-stu-id="5fefb-108">External participants in Teams meetings can be categorized as follows:</span></span>

- <span data-ttu-id="5fefb-109">匿名用户</span><span class="sxs-lookup"><span data-stu-id="5fefb-109">Anonymous user</span></span>
- <span data-ttu-id="5fefb-110">来宾用户</span><span class="sxs-lookup"><span data-stu-id="5fefb-110">Guest users</span></span>
- <span data-ttu-id="5fefb-111">B2B 用户</span><span class="sxs-lookup"><span data-stu-id="5fefb-111">B2B user</span></span>
- <span data-ttu-id="5fefb-112">联合用户</span><span class="sxs-lookup"><span data-stu-id="5fefb-112">Federated user</span></span>

<span data-ttu-id="5fefb-113">若要配置屏幕共享，请创建新的会议策略，然后将其分配给要管理的用户。</span><span class="sxs-lookup"><span data-stu-id="5fefb-113">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="5fefb-114">**在 [Microsoft Teams 管理中心](https://admin.teams.microsoft.com/)**</span><span class="sxs-lookup"><span data-stu-id="5fefb-114">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="5fefb-115">选择“**会议**” > “**会议策略**”。</span><span class="sxs-lookup"><span data-stu-id="5fefb-115">Select **Meetings** > **Meeting policies**.</span></span>

    ![选择的会议策略](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="5fefb-117">在"**会议策略"** 页面上，选择"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="5fefb-117">On the **Meeting policies** page, select **Add**.</span></span>

    !["会议策略"消息](media/addMeeting.png)

3. <span data-ttu-id="5fefb-119">为策略提供唯一的标题，并输入简要说明。</span><span class="sxs-lookup"><span data-stu-id="5fefb-119">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="5fefb-120">在“**内容共享**”下，从下拉列表中选择一种 **屏幕共享模式**：</span><span class="sxs-lookup"><span data-stu-id="5fefb-120">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="5fefb-121">**整个屏幕** - 让用户共享其整个桌面。</span><span class="sxs-lookup"><span data-stu-id="5fefb-121">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="5fefb-122">**单个应用程序** - 允许用户将屏幕共享限制为单个活动的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5fefb-122">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="5fefb-123">**已禁用** - 关闭屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="5fefb-123">**Disabled** – Turns off screen sharing.</span></span>

    ![共享模式选项](media/configure-desktop-sharing-image3.png)

  > [!Note]
  > <span data-ttu-id="5fefb-125">你不必启用呼叫策略，用户就可使用聊天中的屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="5fefb-125">You don't have to enable the calling policy in order for users to use screen share from chat.</span></span> <span data-ttu-id="5fefb-126">但是，他们的音频将关闭，直到他们自行取消静音。</span><span class="sxs-lookup"><span data-stu-id="5fefb-126">However, their audio is turned off until they unmute themselves.</span></span> <span data-ttu-id="5fefb-127">此外，共享屏幕的用户可以单击" **添加音频"** 以启用音频。</span><span class="sxs-lookup"><span data-stu-id="5fefb-127">In addition, the user sharing the screen can click **Add Audio** to enable audio.</span></span> <span data-ttu-id="5fefb-128">如果呼叫策略被禁用，用户将无法从聊天会话将音频添加到屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="5fefb-128">If the calling policy is disabled, users won't be able to add audio to the screen share from a chat session.</span></span>

5. <span data-ttu-id="5fefb-129">打开或关闭以下设置：</span><span class="sxs-lookup"><span data-stu-id="5fefb-129">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="5fefb-130">**允许参与者授予或请求控制权** – 允许团队成员授予或请求控制演示者的桌面或应用程序。</span><span class="sxs-lookup"><span data-stu-id="5fefb-130">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="5fefb-131">**允许外部参与者授予或请求控制权** – 这是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="5fefb-131">**Allow an external participant to give or request control** – This is a per-user policy.</span></span> <span data-ttu-id="5fefb-132">无论会议组织者设置了什么，组织是否为用户设置了这个功能，都无法控制外部参与者的行为。</span><span class="sxs-lookup"><span data-stu-id="5fefb-132">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="5fefb-133">该参数控制是否可以让外部参与者控制或请求控制共享者的屏幕，这取决于共享者在其组织的会议策略中设置的内容。</span><span class="sxs-lookup"><span data-stu-id="5fefb-133">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span>
    - <span data-ttu-id="5fefb-134">**允许 PowerPoint 共享** - 允许用户创建可上传和共享 PowerPoint 演示文稿的会议。</span><span class="sxs-lookup"><span data-stu-id="5fefb-134">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="5fefb-135">**允许白板** - 允许用户共享白板。</span><span class="sxs-lookup"><span data-stu-id="5fefb-135">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="5fefb-136">**允许共享笔记** - 允许用户记录共享笔记。</span><span class="sxs-lookup"><span data-stu-id="5fefb-136">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="5fefb-137">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="5fefb-137">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="5fefb-138">使用 PowerShell 配置共享桌面</span><span class="sxs-lookup"><span data-stu-id="5fefb-138">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="5fefb-139">你还可以使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet 来控制桌面共享。</span><span class="sxs-lookup"><span data-stu-id="5fefb-139">You can also use the [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="5fefb-140">设置以下参数：</span><span class="sxs-lookup"><span data-stu-id="5fefb-140">Set the following parameters:</span></span>

- <span data-ttu-id="5fefb-141">Description</span><span class="sxs-lookup"><span data-stu-id="5fefb-141">Description</span></span>
- <span data-ttu-id="5fefb-142">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="5fefb-142">ScreenSharingMode</span></span>
- <span data-ttu-id="5fefb-143">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="5fefb-143">AllowPrivateCalling</span></span>
- <span data-ttu-id="5fefb-144">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="5fefb-144">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="5fefb-145">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="5fefb-145">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="5fefb-146">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="5fefb-146">AllowPowerPointSharing</span></span>
- <span data-ttu-id="5fefb-147">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="5fefb-147">AllowWhiteboard</span></span>
- <span data-ttu-id="5fefb-148">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="5fefb-148">AllowSharedNotes</span></span>

<span data-ttu-id="5fefb-149">[了解有关使用 csTeamsMeetingPolicy cmdlet 的详细信息](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="5fefb-149">[Learn more about using the csTeamsMeetingPolicy cmdlet](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>