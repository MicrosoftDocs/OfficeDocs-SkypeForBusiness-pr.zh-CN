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
ms.openlocfilehash: d9ad5c2308ead1fe5761755270f81f058bf0fa3c
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "44353025"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="b1e7e-103">管理 Microsoft 团队中的策略程序包</span><span class="sxs-lookup"><span data-stu-id="b1e7e-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="b1e7e-104">Microsoft 团队中的策略包是预定义策略和策略设置的集合，可分配给在组织中具有类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="b1e7e-105">我们构建了策略程序包，以便在管理组织内的用户组策略时提供简化、简化和帮助。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="b1e7e-106">向用户分配策略包时，将创建程序包中的策略，然后你可以自定义程序包中的策略设置以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

<span data-ttu-id="b1e7e-107">策略程序包不可用于美国政府云社区（GCC）组织。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-107">Policy packages aren't available for US Government Cloud Community (GCC) organizations.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="b1e7e-108">什么是策略包？</span><span class="sxs-lookup"><span data-stu-id="b1e7e-108">What is a policy package?</span></span>

<span data-ttu-id="b1e7e-109">通过策略程序包，你可以控制你希望允许或限制你的组织中的特定人员组的团队功能。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-109">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="b1e7e-110">团队中的每个策略包都围绕用户角色进行设计，其中包括预定义的策略和策略设置，这些策略和策略设置支持为该角色典型的协作和通信活动。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-110">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="b1e7e-111">团队当前包含以下策略程序包。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-111">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="b1e7e-112">**程序包名称**</span><span class="sxs-lookup"><span data-stu-id="b1e7e-112">**Package name**</span></span>  |<span data-ttu-id="b1e7e-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="b1e7e-113">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="b1e7e-114">教育版（更高教育学生）</span><span class="sxs-lookup"><span data-stu-id="b1e7e-114">Education (Higher education student)</span></span>    |<span data-ttu-id="b1e7e-115">创建一组适用于更高教育学生的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-115">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="b1e7e-116">教育版（主要学校学生）</span><span class="sxs-lookup"><span data-stu-id="b1e7e-116">Education (Primary school student)</span></span>   |<span data-ttu-id="b1e7e-117">创建一组适用于主要学生的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-117">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="b1e7e-118">教育版（次要学校学生）</span><span class="sxs-lookup"><span data-stu-id="b1e7e-118">Education (Secondary school student)</span></span>    |<span data-ttu-id="b1e7e-119">创建一组适用于次要学生的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-119">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="b1e7e-120">教育版（教师）</span><span class="sxs-lookup"><span data-stu-id="b1e7e-120">Education (Teacher)</span></span>    |<span data-ttu-id="b1e7e-121">创建一组适用于教师的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-121">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="b1e7e-122">教育版（使用远程学习的主要学校教师）</span><span class="sxs-lookup"><span data-stu-id="b1e7e-122">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="b1e7e-123">创建一组适用于主要教师的策略，以便在使用远程学习时最大化学生的安全和协作。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-123">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="b1e7e-124">教育版（使用远程学习的主要学校学生）</span><span class="sxs-lookup"><span data-stu-id="b1e7e-124">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="b1e7e-125">创建一组适用于主要学生的策略，以便在使用远程学习时最大化学生的安全和协作。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-125">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="b1e7e-126">医疗保健临床工作者</span><span class="sxs-lookup"><span data-stu-id="b1e7e-126">Healthcare clinical worker</span></span>  |<span data-ttu-id="b1e7e-127">创建一组策略和策略设置，为临床工作者（如注册的护士、费用护理、医生和社会工作者）提供对聊天、通话、班次管理和会议的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-127">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="b1e7e-128">医疗保健信息工作者</span><span class="sxs-lookup"><span data-stu-id="b1e7e-128">Healthcare information worker</span></span>  |<span data-ttu-id="b1e7e-129">创建一组策略和策略设置，提供信息工作者，如 IT 人员、informatics 员工、财务人员和合规性监察官、对聊天、通话和会议的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-129">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="b1e7e-130">医疗保健患者聊天室</span><span class="sxs-lookup"><span data-stu-id="b1e7e-130">Healthcare patient room</span></span>  |<span data-ttu-id="b1e7e-131">创建一组策略和策略设置，这些策略设置适用于您的医疗保健组织中的患者聊天室。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-131">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="b1e7e-132">中小型企业用户（企业语音）</span><span class="sxs-lookup"><span data-stu-id="b1e7e-132">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="b1e7e-133">创建包含商业语音体验应用的应用安装策略。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-133">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="b1e7e-134">中小型企业用户（无业务语音）</span><span class="sxs-lookup"><span data-stu-id="b1e7e-134">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="b1e7e-135">创建一组策略和策略设置，适用于不带任何商业语音功能的中小型企业用户。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-135">Creates a set of policies and policy settings that apply to small and medium sized business users without any Business Voice features.</span></span>|
|<span data-ttu-id="b1e7e-136">公共安全专员</span><span class="sxs-lookup"><span data-stu-id="b1e7e-136">Public safety officer</span></span>   |<span data-ttu-id="b1e7e-137">创建一组策略和策略设置，这些策略设置适用于您的组织中的公共安全专员。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-137">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|



