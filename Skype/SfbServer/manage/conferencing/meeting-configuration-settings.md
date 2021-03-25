---
title: 在 Skype for Business Server 中管理会议配置设置
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
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 摘要：了解如何在 Skype for Business Server 中管理会议配置设置。
ms.openlocfilehash: 1e6ef11992a547456d2a971c2f8de6f3097b166e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119431"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="d07d5-103">在 Skype for Business Server 中管理会议配置设置</span><span class="sxs-lookup"><span data-stu-id="d07d5-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="d07d5-104">**摘要：** 了解如何在 Skype for Business Server 中管理会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="d07d5-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="d07d5-105">本主题介绍如何管理会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="d07d5-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="d07d5-106">若要详细了解如何计划和部署会议，请参阅在 [Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) 中规划会议和在 Skype for Business Server 中部署 [会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="d07d5-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="d07d5-107">会议配置设置规定用户可创建的会议类型，以及控制 (或者) 匿名用户和电话拨入式会议用户能否加入这些会议。</span><span class="sxs-lookup"><span data-stu-id="d07d5-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="d07d5-108">请注意，这些设置仅影响安排的会议;它们不会影响通过单击 Skype for Business 中的"现在开会"选项创建临时会议。</span><span class="sxs-lookup"><span data-stu-id="d07d5-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="d07d5-109">会议配置设置定义以下内容：</span><span class="sxs-lookup"><span data-stu-id="d07d5-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="d07d5-110">从公用电话交换网 (PSTN) 拨入的用户是否进入会议厅</span><span class="sxs-lookup"><span data-stu-id="d07d5-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="d07d5-111">谁能成为演示者</span><span class="sxs-lookup"><span data-stu-id="d07d5-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="d07d5-112">默认情况下是否分配会议类型</span><span class="sxs-lookup"><span data-stu-id="d07d5-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="d07d5-113">默认情况下是否允许匿名（未经身份验证）用户加入会议</span><span class="sxs-lookup"><span data-stu-id="d07d5-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="d07d5-114">可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序定义会议的特征。</span><span class="sxs-lookup"><span data-stu-id="d07d5-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="d07d5-115">可以在全局级别指定会议设置 (默认创建) 、站点级别或池级别。</span><span class="sxs-lookup"><span data-stu-id="d07d5-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="d07d5-116">默认情况下，全局设置定义会议体验。</span><span class="sxs-lookup"><span data-stu-id="d07d5-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="d07d5-117">如果创建池级别的设置，则这些设置将应用于由该池托管的所有会议。</span><span class="sxs-lookup"><span data-stu-id="d07d5-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="d07d5-118">如果未创建池级别的设置，则应用站点级别的设置（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="d07d5-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="d07d5-119">如果未定义站点级别的设置，则全局设置将应用于所有会议。</span><span class="sxs-lookup"><span data-stu-id="d07d5-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d07d5-120">使用 Skype for Business Server 控制面板管理会议设置</span><span class="sxs-lookup"><span data-stu-id="d07d5-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="d07d5-121">若要使用 Skype for Business Server 控制面板管理会议设置：</span><span class="sxs-lookup"><span data-stu-id="d07d5-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="d07d5-122">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d07d5-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="d07d5-123">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="d07d5-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d07d5-124">在左侧导航栏中，单击 **"会议"，** 然后单击"会议 **配置"。**</span><span class="sxs-lookup"><span data-stu-id="d07d5-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d07d5-125">使用 Skype for Business Server 命令行管理程序管理会议设置</span><span class="sxs-lookup"><span data-stu-id="d07d5-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="d07d5-126">若要使用 Skype for Business Server 命令行管理程序管理会议，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d07d5-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="d07d5-127">**会议配置设置**</span><span class="sxs-lookup"><span data-stu-id="d07d5-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="d07d5-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="d07d5-128">**Cmdlet**</span></span>|<span data-ttu-id="d07d5-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="d07d5-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="d07d5-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d07d5-130">Get-CsMeetingConfiguration</span></span>](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="d07d5-131">返回有关组织中当前使用的会议配置设置的信息。</span><span class="sxs-lookup"><span data-stu-id="d07d5-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="d07d5-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d07d5-132">New-CsMeetingConfiguration</span></span>](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="d07d5-133">在站点或服务范围创建新的会议配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="d07d5-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="d07d5-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d07d5-134">Remove-CsMeetingConfiguration</span></span>](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="d07d5-135">删除现有的会议配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="d07d5-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="d07d5-136">Set-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d07d5-136">Set-CsMeetingConfiguration</span></span>](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="d07d5-137">修改组织中当前使用的会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="d07d5-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
