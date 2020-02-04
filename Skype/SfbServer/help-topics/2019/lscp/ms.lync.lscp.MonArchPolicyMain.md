---
title: 存档策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: 使用存档策略为驻留在 Skype for business 服务器上的用户启用和禁用存档。 在每个存档策略中，您可以对以下任一项或者两项启用或禁用存档：
ms.openlocfilehash: 63d1001a972b185fd8e36596798bc23e36a6ca3a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41704787"
---
# <a name="archiving-policy"></a><span data-ttu-id="9b17c-104">存档策略</span><span class="sxs-lookup"><span data-stu-id="9b17c-104">Archiving Policy</span></span>
 
<span data-ttu-id="9b17c-105">使用存档策略为驻留在 Skype for business 服务器上的用户启用和禁用存档。</span><span class="sxs-lookup"><span data-stu-id="9b17c-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="9b17c-106">在每个存档策略中，您可以对以下任一项或者两项启用或禁用存档：</span><span class="sxs-lookup"><span data-stu-id="9b17c-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="9b17c-107">内部通信</span><span class="sxs-lookup"><span data-stu-id="9b17c-107">Internal communications</span></span>
    
- <span data-ttu-id="9b17c-108">外部通信（在内部网络之外至少包含一位用户的通信）</span><span class="sxs-lookup"><span data-stu-id="9b17c-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="9b17c-109">存档策略包括全局策略以及可选的一个或多个站点和用户存档策略：</span><span class="sxs-lookup"><span data-stu-id="9b17c-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="9b17c-110">**全局策略**默认情况下，全局策略在所有部署中创建。</span><span class="sxs-lookup"><span data-stu-id="9b17c-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="9b17c-111">您可以编辑全局策略，但无法删除此策略。</span><span class="sxs-lookup"><span data-stu-id="9b17c-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="9b17c-112">如果您尝试将其删除，则所有选项将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="9b17c-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="9b17c-113">**网站策略（可选）** 你可以指定一个或多个网站存档策略，每个策略都可以配置为对单个网站启用和禁用内部或外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="9b17c-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="9b17c-114">站点策略会覆盖全局策略，但仅限于在存档站点策略中指定的站点。</span><span class="sxs-lookup"><span data-stu-id="9b17c-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="9b17c-115">可以编辑或删除站点策略。</span><span class="sxs-lookup"><span data-stu-id="9b17c-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="9b17c-116">**用户策略（可选）** 你可以指定一个或多个用户存档策略，每个策略都可以配置为特定用户或用户组启用和禁用内部或外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="9b17c-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="9b17c-117">用户策略会覆盖全局策略和站点策略，但仅限于分配了用户级别存档策略的用户和用户组。</span><span class="sxs-lookup"><span data-stu-id="9b17c-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="9b17c-118">可以编辑或删除用户策略。</span><span class="sxs-lookup"><span data-stu-id="9b17c-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9b17c-119">存档策略仅适用于驻留在 Skype for Business 服务器上的用户。</span><span class="sxs-lookup"><span data-stu-id="9b17c-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="9b17c-120">如果您使用 Exchange 集成将存档数据存储在 Microsoft Exchange 中，则 Exchange 策略将控制驻留在 Exchange 上的用户的存档。</span><span class="sxs-lookup"><span data-stu-id="9b17c-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange policies control archiving for users homed on Exchange.</span></span> <span data-ttu-id="9b17c-121">若要为这些用户启用存档，用户的邮箱必须放置在原地保留。</span><span class="sxs-lookup"><span data-stu-id="9b17c-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="9b17c-p107">“**存档策略**”页将列出为部署配置的每个存档策略。该页还将显示策略名称、范围（全局、站点或用户）以及为每个存档策略启用的存档选项。在“**存档策略**”页上，您有以下选项：</span><span class="sxs-lookup"><span data-stu-id="9b17c-p107">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy. From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="9b17c-125">**新**你可以添加以下每个可选存档策略中的一个或多个：</span><span class="sxs-lookup"><span data-stu-id="9b17c-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="9b17c-126">站点策略</span><span class="sxs-lookup"><span data-stu-id="9b17c-126">Site policy</span></span>
    
  - <span data-ttu-id="9b17c-127">用户策略</span><span class="sxs-lookup"><span data-stu-id="9b17c-127">User policy</span></span>
    
- <span data-ttu-id="9b17c-128">**编辑**你可以更改页面上列出的任何存档策略的选项。</span><span class="sxs-lookup"><span data-stu-id="9b17c-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="9b17c-129">使用此选项，您可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9b17c-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="9b17c-130">**显示详细信息** 此选项可打开一个对话框，您可在其中更改存档策略的存档选项。</span><span class="sxs-lookup"><span data-stu-id="9b17c-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="9b17c-131">**全选** 此选项可选择列表中的所有存档策略。</span><span class="sxs-lookup"><span data-stu-id="9b17c-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="9b17c-132">**删除** 此选项可删除所有选定的存档策略。</span><span class="sxs-lookup"><span data-stu-id="9b17c-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="9b17c-133">**操作**可使用此选项快速启用或禁用对页面上列出的任何策略（而不是编辑策略）的内部或外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="9b17c-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="9b17c-134">"**操作**" 下的可用选项取决于存档策略中当前指定的选项。</span><span class="sxs-lookup"><span data-stu-id="9b17c-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="9b17c-135">除了当前对存档策略有效的选项之外，所有选项均可用。</span><span class="sxs-lookup"><span data-stu-id="9b17c-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="9b17c-136">选项包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="9b17c-136">Options include the following:</span></span>
    
  - <span data-ttu-id="9b17c-137">**启用内部通信的存档**</span><span class="sxs-lookup"><span data-stu-id="9b17c-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="9b17c-138">**禁用内部通信的存档**</span><span class="sxs-lookup"><span data-stu-id="9b17c-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="9b17c-139">**启用外部通信的存档**</span><span class="sxs-lookup"><span data-stu-id="9b17c-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="9b17c-140">**禁用外部通信的存档**</span><span class="sxs-lookup"><span data-stu-id="9b17c-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="9b17c-141">**刷新**你可以刷新 "**存档策略**" 页面以验证所有存档策略的选项的状态。</span><span class="sxs-lookup"><span data-stu-id="9b17c-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="9b17c-142">有关存档功能和功能（包括 Exchange 集成）的详细信息，请参阅[在 skype for Business 服务器中规划存档](../../../plan-your-deployment/archiving/archiving.md)、[部署 Skype for business 服务器存档](../../../deploy/deploy-archiving/deploy-archiving.md)和[管理 skype for business 服务器中的存档](../../../manage/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="9b17c-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

