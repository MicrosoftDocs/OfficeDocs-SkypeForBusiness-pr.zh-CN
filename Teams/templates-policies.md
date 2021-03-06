---
title: 在管理中心管理 Teams 模板
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: yinchang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何在管理中心管理 Teams 模板
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: bcb99538ebd129e02e511c8260dc3bfa101bff9d
ms.sourcegitcommit: 113f587a1c09d42b7394ba1195c32cb054bdf31c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50507965"
---
# <a name="create-and-manage-teams-templates-in-the-admin-center"></a><span data-ttu-id="dcd5d-103">在管理中心创建和管理 Teams 模板</span><span class="sxs-lookup"><span data-stu-id="dcd5d-103">Create and manage Teams templates in the admin center</span></span>

<span data-ttu-id="dcd5d-104">在管理中心创建模板策略，管理最终用户看到的 Teams 模板。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-104">Manage the Teams templates that your end users see by creating templates policies in the admin center.</span></span> <span data-ttu-id="dcd5d-105">在每个模板策略中，可以指定显示或隐藏的模板。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-105">Within each template policy, you can designate which templates are shown or hidden.</span></span>
<span data-ttu-id="dcd5d-106">将不同的用户分配到不同的模板策略，以便用户仅查看指定的 Teams 模板子集。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-106">Assign different users to different template policies so that your users only view the subset of Teams templates specified.</span></span>

## <a name="create-template-policies-and-assign-available-templates"></a><span data-ttu-id="dcd5d-107">创建模板策略并分配可用模板</span><span class="sxs-lookup"><span data-stu-id="dcd5d-107">Create template policies and assign available templates</span></span>

1. <span data-ttu-id="dcd5d-108">登录到 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-108">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="dcd5d-109">展开 **Teams**  >  **模板策略**。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-109">Expand **Teams** > **Templates policies**.</span></span>

3. <span data-ttu-id="dcd5d-110">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-110">Select **Add**.</span></span>

    ![已选择模板策略并突出显示"添加"](media/template-policies-1.png)

1. <span data-ttu-id="dcd5d-112">在" **模板策略设置** "部分中，完成以下字段：</span><span class="sxs-lookup"><span data-stu-id="dcd5d-112">In the **Templates Policies Settings** section, complete the following fields:</span></span>

    - <span data-ttu-id="dcd5d-113">模板策略名称</span><span class="sxs-lookup"><span data-stu-id="dcd5d-113">Templates Policy name</span></span>

    - <span data-ttu-id="dcd5d-114">模板策略简短说明</span><span class="sxs-lookup"><span data-stu-id="dcd5d-114">Templates Policy short description</span></span>

2. <span data-ttu-id="dcd5d-115">在"**可查看的模板"** 表中，选择要隐藏的模板，然后选择"隐藏 **"。**</span><span class="sxs-lookup"><span data-stu-id="dcd5d-115">In the **Viewable Templates** table, select the templates you want to hide and select **Hide**.</span></span>

    ![突出显示"隐藏"的所选模板](media/template-policies-2.png)

    <span data-ttu-id="dcd5d-117">可以在"隐藏模板"表中查看已选择 **隐藏的模板。**</span><span class="sxs-lookup"><span data-stu-id="dcd5d-117">You can see the templates you've selected to hide in the **Hidden Templates** table.</span></span>

1. <span data-ttu-id="dcd5d-118">若要取消隐藏某些模板，请滚动到 **"隐藏模板"** 表。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-118">To unhide certain templates, scroll to the **Hidden templates** table.</span></span>

1. <span data-ttu-id="dcd5d-119">选择要取消隐藏模板，然后选择"显示 **"。**</span><span class="sxs-lookup"><span data-stu-id="dcd5d-119">Select the templates to unhide, and then select **Show**.</span></span>

   ![未隐藏的所选模板](media/template-policies-3.png)

   <span data-ttu-id="dcd5d-121">所选模板将显示在"可查看的模板 **"表中** 。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-121">The selected templates will appear in your **Viewable templates** table.</span></span>
3. <span data-ttu-id="dcd5d-122">选择 **"保存"。**</span><span class="sxs-lookup"><span data-stu-id="dcd5d-122">Select **Save**.</span></span>

   <span data-ttu-id="dcd5d-123">新模板策略显示在" **模板策略"** 列表中。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-123">Your new template policy is displayed in the **Templates Policies** list.</span></span>

