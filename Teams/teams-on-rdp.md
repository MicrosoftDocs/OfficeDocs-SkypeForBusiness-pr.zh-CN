---
title: 将 Teams 与远程桌面服务一同使用
author: cichur
ms.author: v-cichur
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何将 Microsoft Teams 与远程桌面服务一同使用。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7090aac3c5e7ff724a079e7f9d9ffe9d712cd447
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119091"
---
# <a name="teams-in-remote-desktop-services"></a><span data-ttu-id="e7ec1-103">远程桌面服务中的 Teams</span><span class="sxs-lookup"><span data-stu-id="e7ec1-103">Teams in Remote Desktop Services</span></span>

<span data-ttu-id="e7ec1-104">本文介绍在 RDS 环境远程桌面服务 (Microsoft Teams) 限制。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-104">This article describes the requirements and limitations for using Microsoft Teams in a remote desktop services (RDS) environment.</span></span>

## <a name="what-is-rds"></a><span data-ttu-id="e7ec1-105">什么是 RDS？</span><span class="sxs-lookup"><span data-stu-id="e7ec1-105">What is RDS?</span></span>

<span data-ttu-id="e7ec1-106">远程桌面 (RDS) 是构建虚拟化解决方案，满足每个最终客户需求的首选平台。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-106">Remote Desktop Services (RDS) is the platform of choice for building virtualization solutions for every end customer need.</span></span> <span data-ttu-id="e7ec1-107">RDS 允许交付单个虚拟化应用程序、提供安全的移动和远程桌面访问，以及使最终用户能够从云中运行其应用程序和桌面。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-107">RDS lets you deliver individual virtualized applications, provide secure mobile and remote desktop access, and provide end users the ability to run their applications and desktops from the cloud.</span></span>

<span data-ttu-id="e7ec1-108">RDS 提供部署灵活性、成本效益和可扩展性。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-108">RDS offers deployment flexibility, cost efficiency, and extensibility.</span></span> <span data-ttu-id="e7ec1-109">RDS 通过各种部署选项提供，包括适用于本地部署的 Windows Server 2016、用于云部署的 Microsoft Azure，以及一系列可靠的合作伙伴解决方案。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-109">RDS is delivered through a variety of deployment options, including Windows Server 2016 for on-premises deployments, Microsoft Azure for cloud deployments, and a robust array of partner solutions.</span></span>
<span data-ttu-id="e7ec1-110">根据环境和首选项，可以将 RDS 解决方案设置为基于会话的虚拟化，作为 VDI (虚拟) </span><span class="sxs-lookup"><span data-stu-id="e7ec1-110">Depending on your environment and preferences, you can set up the RDS solution for session-based virtualization, as a virtual desktop infrastructure (VDI)</span></span>

<span data-ttu-id="e7ec1-111">目前，远程桌面服务环境中 Teams 支持协作和聊天功能。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-111">Currently, Teams in a remote desktop services environment is available with support for collaboration and chat functionality.</span></span> <span data-ttu-id="e7ec1-112">若要确保获得最佳用户体验，请遵循本文中的指导。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-112">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-rds-with-chat-and-collaboration"></a><span data-ttu-id="e7ec1-113">RDS 上的 Teams 与聊天和协作</span><span class="sxs-lookup"><span data-stu-id="e7ec1-113">Teams on RDS with chat and collaboration</span></span>

