---
title: 部署 Skype for Business Server 与 Skype for Business Online 之间的混合连接
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
description: 摘要： 请阅读本主题，以了解如何部署 Skype 业务服务器和 Skype 的在线业务之间的混合连接。
ms.openlocfilehash: 6dfe230088a2f3ecf827f3d8da9b6c9230ed4989
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a><span data-ttu-id="c17e1-103">部署 Skype for Business Server 与 Skype for Business Online 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="c17e1-103">Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online</span></span>
 
<span data-ttu-id="c17e1-104">**摘要：**阅读本主题可了解如何部署 Skype for Business Server 与 Skype for Business Online 之间的混合连接。</span><span class="sxs-lookup"><span data-stu-id="c17e1-104">**Summary:** Read this topic to learn how to deploy hybrid connectivity between Skype for Business Server and Skype for Business Online.</span></span>
  
<span data-ttu-id="c17e1-105">执行本主题中的步骤之前, 您应阅读[计划业务服务器和 Skype 的在线业务 Skype 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="c17e1-105">Before performing the steps in this topic, you should have read [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span>
  
<span data-ttu-id="c17e1-106">Skype 业务服务器和 Skype 的在线业务之间的混合连接意味着用户的域，如 contoso.com，都分为使用 Skype 业务服务器上部署和 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="c17e1-106">Hybrid connectivity between Skype for Business Server and Skype for Business Online means users of a domain, such as contoso.com, are split between using Skype for Business Server on premises and Skype for Business Online.</span></span> <span data-ttu-id="c17e1-107">部分域用户驻留在本地，而另一部分用户驻留在线上。</span><span class="sxs-lookup"><span data-stu-id="c17e1-107">Some of the domain users are homed on premises, and some users are homed online.</span></span> 
  
<span data-ttu-id="c17e1-108">下表列出准备在线业务和 Microsoft Office 365 的 Skype 混合部署您的环境所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="c17e1-108">The following table lists the steps required to prepare your environment for a hybrid deployment with Skype for Business Online and Microsoft Office 365.</span></span> 
  
|<span data-ttu-id="c17e1-109">**步骤**</span><span class="sxs-lookup"><span data-stu-id="c17e1-109">**Step**</span></span>|<span data-ttu-id="c17e1-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="c17e1-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c17e1-111">创建 Office 365 的租户帐户并启用 Skype 的在线业务</span><span class="sxs-lookup"><span data-stu-id="c17e1-111">Create a tenant account for Office 365 and enable Skype for Business Online</span></span>  <br/> |<span data-ttu-id="c17e1-112">在[Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980)在线业务的了解 Office 365 和 Skype。</span><span class="sxs-lookup"><span data-stu-id="c17e1-112">Learn about Office 365 and Skype for Business Online at [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).</span></span>  <br/> <span data-ttu-id="c17e1-113">若要确保您的环境是 Office 365 的准备，请参阅[系统要求](https://go.microsoft.com/fwlink/p/?LinkId=401408)。</span><span class="sxs-lookup"><span data-stu-id="c17e1-113">To make sure that your environment is ready for Office 365, see the [System Requirements](https://go.microsoft.com/fwlink/p/?LinkId=401408).</span></span>  <br/> <span data-ttu-id="c17e1-114">有关 Office 365 的设置的详细信息，请参阅[Office 365 入门知识](https://go.microsoft.com/fwlink/p/?LinkId=254982)。</span><span class="sxs-lookup"><span data-stu-id="c17e1-114">For details about setting up Office 365, see [Getting Started with Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).</span></span>  <br/> |
|<span data-ttu-id="c17e1-115">将您的域添加到 Office 365 租户和验证所有权</span><span class="sxs-lookup"><span data-stu-id="c17e1-115">Add your domain to your Office 365 tenant and verify ownership</span></span>  <br/> | <span data-ttu-id="c17e1-116">您必须将您的域添加到 Office 365 租户中，然后按照步骤在 Office 365 中验证域。</span><span class="sxs-lookup"><span data-stu-id="c17e1-116">You must add your domain to your Office 365 tenant, and then follow the steps to validate the domain with Office 365.</span></span> <span data-ttu-id="c17e1-117">这是为了确认您是域的所有者。</span><span class="sxs-lookup"><span data-stu-id="c17e1-117">This is to confirm that you are the owner of the domain.</span></span> <br/> <span data-ttu-id="c17e1-118">若要将您的域添加到 Office 365 租户，请按照[添加到 Office 365 域](https://go.microsoft.com/fwlink/p/?LinkId=254983)在所述的步骤。</span><span class="sxs-lookup"><span data-stu-id="c17e1-118">To add your domain to your Office 365 tenant, follow the steps described at [Add your domain to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254983).</span></span>  <br/> |
|<span data-ttu-id="c17e1-119">准备活动目录同步</span><span class="sxs-lookup"><span data-stu-id="c17e1-119">Prepare for Active Directory synchronization</span></span>  <br/> |<span data-ttu-id="c17e1-120">活动目录同步保持内部活动目录与 Office 365 连续同步。</span><span class="sxs-lookup"><span data-stu-id="c17e1-120">Active Directory synchronization keeps your on-premises Active Directory continuously synchronized with Office 365.</span></span> <span data-ttu-id="c17e1-121">这样，您可以创建每个用户帐户和组的同步版本，同时实现从本地 Microsoft Exchange Server 环境到 Microsoft Exchange Online 的全局地址列表 (GAL) 同步。</span><span class="sxs-lookup"><span data-stu-id="c17e1-121">This lets you create synchronized versions of each user account and group, and also enables global address list (GAL) synchronization from your local Microsoft Exchange Server environment to Microsoft Exchange Online.</span></span> <span data-ttu-id="c17e1-122">有关详细信息，请参阅[目录集成工具](https://go.microsoft.com/fwlink/p/?LinkId=530320)。</span><span class="sxs-lookup"><span data-stu-id="c17e1-122">For more information, see [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?LinkId=530320).</span></span>  <br/> <span data-ttu-id="c17e1-123">> [!IMPORTANT]> 您需要同步的所有内部部署和联机部署，您组织中的业务用户的 Skype 的 AD 帐户即使用户不移到 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="c17e1-123">> [!IMPORTANT]> You need to synchronize the AD accounts for all Skype for Business users in your organization between your on-premises and online deployments, even if users are not moved to Skype for Business Online.</span></span> <span data-ttu-id="c17e1-124">如果未能同步所有用户，组织内本地用户与联机用户之间的通信将出现问题。</span><span class="sxs-lookup"><span data-stu-id="c17e1-124">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>           |
|<span data-ttu-id="c17e1-125">移动试用用户</span><span class="sxs-lookup"><span data-stu-id="c17e1-125">Move pilot users</span></span>  <br/> |<span data-ttu-id="c17e1-126">准备和配置您的环境的 Skype 的在线业务的步骤完成后，您可以启动将试点项目的用户移到您在线 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="c17e1-126">After you have completed the steps to prepare and configure your environment for Skype for Business Online, you can start moving pilot users to your online Office 365 tenant.</span></span> <span data-ttu-id="c17e1-127">请参阅[移动用户 Skype 的在线业务的场所上](move-users-from-on-premises-to-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="c17e1-127">See [Move users from on premises to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>  <br/> |
|<span data-ttu-id="c17e1-128">管理混合部署中的用户</span><span class="sxs-lookup"><span data-stu-id="c17e1-128">Manage users in a hybrid deployment</span></span>  <br/> |<span data-ttu-id="c17e1-129">有关如何管理混合部署中的用户的详细信息，请参阅[管理混合部署中的用户](http://technet.microsoft.com/library/6924ed7b-30a9-4be7-b952-90655625f2c8.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c17e1-129">For details about how to manage users in a hybrid deployment, see [Administering users in a Hybrid Deployment](http://technet.microsoft.com/library/6924ed7b-30a9-4be7-b952-90655625f2c8.aspx).</span></span>  <br/> |
   

