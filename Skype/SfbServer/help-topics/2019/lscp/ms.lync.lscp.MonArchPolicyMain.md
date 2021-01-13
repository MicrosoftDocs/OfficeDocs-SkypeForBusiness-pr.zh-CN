---
title: 存档策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: 使用存档策略为 Skype for Business Server 上用户启用和禁用存档。 在每个存档策略中，您可以对以下任一项或者两项启用或禁用存档：
ms.openlocfilehash: 041fc71da18ff38b14e82ce9d2ab14f366326b29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833612"
---
# <a name="archiving-policy"></a><span data-ttu-id="b2eeb-104">存档策略</span><span class="sxs-lookup"><span data-stu-id="b2eeb-104">Archiving Policy</span></span>
 
<span data-ttu-id="b2eeb-105">使用存档策略为 Skype for Business Server 上用户启用和禁用存档。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="b2eeb-106">在每个存档策略中，您可以对以下任一项或者两项启用或禁用存档：</span><span class="sxs-lookup"><span data-stu-id="b2eeb-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="b2eeb-107">内部通信</span><span class="sxs-lookup"><span data-stu-id="b2eeb-107">Internal communications</span></span>
    
- <span data-ttu-id="b2eeb-108">外部通信（在内部网络之外至少包含一位用户的通信）</span><span class="sxs-lookup"><span data-stu-id="b2eeb-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="b2eeb-109">存档策略包括全局策略以及可选的一个或多个站点和用户存档策略：</span><span class="sxs-lookup"><span data-stu-id="b2eeb-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="b2eeb-110">**全局策略** 默认情况下，在所有部署中创建全局策略。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="b2eeb-111">您可以编辑全局策略，但无法删除此策略。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="b2eeb-112">如果您尝试将其删除，则所有选项将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="b2eeb-113">**站点策略 (可选)** 可以指定一个或多个站点存档策略，每个存档策略都可以配置为启用和禁用对单个站点的内部或外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="b2eeb-114">站点策略会覆盖全局策略，但仅限于在存档站点策略中指定的站点。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="b2eeb-115">可以编辑或删除站点策略。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="b2eeb-116">**用户策略 (可选)** 可以指定一个或多个用户存档策略，每个存档策略都可以配置为为特定用户或用户组启用和禁用内部或外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="b2eeb-117">用户策略会覆盖全局策略和站点策略，但仅限于分配了用户级别存档策略的用户和用户组。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="b2eeb-118">可以编辑或删除用户策略。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b2eeb-119">存档策略仅适用于位于 Skype for Business Server 上的用户。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="b2eeb-120">如果使用 Exchange 集成在 Microsoft Exchange 中存储存档数据，则 Exchange 策略将控制 Exchange 上用户存档。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange policies control archiving for users homed on Exchange.</span></span> <span data-ttu-id="b2eeb-121">若要为这些用户启用存档，必须将用户的邮箱置于In-Place保留状态。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="b2eeb-p107">“存档策略”页将列出为部署配置的每个存档策略。该页还将显示策略名称、范围（全局、站点或用户）以及为每个存档策略启用的存档选项。在“存档策略”页上，您有以下选项：</span><span class="sxs-lookup"><span data-stu-id="b2eeb-p107">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy. From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="b2eeb-125">**新建** 可以添加以下一个或多个可选的存档策略：</span><span class="sxs-lookup"><span data-stu-id="b2eeb-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="b2eeb-126">站点策略</span><span class="sxs-lookup"><span data-stu-id="b2eeb-126">Site policy</span></span>
    
  - <span data-ttu-id="b2eeb-127">用户策略</span><span class="sxs-lookup"><span data-stu-id="b2eeb-127">User policy</span></span>
    
- <span data-ttu-id="b2eeb-128">**编辑** 您可以更改页面上列出的任何存档策略的选项。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="b2eeb-129">使用此选项，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b2eeb-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="b2eeb-130">**显示详细信息** 此选项可打开一个对话框，您可在其中更改存档策略的存档选项。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="b2eeb-131">**全选** 此选项可选择列表中的所有存档策略。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="b2eeb-132">**删除** 此选项可删除所有选定的存档策略。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="b2eeb-133">**操作** 可以使用此选项快速启用或禁用页面上列出的任何策略中的内部或外部通信存档，而不是编辑该策略。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="b2eeb-134">"操作" **下可用的** 选项取决于当前在存档策略中指定的选项。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="b2eeb-135">所有选项都可用，但当前对存档策略有效的选项除外。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="b2eeb-136">选项包括：</span><span class="sxs-lookup"><span data-stu-id="b2eeb-136">Options include the following:</span></span>
    
  - <span data-ttu-id="b2eeb-137">**启用内部通信的存档**</span><span class="sxs-lookup"><span data-stu-id="b2eeb-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="b2eeb-138">**禁用内部通信的存档**</span><span class="sxs-lookup"><span data-stu-id="b2eeb-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="b2eeb-139">**启用外部通信的存档**</span><span class="sxs-lookup"><span data-stu-id="b2eeb-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="b2eeb-140">**禁用外部通信的存档**</span><span class="sxs-lookup"><span data-stu-id="b2eeb-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="b2eeb-141">**刷新** 可以刷新" **存档策略** "页以验证所有存档策略的选项状态。</span><span class="sxs-lookup"><span data-stu-id="b2eeb-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="b2eeb-142">有关存档特性和功能的详细信息，包括 Exchange 集成，请参阅 Plan [for archiving in Skype for Business Server，](../../../plan-your-deployment/archiving/archiving.md)Deploy archiving for Skype for Business [Server，](../../../deploy/deploy-archiving/deploy-archiving.md)and [Manage archiving in Skype for Business Server.](../../../manage/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="b2eeb-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

