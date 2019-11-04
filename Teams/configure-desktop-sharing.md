---
title: 在 Microsoft Teams 中配置桌面共享
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 配置会议策略以允许用户在团队聊天或会议中共享其桌面
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 99c6e2a5adb9d0f9a4b4e3f6f17b7484bda96a74
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "37516882"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="6836a-103">在 Microsoft Teams 中配置桌面共享</span><span class="sxs-lookup"><span data-stu-id="6836a-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="6836a-104">桌面共享允许用户在会议或聊天期间演示屏幕或应用。</span><span class="sxs-lookup"><span data-stu-id="6836a-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="6836a-105">管理员可以在 Microsoft 团队中配置屏幕共享，让用户共享整个屏幕、应用或文件。</span><span class="sxs-lookup"><span data-stu-id="6836a-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="6836a-106">你可以让用户提供或请求控制、允许 PowerPoint 共享、添加白板以及允许共享笔记。</span><span class="sxs-lookup"><span data-stu-id="6836a-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="6836a-107">你还可以配置匿名用户或外部用户是否可以请求共享屏幕的控制权。</span><span class="sxs-lookup"><span data-stu-id="6836a-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="6836a-108">若要配置屏幕共享，请创建新的会议策略，然后将其分配给要管理的用户。</span><span class="sxs-lookup"><span data-stu-id="6836a-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="6836a-109">**在 Microsoft 团队管理中心**</span><span class="sxs-lookup"><span data-stu-id="6836a-109">**In the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="6836a-110">选择 "**会议** > **会议策略**"。</span><span class="sxs-lookup"><span data-stu-id="6836a-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![显示所选会议策略的屏幕截图](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="6836a-112">在 "**会议策略**" 页面上，选择 "**新建策略**"。</span><span class="sxs-lookup"><span data-stu-id="6836a-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![显示会议策略消息的屏幕截图](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="6836a-114">为你的策略提供一个唯一的标题，并输入简短说明。</span><span class="sxs-lookup"><span data-stu-id="6836a-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="6836a-115">在 "**内容共享**" 下，从下拉列表中选择**屏幕共享模式**：</span><span class="sxs-lookup"><span data-stu-id="6836a-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="6836a-116">**整个屏幕**-允许用户共享其整个桌面。</span><span class="sxs-lookup"><span data-stu-id="6836a-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="6836a-117">**单个应用程序**-允许用户将屏幕共享限制在单个活动应用程序中。</span><span class="sxs-lookup"><span data-stu-id="6836a-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="6836a-118">**已禁用**–关闭屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="6836a-118">**Disabled** – Turns off screen sharing.</span></span>

    ![显示共享模式选项的屏幕截图](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="6836a-120">打开或关闭以下设置：</span><span class="sxs-lookup"><span data-stu-id="6836a-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="6836a-121">**允许参与者授予或请求控制**–允许团队成员授予或请求演示者的桌面或应用程序的控制权。</span><span class="sxs-lookup"><span data-stu-id="6836a-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="6836a-122">**允许外部参与者授予或请求控制**-允许来宾和外部（联合）用户向演示者的桌面或应用程序提供或请求控制。</span><span class="sxs-lookup"><span data-stu-id="6836a-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="6836a-123">**允许 powerpoint 共享**-允许用户创建允许上载和共享 PowerPoint 演示文稿的会议。</span><span class="sxs-lookup"><span data-stu-id="6836a-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="6836a-124">**允许使用白板**-允许用户共享白板。</span><span class="sxs-lookup"><span data-stu-id="6836a-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="6836a-125">**允许共享笔记**-使用户可以拍摄共享笔记。</span><span class="sxs-lookup"><span data-stu-id="6836a-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="6836a-126">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="6836a-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="6836a-127">使用 PowerShell 配置共享桌面</span><span class="sxs-lookup"><span data-stu-id="6836a-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="6836a-128">你还可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet 控制桌面共享。</span><span class="sxs-lookup"><span data-stu-id="6836a-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="6836a-129">设置以下参数：</span><span class="sxs-lookup"><span data-stu-id="6836a-129">Set the following parameters:</span></span>

- <span data-ttu-id="6836a-130">说明</span><span class="sxs-lookup"><span data-stu-id="6836a-130">Description</span></span>
- <span data-ttu-id="6836a-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="6836a-131">ScreenSharingMode</span></span>
- <span data-ttu-id="6836a-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="6836a-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="6836a-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="6836a-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="6836a-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="6836a-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="6836a-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="6836a-135">AllowWhiteboard</span></span>
- <span data-ttu-id="6836a-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="6836a-136">AllowSharedNotes</span></span>

<span data-ttu-id="6836a-137">[了解有关使用 csTeamsMeetingPolicy cmdlet 的详细信息](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="6836a-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

