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
description: 了解如何使用和管理 Microsoft Teams 中的策略包，以简化、简化和帮助在管理用户组的策略时提供一致性。
ms.openlocfilehash: 62250644d29f65a9c650db0e80477eec6baf4f3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49839457"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="77c63-103">在 Microsoft Teams 中管理策略包</span><span class="sxs-lookup"><span data-stu-id="77c63-103">Manage policy packages in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="77c63-104">本文讨论的功能之一（ [自定义策略包](#custom-policy-packages)）目前以个人预览版提供。</span><span class="sxs-lookup"><span data-stu-id="77c63-104">One of the features discussed in this article, [custom policy packages](#custom-policy-packages), is currently in private preview.</span></span>

<span data-ttu-id="77c63-105">Microsoft Teams 中的策略包是预定义的策略和策略设置的集合，可将其分配给组织中具有类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="77c63-105">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="77c63-106">我们构建了策略包，以简化、简化和帮助在管理整个组织中用户组的策略时提供一致性。</span><span class="sxs-lookup"><span data-stu-id="77c63-106">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="77c63-107">可以使用 Teams[中包含的策略包](#policy-packages-included-in-teams)，也可以创建自己的[](#custom-policy-packages)自定义策略包 (预览版) 。</span><span class="sxs-lookup"><span data-stu-id="77c63-107">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages) (in private preview).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="管理中心中"策略包"页的屏幕截图":::

<span data-ttu-id="77c63-109">可以自定义策略包中策略的设置以满足用户的需求。</span><span class="sxs-lookup"><span data-stu-id="77c63-109">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="77c63-110">更改包中策略的设置时，分配到该包的所有用户将获取更新的设置。</span><span class="sxs-lookup"><span data-stu-id="77c63-110">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="77c63-111">可以使用 Microsoft Teams 管理中心或 PowerShell 管理策略包。</span><span class="sxs-lookup"><span data-stu-id="77c63-111">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="77c63-112">什么是策略包？</span><span class="sxs-lookup"><span data-stu-id="77c63-112">What is a policy package?</span></span>

<span data-ttu-id="77c63-113">使用策略包可以控制要允许或限制整个组织中特定人员集的 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="77c63-113">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="77c63-114">Teams 中的每个策略包都围绕用户角色设计，包括预定义的策略和策略设置，这些策略和策略设置支持该角色的典型协作和通信活动。</span><span class="sxs-lookup"><span data-stu-id="77c63-114">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="77c63-115">策略包支持以下 Teams 策略类型：</span><span class="sxs-lookup"><span data-stu-id="77c63-115">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="77c63-116">消息传递策略</span><span class="sxs-lookup"><span data-stu-id="77c63-116">Messaging policy</span></span>
- <span data-ttu-id="77c63-117">会议策略</span><span class="sxs-lookup"><span data-stu-id="77c63-117">Meeting policy</span></span>
- <span data-ttu-id="77c63-118">应用设置策略</span><span class="sxs-lookup"><span data-stu-id="77c63-118">App setup policy</span></span>
- <span data-ttu-id="77c63-119">呼叫策略</span><span class="sxs-lookup"><span data-stu-id="77c63-119">Calling policy</span></span>
- <span data-ttu-id="77c63-120">实时事件策略</span><span class="sxs-lookup"><span data-stu-id="77c63-120">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="77c63-121">Teams 中包含的策略包</span><span class="sxs-lookup"><span data-stu-id="77c63-121">Policy packages included in Teams</span></span>

<span data-ttu-id="77c63-122">Teams 当前包括以下策略包。</span><span class="sxs-lookup"><span data-stu-id="77c63-122">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="77c63-123">**包名称**</span><span class="sxs-lookup"><span data-stu-id="77c63-123">**Package name**</span></span>  |<span data-ttu-id="77c63-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="77c63-124">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="77c63-125">教育 (教育学生) </span><span class="sxs-lookup"><span data-stu-id="77c63-125">Education (Higher education student)</span></span>    |<span data-ttu-id="77c63-126">创建一组适用于大教育学生的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="77c63-126">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="77c63-127">教育 (中学生) </span><span class="sxs-lookup"><span data-stu-id="77c63-127">Education (Primary school student)</span></span>   |<span data-ttu-id="77c63-128">创建一组适用于主要学生的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="77c63-128">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="77c63-129">教育 (中学生) </span><span class="sxs-lookup"><span data-stu-id="77c63-129">Education (Secondary school student)</span></span>    |<span data-ttu-id="77c63-130">创建一组适用于学生的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="77c63-130">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="77c63-131">教育 (教师) </span><span class="sxs-lookup"><span data-stu-id="77c63-131">Education (Teacher)</span></span>    |<span data-ttu-id="77c63-132">创建一组适用于教师的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="77c63-132">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="77c63-133">使用 (远程学习工具的教师) </span><span class="sxs-lookup"><span data-stu-id="77c63-133">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="77c63-134">创建一组适用于主要教师的策略，在远程学习中最大化学生的安全和协作。</span><span class="sxs-lookup"><span data-stu-id="77c63-134">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="77c63-135">使用远程 (远程学习工具的) </span><span class="sxs-lookup"><span data-stu-id="77c63-135">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="77c63-136">创建一组适用于主要学生的策略，在远程学习中最大化学生的安全和协作。</span><span class="sxs-lookup"><span data-stu-id="77c63-136">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="77c63-137">一线管理器</span><span class="sxs-lookup"><span data-stu-id="77c63-137">Firstline manager</span></span> |<span data-ttu-id="77c63-138">创建一组策略，将这些设置应用到组织中第一线经理。</span><span class="sxs-lookup"><span data-stu-id="77c63-138">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span> |
|<span data-ttu-id="77c63-139">一线员工</span><span class="sxs-lookup"><span data-stu-id="77c63-139">Firstline worker</span></span> |<span data-ttu-id="77c63-140">创建一组策略，将这些设置应用于组织中一线员工。</span><span class="sxs-lookup"><span data-stu-id="77c63-140">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span> |
|<span data-ttu-id="77c63-141">医疗保健医生</span><span class="sxs-lookup"><span data-stu-id="77c63-141">Healthcare clinical worker</span></span>  |<span data-ttu-id="77c63-142">创建一组策略和策略设置，为注册的医生、医生、医生和社交工作者等医疗工作者提供聊天、呼叫、轮班管理和会议的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="77c63-142">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="77c63-143">医疗保健信息工作者</span><span class="sxs-lookup"><span data-stu-id="77c63-143">Healthcare information worker</span></span>  |<span data-ttu-id="77c63-144">创建一组策略和策略设置，为信息工作者（例如 IT 人员、信息工作者、财务人员和合规官）提供聊天、呼叫和会议的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="77c63-144">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="77c63-145">医疗保健患者室</span><span class="sxs-lookup"><span data-stu-id="77c63-145">Healthcare patient room</span></span>  |<span data-ttu-id="77c63-146">创建一组适用于医疗保健组织中患者室的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="77c63-146">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="77c63-147">小型企业用户 (Business Voice) </span><span class="sxs-lookup"><span data-stu-id="77c63-147">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="77c63-148">创建一个应用设置策略，其中包括用于业务语音体验的应用。</span><span class="sxs-lookup"><span data-stu-id="77c63-148">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="77c63-149">没有 Business Voice (的中小型企业) </span><span class="sxs-lookup"><span data-stu-id="77c63-149">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="77c63-150">为具有非业务语音体验的小型企业 Teams 用户创建 (设置) 。</span><span class="sxs-lookup"><span data-stu-id="77c63-150">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="77c63-151">公共安全主管</span><span class="sxs-lookup"><span data-stu-id="77c63-151">Public safety officer</span></span>   |<span data-ttu-id="77c63-152">创建一组适用于组织中公共安全人员的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="77c63-152">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="77c63-153">我们将在将来的 Teams 版本中添加更多策略包，因此请返回查看最新信息。</span><span class="sxs-lookup"><span data-stu-id="77c63-153">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="77c63-154">每个单独的策略都获得策略包的名称，因此可以轻松识别链接到策略包的策略。</span><span class="sxs-lookup"><span data-stu-id="77c63-154">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="77c63-155">例如，将教育 (教师) 策略包分配给学校教师时，会为包中的每个策略创建名为 Education_Teacher 的策略。</span><span class="sxs-lookup"><span data-stu-id="77c63-155">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![教育教师教师 (策略) 的屏幕截图](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="77c63-157">自定义策略包</span><span class="sxs-lookup"><span data-stu-id="77c63-157">Custom policy packages</span></span>

<span data-ttu-id="77c63-158">**此功能在私有预览版中**</span><span class="sxs-lookup"><span data-stu-id="77c63-158">**This feature is in private preview**</span></span>

<span data-ttu-id="77c63-159">自定义策略包允许为组织中具有类似角色的用户捆绑自己的一组策略。</span><span class="sxs-lookup"><span data-stu-id="77c63-159">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="77c63-160">通过添加所需的策略类型和策略创建自己的策略包。</span><span class="sxs-lookup"><span data-stu-id="77c63-160">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="77c63-161">创建新的自定义策略包：</span><span class="sxs-lookup"><span data-stu-id="77c63-161">To create a new custom policy package:</span></span>

1. <span data-ttu-id="77c63-162">在 Microsoft Teams 管理中心的左侧导航栏中，选择"**策略包**"，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="77c63-162">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>
    :::image type="content" source="media/policy-packages-add.png" alt-text="管理中心"策略包"页上的"添加"按钮的屏幕截图":::
2. <span data-ttu-id="77c63-164">输入包的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="77c63-164">Enter a name and description for your package.</span></span>
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="添加新的自定义策略包的屏幕截图":::
3. <span data-ttu-id="77c63-166">选择要包括在包中的策略类型和策略名称。</span><span class="sxs-lookup"><span data-stu-id="77c63-166">Select the policy types and policy names to include in the package.</span></span>
4. <span data-ttu-id="77c63-167">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="77c63-167">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="77c63-168">如何使用策略包</span><span class="sxs-lookup"><span data-stu-id="77c63-168">How to use policy packages</span></span>

<span data-ttu-id="77c63-169">下面概述了如何在组织中使用策略包。</span><span class="sxs-lookup"><span data-stu-id="77c63-169">The following outlines how to use policy packages in your organization.</span></span>

![如何使用策略包的概述](media/manage-policy-packages-overview.png)

- <span data-ttu-id="77c63-171">**[视图](#view-the-settings-of-a-policy-in-a-policy-package)**：查看策略包中的策略。</span><span class="sxs-lookup"><span data-stu-id="77c63-171">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="77c63-172">然后，在分配包之前，查看包中每个策略的设置。</span><span class="sxs-lookup"><span data-stu-id="77c63-172">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="77c63-173">请确保了解每个设置。</span><span class="sxs-lookup"><span data-stu-id="77c63-173">Make sure that you understand each setting.</span></span> <span data-ttu-id="77c63-174">根据组织的需求决定预定义值是否适合组织，或者是否需要将它们更改为更严格或更宽松。</span><span class="sxs-lookup"><span data-stu-id="77c63-174">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="77c63-175">如果删除策略，仍可以查看设置，但无法更改任何设置。</span><span class="sxs-lookup"><span data-stu-id="77c63-175">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="77c63-176">分配策略包时，会使用预定义设置重新创建已删除的策略。</span><span class="sxs-lookup"><span data-stu-id="77c63-176">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="77c63-177">**[自定义](#customize-policies-in-a-policy-package)**：自定义策略包中策略的设置以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="77c63-177">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="77c63-178">**[分配](#assign-a-policy-package)**：将策略包分配给用户。</span><span class="sxs-lookup"><span data-stu-id="77c63-178">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="77c63-179">分配包后，还可以更改策略包中的策略设置。</span><span class="sxs-lookup"><span data-stu-id="77c63-179">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="77c63-180">对策略设置所做的任何更改都将自动应用到已分配了该包的用户。</span><span class="sxs-lookup"><span data-stu-id="77c63-180">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="77c63-181">下面是在 Microsoft Teams 管理中心中查看、分配和自定义策略包的步骤。</span><span class="sxs-lookup"><span data-stu-id="77c63-181">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="77c63-182">查看策略包中的策略设置</span><span class="sxs-lookup"><span data-stu-id="77c63-182">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="77c63-183">在 Microsoft Teams 管理中心的左侧导航栏中，选择"策略包"，然后单击程序包名称左侧选择策略包。</span><span class="sxs-lookup"><span data-stu-id="77c63-183">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="77c63-184">单击要查看的策略。</span><span class="sxs-lookup"><span data-stu-id="77c63-184">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="77c63-185">自定义策略包中的策略</span><span class="sxs-lookup"><span data-stu-id="77c63-185">Customize policies in a policy package</span></span>

<span data-ttu-id="77c63-186">可以通过"策略包"页或直接进入Microsoft Teams 管理中心的策略页来编辑策略的设置。</span><span class="sxs-lookup"><span data-stu-id="77c63-186">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="77c63-187">在 Microsoft Teams 管理中心的左侧导航栏中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="77c63-187">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="77c63-188">单击 **"** 策略包"，然后单击包名称左侧选择策略包。</span><span class="sxs-lookup"><span data-stu-id="77c63-188">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="77c63-189">单击策略类型。</span><span class="sxs-lookup"><span data-stu-id="77c63-189">Click the policy type.</span></span>  <span data-ttu-id="77c63-190">例如，单击 **"消息传送策略"。**</span><span class="sxs-lookup"><span data-stu-id="77c63-190">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="77c63-191">选择要编辑的策略。</span><span class="sxs-lookup"><span data-stu-id="77c63-191">Select the policy you want to edit.</span></span> <span data-ttu-id="77c63-192">链接到策略包的策略与策略包同名。</span><span class="sxs-lookup"><span data-stu-id="77c63-192">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="77c63-193">进行您需要的更改，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="77c63-193">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="77c63-194">分配策略包</span><span class="sxs-lookup"><span data-stu-id="77c63-194">Assign a policy package</span></span> 

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="77c63-195">将策略包分配给一个用户</span><span class="sxs-lookup"><span data-stu-id="77c63-195">Assign a policy package to one user</span></span>

1. <span data-ttu-id="77c63-196">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。</span><span class="sxs-lookup"><span data-stu-id="77c63-196">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="77c63-197">在用户的页面上，**单击"策略**"，然后在"策略包"**旁边单击"** 编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="77c63-197">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="77c63-198">在"**分配策略包"** 窗格中，选择要分配的包，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="77c63-198">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="77c63-199">将策略包分配给多个用户</span><span class="sxs-lookup"><span data-stu-id="77c63-199">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="77c63-200">在 Microsoft Teams 管理中心的左侧导航栏中，转到"策略包"，然后单击程序包名称左侧，选择要分配的策略包。</span><span class="sxs-lookup"><span data-stu-id="77c63-200">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="77c63-201">单击 **"管理用户"。**</span><span class="sxs-lookup"><span data-stu-id="77c63-201">Click **Manage users**.</span></span>
3. <span data-ttu-id="77c63-202">在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="77c63-202">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="77c63-203">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="77c63-203">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="77c63-204">添加完用户后，单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="77c63-204">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="77c63-205">将策略包分配给组。</span><span class="sxs-lookup"><span data-stu-id="77c63-205">Assign a policy package to a group</span></span>

<span data-ttu-id="77c63-206">**此功能在私有预览版中**</span><span class="sxs-lookup"><span data-stu-id="77c63-206">**This feature is in private preview**</span></span>

<span data-ttu-id="77c63-207">通过将策略包分配到组，可将多个策略分配给一组用户，例如安全组或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="77c63-207">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="77c63-208">根据优先级规则，将策略分配传播到组中的成员。</span><span class="sxs-lookup"><span data-stu-id="77c63-208">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="77c63-209">将成员添加到组或从组中删除成员时，将相应更新其继承的策略分配。</span><span class="sxs-lookup"><span data-stu-id="77c63-209">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="77c63-210">建议将此方法用于最多 50,000 个用户的组，但也可使用更大的组。</span><span class="sxs-lookup"><span data-stu-id="77c63-210">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="77c63-211">若要了解详细信息，请参阅[将策略包分配到组](assign-policies.md#assign-a-policy-package-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="77c63-211">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="77c63-212">向大型组（批处理）分配策略包</span><span class="sxs-lookup"><span data-stu-id="77c63-212">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="77c63-213">使用批处理策略包分配，每次向大型用户组分配策略包。</span><span class="sxs-lookup"><span data-stu-id="77c63-213">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="77c63-214">使用 [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet 提交要分配的一批用户和策略包。</span><span class="sxs-lookup"><span data-stu-id="77c63-214">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="77c63-215">作业将作为后台操作处理，并为每个批处理生成操作 ID。</span><span class="sxs-lookup"><span data-stu-id="77c63-215">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="77c63-216">批处理最多可包含 5,000 个用户。</span><span class="sxs-lookup"><span data-stu-id="77c63-216">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="77c63-217">可通过对象 Id、UPN、SIP 地址或电子邮件地址指定用户。</span><span class="sxs-lookup"><span data-stu-id="77c63-217">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="77c63-218">若要了解详细信息，请参阅[将策略包分配给批次用户](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="77c63-218">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="77c63-219">疑难解答</span><span class="sxs-lookup"><span data-stu-id="77c63-219">Troubleshooting</span></span>

<span data-ttu-id="77c63-220">**分配策略包时收到错误**</span><span class="sxs-lookup"><span data-stu-id="77c63-220">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="77c63-221">如果未成功创建或应用包中的一个或多个策略，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="77c63-221">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="77c63-222">将策略包重新分配给用户。</span><span class="sxs-lookup"><span data-stu-id="77c63-222">Reassign the policy package to your users.</span></span> <span data-ttu-id="77c63-223">重试操作通常可修复此问题。</span><span class="sxs-lookup"><span data-stu-id="77c63-223">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="77c63-224">相关主题</span><span class="sxs-lookup"><span data-stu-id="77c63-224">Related topics</span></span>

[<span data-ttu-id="77c63-225">在 Teams 中向用户分配策略</span><span class="sxs-lookup"><span data-stu-id="77c63-225">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="77c63-226">适用于 EDU 管理员的 Teams 策略包</span><span class="sxs-lookup"><span data-stu-id="77c63-226">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)

[<span data-ttu-id="77c63-227">用于医疗保健的 Teams 策略包</span><span class="sxs-lookup"><span data-stu-id="77c63-227">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)

[<span data-ttu-id="77c63-228">适用于政府的 Teams 策略包</span><span class="sxs-lookup"><span data-stu-id="77c63-228">Teams policy packages for government</span></span>](policy-packages-gov.md)
