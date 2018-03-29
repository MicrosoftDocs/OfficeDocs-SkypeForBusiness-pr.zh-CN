---
title: 新建或编辑现有的存档策略
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
description: 存档策略用于控制业务服务器驻留在 Skype 的用户部署中的内部和外部通信存档。 存档策略包括全局策略以及可选的一个或多个站点和用户策略：
ms.openlocfilehash: af8038371cd421b0232ce2df0ba92aa5b079702e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="archiving-policy-create-new-or-edit-existing"></a><span data-ttu-id="45c93-104">存档策略：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="45c93-104">Archiving Policy: Create New or Edit Existing</span></span>
 
<span data-ttu-id="45c93-105">存档策略用于控制业务服务器驻留在 Skype 的用户部署中的内部和外部通信存档。</span><span class="sxs-lookup"><span data-stu-id="45c93-105">You use Archiving policies to control archiving of internal and external communications in your deployment for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="45c93-106">存档策略包括全局策略以及可选的一个或多个站点和用户策略：</span><span class="sxs-lookup"><span data-stu-id="45c93-106">Archiving policies include the global policy, and, optionally, one or more site and user policies:</span></span>
  
- <span data-ttu-id="45c93-107">**全球政策**默认情况下，所有 Skype 业务服务器部署中创建全局策略。</span><span class="sxs-lookup"><span data-stu-id="45c93-107">**Global policy** The global policy is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="45c93-108">您可以编辑全局策略，但无法删除此策略。</span><span class="sxs-lookup"><span data-stu-id="45c93-108">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="45c93-109">如果您尝试将其删除，则所有选项将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="45c93-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="45c93-110">**站点策略 （可选）**您可以指定一个或多个网站存档策略，您可以配置每个启用和禁用特定站点的内部或外部通信存档。</span><span class="sxs-lookup"><span data-stu-id="45c93-110">**Site policies (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific site.</span></span> <span data-ttu-id="45c93-111">站点策略会覆盖全局策略，但仅限于在存档策略中指定的站点。</span><span class="sxs-lookup"><span data-stu-id="45c93-111">A site policy overrides the global policy, but only for the sites specified in Archiving policies.</span></span> <span data-ttu-id="45c93-112">可以编辑或删除站点策略。</span><span class="sxs-lookup"><span data-stu-id="45c93-112">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="45c93-113">**用户策略 （可选）**您可以指定一个或多个用户存档策略，您可以配置每个启用和禁用针对特定用户的内部或外部通信存档。</span><span class="sxs-lookup"><span data-stu-id="45c93-113">**User policies (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving for internal or external communications for a specific user.</span></span> <span data-ttu-id="45c93-114">用户策略会覆盖全局策略和站点策略，但仅限于分配了用户策略的用户。</span><span class="sxs-lookup"><span data-stu-id="45c93-114">A user policy overrides the global policy and site policies, but only for the user(s) to whom you assign a user policy.</span></span> <span data-ttu-id="45c93-115">可以编辑或删除用户策略。</span><span class="sxs-lookup"><span data-stu-id="45c93-115">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="45c93-116">如果使用 Exchange 集成存储归档中 Microsoft Exchange，然后交换 2013年策略数据存档的用户控件驻留于 Exchange 2013 年。</span><span class="sxs-lookup"><span data-stu-id="45c93-116">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange 2013 policies control archiving for users homed on Exchange 2013.</span></span> <span data-ttu-id="45c93-117">为启用存档的用户，该用户的邮箱必须放在适当地存放。</span><span class="sxs-lookup"><span data-stu-id="45c93-117">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="45c93-118">若要为新的存档策略或现有的存档策略配置设置，请指定以下选项：</span><span class="sxs-lookup"><span data-stu-id="45c93-118">To configure the settings for a new or existing Archiving policy, you specify the following options:</span></span>
- <span data-ttu-id="45c93-119">**名称**每个存档策略需要一个名称。</span><span class="sxs-lookup"><span data-stu-id="45c93-119">**Name** Each Archiving policy requires a name.</span></span> <span data-ttu-id="45c93-120">名称取决于您在添加或编辑的策略的类型：</span><span class="sxs-lookup"><span data-stu-id="45c93-120">The name is determined by the type of policy that you are adding or editing:</span></span>
    
  - <span data-ttu-id="45c93-121">**全球政策**默认名称是全局。</span><span class="sxs-lookup"><span data-stu-id="45c93-121">**Global policy** The default name is Global.</span></span> <span data-ttu-id="45c93-122">可以将该名称更改成一个更具描述性的名称。</span><span class="sxs-lookup"><span data-stu-id="45c93-122">You can change it to a more descriptive name.</span></span> <span data-ttu-id="45c93-123">例如，Contoso 北美机构。</span><span class="sxs-lookup"><span data-stu-id="45c93-123">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="45c93-124">**站点策略**在此对话框中列出的站点在部署中包括的所有可用站点。</span><span class="sxs-lookup"><span data-stu-id="45c93-124">**Site policy** The sites listed in this dialog box include all available sites in your deployment.</span></span> <span data-ttu-id="45c93-125">单击某个站点将其选中。</span><span class="sxs-lookup"><span data-stu-id="45c93-125">Click a single site to select it.</span></span> <span data-ttu-id="45c93-126">例如，Redmond 数据中心。</span><span class="sxs-lookup"><span data-stu-id="45c93-126">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="45c93-127">**用户策略**指定适当的名称，例如特定的用户的名称或用户组或您的组织中的团队的名称。</span><span class="sxs-lookup"><span data-stu-id="45c93-127">**User policy** Specify an appropriate name, such as the name of a specific user or the name of a user group or team in your organization.</span></span> <span data-ttu-id="45c93-128">例如，法律部门。</span><span class="sxs-lookup"><span data-stu-id="45c93-128">For example, Legal Department.</span></span>
    
