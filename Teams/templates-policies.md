---
title: 管理中心中的管理团队模板
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
description: 了解如何在管理中心中管理团队模板
ms.openlocfilehash: dd88f76d0f74b6a1fe48bd934e7cfc8ee9ab4ccc
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684579"
---
# <a name="manage-team-templates-in-the-admin-center"></a><span data-ttu-id="7ad02-103">管理中心中的管理团队模板</span><span class="sxs-lookup"><span data-stu-id="7ad02-103">Manage team templates in the admin center</span></span>

<span data-ttu-id="7ad02-104">在管理中心创建模板策略，管理最终用户看到的团队模板。</span><span class="sxs-lookup"><span data-stu-id="7ad02-104">Manage the team templates that your end users see by creating templates policies in the admin center.</span></span> <span data-ttu-id="7ad02-105">在每个模板策略中，可以指定显示或隐藏的模板。</span><span class="sxs-lookup"><span data-stu-id="7ad02-105">Within each template policy, you can designate which templates are shown or hidden.</span></span>
<span data-ttu-id="7ad02-106">将不同的用户分配到不同的模板策略，以便用户仅查看指定的团队模板子集。</span><span class="sxs-lookup"><span data-stu-id="7ad02-106">Assign different users to different template policies so that your users view only the subset of team templates specified.</span></span>

<span data-ttu-id="7ad02-107">观看此简短视频，了解如何管理模板策略。</span><span class="sxs-lookup"><span data-stu-id="7ad02-107">Watch this short video to learn how to manage template policies.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyXL9]

## <a name="create-template-policies-and-assign-available-templates"></a><span data-ttu-id="7ad02-108">创建模板策略并分配可用模板</span><span class="sxs-lookup"><span data-stu-id="7ad02-108">Create template policies and assign available templates</span></span>

1. <span data-ttu-id="7ad02-109">登录到 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="7ad02-109">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="7ad02-110">展开 **Teams**  >  **模板策略"。**</span><span class="sxs-lookup"><span data-stu-id="7ad02-110">Expand **Teams** > **Templates policies**.</span></span>

3. <span data-ttu-id="7ad02-111">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="7ad02-111">Select **Add**.</span></span>

    ![已选择模板策略，并突出显示"添加"](media/template-policies-1.png)

1. <span data-ttu-id="7ad02-113">在"**模板策略设置** 部分中，完成以下字段：</span><span class="sxs-lookup"><span data-stu-id="7ad02-113">In the **Templates Policies Settings** section, complete the following fields:</span></span>

    - <span data-ttu-id="7ad02-114">模板策略名称</span><span class="sxs-lookup"><span data-stu-id="7ad02-114">Templates Policy name</span></span>

    - <span data-ttu-id="7ad02-115">模板策略简短说明</span><span class="sxs-lookup"><span data-stu-id="7ad02-115">Templates Policy short description</span></span>

2. <span data-ttu-id="7ad02-116">在"**可查看的模板"** 表中，选择要隐藏的模板，然后选择"隐藏 **"。**</span><span class="sxs-lookup"><span data-stu-id="7ad02-116">In the **Viewable Templates** table, select the templates you want to hide and select **Hide**.</span></span>

    ![突出显示"隐藏"的所选模板](media/template-policies-2.png)

    <span data-ttu-id="7ad02-118">可以在"隐藏模板"表中查看已选择 **隐藏的模板。**</span><span class="sxs-lookup"><span data-stu-id="7ad02-118">You can see the templates you've selected to hide in the **Hidden Templates** table.</span></span>

1. <span data-ttu-id="7ad02-119">若要取消隐藏某些模板，请滚动到"隐藏 **模板"** 表。</span><span class="sxs-lookup"><span data-stu-id="7ad02-119">To unhide certain templates, scroll to the **Hidden templates** table.</span></span>

2. <span data-ttu-id="7ad02-120">选择要取消隐藏模板，然后选择"显示 **"。**</span><span class="sxs-lookup"><span data-stu-id="7ad02-120">Select the templates to unhide, and then select **Show**.</span></span>

   ![未隐藏的所选模板](media/template-policies-3.png)

   <span data-ttu-id="7ad02-122">所选模板将显示在"可查看的模板 **"** 表中。</span><span class="sxs-lookup"><span data-stu-id="7ad02-122">The selected templates will appear in your **Viewable templates** table.</span></span>
3. <span data-ttu-id="7ad02-123">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="7ad02-123">Select **Save**.</span></span>

   <span data-ttu-id="7ad02-124">新模板策略显示在"模板 **策略"** 列表中。</span><span class="sxs-lookup"><span data-stu-id="7ad02-124">Your new template policy is displayed in the **Templates Policies** list.</span></span>

## <a name="assign-users-to-the-template-policies"></a><span data-ttu-id="7ad02-125">将用户分配到模板策略</span><span class="sxs-lookup"><span data-stu-id="7ad02-125">Assign users to the template policies</span></span>