## <a name="assign-users-to-the-template-policies"></a><span data-ttu-id="dcd5d-124">将用户分配到模板策略</span><span class="sxs-lookup"><span data-stu-id="dcd5d-124">Assign users to the template policies</span></span>

<span data-ttu-id="dcd5d-125">分配到策略的用户只能查看该策略中的可查看模板。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-125">Users assigned to a policy will only be able to view the viewable templates within that policy.</span></span>

1. <span data-ttu-id="dcd5d-126">从 **"模板策略"** 中选择一个策略，然后选择"**管理用户"。**</span><span class="sxs-lookup"><span data-stu-id="dcd5d-126">From **Templates Policies**, select a policy, and then select **Manage users**.</span></span>

2. <span data-ttu-id="dcd5d-127">键入要分配到此策略的用户。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-127">Type the users to assign to this policy.</span></span>

   ![将用户分配到模板策略](media/template-policies-4.png)

3. <span data-ttu-id="dcd5d-129">选择 **"应用"。**</span><span class="sxs-lookup"><span data-stu-id="dcd5d-129">Select **Apply**.</span></span>

> [!Note]
> <span data-ttu-id="dcd5d-130">新策略最多可能需要 24 小时才能对最终用户生效。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-130">It might take up to 24 hours for your new policy to take effect for end users.</span></span>

## <a name="size-limits-for-template-policies"></a><span data-ttu-id="dcd5d-131">模板策略的大小限制</span><span class="sxs-lookup"><span data-stu-id="dcd5d-131">Size limits for Template policies</span></span>

<span data-ttu-id="dcd5d-132">每个策略最多可以隐藏 100 个模板。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-132">You can hide a max of 100 templates per policy.</span></span> <span data-ttu-id="dcd5d-133">如果 **给定** 策略已隐藏 100 个模板，则禁用"隐藏"按钮。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-133">The **Hide** button is disabled if the given policy already has 100 templates hidden.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="dcd5d-134">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="dcd5d-134">Frequently asked questions</span></span>

<span data-ttu-id="dcd5d-135">**问：能否批量将用户分配到团队模板策略？**</span><span class="sxs-lookup"><span data-stu-id="dcd5d-135">**Q: Can I batch assign users to team templates policies?**</span></span>
  
<span data-ttu-id="dcd5d-136">答：是的，我们支持在 PowerShell 中对模板策略进行批处理分配。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-136">A: Yes, we support batch assignment for template policy in PowerShell.</span></span> <span data-ttu-id="dcd5d-137">此操作的策略类型是 TeamsTemplatePermissionPolicy。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-137">The policy type for this action is TeamsTemplatePermissionPolicy.</span></span> [<span data-ttu-id="dcd5d-138">了解更多信息</span><span class="sxs-lookup"><span data-stu-id="dcd5d-138">Learn more</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)

<span data-ttu-id="dcd5d-139">**问：能否将组分配到团队模板策略？**</span><span class="sxs-lookup"><span data-stu-id="dcd5d-139">**Q: Can Groups be assigned to team templates policies?**</span></span>

<span data-ttu-id="dcd5d-140">答：目前否。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-140">A: Currently no.</span></span> <span data-ttu-id="dcd5d-141">将来会提供此功能。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-141">This functionality will be available in the future.</span></span>

<span data-ttu-id="dcd5d-142">**问：如果创建了一个新模板，该模板是否将包含在策略中？**</span><span class="sxs-lookup"><span data-stu-id="dcd5d-142">**Q: If a new template is created, will the template be included in my policies?**</span></span>

<span data-ttu-id="dcd5d-143">答：默认情况下，任何新模板都可见。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-143">A: Any new templates will be visible by default.</span></span> <span data-ttu-id="dcd5d-144">可以选择在"模板策略"部分的管理中心中隐藏模板。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-144">You can choose to hide the template in the admin center in the Templates Policies section.</span></span>

<span data-ttu-id="dcd5d-145">**问：删除模板会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="dcd5d-145">**Q: What happens if a template is deleted?**</span></span>

<span data-ttu-id="dcd5d-146">答：任何已删除的模板将不再存在于任何模板策略中。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-146">A: Any deleted templates will no longer be present in any templates policies.</span></span>

