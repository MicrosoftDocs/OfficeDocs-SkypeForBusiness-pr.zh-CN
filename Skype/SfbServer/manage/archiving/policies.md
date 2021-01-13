---
title: 在 Skype for Business Server 中管理存档策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 摘要：了解如何管理 Skype for Business Server 的用户存档策略。
ms.openlocfilehash: 949ac807faea4f563ee078512a3c0a335a517d2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828542"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="0d5e8-103">在 Skype for Business Server 中管理存档策略</span><span class="sxs-lookup"><span data-stu-id="0d5e8-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="0d5e8-104">**摘要：** 了解如何管理 Skype for Business Server 的用户存档策略。</span><span class="sxs-lookup"><span data-stu-id="0d5e8-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="0d5e8-105">您最初在部署存档时设置存档策略，但您可以在部署后更改、添加和删除配置。</span><span class="sxs-lookup"><span data-stu-id="0d5e8-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="0d5e8-106">存档策略确定是否存档：</span><span class="sxs-lookup"><span data-stu-id="0d5e8-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="0d5e8-107">内部通信</span><span class="sxs-lookup"><span data-stu-id="0d5e8-107">Internal communications</span></span>
    
- <span data-ttu-id="0d5e8-108">外部通信</span><span class="sxs-lookup"><span data-stu-id="0d5e8-108">External communications</span></span>
    
<span data-ttu-id="0d5e8-109">可以在全局、站点或用户级别设置存档策略。</span><span class="sxs-lookup"><span data-stu-id="0d5e8-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0d5e8-110">如果为部署启用了 Microsoft Exchange 集成，Exchange 策略将控制是否对位于 Exchange 上且其邮箱置于"保留"状态In-Place存档。</span><span class="sxs-lookup"><span data-stu-id="0d5e8-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="0d5e8-111">有关详细信息，请参阅[Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for Skype for Business [Server.](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)</span><span class="sxs-lookup"><span data-stu-id="0d5e8-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="0d5e8-112">使用控制面板管理存档策略</span><span class="sxs-lookup"><span data-stu-id="0d5e8-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="0d5e8-113">您可以使用控制面板管理存档策略，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0d5e8-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="0d5e8-114">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="0d5e8-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="0d5e8-115">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="0d5e8-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="0d5e8-116">在左侧导航栏中，单击 **"存档策略"**</span><span class="sxs-lookup"><span data-stu-id="0d5e8-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="0d5e8-117">使用策略管理存档Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d5e8-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="0d5e8-118">您还可以使用下表中列出的 Windows PowerShell cmdlet 配置存档策略。</span><span class="sxs-lookup"><span data-stu-id="0d5e8-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="0d5e8-119">有关语法的详细信息，包括所有可用参数，请参阅 Skype [for Business Server 命令行管理程序](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="0d5e8-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="0d5e8-120">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="0d5e8-120">**Cmdlet**</span></span>|<span data-ttu-id="0d5e8-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="0d5e8-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0d5e8-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="0d5e8-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="0d5e8-123">返回有关组织的即时消息和 IM (会话) 策略的信息。</span><span class="sxs-lookup"><span data-stu-id="0d5e8-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="0d5e8-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="0d5e8-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="0d5e8-125">将即时消息 (IM) 会话存档策略分配给用户或一组用户。</span><span class="sxs-lookup"><span data-stu-id="0d5e8-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="0d5e8-126">通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="0d5e8-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="0d5e8-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="0d5e8-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="0d5e8-128">创建新的即时消息 (IM) 会话存档策略。</span><span class="sxs-lookup"><span data-stu-id="0d5e8-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="0d5e8-129">通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="0d5e8-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="0d5e8-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="0d5e8-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="0d5e8-131">删除指定的即时消息 (IM) 存档策略，该策略确定 Skype for Business Server 是否将自动保存内部用户之间发生的所有 IM 会话，以及/或内部用户和联盟伙伴之间的所有 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="0d5e8-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="0d5e8-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="0d5e8-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="0d5e8-133">修改现有的即时消息 (IM) 存档策略。</span><span class="sxs-lookup"><span data-stu-id="0d5e8-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="0d5e8-134">通过存档策略，您可以存档在内部用户之间发生的所有 IM 会话和会议；您还可以存档在内部用户与联盟伙伴之间发生的会话。</span><span class="sxs-lookup"><span data-stu-id="0d5e8-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