<span data-ttu-id="7ad02-126">分配到策略的用户只能查看该策略中的可查看模板。</span><span class="sxs-lookup"><span data-stu-id="7ad02-126">Users assigned to a policy will only be able to view the viewable templates within that policy.</span></span>

1. <span data-ttu-id="7ad02-127">在 **"模板策略"** 中，选择一个策略，然后选择"**管理用户"。**</span><span class="sxs-lookup"><span data-stu-id="7ad02-127">From **Templates Policies**, select a policy, and then select **Manage users**.</span></span>

2. <span data-ttu-id="7ad02-128">键入要分配到此策略的用户。</span><span class="sxs-lookup"><span data-stu-id="7ad02-128">Type the users to assign to this policy.</span></span>

   ![将用户分配到模板策略](media/template-policies-4.png)

3. <span data-ttu-id="7ad02-130">选择"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="7ad02-130">Select **Apply**.</span></span>

> [!Note]
> <span data-ttu-id="7ad02-131">新策略最多可能需要 24 小时才能对最终用户生效。</span><span class="sxs-lookup"><span data-stu-id="7ad02-131">It might take up to 24 hours for your new policy to take effect for end users.</span></span>

## <a name="size-limits-for-template-policies"></a><span data-ttu-id="7ad02-132">模板策略的大小限制</span><span class="sxs-lookup"><span data-stu-id="7ad02-132">Size limits for Template policies</span></span>

<span data-ttu-id="7ad02-133">可以隐藏每个策略最多 100 个模板。</span><span class="sxs-lookup"><span data-stu-id="7ad02-133">You can hide a max of 100 templates per policy.</span></span> <span data-ttu-id="7ad02-134">如果 **给定** 策略已隐藏 100 个模板，则禁用"隐藏"按钮。</span><span class="sxs-lookup"><span data-stu-id="7ad02-134">The **Hide** button is disabled if the given policy already has 100 templates hidden.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="7ad02-135">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="7ad02-135">Frequently asked questions</span></span>

<span data-ttu-id="7ad02-136">**问：能否批量将用户分配到团队模板策略？**</span><span class="sxs-lookup"><span data-stu-id="7ad02-136">**Q: Can I batch assign users to team templates policies?**</span></span>
  
