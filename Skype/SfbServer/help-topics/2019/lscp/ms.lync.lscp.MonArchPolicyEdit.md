---
title: 存档策略创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
ROBOTS: NOINDEX, NOFOLLOW
description: 使用存档策略控制在部署中为位于 Skype for Business Server 上的用户存档内部和外部通信。 存档策略包括全局策略以及可选的一个或多个站点和用户策略：
ms.openlocfilehash: 71ffa03d0d3af8ea98fcc9ded17d4e3498e1705e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820312"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a><span data-ttu-id="870b1-104">存档策略：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="870b1-104">Archiving Policy: Create New or Edit Existing</span></span>
 
<span data-ttu-id="870b1-105">使用存档策略控制在部署中为位于 Skype for Business Server 上的用户存档内部和外部通信。</span><span class="sxs-lookup"><span data-stu-id="870b1-105">You use Archiving policies to control archiving of internal and external communications in your deployment for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="870b1-106">存档策略包括全局策略以及可选的一个或多个站点和用户策略：</span><span class="sxs-lookup"><span data-stu-id="870b1-106">Archiving policies include the global policy, and, optionally, one or more site and user policies:</span></span>
  
- <span data-ttu-id="870b1-107">**全局策略** 默认情况下，全局策略在所有 Skype for Business Server 部署中创建。</span><span class="sxs-lookup"><span data-stu-id="870b1-107">**Global policy** The global policy is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="870b1-108">您可以编辑全局策略，但无法删除此策略。</span><span class="sxs-lookup"><span data-stu-id="870b1-108">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="870b1-109">如果您尝试将其删除，则所有选项将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="870b1-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="870b1-110">**网站策略 (可选)** 可以指定一个或多个站点存档策略，每个存档策略都可以配置为启用和禁用对特定站点的内部或外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="870b1-110">**Site policies (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific site.</span></span> <span data-ttu-id="870b1-111">站点策略会覆盖全局策略，但仅限于在存档策略中指定的站点。</span><span class="sxs-lookup"><span data-stu-id="870b1-111">A site policy overrides the global policy, but only for the sites specified in Archiving policies.</span></span> <span data-ttu-id="870b1-112">可以编辑或删除站点策略。</span><span class="sxs-lookup"><span data-stu-id="870b1-112">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="870b1-113">**用户策略 (可选)** 可以指定一个或多个用户存档策略，每个存档策略都可以配置为为特定用户的内部或外部通信启用和禁用存档。</span><span class="sxs-lookup"><span data-stu-id="870b1-113">**User policies (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving for internal or external communications for a specific user.</span></span> <span data-ttu-id="870b1-114">用户策略会覆盖全局策略和站点策略，但仅限于分配了用户策略的用户。</span><span class="sxs-lookup"><span data-stu-id="870b1-114">A user policy overrides the global policy and site policies, but only for the user(s) to whom you assign a user policy.</span></span> <span data-ttu-id="870b1-115">可以编辑或删除用户策略。</span><span class="sxs-lookup"><span data-stu-id="870b1-115">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="870b1-116">如果使用 Exchange 集成在 Microsoft Exchange 中存储存档数据，则 Exchange 策略将控制 Exchange 上用户存档。</span><span class="sxs-lookup"><span data-stu-id="870b1-116">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange policies control archiving for users homed on Exchange.</span></span> <span data-ttu-id="870b1-117">若要为这些用户启用存档，必须将用户的邮箱置于In-Place保留状态。</span><span class="sxs-lookup"><span data-stu-id="870b1-117">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="870b1-118">若要为新的存档策略或现有的存档策略配置设置，请指定以下选项：</span><span class="sxs-lookup"><span data-stu-id="870b1-118">To configure the settings for a new or existing Archiving policy, you specify the following options:</span></span>
- <span data-ttu-id="870b1-119">**名称** 每个存档策略都需要一个名称。</span><span class="sxs-lookup"><span data-stu-id="870b1-119">**Name** Each Archiving policy requires a name.</span></span> <span data-ttu-id="870b1-120">该名称由要添加或编辑的策略类型确定：</span><span class="sxs-lookup"><span data-stu-id="870b1-120">The name is determined by the type of policy that you are adding or editing:</span></span>
    
  - <span data-ttu-id="870b1-121">**全局策略** 默认名称为 Global。</span><span class="sxs-lookup"><span data-stu-id="870b1-121">**Global policy** The default name is Global.</span></span> <span data-ttu-id="870b1-122">可以将该名称更改成一个更具描述性的名称。</span><span class="sxs-lookup"><span data-stu-id="870b1-122">You can change it to a more descriptive name.</span></span> <span data-ttu-id="870b1-123">例如，Contoso 北美机构。</span><span class="sxs-lookup"><span data-stu-id="870b1-123">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="870b1-124">**站点策略** 此对话框中列出的站点包括部署中所有可用的网站。</span><span class="sxs-lookup"><span data-stu-id="870b1-124">**Site policy** The sites listed in this dialog box include all available sites in your deployment.</span></span> <span data-ttu-id="870b1-125">单击某个站点将其选中。</span><span class="sxs-lookup"><span data-stu-id="870b1-125">Click a single site to select it.</span></span> <span data-ttu-id="870b1-126">例如，Redmond 数据中心。</span><span class="sxs-lookup"><span data-stu-id="870b1-126">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="870b1-127">**用户策略** 指定适当的名称，例如特定用户的名称或组织中用户组或团队的名称。</span><span class="sxs-lookup"><span data-stu-id="870b1-127">**User policy** Specify an appropriate name, such as the name of a specific user or the name of a user group or team in your organization.</span></span> <span data-ttu-id="870b1-128">例如，法律部门。</span><span class="sxs-lookup"><span data-stu-id="870b1-128">For example, Legal Department.</span></span>
    
