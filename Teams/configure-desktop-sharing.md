---
title: 在 Microsoft Teams 中配置桌面共享
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 12/07/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 配置会议策略以让用户共享其桌面团队聊天或会议中
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 757f023d5f988e5a4f45c6274358aa51f3417ce0
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464457"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="3d051-103">在 Microsoft Teams 中配置桌面共享</span><span class="sxs-lookup"><span data-stu-id="3d051-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="3d051-104">桌面共享允许用户在会议或对话过程中演示屏幕或应用程序。</span><span class="sxs-lookup"><span data-stu-id="3d051-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="3d051-105">管理员可以配置屏幕中 Microsoft 团队以使用户可以共享整个屏幕、 应用程序或文件共享。</span><span class="sxs-lookup"><span data-stu-id="3d051-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="3d051-106">您可以让用户授予或请求控制、 允许共享 PowerPoint、 添加白板和允许共享的便笺。</span><span class="sxs-lookup"><span data-stu-id="3d051-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="3d051-107">您还可以配置是否匿名或外部用户可以请求对共享屏幕的控制权。</span><span class="sxs-lookup"><span data-stu-id="3d051-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="3d051-108">要配置屏幕共享，您创建新的会议策略，然后将其分配给您要管理的用户。</span><span class="sxs-lookup"><span data-stu-id="3d051-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="3d051-109">**在 Microsoft 团队管理中心**</span><span class="sxs-lookup"><span data-stu-id="3d051-109">**In the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="3d051-110">选择**会议** > **会议策略**。</span><span class="sxs-lookup"><span data-stu-id="3d051-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![选择会议策略](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="3d051-112">在**会议策略**页上，选择**新建策略**。</span><span class="sxs-lookup"><span data-stu-id="3d051-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![选择新策略](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="3d051-114">为您的策略指定唯一的标题，并输入的简要说明。</span><span class="sxs-lookup"><span data-stu-id="3d051-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="3d051-115">在**内容共享**下从下拉列表中选择**屏幕共享模式**:</span><span class="sxs-lookup"><span data-stu-id="3d051-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="3d051-116">**整个屏幕**– 允许共享整个桌面的用户。</span><span class="sxs-lookup"><span data-stu-id="3d051-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="3d051-117">**单个应用程序**– 允许用户限制屏幕共享单个活动应用程序。</span><span class="sxs-lookup"><span data-stu-id="3d051-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="3d051-118">**禁用**— 将会关闭屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="3d051-118">**Disabled** – Turns off screen sharing.</span></span>

    ![选择屏幕共享模式](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="3d051-120">打开或关闭以下设置：</span><span class="sxs-lookup"><span data-stu-id="3d051-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="3d051-121">**允许参与者授予或请求控制权**– 允许工作组成员授予或请求演示者的桌面或应用程序的控制权。</span><span class="sxs-lookup"><span data-stu-id="3d051-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="3d051-122">**允许外部参与者授予或请求控制**– 允许来宾和外部 （联盟） 的用户授予或请求演示者的桌面或应用程序的控制权。</span><span class="sxs-lookup"><span data-stu-id="3d051-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="3d051-123">**允许 PowerPoint 共享**-允许用户创建允许 PowerPoint 演示文稿上载和共享的会议。</span><span class="sxs-lookup"><span data-stu-id="3d051-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="3d051-124">**允许白板**– 允许用户共享的白板。</span><span class="sxs-lookup"><span data-stu-id="3d051-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="3d051-125">**允许共享的便笺**– 允许用户执行共享的便笺。</span><span class="sxs-lookup"><span data-stu-id="3d051-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="3d051-126">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3d051-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="3d051-127">使用 PowerShell 配置共享的桌面</span><span class="sxs-lookup"><span data-stu-id="3d051-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="3d051-128">[设置 CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet 还可用于控制桌面共享。</span><span class="sxs-lookup"><span data-stu-id="3d051-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="3d051-129">设置以下参数：</span><span class="sxs-lookup"><span data-stu-id="3d051-129">Set the following parameters:</span></span>

- <span data-ttu-id="3d051-130">说明</span><span class="sxs-lookup"><span data-stu-id="3d051-130">Description</span></span>
- <span data-ttu-id="3d051-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="3d051-131">ScreenSharingMode</span></span>
- <span data-ttu-id="3d051-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="3d051-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="3d051-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="3d051-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="3d051-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="3d051-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="3d051-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="3d051-135">AllowWhiteboard</span></span>
- <span data-ttu-id="3d051-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="3d051-136">AllowSharedNotes</span></span>

<span data-ttu-id="3d051-137">[了解有关使用 csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="3d051-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

