---
title: 在 Microsoft Teams 中管理策略包
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中使用和管理策略包，以简化、简化和帮助在管理用户组的策略时提供一致性。
ms.openlocfilehash: 5713274270a7784379eb47c6dd1fa875b41e20b1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162665"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="09ce3-103">在 Microsoft Teams 中管理策略包</span><span class="sxs-lookup"><span data-stu-id="09ce3-103">Manage policy packages in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="09ce3-104">本文讨论的功能之一（ [自定义策略包](#custom-policy-packages)）目前以个人预览版提供。</span><span class="sxs-lookup"><span data-stu-id="09ce3-104">One of the features discussed in this article, [custom policy packages](#custom-policy-packages), is currently in private preview.</span></span>

<span data-ttu-id="09ce3-105">Microsoft Teams 中的策略包是一组预定义的策略和策略设置，你可以将其分配给组织中具有类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="09ce3-105">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="09ce3-106">我们构建了策略包，用于简化、简化和帮助在管理组织中用户组的策略时提供一致性。</span><span class="sxs-lookup"><span data-stu-id="09ce3-106">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="09ce3-107">可以使用 Teams[中包含的策略包](#policy-packages-included-in-teams)，或在个人[](#custom-policy-packages)预览版中 (自定义策略) 。</span><span class="sxs-lookup"><span data-stu-id="09ce3-107">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages) (in private preview).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="管理中心中"策略包"页的屏幕截图":::

<span data-ttu-id="09ce3-109">可以自定义策略包中策略的设置以满足用户的需求。</span><span class="sxs-lookup"><span data-stu-id="09ce3-109">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="09ce3-110">更改包中的策略设置时，分配到该包的所有用户将获取更新的设置。</span><span class="sxs-lookup"><span data-stu-id="09ce3-110">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="09ce3-111">使用 Microsoft Teams 管理中心或 PowerShell 管理策略包。</span><span class="sxs-lookup"><span data-stu-id="09ce3-111">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="09ce3-112">什么是策略包？</span><span class="sxs-lookup"><span data-stu-id="09ce3-112">What is a policy package?</span></span>

<span data-ttu-id="09ce3-113">使用策略包可以控制要允许或限制组织中特定人员集的 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="09ce3-113">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="09ce3-114">Teams 中的每个策略包都围绕用户角色设计，包括预定义的策略和策略设置，这些策略和策略设置支持该角色的典型协作和通信活动。</span><span class="sxs-lookup"><span data-stu-id="09ce3-114">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="09ce3-115">策略包支持以下 Teams 策略类型：</span><span class="sxs-lookup"><span data-stu-id="09ce3-115">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="09ce3-116">消息传递策略</span><span class="sxs-lookup"><span data-stu-id="09ce3-116">Messaging policy</span></span>
- <span data-ttu-id="09ce3-117">会议策略</span><span class="sxs-lookup"><span data-stu-id="09ce3-117">Meeting policy</span></span>
- <span data-ttu-id="09ce3-118">应用设置策略</span><span class="sxs-lookup"><span data-stu-id="09ce3-118">App setup policy</span></span>
- <span data-ttu-id="09ce3-119">呼叫策略</span><span class="sxs-lookup"><span data-stu-id="09ce3-119">Calling policy</span></span>
- <span data-ttu-id="09ce3-120">实时事件策略</span><span class="sxs-lookup"><span data-stu-id="09ce3-120">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="09ce3-121">Teams 中包含的策略包</span><span class="sxs-lookup"><span data-stu-id="09ce3-121">Policy packages included in Teams</span></span>

<span data-ttu-id="09ce3-122">Teams 当前包括以下策略包。</span><span class="sxs-lookup"><span data-stu-id="09ce3-122">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="09ce3-123">**包名称**</span><span class="sxs-lookup"><span data-stu-id="09ce3-123">**Package name**</span></span>  |<span data-ttu-id="09ce3-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="09ce3-124">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="09ce3-125">教育 (教育学生) </span><span class="sxs-lookup"><span data-stu-id="09ce3-125">Education (Higher education student)</span></span>    |<span data-ttu-id="09ce3-126">创建一组适用于教育程度学生的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="09ce3-126">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="09ce3-127">教育 (中学生) </span><span class="sxs-lookup"><span data-stu-id="09ce3-127">Education (Primary school student)</span></span>   |<span data-ttu-id="09ce3-128">创建一组适用于主要学生的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="09ce3-128">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="09ce3-129">教育 (中学生) </span><span class="sxs-lookup"><span data-stu-id="09ce3-129">Education (Secondary school student)</span></span>    |<span data-ttu-id="09ce3-130">创建一组适用于学生的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="09ce3-130">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="09ce3-131">教育 (教师) </span><span class="sxs-lookup"><span data-stu-id="09ce3-131">Education (Teacher)</span></span>    |<span data-ttu-id="09ce3-132">创建一组适用于教师的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="09ce3-132">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="09ce3-133">使用 (远程学习的教师) </span><span class="sxs-lookup"><span data-stu-id="09ce3-133">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="09ce3-134">创建一组适用于主要教师的策略，在远程学习中最大化学生的安全和协作。</span><span class="sxs-lookup"><span data-stu-id="09ce3-134">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="09ce3-135">使用 (远程学习工具的"教育) </span><span class="sxs-lookup"><span data-stu-id="09ce3-135">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="09ce3-136">创建一组适用于主要学生的策略，在远程学习中最大化学生的安全和协作。</span><span class="sxs-lookup"><span data-stu-id="09ce3-136">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="09ce3-137">前端管理器</span><span class="sxs-lookup"><span data-stu-id="09ce3-137">Frontline manager</span></span> |<span data-ttu-id="09ce3-138">创建一组策略，将这些设置应用于组织的一线经理。</span><span class="sxs-lookup"><span data-stu-id="09ce3-138">Creates a set of policies and applies those settings to Frontline managers in your organization.</span></span> |
|<span data-ttu-id="09ce3-139">一线辅助角色</span><span class="sxs-lookup"><span data-stu-id="09ce3-139">Frontline worker</span></span> |<span data-ttu-id="09ce3-140">创建一组策略，将这些设置应用到组织的一线员工。</span><span class="sxs-lookup"><span data-stu-id="09ce3-140">Creates a set of policies and applies those settings to Frontline workers in your organization.</span></span> |
|<span data-ttu-id="09ce3-141">医疗保健临床工作者</span><span class="sxs-lookup"><span data-stu-id="09ce3-141">Healthcare clinical worker</span></span>  |<span data-ttu-id="09ce3-142">创建一组策略和策略设置，以使临床工作者（例如注册护士、护士长、医师和社会工作者）可以完全访问聊天、通话、轮班管理和会议。</span><span class="sxs-lookup"><span data-stu-id="09ce3-142">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="09ce3-143">医疗保健信息工作者</span><span class="sxs-lookup"><span data-stu-id="09ce3-143">Healthcare information worker</span></span>  |<span data-ttu-id="09ce3-144">创建一组策略和策略设置，以使信息工作者（例如 IT 人员、信息学人员、财务人员和合规专员）可以完全访问聊天、通话和会议。</span><span class="sxs-lookup"><span data-stu-id="09ce3-144">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="09ce3-145">医疗保健病房</span><span class="sxs-lookup"><span data-stu-id="09ce3-145">Healthcare patient room</span></span>  |<span data-ttu-id="09ce3-146">创建一组适用于医疗保健组织中病房的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="09ce3-146">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="09ce3-147">小型企业和中型企业用户 (Business Voice) </span><span class="sxs-lookup"><span data-stu-id="09ce3-147">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="09ce3-148">创建一个应用设置策略，其中包含用于业务语音体验的应用。</span><span class="sxs-lookup"><span data-stu-id="09ce3-148">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="09ce3-149">没有 Business Voice (的中小型企业) </span><span class="sxs-lookup"><span data-stu-id="09ce3-149">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="09ce3-150">为具有非业务语音体验的中小型企业 Teams 用户创建 (设置) 。</span><span class="sxs-lookup"><span data-stu-id="09ce3-150">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="09ce3-151">公共安全人员</span><span class="sxs-lookup"><span data-stu-id="09ce3-151">Public safety officer</span></span>   |<span data-ttu-id="09ce3-152">创建一组适用于组织中公共安全人员的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="09ce3-152">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="09ce3-153">我们将在将来的 Teams 版本中添加更多策略包，因此请返回查看最新信息。</span><span class="sxs-lookup"><span data-stu-id="09ce3-153">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="09ce3-154">将为每个单独的策略提供策略包的名称，以便你可以轻松识别链接到该策略包的策略。</span><span class="sxs-lookup"><span data-stu-id="09ce3-154">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="09ce3-155">例如，将教育 (教师) 策略包分配给学校中的教师时，会为包中的每个策略创建名为 Education_Teacher 的策略。</span><span class="sxs-lookup"><span data-stu-id="09ce3-155">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![教育教师教师 (策略) 屏幕截图](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="09ce3-157">自定义策略包</span><span class="sxs-lookup"><span data-stu-id="09ce3-157">Custom policy packages</span></span>

<span data-ttu-id="09ce3-158">**此功能在私有预览版中**</span><span class="sxs-lookup"><span data-stu-id="09ce3-158">**This feature is in private preview**</span></span>

<span data-ttu-id="09ce3-159">自定义策略包允许为组织中具有类似角色的用户捆绑自己的策略集。</span><span class="sxs-lookup"><span data-stu-id="09ce3-159">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="09ce3-160">通过添加所需的策略类型和策略创建自己的策略包。</span><span class="sxs-lookup"><span data-stu-id="09ce3-160">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="09ce3-161">创建新的自定义策略包：</span><span class="sxs-lookup"><span data-stu-id="09ce3-161">To create a new custom policy package:</span></span>

1. <span data-ttu-id="09ce3-162">在 Microsoft Teams 管理中心的左侧导航栏中，选择"**策略包"，** 然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="09ce3-162">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>
    :::image type="content" source="media/policy-packages-add.png" alt-text="管理中心中"策略包"页面上的"添加"按钮的屏幕截图":::
2. <span data-ttu-id="09ce3-164">输入包的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="09ce3-164">Enter a name and description for your package.</span></span>
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="添加新的自定义策略包的屏幕截图":::
3. <span data-ttu-id="09ce3-166">选择要包括在包中的策略类型和策略名称。</span><span class="sxs-lookup"><span data-stu-id="09ce3-166">Select the policy types and policy names to include in the package.</span></span>
4. <span data-ttu-id="09ce3-167">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="09ce3-167">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="09ce3-168">如何使用策略包</span><span class="sxs-lookup"><span data-stu-id="09ce3-168">How to use policy packages</span></span>

<span data-ttu-id="09ce3-169">下面概述了如何在组织中使用策略包。</span><span class="sxs-lookup"><span data-stu-id="09ce3-169">The following outlines how to use policy packages in your organization.</span></span>

![如何使用策略包的概述](media/manage-policy-packages-overview.png)

- <span data-ttu-id="09ce3-171">**[视图](#view-the-settings-of-a-policy-in-a-policy-package)**：查看策略包中的策略。</span><span class="sxs-lookup"><span data-stu-id="09ce3-171">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="09ce3-172">然后，在分配包之前，查看包中每个策略的设置。</span><span class="sxs-lookup"><span data-stu-id="09ce3-172">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="09ce3-173">请确保了解每个设置。</span><span class="sxs-lookup"><span data-stu-id="09ce3-173">Make sure that you understand each setting.</span></span> <span data-ttu-id="09ce3-174">根据组织的需求，确定预定义值是否适合组织，或者是否需要更改这些值，以更严格或宽松。</span><span class="sxs-lookup"><span data-stu-id="09ce3-174">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="09ce3-175">如果策略已删除，仍可查看设置，但无法更改任何设置。</span><span class="sxs-lookup"><span data-stu-id="09ce3-175">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="09ce3-176">分配策略包时，会使用预定义设置重新创建已删除的策略。</span><span class="sxs-lookup"><span data-stu-id="09ce3-176">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="09ce3-177">**[自定义](#customize-policies-in-a-policy-package)**：自定义策略包中的策略设置，以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="09ce3-177">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="09ce3-178">**[分配](#assign-a-policy-package)**：将策略包分配给用户。</span><span class="sxs-lookup"><span data-stu-id="09ce3-178">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="09ce3-179">分配包后，还可以更改策略包中的策略设置。</span><span class="sxs-lookup"><span data-stu-id="09ce3-179">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="09ce3-180">对策略设置所做的任何更改都将自动应用到已分配了该包的用户。</span><span class="sxs-lookup"><span data-stu-id="09ce3-180">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="09ce3-181">下面是在 Microsoft Teams 管理中心中查看、分配和自定义策略包的步骤。</span><span class="sxs-lookup"><span data-stu-id="09ce3-181">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="09ce3-182">查看策略包中的策略设置</span><span class="sxs-lookup"><span data-stu-id="09ce3-182">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="09ce3-183">在 Microsoft Teams 管理中心的左侧导航栏中，选择"策略包"，然后单击程序包名称左侧选择策略包。</span><span class="sxs-lookup"><span data-stu-id="09ce3-183">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="09ce3-184">单击要查看的策略。</span><span class="sxs-lookup"><span data-stu-id="09ce3-184">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="09ce3-185">自定义策略包中的策略</span><span class="sxs-lookup"><span data-stu-id="09ce3-185">Customize policies in a policy package</span></span>

<span data-ttu-id="09ce3-186">可以通过"策略包"页或直接进入Microsoft Teams 管理中心的策略页面来编辑策略设置。</span><span class="sxs-lookup"><span data-stu-id="09ce3-186">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="09ce3-187">在 Microsoft Teams 管理中心的左侧导航栏中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="09ce3-187">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="09ce3-188">单击 **"策略** 包"，然后单击包名称左侧选择策略包。</span><span class="sxs-lookup"><span data-stu-id="09ce3-188">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="09ce3-189">单击策略类型。</span><span class="sxs-lookup"><span data-stu-id="09ce3-189">Click the policy type.</span></span>  <span data-ttu-id="09ce3-190">例如，单击"**消息传送策略"。**</span><span class="sxs-lookup"><span data-stu-id="09ce3-190">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="09ce3-191">选择要编辑的策略。</span><span class="sxs-lookup"><span data-stu-id="09ce3-191">Select the policy you want to edit.</span></span> <span data-ttu-id="09ce3-192">链接到策略包的策略与策略包同名。</span><span class="sxs-lookup"><span data-stu-id="09ce3-192">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="09ce3-193">进行您需要的更改，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="09ce3-193">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="09ce3-194">分配策略包</span><span class="sxs-lookup"><span data-stu-id="09ce3-194">Assign a policy package</span></span> 

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="09ce3-195">将策略包分配给一个用户</span><span class="sxs-lookup"><span data-stu-id="09ce3-195">Assign a policy package to one user</span></span>

1. <span data-ttu-id="09ce3-196">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。</span><span class="sxs-lookup"><span data-stu-id="09ce3-196">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="09ce3-197">在用户的页面上，单击"策略 **"，** 然后在"**策略包"旁边** 单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="09ce3-197">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="09ce3-198">在"**分配策略包"** 窗格中，选择要分配的包，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="09ce3-198">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="09ce3-199">将策略包分配给多个用户</span><span class="sxs-lookup"><span data-stu-id="09ce3-199">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="09ce3-200">在 Microsoft Teams 管理中心的左侧导航中，转到"策略包"，然后单击程序包名称左侧，选择要分配的策略包。</span><span class="sxs-lookup"><span data-stu-id="09ce3-200">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="09ce3-201">单击"**管理用户"。**</span><span class="sxs-lookup"><span data-stu-id="09ce3-201">Click **Manage users**.</span></span>
3. <span data-ttu-id="09ce3-202">在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="09ce3-202">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="09ce3-203">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="09ce3-203">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="09ce3-204">添加完用户后，单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="09ce3-204">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="09ce3-205">将策略包分配给组。</span><span class="sxs-lookup"><span data-stu-id="09ce3-205">Assign a policy package to a group</span></span>

<span data-ttu-id="09ce3-206">通过将策略包分配到组，可将多个策略分配给一组用户，例如安全组或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="09ce3-206">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="09ce3-207">根据优先级规则，将策略分配传播到组中的成员。</span><span class="sxs-lookup"><span data-stu-id="09ce3-207">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="09ce3-208">将成员添加到组或从组中删除成员时，将相应更新其继承的策略分配。</span><span class="sxs-lookup"><span data-stu-id="09ce3-208">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="09ce3-209">建议将此方法用于最多 50,000 个用户的组，但也可使用更大的组。</span><span class="sxs-lookup"><span data-stu-id="09ce3-209">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="09ce3-210">若要了解详细信息，请参阅[将策略包分配到组](assign-policies.md#assign-a-policy-package-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="09ce3-210">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="09ce3-211">向大型组（批处理）分配策略包</span><span class="sxs-lookup"><span data-stu-id="09ce3-211">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="09ce3-212">使用批处理策略包分配，每次向大型用户组分配策略包。</span><span class="sxs-lookup"><span data-stu-id="09ce3-212">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="09ce3-213">使用 [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet 提交要分配的一批用户和策略包。</span><span class="sxs-lookup"><span data-stu-id="09ce3-213">You use the [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="09ce3-214">作业将作为后台操作处理，并为每个批处理生成操作 ID。</span><span class="sxs-lookup"><span data-stu-id="09ce3-214">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="09ce3-215">批处理最多可包含 5,000 个用户。</span><span class="sxs-lookup"><span data-stu-id="09ce3-215">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="09ce3-216">可通过对象 Id、UPN、SIP 地址或电子邮件地址指定用户。</span><span class="sxs-lookup"><span data-stu-id="09ce3-216">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="09ce3-217">若要了解详细信息，请参阅[将策略包分配给批次用户](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="09ce3-217">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="09ce3-218">疑难解答</span><span class="sxs-lookup"><span data-stu-id="09ce3-218">Troubleshooting</span></span>

<span data-ttu-id="09ce3-219">**分配策略包时收到错误**</span><span class="sxs-lookup"><span data-stu-id="09ce3-219">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="09ce3-220">如果未成功创建或应用包中的一个或多个策略，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="09ce3-220">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="09ce3-221">将策略包重新分配给用户。</span><span class="sxs-lookup"><span data-stu-id="09ce3-221">Reassign the policy package to your users.</span></span> <span data-ttu-id="09ce3-222">重试操作通常可以修复此问题。</span><span class="sxs-lookup"><span data-stu-id="09ce3-222">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="09ce3-223">相关主题</span><span class="sxs-lookup"><span data-stu-id="09ce3-223">Related topics</span></span>

[<span data-ttu-id="09ce3-224">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="09ce3-224">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="09ce3-225">适用于 EDU 管理员的 Teams 策略包</span><span class="sxs-lookup"><span data-stu-id="09ce3-225">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)

[<span data-ttu-id="09ce3-226">Teams 医疗保健策略包</span><span class="sxs-lookup"><span data-stu-id="09ce3-226">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)

[<span data-ttu-id="09ce3-227">适用于政府的 Teams 策略包</span><span class="sxs-lookup"><span data-stu-id="09ce3-227">Teams policy packages for government</span></span>](policy-packages-gov.md)