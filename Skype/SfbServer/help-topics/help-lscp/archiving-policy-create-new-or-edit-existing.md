---
title: 存档策略创建新的或编辑现有的
ms.reviewer: ''
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
description: 您可以使用存档策略来控制用户的企业服务器驻留在 Skype 上部署中的内部和外部通信的存档。 存档策略包括全局策略以及可选的一个或多个站点和用户策略：
ms.openlocfilehash: 76dcc63ed6c08c0a8d11c79547b8a11f6b1e4b39
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234836"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a><span data-ttu-id="e4ab9-104">存档策略：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="e4ab9-104">Archiving Policy: Create New or Edit Existing</span></span>
 
<span data-ttu-id="e4ab9-105">您可以使用存档策略来控制用户的企业服务器驻留在 Skype 上部署中的内部和外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-105">You use Archiving policies to control archiving of internal and external communications in your deployment for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="e4ab9-106">存档策略包括全局策略以及可选的一个或多个站点和用户策略：</span><span class="sxs-lookup"><span data-stu-id="e4ab9-106">Archiving policies include the global policy, and, optionally, one or more site and user policies:</span></span>
  
- <span data-ttu-id="e4ab9-107">**全局策略**默认情况下，所有 Skype 业务服务器部署中创建的全局策略。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-107">**Global policy** The global policy is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="e4ab9-108">您可以编辑全局策略，但无法删除此策略。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-108">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="e4ab9-109">如果您尝试将其删除，则所有选项将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="e4ab9-110">**（可选） 的站点策略**您可以指定一个或多个站点存档策略，您可以配置每种启用和禁用为特定站点的内部或外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-110">**Site policies (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific site.</span></span> <span data-ttu-id="e4ab9-111">站点策略会覆盖全局策略，但仅限于在存档策略中指定的站点。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-111">A site policy overrides the global policy, but only for the sites specified in Archiving policies.</span></span> <span data-ttu-id="e4ab9-112">可以编辑或删除站点策略。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-112">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="e4ab9-113">**（可选） 的用户策略**您可以指定一个或多个用户存档策略，您可以配置每种启用或禁用特定用户的内部或外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-113">**User policies (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving for internal or external communications for a specific user.</span></span> <span data-ttu-id="e4ab9-114">用户策略会覆盖全局策略和站点策略，但仅限于分配了用户策略的用户。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-114">A user policy overrides the global policy and site policies, but only for the user(s) to whom you assign a user policy.</span></span> <span data-ttu-id="e4ab9-115">可以编辑或删除用户策略。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-115">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e4ab9-116">如果您使用 Exchange 集成存储存档数据在 Microsoft Exchange、 然后 Exchange 2013 策略控制的用户存档驻留在 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-116">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange 2013 policies control archiving for users homed on Exchange 2013.</span></span> <span data-ttu-id="e4ab9-117">要启用存档这些用户，用户邮箱必须置于就地保留上。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-117">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="e4ab9-118">若要为新的存档策略或现有的存档策略配置设置，请指定以下选项：</span><span class="sxs-lookup"><span data-stu-id="e4ab9-118">To configure the settings for a new or existing Archiving policy, you specify the following options:</span></span>
- <span data-ttu-id="e4ab9-119">**名称**每个存档策略需要一个名称。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-119">**Name** Each Archiving policy requires a name.</span></span> <span data-ttu-id="e4ab9-120">名称取决于要添加或编辑的策略类型：</span><span class="sxs-lookup"><span data-stu-id="e4ab9-120">The name is determined by the type of policy that you are adding or editing:</span></span>
    
  - <span data-ttu-id="e4ab9-121">**全局策略**默认名称为 Global。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-121">**Global policy** The default name is Global.</span></span> <span data-ttu-id="e4ab9-122">可以将该名称更改成一个更具描述性的名称。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-122">You can change it to a more descriptive name.</span></span> <span data-ttu-id="e4ab9-123">例如，Contoso 北美机构。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-123">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="e4ab9-124">**站点策略**在此对话框中列出的站点部署中包括所有可用的站点。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-124">**Site policy** The sites listed in this dialog box include all available sites in your deployment.</span></span> <span data-ttu-id="e4ab9-125">单击某个站点即可将其选中。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-125">Click a single site to select it.</span></span> <span data-ttu-id="e4ab9-126">例如，Redmond 数据中心。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-126">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="e4ab9-127">**用户策略**指定适当的名称，如特定用户的名称或用户组或组织中的工作组的名称。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-127">**User policy** Specify an appropriate name, such as the name of a specific user or the name of a user group or team in your organization.</span></span> <span data-ttu-id="e4ab9-128">例如，法律部门。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-128">For example, Legal Department.</span></span>
    
- <span data-ttu-id="e4ab9-129">**说明**这是可选的。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-129">**Description** This is optional.</span></span> <span data-ttu-id="e4ab9-130">使用它来提供其他详细信息，例如使用策略的范围。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-130">Use it to provide additional details, such as the scope or use of the policy.</span></span> <span data-ttu-id="e4ab9-131">例如，法律部门的其他网站与协调一致。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-131">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="e4ab9-132">**存档内部通信**选中此复选框可允许在内部网络通信的存档。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-132">**Archive internal communications** Select this check box to enable archiving of communications on your internal network.</span></span> <span data-ttu-id="e4ab9-133">默认情况下，这不是中的任何策略启用。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-133">By default, this is not enabled in any policy.</span></span>
    
- <span data-ttu-id="e4ab9-134">**外部通信的存档**选中此复选框以启用包括外部用户，例如 （包括匿名用户和 PIC 设置用户），远程用户和联盟伙伴的通信的存档。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-134">**Archive external communications** Select this check box to enable archiving of communications that include external users, such as remote users, (including anonymous and PIC-setting users), and federated partners.</span></span> <span data-ttu-id="e4ab9-135">默认情况下，这不是中的任何策略启用。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-135">By default, this is not enabled in any policy.</span></span>
    
<span data-ttu-id="e4ab9-136">有关的存档功能和功能，包括 Exchange 集成的详细信息，请参阅[规划存档中的业务服务器 2015 Skype](../../plan-your-deployment/archiving/archiving.md)、[业务服务器 2015年的 Skype 存档的部署](../../deploy/deploy-archiving/deploy-archiving.md)，和[管理存档中的 Skype业务服务器 2015年](../../manage/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ab9-136">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

