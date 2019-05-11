---
title: 管理会议中 Skype 业务服务器的配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 摘要： 了解如何管理会议中 Skype 业务服务器的配置设置。
ms.openlocfilehash: 2e4a3dae9eac83b94f6623faf07e5ee6e8e346db
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888175"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="9b896-103">管理会议中 Skype 业务服务器的配置设置</span><span class="sxs-lookup"><span data-stu-id="9b896-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="9b896-104">**摘要：** 了解如何管理会议中 Skype 业务服务器的配置设置。</span><span class="sxs-lookup"><span data-stu-id="9b896-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="9b896-105">本主题描述如何管理会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="9b896-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="9b896-106">有关如何规划和部署会议的详细信息，请参阅[Plan for Business Server 的 Skype 中的会议](../../plan-your-deployment/conferencing/conferencing.md)和[Skype 业务服务器中的部署会议](../../deploy/deploy-conferencing/deploy-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="9b896-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="9b896-107">会议配置设置规定了用户可创建的会议类型，此外还控制匿名用户和电话拨入式会议用户如何（甚至是否）加入这些会议。</span><span class="sxs-lookup"><span data-stu-id="9b896-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="9b896-108">请注意，这些设置仅影响安排的会议;它们不会影响通过单击 Skype for Business 中的立即开会选项创建的临时会议。</span><span class="sxs-lookup"><span data-stu-id="9b896-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="9b896-109">会议配置设置定义以下事项：</span><span class="sxs-lookup"><span data-stu-id="9b896-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="9b896-110">从公用电话交换网 (PSTN) 拨入的用户是否进入会议厅</span><span class="sxs-lookup"><span data-stu-id="9b896-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="9b896-111">谁能成为演示者</span><span class="sxs-lookup"><span data-stu-id="9b896-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="9b896-112">默认情况下是否分配会议类型</span><span class="sxs-lookup"><span data-stu-id="9b896-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="9b896-113">默认情况下是否允许匿名（未经身份验证）用户加入会议</span><span class="sxs-lookup"><span data-stu-id="9b896-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="9b896-114">使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序，您可以定义的会议的特征。</span><span class="sxs-lookup"><span data-stu-id="9b896-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="9b896-115">您可以指定会议在全局级别 （默认情况下创建） 的设置，网站级别或池级别。</span><span class="sxs-lookup"><span data-stu-id="9b896-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="9b896-116">默认情况下，全局设置定义会议体验。</span><span class="sxs-lookup"><span data-stu-id="9b896-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="9b896-117">如果创建池级别的设置，则这些设置将应用于由该池托管的所有会议。</span><span class="sxs-lookup"><span data-stu-id="9b896-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="9b896-118">如果未创建池级别的设置，则应用站点级别的设置（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="9b896-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="9b896-119">如果未定义站点级别的设置，则全局设置将应用于所有会议。</span><span class="sxs-lookup"><span data-stu-id="9b896-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9b896-120">使用适用于业务 Server Control Panel Skype 管理会议设置</span><span class="sxs-lookup"><span data-stu-id="9b896-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="9b896-121">使用适用于业务 Server Control Panel Skype 管理会议设置：</span><span class="sxs-lookup"><span data-stu-id="9b896-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="9b896-122">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="9b896-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="9b896-123">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="9b896-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="9b896-124">在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。</span><span class="sxs-lookup"><span data-stu-id="9b896-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="9b896-125">使用 Skype 业务 Server Management Shell 管理会议设置</span><span class="sxs-lookup"><span data-stu-id="9b896-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="9b896-126">若要使用 Skype 业务 Server Management Shell 管理会议，请使用以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="9b896-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="9b896-127">**会议配置设置**</span><span class="sxs-lookup"><span data-stu-id="9b896-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="9b896-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="9b896-128">**Cmdlet**</span></span>|<span data-ttu-id="9b896-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="9b896-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="9b896-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9b896-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="9b896-131">返回有关当前组织中使用的会议配置设置的信息。</span><span class="sxs-lookup"><span data-stu-id="9b896-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="9b896-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9b896-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="9b896-133">在 site 或服务范围创建新的会议配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="9b896-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="9b896-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9b896-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="9b896-135">删除会议配置设置的现有集合。</span><span class="sxs-lookup"><span data-stu-id="9b896-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="9b896-136">Set-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9b896-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="9b896-137">修改组织中当前使用的会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="9b896-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