<span data-ttu-id="7ad02-137">答：是的，我们支持在 PowerShell 中对模板策略进行批处理分配。</span><span class="sxs-lookup"><span data-stu-id="7ad02-137">A: Yes, we support batch assignment for template policy in PowerShell.</span></span> <span data-ttu-id="7ad02-138">此操作的策略类型是 TeamsTemplatePermissionPolicy。</span><span class="sxs-lookup"><span data-stu-id="7ad02-138">The policy type for this action is TeamsTemplatePermissionPolicy.</span></span> [<span data-ttu-id="7ad02-139">了解更多信息</span><span class="sxs-lookup"><span data-stu-id="7ad02-139">Learn more</span></span>](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

<span data-ttu-id="7ad02-140">**问：能否将组分配到团队模板策略？**</span><span class="sxs-lookup"><span data-stu-id="7ad02-140">**Q: Can Groups be assigned to team templates policies?**</span></span>

<span data-ttu-id="7ad02-141">答：目前没有。</span><span class="sxs-lookup"><span data-stu-id="7ad02-141">A: Currently no.</span></span> <span data-ttu-id="7ad02-142">将来会提供此功能。</span><span class="sxs-lookup"><span data-stu-id="7ad02-142">This functionality will be available in the future.</span></span>

<span data-ttu-id="7ad02-143">**问：如果创建了一个新模板，该模板是否将包含在策略中？**</span><span class="sxs-lookup"><span data-stu-id="7ad02-143">**Q: If a new template is created, will the template be included in my policies?**</span></span>

<span data-ttu-id="7ad02-144">答：默认情况下，任何新模板都可见。</span><span class="sxs-lookup"><span data-stu-id="7ad02-144">A: Any new templates will be visible by default.</span></span> <span data-ttu-id="7ad02-145">可以选择在"模板策略"部分的管理中心中隐藏模板。</span><span class="sxs-lookup"><span data-stu-id="7ad02-145">You can choose to hide the template in the admin center in the Templates Policies section.</span></span>

<span data-ttu-id="7ad02-146">**问：删除模板后会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="7ad02-146">**Q: What happens if a template is deleted?**</span></span>

<span data-ttu-id="7ad02-147">答：任何已删除的模板将不再存在于任何模板策略中。</span><span class="sxs-lookup"><span data-stu-id="7ad02-147">A: Any deleted templates will no longer be present in any templates policies.</span></span>

<span data-ttu-id="7ad02-148">**问：能否将多个用户分配到管理中心中的Teams策略？**</span><span class="sxs-lookup"><span data-stu-id="7ad02-148">**Q: Can I assign multiple users to a template policy in the Teams Admin Center?**</span></span>

<span data-ttu-id="7ad02-149">答：可以。</span><span class="sxs-lookup"><span data-stu-id="7ad02-149">A: Yes.</span></span>

1. <span data-ttu-id="7ad02-150">在管理中心，转到"用户 **"。**</span><span class="sxs-lookup"><span data-stu-id="7ad02-150">In the Admin center, go to **Users**.</span></span>
1. <span data-ttu-id="7ad02-151">在"用户"列表表中，选择要分配到特定模板策略的用户。</span><span class="sxs-lookup"><span data-stu-id="7ad02-151">In the Users list table, select the users you want to assign to a certain templates policy.</span></span>
1. <span data-ttu-id="7ad02-152">选择"编辑设置"，并更改"模板策略"字段。</span><span class="sxs-lookup"><span data-stu-id="7ad02-152">Select Edit settings, and change the Templates policies field.</span></span>
1. <span data-ttu-id="7ad02-153">选择"应用"。</span><span class="sxs-lookup"><span data-stu-id="7ad02-153">Select apply.</span></span>
   <span data-ttu-id="7ad02-154">在 Microsoft [ \| Docs 中详细了解如何Microsoft Teams用户Microsoft Teams策略](./assign-policies.md#assign-a-policy-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="7ad02-154">Learn more [Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs](./assign-policies.md#assign-a-policy-to-a-batch-of-users).</span></span>

<span data-ttu-id="7ad02-155">**问：如何查看分配到特定策略的所有用户？**</span><span class="sxs-lookup"><span data-stu-id="7ad02-155">**Q: How do I view all users assigned to a specific policy?**</span></span>

<span data-ttu-id="7ad02-156">答：在管理中心：</span><span class="sxs-lookup"><span data-stu-id="7ad02-156">A: In the Admin center:</span></span>

1. <span data-ttu-id="7ad02-157">转到"用户 **"** 部分。</span><span class="sxs-lookup"><span data-stu-id="7ad02-157">Go to the **Users** section.</span></span>
2. <span data-ttu-id="7ad02-158">在"用户"列表表中选择筛选器，并筛选团队模板策略。</span><span class="sxs-lookup"><span data-stu-id="7ad02-158">Select the filter in the Users list table and filter for the team template policy.</span></span>
3. <span data-ttu-id="7ad02-159">选择"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="7ad02-159">Select **Apply**.</span></span>

![所选模板策略和查看用户](media/template-policies-5.png)

<span data-ttu-id="7ad02-161">**问：能否通过 PowerShell 管理模板策略？**</span><span class="sxs-lookup"><span data-stu-id="7ad02-161">**Q: Can I manage templates policies via PowerShell?**</span></span>

<span data-ttu-id="7ad02-162">答：不支持在 PowerShell 中管理模板。</span><span class="sxs-lookup"><span data-stu-id="7ad02-162">A: No, managing templates in PowerShell isn't supported.</span></span>

<span data-ttu-id="7ad02-163">**问：模板策略是否适用于 EDU？**</span><span class="sxs-lookup"><span data-stu-id="7ad02-163">**Q: Are templates policies applicable to EDU?**</span></span>

<span data-ttu-id="7ad02-164">答：不支持 EDU 的模板策略。</span><span class="sxs-lookup"><span data-stu-id="7ad02-164">A: No, template policies for EDU isn't supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7ad02-165">相关主题</span><span class="sxs-lookup"><span data-stu-id="7ad02-165">Related topics</span></span>

- [<span data-ttu-id="7ad02-166">管理中心中的团队模板入门</span><span class="sxs-lookup"><span data-stu-id="7ad02-166">Get started with team templates in the admin center</span></span>](./get-started-with-teams-templates-in-the-admin-console.md)

- [<span data-ttu-id="7ad02-167">创建自定义团队模板</span><span class="sxs-lookup"><span data-stu-id="7ad02-167">Create a custom team template</span></span>](./create-a-team-template.md)

- [<span data-ttu-id="7ad02-168">从现有团队创建模板</span><span class="sxs-lookup"><span data-stu-id="7ad02-168">Create a template from an existing team</span></span>](./create-template-from-existing-team.md)

- [<span data-ttu-id="7ad02-169">从现有团队模板创建团队模板</span><span class="sxs-lookup"><span data-stu-id="7ad02-169">Create a team template from an existing team template</span></span>](./create-template-from-existing-template.md)

- [<span data-ttu-id="7ad02-170">在 Microsoft Docs 中Microsoft Teams用户Microsoft Teams \| 策略</span><span class="sxs-lookup"><span data-stu-id="7ad02-170">Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span></span>](./assign-policies.md)

- [<span data-ttu-id="7ad02-171">将用户批量分配到策略</span><span class="sxs-lookup"><span data-stu-id="7ad02-171">Batch assign users to a policy</span></span>](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
