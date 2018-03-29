---
title: 在 Skype for Business Server 2015 中管理存档策略
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 摘要： 了解如何管理用户 Skype 业务服务器 2015年的存档策略。
ms.openlocfilehash: 584849862e106098bc4bbad92ed4e0b87be410e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-archiving-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="61c5f-103">在 Skype for Business Server 2015 中管理存档策略</span><span class="sxs-lookup"><span data-stu-id="61c5f-103">Manage archiving policies in Skype for Business Server 2015</span></span>

<span data-ttu-id="61c5f-104">**摘要：**了解如何管理用户 Skype 业务服务器 2015年的存档策略。</span><span class="sxs-lookup"><span data-stu-id="61c5f-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="61c5f-105">您初次设置归档策略，当您部署存档，但您可以更改、 添加和删除部署后配置。</span><span class="sxs-lookup"><span data-stu-id="61c5f-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="61c5f-106">存档策略确定是否存档：</span><span class="sxs-lookup"><span data-stu-id="61c5f-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="61c5f-107">内部通信</span><span class="sxs-lookup"><span data-stu-id="61c5f-107">Internal communications</span></span>
    
- <span data-ttu-id="61c5f-108">外部通信</span><span class="sxs-lookup"><span data-stu-id="61c5f-108">External communications</span></span>
    
<span data-ttu-id="61c5f-109">存档策略可以在全局组、 站点或用户级别。</span><span class="sxs-lookup"><span data-stu-id="61c5f-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="61c5f-110">如果您启用 Microsoft Exchange 集成部署，交换策略控制是否驻留在 Exchange 的用户启用存档和保留在原位上放有自己的邮箱。</span><span class="sxs-lookup"><span data-stu-id="61c5f-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="61c5f-111">有关详细信息，请参阅[规划业务服务器 2015年的 Skype 在归档](../../plan-your-deployment/archiving/archiving.md)和[具有的业务服务器 2015 Skype 的 Exchange 存储配置集成](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="61c5f-111">For details, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="61c5f-112">使用控制面板管理存档策略</span><span class="sxs-lookup"><span data-stu-id="61c5f-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="61c5f-113">可以使用控制面板管理存档策略，如下所示：</span><span class="sxs-lookup"><span data-stu-id="61c5f-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="61c5f-114">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="61c5f-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="61c5f-115">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="61c5f-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="61c5f-116">在左侧导航栏中，单击“**存档策略**”</span><span class="sxs-lookup"><span data-stu-id="61c5f-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="61c5f-117">使用 Windows PowerShell 管理存档策略</span><span class="sxs-lookup"><span data-stu-id="61c5f-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="61c5f-118">也可以使用下表中列出的 Windows PowerShell cmdlet 配置存档策略。</span><span class="sxs-lookup"><span data-stu-id="61c5f-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="61c5f-119">有关语法，包括所有的可用参数的详细信息请参阅[业务服务器 2015年管理外壳的 Skype](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="61c5f-119">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="61c5f-120">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="61c5f-120">**Cmdlet**</span></span>|<span data-ttu-id="61c5f-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="61c5f-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="61c5f-122">获得 CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="61c5f-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="61c5f-123">返回有关您组织的即时消息 (IM) 会话存档策略的信息。</span><span class="sxs-lookup"><span data-stu-id="61c5f-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="61c5f-124">授予 CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="61c5f-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="61c5f-125">将即时消息 (IM) 会话存档策略分配给用户或用户集。</span><span class="sxs-lookup"><span data-stu-id="61c5f-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="61c5f-126">通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="61c5f-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="61c5f-127">新 CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="61c5f-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="61c5f-128">创建新的即时消息 (IM) 会话存档策略。</span><span class="sxs-lookup"><span data-stu-id="61c5f-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="61c5f-129">通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="61c5f-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="61c5f-130">删除 CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="61c5f-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="61c5f-131">删除存档策略，用于确定是否 Skype 业务服务器自动将所有内部用户，和/或内部用户和联盟的用户之间的所有 IM 会话之间进行的 IM 会话指定即时消息 (IM)。</span><span class="sxs-lookup"><span data-stu-id="61c5f-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="61c5f-132">一组 CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="61c5f-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="61c5f-133">修改现有的即时消息 (IM) 存档策略。</span><span class="sxs-lookup"><span data-stu-id="61c5f-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="61c5f-134">通过存档策略，您可以存档在内部用户之间发生的所有 IM 会话和会议；您还可以存档在内部用户与联盟伙伴之间发生的会话。</span><span class="sxs-lookup"><span data-stu-id="61c5f-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