- <span data-ttu-id="870b1-129">**说明** 这是可选的。</span><span class="sxs-lookup"><span data-stu-id="870b1-129">**Description** This is optional.</span></span> <span data-ttu-id="870b1-130">使用它提供其他详细信息，例如策略的范围或使用。</span><span class="sxs-lookup"><span data-stu-id="870b1-130">Use it to provide additional details, such as the scope or use of the policy.</span></span> <span data-ttu-id="870b1-131">例如，与其他网站的法律部门协调。</span><span class="sxs-lookup"><span data-stu-id="870b1-131">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="870b1-132">**存档内部通信** 选中此复选框可启用内部网络上通信的存档。</span><span class="sxs-lookup"><span data-stu-id="870b1-132">**Archive internal communications** Select this check box to enable archiving of communications on your internal network.</span></span> <span data-ttu-id="870b1-133">默认情况下，这在任何策略中都未启用。</span><span class="sxs-lookup"><span data-stu-id="870b1-133">By default, this is not enabled in any policy.</span></span>
    
- <span data-ttu-id="870b1-134">**存档外部通信** 选中此复选框可启用包括外部用户（如远程用户、 (匿名用户和 PIC 设置用户) 联盟伙伴）的存档。</span><span class="sxs-lookup"><span data-stu-id="870b1-134">**Archive external communications** Select this check box to enable archiving of communications that include external users, such as remote users, (including anonymous and PIC-setting users), and federated partners.</span></span> <span data-ttu-id="870b1-135">默认情况下，这在任何策略中都未启用。</span><span class="sxs-lookup"><span data-stu-id="870b1-135">By default, this is not enabled in any policy.</span></span>
    
<span data-ttu-id="870b1-136">有关存档特性和功能的详细信息，包括 Exchange 集成，请参阅 Plan [for archiving in Skype for Business Server，](../../../plan-your-deployment/archiving/archiving.md)Deploy archiving for Skype for Business [Server，](../../../deploy/deploy-archiving/deploy-archiving.md)and [Manage archiving in Skype for Business Server.](../../../manage/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="870b1-136">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

