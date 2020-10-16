---
title: 管理 Microsoft 团队中的策略程序包
author: lanachin
ms.author: v-lanac
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
description: 了解如何在 Microsoft 团队中使用和管理策略程序包，以便在管理用户组策略时简化、简化和帮助提供一致性。
ms.openlocfilehash: 140b67ae8df01d29b8e6d37c6fe1a36afebbd949
ms.sourcegitcommit: 8a345ca9a8ddc6a84f9e270ab55f1b28f6ba49c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48488386"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="1d0c6-103">管理 Microsoft 团队中的策略程序包</span><span class="sxs-lookup"><span data-stu-id="1d0c6-103">Manage policy packages in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="1d0c6-104">本文中所述的功能之一是 " [自定义策略" 程序包](#custom-policy-packages)，当前位于 "私人预览" 中。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-104">One of the features discussed in this article, [custom policy packages](#custom-policy-packages), is currently in private preview.</span></span>

<span data-ttu-id="1d0c6-105">Microsoft 团队中的策略包是预定义策略和策略设置的集合，可分配给在组织中具有类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-105">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="1d0c6-106">我们构建了策略程序包，以便在管理组织内的用户组策略时提供简化、简化和帮助。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-106">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="1d0c6-107">你可以使用 [团队中包含的策略程序包](#policy-packages-included-in-teams) 或 [创建你自己的自定义策略包](#custom-policy-packages) (在私人预览版) 中。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-107">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages) (in private preview).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="管理中心中 "策略程序包" 页面的屏幕截图":::

<span data-ttu-id="1d0c6-109">你可以自定义策略包中的策略设置以满足你的用户需求。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-109">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="1d0c6-110">更改程序包中的策略设置时，分配到该程序包的所有用户都将获得更新的设置。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-110">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="1d0c6-111">你可以使用 Microsoft 团队管理中心或 PowerShell 管理策略包。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-111">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="1d0c6-112">什么是策略包？</span><span class="sxs-lookup"><span data-stu-id="1d0c6-112">What is a policy package?</span></span>

<span data-ttu-id="1d0c6-113">通过策略程序包，你可以控制你希望允许或限制你的组织中的特定人员组的团队功能。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-113">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="1d0c6-114">团队中的每个策略包都围绕用户角色进行设计，其中包括预定义的策略和策略设置，这些策略和策略设置支持为该角色典型的协作和通信活动。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-114">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="1d0c6-115">策略程序包支持以下团队策略类型：</span><span class="sxs-lookup"><span data-stu-id="1d0c6-115">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="1d0c6-116">消息传递策略</span><span class="sxs-lookup"><span data-stu-id="1d0c6-116">Messaging policy</span></span>
- <span data-ttu-id="1d0c6-117">会议策略</span><span class="sxs-lookup"><span data-stu-id="1d0c6-117">Meeting policy</span></span>
- <span data-ttu-id="1d0c6-118">应用设置策略</span><span class="sxs-lookup"><span data-stu-id="1d0c6-118">App setup policy</span></span>
- <span data-ttu-id="1d0c6-119">呼叫策略</span><span class="sxs-lookup"><span data-stu-id="1d0c6-119">Calling policy</span></span>
- <span data-ttu-id="1d0c6-120">实时事件策略</span><span class="sxs-lookup"><span data-stu-id="1d0c6-120">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="1d0c6-121">团队中包含的策略包</span><span class="sxs-lookup"><span data-stu-id="1d0c6-121">Policy packages included in Teams</span></span>

<span data-ttu-id="1d0c6-122">团队当前包含以下策略程序包。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-122">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="1d0c6-123">**程序包名称**</span><span class="sxs-lookup"><span data-stu-id="1d0c6-123">**Package name**</span></span>  |<span data-ttu-id="1d0c6-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="1d0c6-124">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="1d0c6-125">教育版 (更高教育学生) </span><span class="sxs-lookup"><span data-stu-id="1d0c6-125">Education (Higher education student)</span></span>    |<span data-ttu-id="1d0c6-126">创建一组适用于更高教育学生的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-126">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="1d0c6-127">教育 (主要学校学生) </span><span class="sxs-lookup"><span data-stu-id="1d0c6-127">Education (Primary school student)</span></span>   |<span data-ttu-id="1d0c6-128">创建一组适用于主要学生的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-128">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="1d0c6-129">教育 (次要学校学生) </span><span class="sxs-lookup"><span data-stu-id="1d0c6-129">Education (Secondary school student)</span></span>    |<span data-ttu-id="1d0c6-130">创建一组适用于次要学生的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-130">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="1d0c6-131"> (教师) 教育</span><span class="sxs-lookup"><span data-stu-id="1d0c6-131">Education (Teacher)</span></span>    |<span data-ttu-id="1d0c6-132">创建一组适用于教师的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-132">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="1d0c6-133">使用 "远程学习" (主要学校教师的教育) </span><span class="sxs-lookup"><span data-stu-id="1d0c6-133">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="1d0c6-134">创建一组适用于主要教师的策略，在远程学习中最大化学生的安全和协作。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-134">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="1d0c6-135">使用远程学习) 的主要教职员工 (教育版教育</span><span class="sxs-lookup"><span data-stu-id="1d0c6-135">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="1d0c6-136">创建一组适用于主要学生的策略，在远程学习中最大化学生的安全和协作。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-136">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="1d0c6-137">一线管理器</span><span class="sxs-lookup"><span data-stu-id="1d0c6-137">Firstline manager</span></span> |<span data-ttu-id="1d0c6-138">创建一组策略，并将这些设置应用到组织中的一线管理员。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-138">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span> |
|<span data-ttu-id="1d0c6-139">一线工作人员</span><span class="sxs-lookup"><span data-stu-id="1d0c6-139">Firstline worker</span></span> |<span data-ttu-id="1d0c6-140">创建一组策略，并将这些设置应用于您的组织中的一线工作人员。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-140">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span> |
|<span data-ttu-id="1d0c6-141">医疗保健临床工作者</span><span class="sxs-lookup"><span data-stu-id="1d0c6-141">Healthcare clinical worker</span></span>  |<span data-ttu-id="1d0c6-142">创建一组策略和策略设置，为临床工作者（如注册的护士、费用护理、医生和社会工作者）提供对聊天、通话、班次管理和会议的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-142">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="1d0c6-143">医疗保健信息工作者</span><span class="sxs-lookup"><span data-stu-id="1d0c6-143">Healthcare information worker</span></span>  |<span data-ttu-id="1d0c6-144">创建一组策略和策略设置，提供信息工作者，如 IT 人员、informatics 员工、财务人员和合规性监察官、对聊天、通话和会议的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-144">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="1d0c6-145">医疗保健患者聊天室</span><span class="sxs-lookup"><span data-stu-id="1d0c6-145">Healthcare patient room</span></span>  |<span data-ttu-id="1d0c6-146">创建一组策略和策略设置，这些策略设置适用于您的医疗保健组织中的患者聊天室。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-146">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="1d0c6-147">中小型企业用户 (商务语音) </span><span class="sxs-lookup"><span data-stu-id="1d0c6-147">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="1d0c6-148">创建包含商业语音体验应用的应用安装策略。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-148">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="1d0c6-149">中小型企业用户 (，无需商用语音) </span><span class="sxs-lookup"><span data-stu-id="1d0c6-149">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="1d0c6-150">创建与中小型企业团队用户 (非企业语音体验) 相关的应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-150">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="1d0c6-151">公共安全专员</span><span class="sxs-lookup"><span data-stu-id="1d0c6-151">Public safety officer</span></span>   |<span data-ttu-id="1d0c6-152">创建一组策略和策略设置，这些策略设置适用于您的组织中的公共安全专员。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-152">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="1d0c6-153">我们将在未来版本的团队中添加更多策略程序包，请查看最新信息。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-153">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="1d0c6-154">每个单独策略都被授予策略程序包的名称，以便你可以轻松地识别链接到策略包的策略。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-154">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="1d0c6-155">例如，当你向学校中的教师分配教育版 (教师) 策略包时，将为程序包中的每个策略创建一个名为 Education_Teacher 的策略。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-155">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![教育版 (教师) 策略包的屏幕截图](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="1d0c6-157">自定义策略程序包</span><span class="sxs-lookup"><span data-stu-id="1d0c6-157">Custom policy packages</span></span>

<span data-ttu-id="1d0c6-158">**此功能在私人预览版中**</span><span class="sxs-lookup"><span data-stu-id="1d0c6-158">**This feature is in private preview**</span></span>

<span data-ttu-id="1d0c6-159">通过自定义策略程序包，你可以为你的组织中具有类似角色的用户捆绑你自己的策略集。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-159">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="1d0c6-160">通过添加所需的策略类型和策略来创建自己的策略程序包。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-160">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="1d0c6-161">要创建新的自定义策略程序包，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1d0c6-161">To create a new custom policy package:</span></span>

1. <span data-ttu-id="1d0c6-162">在 Microsoft 团队管理中心的左侧导航中，选择 " **策略包**"，然后单击 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-162">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>
    :::image type="content" source="media/policy-packages-add.png" alt-text="管理中心中 "策略程序包" 页面上的 "添加" 按钮的屏幕截图":::
2. <span data-ttu-id="1d0c6-164">输入程序包的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-164">Enter a name and description for your package.</span></span>
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="添加新的自定义策略程序包的屏幕截图":::
3. <span data-ttu-id="1d0c6-166">选择要包括在程序包中的策略类型和策略名称。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-166">Select the policy types and policy names to include in the package.</span></span>
4. <span data-ttu-id="1d0c6-167">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-167">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="1d0c6-168">如何使用策略程序包</span><span class="sxs-lookup"><span data-stu-id="1d0c6-168">How to use policy packages</span></span>

<span data-ttu-id="1d0c6-169">以下概述了如何使用组织中的策略包。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-169">The following outlines how to use policy packages in your organization.</span></span>

![如何使用策略程序包概述](media/manage-policy-packages-overview.png)

- <span data-ttu-id="1d0c6-171">**[查看](#view-the-settings-of-a-policy-in-a-policy-package)**：查看策略包中的策略。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-171">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="1d0c6-172">然后，在分配程序包之前查看程序包中每个策略的设置。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-172">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="1d0c6-173">请确保你了解每个设置。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-173">Make sure that you understand each setting.</span></span> <span data-ttu-id="1d0c6-174">确定预定义的值是否适合你的组织，或者你是否需要根据组织的需要将其更改为更具限制性或 lenient 的值。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-174">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="1d0c6-175">如果删除策略，您仍然可以查看设置，但不能更改任何设置。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-175">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="1d0c6-176">分配策略包时，将使用预定义的设置重新创建已删除的策略。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-176">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="1d0c6-177">**[自定义](#customize-policies-in-a-policy-package)**：自定义策略包中的策略设置以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-177">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="1d0c6-178">**[分配](#assign-a-policy-package)**：将策略包分配给用户。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-178">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="1d0c6-179">你还可以在分配程序包后更改策略包中的策略设置。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-179">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="1d0c6-180">对策略设置所做的任何更改都将自动应用到分配了该程序包的用户。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-180">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="1d0c6-181">下面是有关如何在 Microsoft 团队管理中心中查看、分配和自定义策略包的步骤。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-181">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="1d0c6-182">查看策略包中的策略设置</span><span class="sxs-lookup"><span data-stu-id="1d0c6-182">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="1d0c6-183">在 "Microsoft 团队管理中心" 的左侧导航中，选择 " **策略程序包**"，然后单击程序包名称左侧的 "策略包" 进行选择。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-183">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="1d0c6-184">单击要查看的策略。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-184">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="1d0c6-185">自定义策略包中的策略</span><span class="sxs-lookup"><span data-stu-id="1d0c6-185">Customize policies in a policy package</span></span>

<span data-ttu-id="1d0c6-186">你可以通过 " **策略包** " 页面编辑策略的设置，或直接转到 Microsoft 团队管理中心中的 "策略" 页面。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-186">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="1d0c6-187">在 Microsoft 团队管理中心的左侧导航中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1d0c6-187">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="1d0c6-188">单击 " **策略程序包**"，然后单击 "程序包名称" 左侧的 "策略程序包" 进行选择。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-188">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="1d0c6-189">单击 "策略类型"。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-189">Click the policy type.</span></span>  <span data-ttu-id="1d0c6-190">例如，单击 " **邮件策略**"。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-190">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="1d0c6-191">选择要编辑的策略。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-191">Select the policy you want to edit.</span></span> <span data-ttu-id="1d0c6-192">链接到策略包的策略与策略包的名称相同。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-192">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="1d0c6-193">进行所需的更改，然后单击 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-193">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="1d0c6-194">分配策略包</span><span class="sxs-lookup"><span data-stu-id="1d0c6-194">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="1d0c6-195">为一个用户分配策略包</span><span class="sxs-lookup"><span data-stu-id="1d0c6-195">Assign a policy package to one user</span></span>

1. <span data-ttu-id="1d0c6-196">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1d0c6-196">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="1d0c6-197">在用户的页面上，单击 " **策略**"，然后单击 " **策略程序包**" 旁边的 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-197">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="1d0c6-198">在 " **分配策略包** " 窗格中，选择要分配的程序包，然后单击 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-198">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="1d0c6-199">向多个用户分配策略包</span><span class="sxs-lookup"><span data-stu-id="1d0c6-199">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="1d0c6-200">在 Microsoft 团队管理中心的左侧导航中，转到 " **策略程序包**"，然后通过单击程序包名称左侧的 "选择要分配的策略包"。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-200">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="1d0c6-201">单击 " **管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-201">Click **Manage users**.</span></span>
3. <span data-ttu-id="1d0c6-202">在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1d0c6-202">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="1d0c6-203">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-203">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="1d0c6-204">添加完用户后，单击 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-204">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="1d0c6-205">将策略包分配给大型集 (批处理) 用户</span><span class="sxs-lookup"><span data-stu-id="1d0c6-205">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="1d0c6-206">使用批处理策略程序包分配来一次为大型用户分配一个策略包。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-206">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="1d0c6-207">使用 [CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet 提交要分配的一批用户和策略包。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-207">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="1d0c6-208">作业作为后台操作处理，并为每个批处理生成操作 ID。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-208">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="1d0c6-209">批处理最多可包含5000个用户。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-209">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="1d0c6-210">你可以按对象 Id、UPN、SIP 地址或电子邮件地址指定用户。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-210">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="1d0c6-211">若要了解详细信息，请参阅向 [一批用户分配策略包](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-211">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="1d0c6-212">故障排除</span><span class="sxs-lookup"><span data-stu-id="1d0c6-212">Troubleshooting</span></span>

<span data-ttu-id="1d0c6-213">**分配策略包时收到错误**</span><span class="sxs-lookup"><span data-stu-id="1d0c6-213">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="1d0c6-214">如果程序包中的一个或多个策略未成功创建或应用，可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-214">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="1d0c6-215">将策略程序包重新分配给你的用户。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-215">Reassign the policy package to your users.</span></span> <span data-ttu-id="1d0c6-216">重试操作通常会修复此问题。</span><span class="sxs-lookup"><span data-stu-id="1d0c6-216">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1d0c6-217">相关主题</span><span class="sxs-lookup"><span data-stu-id="1d0c6-217">Related topics</span></span>

[<span data-ttu-id="1d0c6-218">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="1d0c6-218">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="1d0c6-219">教育机构管理员的团队策略包</span><span class="sxs-lookup"><span data-stu-id="1d0c6-219">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)

[<span data-ttu-id="1d0c6-220">医疗保健的团队策略程序包</span><span class="sxs-lookup"><span data-stu-id="1d0c6-220">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)

[<span data-ttu-id="1d0c6-221">政府团队政策包</span><span class="sxs-lookup"><span data-stu-id="1d0c6-221">Teams policy packages for government</span></span>](policy-packages-gov.md)
