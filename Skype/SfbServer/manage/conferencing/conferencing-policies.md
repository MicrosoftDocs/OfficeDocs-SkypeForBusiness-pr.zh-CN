---
title: Skype 中的会议策略管理业务服务器 （英文）
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 摘要： 了解如何为业务服务器管理 Skype 中的会议策略。
ms.openlocfilehash: d5fed0c6615747069d71015fca33144ca41dd64b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20986655"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="09e45-103">Skype 中的会议策略管理业务服务器 （英文）</span><span class="sxs-lookup"><span data-stu-id="09e45-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="09e45-104">**摘要：** 了解如何为业务服务器管理 Skype 中的会议策略。</span><span class="sxs-lookup"><span data-stu-id="09e45-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="09e45-105">本主题描述如何管理会议策略。</span><span class="sxs-lookup"><span data-stu-id="09e45-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="09e45-106">有关如何规划和部署会议的详细信息，请参阅[Plan for Business Server 的 Skype 中的会议](../../plan-your-deployment/conferencing/conferencing.md)和[Skype 业务服务器中的部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="09e45-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="09e45-p102">会议策略允许你定义各种安排和参与选项，包括从会议能否包括 IP 音频和视频，到可参与会议的最大人数。可以使用会议策略管理会议的安全性、带宽以及法律发面的问题。</span><span class="sxs-lookup"><span data-stu-id="09e45-p102">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend. You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="09e45-p103">可以在三个级别定义会议策略：全局作用域、站点作用域和用户作用域。可以为不同范围的作用域中的特定用户应用设置。如果为用户分配策略，则优先应用这些设置。如果未分配用户策略，则应用站点设置。如果未应用用户策略或站点策略，则全局策略会提供默认设置。</span><span class="sxs-lookup"><span data-stu-id="09e45-p103">You can define conferencing policy on three levels: global scope, site scope, and user scope. Settings apply to a specific user from the narrowest scope to the widest scope. If you assign a policy to a user, those settings take precedence. If you do not assign a user policy, site settings apply. If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="09e45-p104">默认情况下，全局策略已存在，因此不能创建新的全局策略。也不能删除现有全局策略，但可以更改现有全局策略以自定义默认设置。</span><span class="sxs-lookup"><span data-stu-id="09e45-p104">A global policy exists by default, so you cannot create a new global policy. You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="09e45-116">使用适用于业务 Server Control Panel Skype 管理会议策略</span><span class="sxs-lookup"><span data-stu-id="09e45-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="09e45-117">使用适用于业务 Server Control Panel Skype 管理会议策略：</span><span class="sxs-lookup"><span data-stu-id="09e45-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="09e45-118">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="09e45-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="09e45-119">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="09e45-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="09e45-120">在左侧导航栏中，单击“**会议**”，然后单击“**会议策略**”。</span><span class="sxs-lookup"><span data-stu-id="09e45-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="09e45-121">使用 Skype 业务 Server Management Shell 管理会议策略</span><span class="sxs-lookup"><span data-stu-id="09e45-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="09e45-122">若要使用 Skype 业务 Server Management Shell 管理会议，请使用以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="09e45-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="09e45-123">**会议策略设置**</span><span class="sxs-lookup"><span data-stu-id="09e45-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="09e45-124">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="09e45-124">**Cmdlet**</span></span>|<span data-ttu-id="09e45-125">**说明**</span><span class="sxs-lookup"><span data-stu-id="09e45-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="09e45-126">Get-csconferencingpolicy</span><span class="sxs-lookup"><span data-stu-id="09e45-126">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="09e45-127">返回有关已配置为在组织中使用的会议策略的信息。</span><span class="sxs-lookup"><span data-stu-id="09e45-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="09e45-128">Grant-csconferencingpolicy</span><span class="sxs-lookup"><span data-stu-id="09e45-128">Grant-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="09e45-129">在每用户范围分配会议策略。</span><span class="sxs-lookup"><span data-stu-id="09e45-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="09e45-130">New-csconferencingpolicy</span><span class="sxs-lookup"><span data-stu-id="09e45-130">New-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="09e45-131">创建在组织中使用的新会议策略。</span><span class="sxs-lookup"><span data-stu-id="09e45-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="09e45-132">Remove-csconferencingpolicy</span><span class="sxs-lookup"><span data-stu-id="09e45-132">Remove-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="09e45-133">删除指定的会议策略。</span><span class="sxs-lookup"><span data-stu-id="09e45-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="09e45-134">Set-csconferencingpolicy</span><span class="sxs-lookup"><span data-stu-id="09e45-134">Set-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="09e45-135">修改现有会议策略。</span><span class="sxs-lookup"><span data-stu-id="09e45-135">Modifies an existing conferencing policy.</span></span>  <br/> |
   