<span data-ttu-id="e7ec1-114">如果你的组织只想使用 Teams 中的聊天和协作功能，你可以设置用户级策略以关闭 Teams 中的呼叫和会议功能。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-114">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="e7ec1-115">设置策略以关闭呼叫和会议功能</span><span class="sxs-lookup"><span data-stu-id="e7ec1-115">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="e7ec1-116">可以使用 Microsoft Teams 管理中心或 PowerShell 设置策略。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-116">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="e7ec1-117">传播策略更改 (可能需要) 几个小时。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-117">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="e7ec1-118">如果未立即看到给定帐户的更改，请在几小时后重试。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-118">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="e7ec1-119">[**调用策略**](teams-calling-policy.md)：Teams 包括内置的 DisallowCalling 调用策略，其中所有调用功能都已关闭。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-119">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="e7ec1-120">将 DisallowCalling 策略分配给组织中在虚拟化环境中使用 Teams 的所有用户。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-120">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="e7ec1-121">[**会议策略**](meeting-policies-in-teams.md)：Teams 包括内置的 AllOff 会议策略，其中所有会议功能都已关闭。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-121">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="e7ec1-122">将 AllOff 策略分配给组织中在虚拟化环境中使用 Teams 的所有用户。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-122">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e7ec1-123">使用 Microsoft Teams 管理中心分配策略</span><span class="sxs-lookup"><span data-stu-id="e7ec1-123">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="e7ec1-124">将 DisallowCalling 调用策略和 AllOff 会议策略分配给用户：</span><span class="sxs-lookup"><span data-stu-id="e7ec1-124">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="e7ec1-125">在 Microsoft Teams 管理中心的左侧导航栏中，转到"用户 **"。**</span><span class="sxs-lookup"><span data-stu-id="e7ec1-125">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="e7ec1-126">通过选择用户名左侧选择用户，然后选择"编辑 **设置"。**</span><span class="sxs-lookup"><span data-stu-id="e7ec1-126">Select the user by selecting to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="e7ec1-127">执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e7ec1-127">Do the following steps:</span></span>

    <span data-ttu-id="e7ec1-128">a.</span><span class="sxs-lookup"><span data-stu-id="e7ec1-128">a.</span></span>  <span data-ttu-id="e7ec1-129">在 **"调用策略"** 下，选择 **"DisallowCalling"。**</span><span class="sxs-lookup"><span data-stu-id="e7ec1-129">Under **Calling policy**, select **DisallowCalling**.</span></span>

    <span data-ttu-id="e7ec1-130">b.</span><span class="sxs-lookup"><span data-stu-id="e7ec1-130">b.</span></span>  <span data-ttu-id="e7ec1-131">在"**会议策略"** 下，选择 **"AllOff"。**</span><span class="sxs-lookup"><span data-stu-id="e7ec1-131">Under **Meeting policy**, select **AllOff**.</span></span>

4. <span data-ttu-id="e7ec1-132">选择"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="e7ec1-132">Select **Apply**.</span></span>

<span data-ttu-id="e7ec1-133">若要一次向多个用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e7ec1-133">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="e7ec1-134">在 Microsoft Teams 管理中心的左侧导航栏中，转到“**用户**”，然后搜索用户或筛选视图，以显示所需的用户。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-134">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="e7ec1-135">在 **&#x2713;**（复选标记）列，选择用户。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-135">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="e7ec1-136">若要选择所有用户，请选择&#x2713; (顶部的) "复选框。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-136">To select all users, select the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="e7ec1-137">选择 **"编辑** 设置"，进行您需要的更改，然后选择"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="e7ec1-137">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="e7ec1-138">或者，也可以执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e7ec1-138">Or, you can also do the following steps:</span></span>

1. <span data-ttu-id="e7ec1-139">在 Microsoft Teams 管理中心的左侧导航栏中，转到要分配的策略。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-139">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="e7ec1-140">例如：</span><span class="sxs-lookup"><span data-stu-id="e7ec1-140">For example:</span></span>

    - <span data-ttu-id="e7ec1-141">转到 **"语音**  >  **呼叫策略"，** 然后选择 **"DisallowCalling"。**</span><span class="sxs-lookup"><span data-stu-id="e7ec1-141">Go to **Voice** > **Calling policies**, and then select **DisallowCalling**.</span></span>
    - <span data-ttu-id="e7ec1-142">转到"**会议**  >  **会议策略"，** 然后选择 **"AllOff"。**</span><span class="sxs-lookup"><span data-stu-id="e7ec1-142">Go to **Meetings** > **Meeting policies**, and then select **AllOff**.</span></span>

2. <span data-ttu-id="e7ec1-143">选择“管理用户”。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-143">Select **Manage users**.</span></span>
3. <span data-ttu-id="e7ec1-144">在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-144">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="e7ec1-145">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-145">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="e7ec1-146">添加完用户后，选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="e7ec1-146">When you're finished adding users, select **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="e7ec1-147">使用 PowerShell 分配策略</span><span class="sxs-lookup"><span data-stu-id="e7ec1-147">Assign policies using PowerShell</span></span>

<span data-ttu-id="e7ec1-148">以下示例演示如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 将 DisallowCalling 调用策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-148">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="e7ec1-149">若要详细了解使用 PowerShell 管理调用策略，请参阅[Set-CsTeamsCallingPolicy。](/powershell/module/skype/set-csteamscallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="e7ec1-149">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="e7ec1-150">以下示例演示如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 将 AllOff 会议策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="e7ec1-150">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="e7ec1-151">若要详细了解使用 PowerShell 管理会议策略，请参阅[Set-CsTeamsMeetingPolicy。](/powershell/module/skype/set-csteamsmeetingpolicy)</span><span class="sxs-lookup"><span data-stu-id="e7ec1-151">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>