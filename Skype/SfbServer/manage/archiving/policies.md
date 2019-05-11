---
title: Skype 中的存档策略管理业务服务器 （英文）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 摘要： 了解如何管理业务服务器 Skype 的存档用户策略。
ms.openlocfilehash: 78c2e9d565ce755c9c23bce97702575a5861a23a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33884963"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="b3895-103">Skype 中的存档策略管理业务服务器 （英文）</span><span class="sxs-lookup"><span data-stu-id="b3895-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="b3895-104">**摘要：** 了解如何管理业务服务器 Skype 的存档用户策略。</span><span class="sxs-lookup"><span data-stu-id="b3895-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="b3895-105">您最初设置了当您部署存档，但您可以更改、 添加和删除部署后的配置存档策略。</span><span class="sxs-lookup"><span data-stu-id="b3895-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="b3895-106">存档策略确定是否存档：</span><span class="sxs-lookup"><span data-stu-id="b3895-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="b3895-107">内部通信</span><span class="sxs-lookup"><span data-stu-id="b3895-107">Internal communications</span></span>
    
- <span data-ttu-id="b3895-108">外部通信</span><span class="sxs-lookup"><span data-stu-id="b3895-108">External communications</span></span>
    
<span data-ttu-id="b3895-109">存档策略可以是在全局设置、 站点或用户级别。</span><span class="sxs-lookup"><span data-stu-id="b3895-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b3895-110">如果您为您的部署，Exchange 策略控件上启用 Microsoft Exchange 集成，是否驻留在 Exchange 上的用户启用存档，并且具有其邮箱置于就地保留。</span><span class="sxs-lookup"><span data-stu-id="b3895-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="b3895-111">有关详细信息，请参阅[规划存档中的业务服务器 Skype](../../plan-your-deployment/archiving/archiving.md)和[配置与业务服务器 Skype 的 Exchange 存储的集成](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="b3895-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="b3895-112">使用控制面板管理存档策略</span><span class="sxs-lookup"><span data-stu-id="b3895-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="b3895-113">可以使用控制面板管理存档策略，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b3895-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="b3895-114">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b3895-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="b3895-115">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="b3895-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="b3895-116">在左侧导航栏中，单击“**存档策略**”</span><span class="sxs-lookup"><span data-stu-id="b3895-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="b3895-117">使用 Windows PowerShell 管理存档策略</span><span class="sxs-lookup"><span data-stu-id="b3895-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="b3895-118">也可以使用下表中列出的 Windows PowerShell cmdlet 配置存档策略。</span><span class="sxs-lookup"><span data-stu-id="b3895-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="b3895-119">有关语法，包括所有可用的参数的详细信息，请参阅[Business Server Management Shell 的 Skype](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="b3895-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="b3895-120">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="b3895-120">**Cmdlet**</span></span>|<span data-ttu-id="b3895-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="b3895-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b3895-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="b3895-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="b3895-123">返回有关您组织的即时消息 (IM) 会话存档策略的信息。</span><span class="sxs-lookup"><span data-stu-id="b3895-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="b3895-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="b3895-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="b3895-125">将即时消息 (IM) 会话存档策略分配给用户或用户集。</span><span class="sxs-lookup"><span data-stu-id="b3895-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="b3895-126">通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="b3895-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="b3895-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="b3895-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="b3895-128">创建新的即时消息 (IM) 会话存档策略。</span><span class="sxs-lookup"><span data-stu-id="b3895-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="b3895-129">通过这些策略，您可以存档在内部用户之间发生的所有 IM 会话，以及/或者存档在内部用户与外部伙伴之间发生的所有 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="b3895-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="b3895-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="b3895-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="b3895-131">删除存档策略，用于确定是否 Skype 业务服务器自动保存所有内部用户和/或内部用户和联盟的伙伴之间的所有 IM 会话之间进行的 IM 会话的指定即时消息 (IM)。</span><span class="sxs-lookup"><span data-stu-id="b3895-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="b3895-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="b3895-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="b3895-133">修改现有的即时消息 (IM) 存档策略。</span><span class="sxs-lookup"><span data-stu-id="b3895-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="b3895-134">通过存档策略，您可以存档在内部用户之间发生的所有 IM 会话和会议；您还可以存档在内部用户与联盟伙伴之间发生的会话。</span><span class="sxs-lookup"><span data-stu-id="b3895-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

