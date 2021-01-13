---
title: 在 Skype for Business Server 中管理会议策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 摘要：了解如何在 Skype for Business Server 中管理会议策略。
ms.openlocfilehash: 3ad59f186ccc4bebdefae1a6bfefdf04e9bf6851
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835272"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="5d5e7-103">在 Skype for Business Server 中管理会议策略</span><span class="sxs-lookup"><span data-stu-id="5d5e7-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="5d5e7-104">**摘要：** 了解如何在 Skype for Business Server 中管理会议策略。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="5d5e7-105">本主题介绍如何管理会议策略。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="5d5e7-106">若要详细了解如何计划和部署会议，请参阅 Plan for [conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and Deploy [conferencing in Skype for Business Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="5d5e7-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="5d5e7-107">会议策略允许你定义各种安排和参与选项，范围从会议是否可以包括 IP 音频和视频到可参与会议的最大人数。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-107">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="5d5e7-108">可以使用会议策略来管理会议的安全性、带宽和法律方面。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-108">You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="5d5e7-109">可以在三个级别定义会议策略：global 作用域、site 作用域和 user 作用域。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-109">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="5d5e7-110">可以为不同范围的作用域中的特定用户应用设置。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-110">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="5d5e7-111">如果将策略分配给用户，则优先使用这些设置。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-111">If you assign a policy to a user, those settings take precedence.</span></span> <span data-ttu-id="5d5e7-112">如果未分配用户策略，则应用站点设置。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-112">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="5d5e7-113">如果未应用用户策略或站点策略，则全局策略会提供默认设置。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-113">If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="5d5e7-p104">默认情况下，全局策略已存在，因此不能创建新的全局策略。也不能删除现有全局策略，但可以更改现有全局策略以自定义默认设置。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-p104">A global policy exists by default, so you cannot create a new global policy. You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="5d5e7-116">使用 Skype for Business Server 控制面板管理会议策略</span><span class="sxs-lookup"><span data-stu-id="5d5e7-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="5d5e7-117">若要使用 Skype for Business Server 控制面板管理会议策略：</span><span class="sxs-lookup"><span data-stu-id="5d5e7-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="5d5e7-118">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="5d5e7-119">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="5d5e7-120">在左侧导航栏中，单击 **"会议"，** 然后单击 **"会议策略"。**</span><span class="sxs-lookup"><span data-stu-id="5d5e7-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="5d5e7-121">使用 Skype for Business Server 命令行管理程序管理会议策略</span><span class="sxs-lookup"><span data-stu-id="5d5e7-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="5d5e7-122">若要使用 Skype for Business Server 命令行管理程序管理会议，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5d5e7-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="5d5e7-123">**会议策略设置**</span><span class="sxs-lookup"><span data-stu-id="5d5e7-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="5d5e7-124">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="5d5e7-124">**Cmdlet**</span></span>|<span data-ttu-id="5d5e7-125">**说明**</span><span class="sxs-lookup"><span data-stu-id="5d5e7-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="5d5e7-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="5d5e7-126">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="5d5e7-127">返回有关已配置为在组织中使用的会议策略的信息。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="5d5e7-128">Grant-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="5d5e7-128">Grant-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="5d5e7-129">在每用户范围分配会议策略。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="5d5e7-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="5d5e7-130">New-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="5d5e7-131">创建在组织中使用的新会议策略。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="5d5e7-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="5d5e7-132">Remove-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="5d5e7-133">删除指定的会议策略。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="5d5e7-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="5d5e7-134">Set-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="5d5e7-135">修改现有的会议策略。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-135">Modifies an existing conferencing policy.</span></span>  <br/> |
   