<span data-ttu-id="dcd5d-147">**问：能否将多个用户分配到 Teams 管理中心中的模板策略？**</span><span class="sxs-lookup"><span data-stu-id="dcd5d-147">**Q: Can I assign multiple users to a template policy in the Teams Admin Center?**</span></span>

<span data-ttu-id="dcd5d-148">答：是的。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-148">A: Yes.</span></span>

1. <span data-ttu-id="dcd5d-149">在管理中心，转到"**用户"。**</span><span class="sxs-lookup"><span data-stu-id="dcd5d-149">In the Admin center, go to **Users**.</span></span>
1. <span data-ttu-id="dcd5d-150">在"用户"列表表中，选择要分配给特定模板策略的用户。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-150">In the Users list table, select the users you want to assign to a certain templates policy.</span></span>
1. <span data-ttu-id="dcd5d-151">选择"编辑设置"，然后更改"模板策略"字段。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-151">Select Edit settings, and change the Templates policies field.</span></span>
1. <span data-ttu-id="dcd5d-152">选择"应用"。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-152">Select apply.</span></span>
   <span data-ttu-id="dcd5d-153">在 Microsoft [Teams 中详细了解如何为用户分配策略 - Microsoft Teams \| Microsoft Docs。](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users)</span><span class="sxs-lookup"><span data-stu-id="dcd5d-153">Learn more [Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).</span></span>

<span data-ttu-id="dcd5d-154">**问：如何查看分配给特定策略的所有用户？**</span><span class="sxs-lookup"><span data-stu-id="dcd5d-154">**Q: How do I view all users assigned to a specific policy?**</span></span>

<span data-ttu-id="dcd5d-155">答：在管理中心：</span><span class="sxs-lookup"><span data-stu-id="dcd5d-155">A: In the Admin center:</span></span>

1. <span data-ttu-id="dcd5d-156">转到"用户 **"** 部分。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-156">Go to the **Users** section.</span></span>
2. <span data-ttu-id="dcd5d-157">在"用户"列表表中选择筛选器，然后筛选团队模板策略。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-157">Select the filter in the Users list table and filter for the teams template policy.</span></span>
3. <span data-ttu-id="dcd5d-158">选择 **"应用"。**</span><span class="sxs-lookup"><span data-stu-id="dcd5d-158">Select **Apply**.</span></span>

![所选模板策略并查看用户](media/template-policies-5.png)

<span data-ttu-id="dcd5d-160">**问：我能否通过 PowerShell 管理模板策略？**</span><span class="sxs-lookup"><span data-stu-id="dcd5d-160">**Q: Can I manage templates policies via PowerShell?**</span></span>

<span data-ttu-id="dcd5d-161">答：不支持在 PowerShell 中管理模板。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-161">A: No, managing templates in PowerShell isn't supported.</span></span>

<span data-ttu-id="dcd5d-162">**问：模板策略是否适用于 EDU？**</span><span class="sxs-lookup"><span data-stu-id="dcd5d-162">**Q: Are templates policies applicable to EDU?**</span></span>

<span data-ttu-id="dcd5d-163">答：不支持，不支持 EDU 的模板策略。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-163">A: No, template policies for EDU isn't supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dcd5d-164">相关主题</span><span class="sxs-lookup"><span data-stu-id="dcd5d-164">Related topics</span></span>

- [<span data-ttu-id="dcd5d-165">管理中心中的团队模板入门</span><span class="sxs-lookup"><span data-stu-id="dcd5d-165">Get started with team templates in the admin center</span></span>](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [<span data-ttu-id="dcd5d-166">创建自定义团队模板</span><span class="sxs-lookup"><span data-stu-id="dcd5d-166">Create a custom team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [<span data-ttu-id="dcd5d-167">从现有团队创建模板</span><span class="sxs-lookup"><span data-stu-id="dcd5d-167">Create a template from an existing team</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [<span data-ttu-id="dcd5d-168">从现有团队模板创建团队模板</span><span class="sxs-lookup"><span data-stu-id="dcd5d-168">Create a team template from an existing team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [<span data-ttu-id="dcd5d-169">在 Microsoft Teams 中向用户分配策略 - Microsoft Teams \| Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="dcd5d-169">Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span></span>](https://docs.microsoft.com/microsoftteams/assign-policies)

- [<span data-ttu-id="dcd5d-170">将用户批量分配到策略</span><span class="sxs-lookup"><span data-stu-id="dcd5d-170">Batch assign users to a policy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)
