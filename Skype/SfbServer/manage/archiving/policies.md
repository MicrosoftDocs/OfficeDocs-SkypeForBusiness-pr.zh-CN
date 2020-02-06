---
title: 管理 Skype for Business 服务器中的存档策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 摘要：了解如何管理适用于 Skype for business 服务器存档的用户策略。
ms.openlocfilehash: f2dca47dd7fd3095b2865ff72516b6be84144352
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818884"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="8ac37-103">管理 Skype for Business 服务器中的存档策略</span><span class="sxs-lookup"><span data-stu-id="8ac37-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="8ac37-104">**摘要：** 了解如何管理用于 Skype for Business 服务器存档的用户策略。</span><span class="sxs-lookup"><span data-stu-id="8ac37-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="8ac37-105">你在部署存档时最初设置存档策略，但你可以在部署后更改、添加和删除配置。</span><span class="sxs-lookup"><span data-stu-id="8ac37-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="8ac37-106">存档策略确定是否存档：</span><span class="sxs-lookup"><span data-stu-id="8ac37-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="8ac37-107">内部通信</span><span class="sxs-lookup"><span data-stu-id="8ac37-107">Internal communications</span></span>
    
- <span data-ttu-id="8ac37-108">外部通信</span><span class="sxs-lookup"><span data-stu-id="8ac37-108">External communications</span></span>
    
<span data-ttu-id="8ac37-109">可以在全局、网站或用户级别设置存档策略。</span><span class="sxs-lookup"><span data-stu-id="8ac37-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8ac37-110">如果为你的部署启用了 Microsoft Exchange 集成，Exchange 策略将控制是否为托管在 Exchange 上的用户启用存档，并将其邮箱置于原地保留。</span><span class="sxs-lookup"><span data-stu-id="8ac37-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="8ac37-111">有关详细信息，请参阅[在 skype for Business 服务器中规划存档](../../plan-your-deployment/archiving/archiving.md)和[配置与 Skype for Business 服务器的 Exchange 存储的集成](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="8ac37-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="8ac37-112">使用控制面板管理存档策略</span><span class="sxs-lookup"><span data-stu-id="8ac37-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="8ac37-113">可以使用控制面板管理存档策略，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8ac37-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="8ac37-114">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="8ac37-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="8ac37-115">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="8ac37-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="8ac37-116">在左侧导航栏中，单击“**存档策略**”</span><span class="sxs-lookup"><span data-stu-id="8ac37-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="8ac37-117">使用 Windows PowerShell 管理存档策略</span><span class="sxs-lookup"><span data-stu-id="8ac37-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="8ac37-118">也可以使用下表中列出的 Windows PowerShell cmdlet 配置存档策略。</span><span class="sxs-lookup"><span data-stu-id="8ac37-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="8ac37-119">有关语法的详细信息（包括所有可用参数），请参阅[Skype for Business Server 命令行管理](../management-shell.md)程序。</span><span class="sxs-lookup"><span data-stu-id="8ac37-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="8ac37-120">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="8ac37-120">**Cmdlet**</span></span>|<span data-ttu-id="8ac37-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="8ac37-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8ac37-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="8ac37-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="8ac37-123">返回有关您组织的即时消息 (IM) 会话存档策略的信息。</span><span class="sxs-lookup"><span data-stu-id="8ac37-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="8ac37-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="8ac37-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="8ac37-125">将即时消息 (IM) 会话存档策略分配给用户或用户集。</span><span class="sxs-lookup"><span data-stu-id="8ac37-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="8ac37-126">通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="8ac37-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="8ac37-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="8ac37-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="8ac37-128">创建新的即时消息 (IM) 会话存档策略。</span><span class="sxs-lookup"><span data-stu-id="8ac37-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="8ac37-129">通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="8ac37-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="8ac37-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="8ac37-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="8ac37-131">删除指定的即时消息（IM）存档策略，该策略确定 Skype for Business 服务器是否会自动保存内部用户和/或内部用户与联盟合作伙伴之间所有 IM 会话之间发生的所有 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="8ac37-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="8ac37-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="8ac37-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="8ac37-133">修改现有的即时消息 (IM) 存档策略。</span><span class="sxs-lookup"><span data-stu-id="8ac37-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="8ac37-134">通过存档策略，您可以存档在内部用户之间发生的所有 IM 会话和会议；您还可以存档在内部用户与联盟伙伴之间发生的会话。</span><span class="sxs-lookup"><span data-stu-id="8ac37-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