> [!NOTE]
> <span data-ttu-id="b1e7e-138">我们将在未来版本的团队中添加更多策略程序包，请查看最新信息。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-138">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="b1e7e-139">每个单独策略都被授予策略程序包的名称，以便你可以轻松地识别链接到策略包的策略。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-139">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="b1e7e-140">例如，当你将教育版（教师）策略包分配给学校中的教师时，将为程序包中的每个策略创建一个名为 Education_Teacher 的策略。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-140">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![教育版（教师）策略包的屏幕截图](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="b1e7e-142">如何使用策略程序包</span><span class="sxs-lookup"><span data-stu-id="b1e7e-142">How to use policy packages</span></span>

<span data-ttu-id="b1e7e-143">以下概述了如何使用组织中的策略包。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-143">The following outlines how to use policy packages in your organization.</span></span>

![如何使用策略程序包概述](media/manage-policy-packages-overview.png)

- <span data-ttu-id="b1e7e-145">**[查看](#view-the-settings-of-a-policy-in-a-policy-package)**：在分配程序包之前查看策略包中每个策略的设置。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-145">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="b1e7e-146">请确保你了解每个设置，然后确定预定义的值是否适合你的组织，或者你是否需要根据组织的需要将其更改为更具限制性或 lenient。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-146">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="b1e7e-147">如果删除策略，您仍然可以查看设置，但不能更改任何设置。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-147">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="b1e7e-148">分配策略包时，将使用预定义的设置重新创建已删除的策略。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-148">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="b1e7e-149">**[分配](#assign-a-policy-package)**：将策略包分配给用户。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-149">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="b1e7e-150">请记住，在分配程序包之前，不会创建策略包中的策略，之后，你可以在程序包中更改单个策略的设置。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-150">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="b1e7e-151">**[自定义](#customize-policies-in-a-policy-package)**：自定义策略包中的策略设置以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-151">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="b1e7e-152">对策略设置所做的任何更改都将自动应用到分配了该程序包的用户。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-152">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="b1e7e-153">下面是有关如何在 Microsoft 团队管理中心中查看、分配和自定义策略包的步骤。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-153">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="b1e7e-154">查看策略包中的策略设置</span><span class="sxs-lookup"><span data-stu-id="b1e7e-154">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="b1e7e-155">在 Microsoft 团队管理中心的左侧导航中，单击 "**策略包**"，然后通过单击程序包名称左侧的 "策略包" 进行选择。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-155">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="b1e7e-156">单击要查看的策略。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-156">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="b1e7e-157">分配策略包</span><span class="sxs-lookup"><span data-stu-id="b1e7e-157">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="b1e7e-158">为一个用户分配策略包</span><span class="sxs-lookup"><span data-stu-id="b1e7e-158">Assign a policy package to one user</span></span>

1. <span data-ttu-id="b1e7e-159">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b1e7e-159">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="b1e7e-160">在用户的页面上，单击 "**策略**"，然后单击 "**策略程序包**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-160">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="b1e7e-161">在 "**分配策略包**" 窗格中，选择要分配的程序包，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-161">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="b1e7e-162">向多个用户分配策略包</span><span class="sxs-lookup"><span data-stu-id="b1e7e-162">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="b1e7e-163">在 Microsoft 团队管理中心的左侧导航中，转到 "**策略程序包**"，然后通过单击程序包名称左侧的 "选择要分配的策略包"。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-163">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="b1e7e-164">单击 "**管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-164">Click **Manage users**.</span></span>
3. <span data-ttu-id="b1e7e-165">在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b1e7e-165">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="b1e7e-166">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-166">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="b1e7e-167">添加完用户后，单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-167">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="b1e7e-168">为一组大型用户（批处理）分配策略包</span><span class="sxs-lookup"><span data-stu-id="b1e7e-168">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="b1e7e-169">使用批处理策略程序包分配来一次为大型用户分配一个策略包。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-169">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="b1e7e-170">使用[CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet 提交要分配的一批用户和策略包。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-170">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="b1e7e-171">作业作为后台操作处理，并为每个批处理生成操作 ID。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-171">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="b1e7e-172">批处理最多可包含20000个用户。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-172">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="b1e7e-173">你可以按对象 Id、UPN、SIP 地址或电子邮件地址指定用户。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-173">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="b1e7e-174">若要了解详细信息，请参阅向[一批用户分配策略包](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-174">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1e7e-175">我们当前建议你一次为每批5000用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-175">We're currently recommending that you assign policies in batches of 5,000 users at a time.</span></span> <span data-ttu-id="b1e7e-176">在增加需求的这些时间内，你可能会遇到处理时间方面的延迟。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-176">During these times of increased demand, you may experience delays in processing times.</span></span> <span data-ttu-id="b1e7e-177">为了将这些增加的处理时间的影响降到最低，我们建议你向5000用户提交较小的批处理大小，并且仅在上一个批处理完成后再提交。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-177">To minimize the impact of these increased processing times, we suggest that you submit smaller batch sizes of up to 5,000 users, and submit each batch only after the previous one is completed.</span></span> <span data-ttu-id="b1e7e-178">在正常工作时间内提交批还会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-178">Submitting batches outside your regular business hours can also help.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="b1e7e-179">自定义策略包中的策略</span><span class="sxs-lookup"><span data-stu-id="b1e7e-179">Customize policies in a policy package</span></span>

<span data-ttu-id="b1e7e-180">你可以通过 "**策略包**" 页面编辑策略的设置，或直接转到 Microsoft 团队管理中心中的 "策略" 页面。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-180">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="b1e7e-181">在 Microsoft 团队管理中心的左侧导航中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b1e7e-181">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="b1e7e-182">单击 "**策略程序包**"，然后单击 "程序包名称" 左侧的 "策略程序包" 进行选择。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-182">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="b1e7e-183">单击 "策略类型"。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-183">Click the policy type.</span></span>  <span data-ttu-id="b1e7e-184">例如，单击 "**邮件策略**"。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-184">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="b1e7e-185">单击要编辑的策略。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-185">Click the policy you want to edit.</span></span> <span data-ttu-id="b1e7e-186">链接到策略包的策略与策略包的名称相同。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-186">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="b1e7e-187">进行所需的更改，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-187">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b1e7e-188">故障排除</span><span class="sxs-lookup"><span data-stu-id="b1e7e-188">Troubleshooting</span></span>

<span data-ttu-id="b1e7e-189">**分配策略包时收到错误**</span><span class="sxs-lookup"><span data-stu-id="b1e7e-189">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="b1e7e-190">如果程序包中的一个或多个策略未成功创建或应用，可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-190">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="b1e7e-191">将策略程序包重新分配给你的用户。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-191">Reassign the policy package to your users.</span></span> <span data-ttu-id="b1e7e-192">重试操作通常会修复此问题。</span><span class="sxs-lookup"><span data-stu-id="b1e7e-192">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b1e7e-193">相关主题</span><span class="sxs-lookup"><span data-stu-id="b1e7e-193">Related topics</span></span>

[<span data-ttu-id="b1e7e-194">用于 EDU 管理员的 Microsoft Teams 政策包</span><span class="sxs-lookup"><span data-stu-id="b1e7e-194">Microsoft Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
