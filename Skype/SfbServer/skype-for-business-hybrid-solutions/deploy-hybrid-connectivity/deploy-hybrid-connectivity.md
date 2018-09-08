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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
description: 摘要：阅读本主题可了解如何部署 Skype for Business Server 与 Skype for Business Online 之间的混合连接。
ms.openlocfilehash: 1e42b0c582f186b785db691e66b9ee88aa6d6a74
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886194"
---
# <a name="deploy-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a><span data-ttu-id="6853b-103">部署 Skype for Business Server 与 Skype for Business Online 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="6853b-103">Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online</span></span>
 
<span data-ttu-id="6853b-104">**摘要：** 阅读本主题可了解如何部署 Skype for Business Server 与 Skype for Business Online 之间的混合连接。</span><span class="sxs-lookup"><span data-stu-id="6853b-104">**Summary:** Read this topic to learn how to deploy hybrid connectivity between Skype for Business Server and Skype for Business Online.</span></span>
  
<span data-ttu-id="6853b-105">之前执行本主题中的步骤，您应该已经阅读[规划 Skype 业务服务器和 Skype 业务 online 之间的混合连接性](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="6853b-105">Before performing the steps in this topic, you should have read [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span>
  
<span data-ttu-id="6853b-106">Skype 业务服务器和 Skype 业务 online 之间的混合连接意味着用户的域名，例如，contoso.com，分别使用 Skype 本地 Business Server 和 Skype 业务 online 之间。</span><span class="sxs-lookup"><span data-stu-id="6853b-106">Hybrid connectivity between Skype for Business Server and Skype for Business Online means users of a domain, such as contoso.com, are split between using Skype for Business Server on premises and Skype for Business Online.</span></span> <span data-ttu-id="6853b-107">部分域用户驻留在本地，而另一部分用户驻留在线上。</span><span class="sxs-lookup"><span data-stu-id="6853b-107">Some of the domain users are homed on premises, and some users are homed online.</span></span> 
  
<span data-ttu-id="6853b-108">下表列出了业务 Online 和 Microsoft Office 365 准备您的环境以进行混合部署 Skype 所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="6853b-108">The following table lists the steps required to prepare your environment for a hybrid deployment with Skype for Business Online and Microsoft Office 365.</span></span> 
  
|<span data-ttu-id="6853b-109">**步骤**</span><span class="sxs-lookup"><span data-stu-id="6853b-109">**Step**</span></span>|<span data-ttu-id="6853b-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="6853b-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6853b-111">创建 Office 365 租户帐户和启用业务联机 Skype</span><span class="sxs-lookup"><span data-stu-id="6853b-111">Create a tenant account for Office 365 and enable Skype for Business Online</span></span>  <br/> |<span data-ttu-id="6853b-112">了解有关 Office 365 和 Skype 的业务 Online 在[Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980)。</span><span class="sxs-lookup"><span data-stu-id="6853b-112">Learn about Office 365 and Skype for Business Online at [Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).</span></span>  <br/> <span data-ttu-id="6853b-113">若要确保您的环境已准备好让 Office 365，请参阅[System Requirements](https://products.office.com/en-US/office-system-requirements)。</span><span class="sxs-lookup"><span data-stu-id="6853b-113">To make sure that your environment is ready for Office 365, see the [System Requirements](https://products.office.com/en-US/office-system-requirements).</span></span>  <br/> <span data-ttu-id="6853b-114">有关设置 Office 365 的详细信息，请参阅[Getting Started with Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982)。</span><span class="sxs-lookup"><span data-stu-id="6853b-114">For details about setting up Office 365, see [Getting Started with Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).</span></span>  <br/> |
|<span data-ttu-id="6853b-115">将您的域添加到 Office 365 租户，并验证所有权</span><span class="sxs-lookup"><span data-stu-id="6853b-115">Add your domain to your Office 365 tenant and verify ownership</span></span>  <br/> | <span data-ttu-id="6853b-116">您必须将您的域添加到 Office 365 租户中，然后按照步骤在 Office 365 中验证域。</span><span class="sxs-lookup"><span data-stu-id="6853b-116">You must add your domain to your Office 365 tenant, and then follow the steps to validate the domain with Office 365.</span></span> <span data-ttu-id="6853b-117">这是为了确认您是域的所有者。</span><span class="sxs-lookup"><span data-stu-id="6853b-117">This is to confirm that you are the owner of the domain.</span></span> <br/> <span data-ttu-id="6853b-118">若要将您的域添加到 Office 365 租户，请按照在[您将域添加到 Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)中所述的步骤。</span><span class="sxs-lookup"><span data-stu-id="6853b-118">To add your domain to your Office 365 tenant, follow the steps described at [Add your domain to Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).</span></span>  <br/> |
|<span data-ttu-id="6853b-119">准备 Active Directory 同步</span><span class="sxs-lookup"><span data-stu-id="6853b-119">Prepare for Active Directory synchronization</span></span>  <br/> |<span data-ttu-id="6853b-120">Active Directory 同步保持内部部署 Active Directory 与 Office 365 持续同步。</span><span class="sxs-lookup"><span data-stu-id="6853b-120">Active Directory synchronization keeps your on-premises Active Directory continuously synchronized with Office 365.</span></span> <span data-ttu-id="6853b-121">这样，您可以创建每个用户帐户和组的同步版本，同时实现从本地 Microsoft Exchange Server 环境到 Microsoft Exchange Online 的全局地址列表 (GAL) 同步。</span><span class="sxs-lookup"><span data-stu-id="6853b-121">This lets you create synchronized versions of each user account and group, and also enables global address list (GAL) synchronization from your local Microsoft Exchange Server environment to Microsoft Exchange Online.</span></span> <span data-ttu-id="6853b-122">有关详细信息，请参阅[目录集成工具](https://go.microsoft.com/fwlink/p/?LinkId=530320)。</span><span class="sxs-lookup"><span data-stu-id="6853b-122">For more information, see [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?LinkId=530320).</span></span>  <br/>  <span data-ttu-id="6853b-123">**重要说明**您需要在本地和联机部署之间您组织中的业务用户的所有 Skype 的同步的 AD 帐户即使用户不移到 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="6853b-123">**IMPORTANT** You need to synchronize the AD accounts for all Skype for Business users in your organization between your on-premises and online deployments, even if users are not moved to Skype for Business Online.</span></span> <span data-ttu-id="6853b-124">如果未能同步所有用户，组织内本地用户与联机用户之间的通信将出现问题。</span><span class="sxs-lookup"><span data-stu-id="6853b-124">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>           |
|<span data-ttu-id="6853b-125">移动试用用户</span><span class="sxs-lookup"><span data-stu-id="6853b-125">Move pilot users</span></span>  <br/> |<span data-ttu-id="6853b-126">您已完成的步骤准备和配置您的环境的 Skype 业务 online 后，您可以开始将试点用户移到 online Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="6853b-126">After you have completed the steps to prepare and configure your environment for Skype for Business Online, you can start moving pilot users to your online Office 365 tenant.</span></span> <span data-ttu-id="6853b-127">请参阅[移动用户从本地到业务 online Skype](move-users-from-on-premises-to-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="6853b-127">See [Move users from on premises to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>  <br/> |
