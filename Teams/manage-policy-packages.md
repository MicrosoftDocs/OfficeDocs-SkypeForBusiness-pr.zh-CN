---
title: 管理策略包Microsoft Teams
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
description: 了解如何在管理用户组的策略时Microsoft Teams管理策略包，以便简化、简化和帮助提供一致性。
ms.openlocfilehash: 63900f301a8b3a48a8c17c6278808cd52e2445da
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2021
ms.locfileid: "52810183"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="b6b62-103">管理策略包Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b6b62-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="b6b62-104">Microsoft Teams 中的策略包是一组预定义的策略和策略设置，你可以将其分配给组织中具有类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="b6b62-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="b6b62-105">我们构建了策略包，用于简化、简化和帮助在管理组织中用户组的策略时提供一致性。</span><span class="sxs-lookup"><span data-stu-id="b6b62-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="b6b62-106">可以使用应用程序[中包含的策略包](#policy-packages-included-in-teams)Teams[或创建自己的自定义策略包](#custom-policy-packages)。</span><span class="sxs-lookup"><span data-stu-id="b6b62-106">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="管理中心中"策略包"页的屏幕截图":::

<span data-ttu-id="b6b62-108">可以自定义策略包中策略的设置以满足用户的需求。</span><span class="sxs-lookup"><span data-stu-id="b6b62-108">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="b6b62-109">更改包中的策略设置时，分配到该包的所有用户将获取更新的设置。</span><span class="sxs-lookup"><span data-stu-id="b6b62-109">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="b6b62-110">可以使用管理中心或 PowerShell Microsoft Teams策略包。</span><span class="sxs-lookup"><span data-stu-id="b6b62-110">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="b6b62-111">每个用户都需要高级通信加载项才能接收自定义策略包分配。</span><span class="sxs-lookup"><span data-stu-id="b6b62-111">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="b6b62-112">有关详细信息，请参阅适用于 Microsoft Teams[的高级通信Microsoft Teams。](/microsoftteams/teams-add-on-licensing/advanced-communications)</span><span class="sxs-lookup"><span data-stu-id="b6b62-112">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="b6b62-113">什么是策略包？</span><span class="sxs-lookup"><span data-stu-id="b6b62-113">What is a policy package?</span></span>

<span data-ttu-id="b6b62-114">策略包允许你Teams组织中特定人员集允许或限制的特定功能。</span><span class="sxs-lookup"><span data-stu-id="b6b62-114">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="b6b62-115">每个策略包Teams用户角色设计，包括预定义的策略和策略设置，这些策略和策略设置支持该角色的典型协作和通信活动。</span><span class="sxs-lookup"><span data-stu-id="b6b62-115">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="b6b62-116">策略包支持以下Teams策略类型：</span><span class="sxs-lookup"><span data-stu-id="b6b62-116">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="b6b62-117">消息传递策略</span><span class="sxs-lookup"><span data-stu-id="b6b62-117">Messaging policy</span></span>
- <span data-ttu-id="b6b62-118">会议策略</span><span class="sxs-lookup"><span data-stu-id="b6b62-118">Meeting policy</span></span>
- <span data-ttu-id="b6b62-119">应用设置策略</span><span class="sxs-lookup"><span data-stu-id="b6b62-119">App setup policy</span></span>
- <span data-ttu-id="b6b62-120">呼叫策略</span><span class="sxs-lookup"><span data-stu-id="b6b62-120">Calling policy</span></span>
- <span data-ttu-id="b6b62-121">实时事件策略</span><span class="sxs-lookup"><span data-stu-id="b6b62-121">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="b6b62-122">包含在策略包Teams</span><span class="sxs-lookup"><span data-stu-id="b6b62-122">Policy packages included in Teams</span></span>

<span data-ttu-id="b6b62-123">Teams包括以下策略包。</span><span class="sxs-lookup"><span data-stu-id="b6b62-123">Teams currently includes the following policy packages.</span></span>

| <span data-ttu-id="b6b62-124">包名称</span><span class="sxs-lookup"><span data-stu-id="b6b62-124">Package name</span></span> | <span data-ttu-id="b6b62-125">说明</span><span class="sxs-lookup"><span data-stu-id="b6b62-125">Description</span></span> |
|---------|---------|
|<span data-ttu-id="b6b62-126">教育 (教育学生) </span><span class="sxs-lookup"><span data-stu-id="b6b62-126">Education (Higher education student)</span></span>    |<span data-ttu-id="b6b62-127">创建一组适用于教育程度学生的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="b6b62-127">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="b6b62-128">教育 (中学生) </span><span class="sxs-lookup"><span data-stu-id="b6b62-128">Education (Primary school student)</span></span>   |<span data-ttu-id="b6b62-129">创建一组适用于主要学生的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="b6b62-129">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="b6b62-130">教育 (中学生) </span><span class="sxs-lookup"><span data-stu-id="b6b62-130">Education (Secondary school student)</span></span>    |<span data-ttu-id="b6b62-131">创建一组适用于学生的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="b6b62-131">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="b6b62-132">教育 (教师) </span><span class="sxs-lookup"><span data-stu-id="b6b62-132">Education (Teacher)</span></span>    |<span data-ttu-id="b6b62-133">创建一组适用于教师的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="b6b62-133">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="b6b62-134">使用 (远程学习的教师) </span><span class="sxs-lookup"><span data-stu-id="b6b62-134">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="b6b62-135">创建一组适用于主要教师的策略，在远程学习中最大化学生的安全和协作。</span><span class="sxs-lookup"><span data-stu-id="b6b62-135">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="b6b62-136">使用 (远程学习工具的"教育) </span><span class="sxs-lookup"><span data-stu-id="b6b62-136">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="b6b62-137">创建一组适用于主要学生的策略，在远程学习中最大化学生的安全和协作。</span><span class="sxs-lookup"><span data-stu-id="b6b62-137">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="b6b62-138">前端管理器</span><span class="sxs-lookup"><span data-stu-id="b6b62-138">Frontline manager</span></span> |<span data-ttu-id="b6b62-139">创建一组策略，将这些设置应用于组织的一线经理。</span><span class="sxs-lookup"><span data-stu-id="b6b62-139">Creates a set of policies and applies those settings to Frontline managers in your organization.</span></span> |
|<span data-ttu-id="b6b62-140">一线辅助角色</span><span class="sxs-lookup"><span data-stu-id="b6b62-140">Frontline worker</span></span> |<span data-ttu-id="b6b62-141">创建一组策略，将这些设置应用到组织的一线员工。</span><span class="sxs-lookup"><span data-stu-id="b6b62-141">Creates a set of policies and applies those settings to Frontline workers in your organization.</span></span> |
|<span data-ttu-id="b6b62-142">医疗保健临床工作者</span><span class="sxs-lookup"><span data-stu-id="b6b62-142">Healthcare clinical worker</span></span>  |<span data-ttu-id="b6b62-143">创建一组策略和策略设置，以使临床工作者（例如注册护士、护士长、医师和社会工作者）可以完全访问聊天、通话、轮班管理和会议。</span><span class="sxs-lookup"><span data-stu-id="b6b62-143">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="b6b62-144">医疗保健信息工作者</span><span class="sxs-lookup"><span data-stu-id="b6b62-144">Healthcare information worker</span></span>  |<span data-ttu-id="b6b62-145">创建一组策略和策略设置，以使信息工作者（例如 IT 人员、信息学人员、财务人员和合规专员）可以完全访问聊天、通话和会议。</span><span class="sxs-lookup"><span data-stu-id="b6b62-145">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="b6b62-146">医疗保健病房</span><span class="sxs-lookup"><span data-stu-id="b6b62-146">Healthcare patient room</span></span>  |<span data-ttu-id="b6b62-147">创建一组适用于医疗保健组织中病房的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="b6b62-147">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="b6b62-148">小型企业和中型企业用户 (Business Voice) </span><span class="sxs-lookup"><span data-stu-id="b6b62-148">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="b6b62-149">创建一个应用设置策略，其中包含用于业务语音体验的应用。</span><span class="sxs-lookup"><span data-stu-id="b6b62-149">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="b6b62-150">没有 Business Voice (的中小型企业) </span><span class="sxs-lookup"><span data-stu-id="b6b62-150">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="b6b62-151">创建与中小型企业用户相关的应用设置策略Teams用户 (非业务语音体验) 。</span><span class="sxs-lookup"><span data-stu-id="b6b62-151">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="b6b62-152">公共安全人员</span><span class="sxs-lookup"><span data-stu-id="b6b62-152">Public safety officer</span></span>   |<span data-ttu-id="b6b62-153">创建一组适用于组织中公共安全人员的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="b6b62-153">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="b6b62-154">我们将在将来的 Teams 版本中添加更多策略包，因此请返回查看最新信息。</span><span class="sxs-lookup"><span data-stu-id="b6b62-154">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="b6b62-155">将为每个单独的策略提供策略包的名称，以便你可以轻松识别链接到该策略包的策略。</span><span class="sxs-lookup"><span data-stu-id="b6b62-155">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="b6b62-156">例如，将教育 (教师) 策略包分配给学校中的教师时，会为包中的每个策略创建名为 Education_Teacher 的策略。</span><span class="sxs-lookup"><span data-stu-id="b6b62-156">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![教育教师教师 (策略) 屏幕截图](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="b6b62-158">自定义策略包</span><span class="sxs-lookup"><span data-stu-id="b6b62-158">Custom policy packages</span></span>

<span data-ttu-id="b6b62-159">**自定义策略包尚不可用于政府社区云 (GCC)**</span><span class="sxs-lookup"><span data-stu-id="b6b62-159">**Custom policy packages is not yet available for the Government Community Cloud (GCC)**</span></span>

<span data-ttu-id="b6b62-160">自定义策略包允许为组织中具有类似角色的用户捆绑自己的策略集。</span><span class="sxs-lookup"><span data-stu-id="b6b62-160">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="b6b62-161">通过添加所需的策略类型和策略创建自己的策略包。</span><span class="sxs-lookup"><span data-stu-id="b6b62-161">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="b6b62-162">创建新的自定义策略包：</span><span class="sxs-lookup"><span data-stu-id="b6b62-162">To create a new custom policy package:</span></span>

1. <span data-ttu-id="b6b62-163">在管理中心左侧导航Microsoft Teams，选择"**策略包**"，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="b6b62-163">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>

    :::image type="content" source="media/policy-packages-add.png" alt-text="管理中心中"策略包"页面上的"添加"按钮的屏幕截图":::

2. <span data-ttu-id="b6b62-165">输入包的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="b6b62-165">Enter a name and description for your package.</span></span>

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="添加新的自定义策略包的屏幕截图":::

3. <span data-ttu-id="b6b62-167">选择要包括在包中的策略类型和策略名称。</span><span class="sxs-lookup"><span data-stu-id="b6b62-167">Select the policy types and policy names to include in the package.</span></span>

4. <span data-ttu-id="b6b62-168">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b6b62-168">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="b6b62-169">如何使用策略包</span><span class="sxs-lookup"><span data-stu-id="b6b62-169">How to use policy packages</span></span>

<span data-ttu-id="b6b62-170">下面概述了如何在组织中使用策略包。</span><span class="sxs-lookup"><span data-stu-id="b6b62-170">The following outlines how to use policy packages in your organization.</span></span>

![如何使用策略包的概述](media/manage-policy-packages-overview.png)

- <span data-ttu-id="b6b62-172">**[视图](#view-the-settings-of-a-policy-in-a-policy-package)**：查看策略包中的策略。</span><span class="sxs-lookup"><span data-stu-id="b6b62-172">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="b6b62-173">然后，在分配包之前，查看包中每个策略的设置。</span><span class="sxs-lookup"><span data-stu-id="b6b62-173">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="b6b62-174">请确保了解每个设置。</span><span class="sxs-lookup"><span data-stu-id="b6b62-174">Make sure that you understand each setting.</span></span> <span data-ttu-id="b6b62-175">根据组织的需求，确定预定义值是否适合组织，或者是否需要更改这些值，以更严格或宽松。</span><span class="sxs-lookup"><span data-stu-id="b6b62-175">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="b6b62-176">如果策略已删除，仍可查看设置，但无法更改任何设置。</span><span class="sxs-lookup"><span data-stu-id="b6b62-176">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="b6b62-177">分配策略包时，会使用预定义设置重新创建已删除的策略。</span><span class="sxs-lookup"><span data-stu-id="b6b62-177">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="b6b62-178">**[自定义](#customize-policies-in-a-policy-package)**：自定义策略包中的策略设置，以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="b6b62-178">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="b6b62-179">**[分配](#assign-a-policy-package)**：将策略包分配给用户。</span><span class="sxs-lookup"><span data-stu-id="b6b62-179">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="b6b62-180">分配包后，还可以更改策略包中的策略设置。</span><span class="sxs-lookup"><span data-stu-id="b6b62-180">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="b6b62-181">对策略设置所做的任何更改都将自动应用到已分配了该包的用户。</span><span class="sxs-lookup"><span data-stu-id="b6b62-181">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="b6b62-182">下面是在管理中心中查看、分配和自定义策略Microsoft Teams的步骤。</span><span class="sxs-lookup"><span data-stu-id="b6b62-182">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="b6b62-183">查看策略包中的策略设置</span><span class="sxs-lookup"><span data-stu-id="b6b62-183">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="b6b62-184">在管理中心的左侧导航Microsoft Teams，选择"策略包 **"，然后单击** 程序包名称左侧选择策略包。</span><span class="sxs-lookup"><span data-stu-id="b6b62-184">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>

2. <span data-ttu-id="b6b62-185">单击要查看的策略。</span><span class="sxs-lookup"><span data-stu-id="b6b62-185">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="b6b62-186">自定义策略包中的策略</span><span class="sxs-lookup"><span data-stu-id="b6b62-186">Customize policies in a policy package</span></span>

<span data-ttu-id="b6b62-187">可以通过"策略包"页或直接进入管理中心中的策略页来编辑Microsoft Teams设置。</span><span class="sxs-lookup"><span data-stu-id="b6b62-187">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="b6b62-188">在管理中心Microsoft Teams导航中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b6b62-188">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="b6b62-189">单击 **"策略** 包"，然后单击包名称左侧选择策略包。</span><span class="sxs-lookup"><span data-stu-id="b6b62-189">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="b6b62-190">单击策略类型。</span><span class="sxs-lookup"><span data-stu-id="b6b62-190">Click the policy type.</span></span>  <span data-ttu-id="b6b62-191">例如，单击"**消息传送策略"。**</span><span class="sxs-lookup"><span data-stu-id="b6b62-191">For example, click **Messaging policies**.</span></span>

2. <span data-ttu-id="b6b62-192">选择要编辑的策略。</span><span class="sxs-lookup"><span data-stu-id="b6b62-192">Select the policy you want to edit.</span></span> <span data-ttu-id="b6b62-193">链接到策略包的策略与策略包同名。</span><span class="sxs-lookup"><span data-stu-id="b6b62-193">Policies that are linked to a policy package have the same name as the policy package.</span></span>

3. <span data-ttu-id="b6b62-194">进行您需要的更改，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="b6b62-194">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="b6b62-195">分配策略包</span><span class="sxs-lookup"><span data-stu-id="b6b62-195">Assign a policy package</span></span>

<span data-ttu-id="b6b62-196">可以将策略包分配给单个用户、组或一批用户。</span><span class="sxs-lookup"><span data-stu-id="b6b62-196">You can assign a policy package to an individual user, a group, or a batch of users.</span></span> <span data-ttu-id="b6b62-197">若要详细了解如何分配策略包，请参阅 [向用户和组分配策略包](assign-policy-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="b6b62-197">For more information on how to assign policy packages, see [Assign policy packages to users and groups](assign-policy-packages.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b6b62-198">相关主题</span><span class="sxs-lookup"><span data-stu-id="b6b62-198">Related topics</span></span>

- [<span data-ttu-id="b6b62-199">分配策略包</span><span class="sxs-lookup"><span data-stu-id="b6b62-199">Assign policy packages</span></span>](assign-policy-packages.md)
- [<span data-ttu-id="b6b62-200">Teams EDU 管理员部署策略包</span><span class="sxs-lookup"><span data-stu-id="b6b62-200">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="b6b62-201">Teams 医疗保健策略包</span><span class="sxs-lookup"><span data-stu-id="b6b62-201">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)
- [<span data-ttu-id="b6b62-202">Teams政府部署策略包</span><span class="sxs-lookup"><span data-stu-id="b6b62-202">Teams policy packages for government</span></span>](policy-packages-gov.md)