- <span data-ttu-id="45c93-129">**说明**这是可选的。</span><span class="sxs-lookup"><span data-stu-id="45c93-129">**Description** This is optional.</span></span> <span data-ttu-id="45c93-130">使用它来提供更多详细信息，如使用策略的范围。</span><span class="sxs-lookup"><span data-stu-id="45c93-130">Use it to provide additional details, such as the scope or use of the policy.</span></span> <span data-ttu-id="45c93-131">例如，协调与其他站点的法律部门。</span><span class="sxs-lookup"><span data-stu-id="45c93-131">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="45c93-132">**内部通信存档**选中此复选框可启用在您的内部网络上的通信存档。</span><span class="sxs-lookup"><span data-stu-id="45c93-132">**Archive internal communications** Select this check box to enable archiving of communications on your internal network.</span></span> <span data-ttu-id="45c93-133">默认情况下，这不是在任何策略中启用。</span><span class="sxs-lookup"><span data-stu-id="45c93-133">By default, this is not enabled in any policy.</span></span>
    
- <span data-ttu-id="45c93-134">**外部通信存档**选中此复选框可以包括外部用户，如远程用户 （包括匿名用户和 PIC 设置用户），用户和联盟伙伴的通信存档。</span><span class="sxs-lookup"><span data-stu-id="45c93-134">**Archive external communications** Select this check box to enable archiving of communications that include external users, such as remote users, (including anonymous and PIC-setting users), and federated partners.</span></span> <span data-ttu-id="45c93-135">默认情况下，这不是在任何策略中启用。</span><span class="sxs-lookup"><span data-stu-id="45c93-135">By default, this is not enabled in any policy.</span></span>
    
<span data-ttu-id="45c93-136">有关存档功能和功能，其中包括交换集成详细信息请参阅[存档业务服务器 2015年的 Skype 的规划](../../plan-your-deployment/archiving/archiving.md)、[部署存档业务服务器 2015年的 Skype](../../deploy/deploy-archiving/deploy-archiving.md)，和[管理存档的 Skype 的商业服务器 2015年](../../manage/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="45c93-136">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

