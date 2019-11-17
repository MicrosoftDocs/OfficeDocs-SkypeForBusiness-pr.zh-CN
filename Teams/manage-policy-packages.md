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
f1keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理 Microsoft 团队中的策略程序包。
ms.openlocfilehash: ecfc6ae6fb1bb4d9632b8cd04b35dcee6d63359d
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "38679821"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="ccf02-103">管理 Microsoft 团队中的策略程序包</span><span class="sxs-lookup"><span data-stu-id="ccf02-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="ccf02-104">Microsoft 团队中的策略包是预定义策略和策略设置的集合，可分配给在组织中具有类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="ccf02-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="ccf02-105">我们构建了策略程序包，以便在管理组织内的用户组策略时提供简化、简化和帮助。</span><span class="sxs-lookup"><span data-stu-id="ccf02-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="ccf02-106">向用户分配策略包时，将创建程序包中的策略，然后你可以自定义程序包中的策略设置以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="ccf02-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="ccf02-107">什么是策略包？</span><span class="sxs-lookup"><span data-stu-id="ccf02-107">What is a policy package?</span></span>

<span data-ttu-id="ccf02-108">通过策略程序包，你可以控制你希望允许或限制你的组织中的特定人员组的团队功能。</span><span class="sxs-lookup"><span data-stu-id="ccf02-108">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="ccf02-109">团队中的每个策略包都围绕用户角色进行设计，其中包括预定义的策略和策略设置，这些策略和策略设置支持为该角色典型的协作和通信活动。</span><span class="sxs-lookup"><span data-stu-id="ccf02-109">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="ccf02-110">团队当前包含以下策略程序包。</span><span class="sxs-lookup"><span data-stu-id="ccf02-110">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="ccf02-111">**程序包名称**</span><span class="sxs-lookup"><span data-stu-id="ccf02-111">**Package name**</span></span>  |<span data-ttu-id="ccf02-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="ccf02-112">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="ccf02-113">Education_Teacher 程序包</span><span class="sxs-lookup"><span data-stu-id="ccf02-113">Education_Teacher package</span></span>     |<span data-ttu-id="ccf02-114">创建一组适用于教师的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="ccf02-114">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="ccf02-115">Education_PrimaryStudent 程序包</span><span class="sxs-lookup"><span data-stu-id="ccf02-115">Education_PrimaryStudent package</span></span>    |<span data-ttu-id="ccf02-116">创建一组适用于主要学生的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="ccf02-116">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="ccf02-117">Education_SecondaryStudent 程序包</span><span class="sxs-lookup"><span data-stu-id="ccf02-117">Education_SecondaryStudent package</span></span>    |<span data-ttu-id="ccf02-118">创建一组适用于次要学生的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="ccf02-118">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="ccf02-119">Education_HigherEducationStudent 程序包</span><span class="sxs-lookup"><span data-stu-id="ccf02-119">Education_HigherEducationStudent package</span></span>    |<span data-ttu-id="ccf02-120">创建一组适用于更高教育学生的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="ccf02-120">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="ccf02-121">SmallMediumBusiness_BusinessVoice 程序包</span><span class="sxs-lookup"><span data-stu-id="ccf02-121">SmallMediumBusiness_BusinessVoice package</span></span>    |<span data-ttu-id="ccf02-122">创建包含商业语音体验应用的应用安装策略。</span><span class="sxs-lookup"><span data-stu-id="ccf02-122">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|

> [!NOTE]
> <span data-ttu-id="ccf02-123">我们将在未来版本的团队中添加更多策略程序包，请查看最新信息。</span><span class="sxs-lookup"><span data-stu-id="ccf02-123">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="ccf02-124">每个单独策略都被授予策略程序包的名称，以便你可以轻松地识别链接到策略包的策略。</span><span class="sxs-lookup"><span data-stu-id="ccf02-124">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="ccf02-125">例如，当你将 Education_Teacher 策略包分配给学校中的教师时，将为程序包中的每个策略创建一个名为 Education_Teacher 的策略。</span><span class="sxs-lookup"><span data-stu-id="ccf02-125">For example, when you assign the Education_Teacher policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Education_Teacher 策略程序包的屏幕截图](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="ccf02-127">如何使用策略程序包</span><span class="sxs-lookup"><span data-stu-id="ccf02-127">How to use policy packages</span></span>

<span data-ttu-id="ccf02-128">以下概述了如何使用组织中的策略包。</span><span class="sxs-lookup"><span data-stu-id="ccf02-128">The following outlines how to use policy packages in your organization.</span></span>

![如何使用策略程序包概述](media/manage-policy-packages-overview.png)

- <span data-ttu-id="ccf02-130">**[查看](#view-the-settings-of-a-policy-in-a-policy-package)**：在分配程序包之前查看策略包中每个策略的设置。</span><span class="sxs-lookup"><span data-stu-id="ccf02-130">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="ccf02-131">请确保你了解每个设置，然后确定预定义的值是否适合你的组织，或者你是否需要根据组织的需要将其更改为更具限制性或 lenient。</span><span class="sxs-lookup"><span data-stu-id="ccf02-131">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="ccf02-132">如果删除策略，您仍然可以查看设置，但不能更改任何设置。</span><span class="sxs-lookup"><span data-stu-id="ccf02-132">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="ccf02-133">分配策略包时，将使用预定义的设置重新创建已删除的策略。</span><span class="sxs-lookup"><span data-stu-id="ccf02-133">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="ccf02-134">**[分配](#assign-a-policy-package)**：将策略包分配给用户。</span><span class="sxs-lookup"><span data-stu-id="ccf02-134">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="ccf02-135">请记住，在分配程序包之前，不会创建策略包中的策略，之后，你可以在程序包中更改单个策略的设置。</span><span class="sxs-lookup"><span data-stu-id="ccf02-135">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="ccf02-136">**[自定义](#customize-policies-in-a-policy-package)**：自定义策略包中的策略设置以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="ccf02-136">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="ccf02-137">对策略设置所做的任何更改都将自动应用到分配了该程序包的用户。</span><span class="sxs-lookup"><span data-stu-id="ccf02-137">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="ccf02-138">下面是有关如何在 Microsoft 团队管理中心中查看、分配和自定义策略包的步骤。</span><span class="sxs-lookup"><span data-stu-id="ccf02-138">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="ccf02-139">查看策略包中的策略设置</span><span class="sxs-lookup"><span data-stu-id="ccf02-139">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="ccf02-140">在 Microsoft 团队管理中心的左侧导航中，单击 "**策略包**"，然后通过单击程序包名称左侧的 "策略包" 进行选择。</span><span class="sxs-lookup"><span data-stu-id="ccf02-140">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="ccf02-141">单击要查看的策略。</span><span class="sxs-lookup"><span data-stu-id="ccf02-141">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="ccf02-142">分配策略包</span><span class="sxs-lookup"><span data-stu-id="ccf02-142">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="ccf02-143">为一个用户分配策略包</span><span class="sxs-lookup"><span data-stu-id="ccf02-143">Assign a policy package to one user</span></span>

1. <span data-ttu-id="ccf02-144">在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"，然后单击 "用户"。</span><span class="sxs-lookup"><span data-stu-id="ccf02-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="ccf02-145">在用户的页面上，单击 "**策略**"，然后单击 "**策略程序包**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="ccf02-145">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="ccf02-146">在 "**分配策略包**" 窗格中，选择要分配的程序包，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="ccf02-146">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="ccf02-147">向多个用户分配策略包</span><span class="sxs-lookup"><span data-stu-id="ccf02-147">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="ccf02-148">在 Microsoft 团队管理中心的左侧导航中，转到 "**策略程序包**"，然后通过单击程序包名称左侧的 "选择要分配的策略包"。</span><span class="sxs-lookup"><span data-stu-id="ccf02-148">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="ccf02-149">单击 "**管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="ccf02-149">Click **Manage users**.</span></span>
3. <span data-ttu-id="ccf02-150">在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="ccf02-150">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="ccf02-151">对要添加的每个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="ccf02-151">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="ccf02-152">添加完用户后，单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="ccf02-152">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="ccf02-153">自定义策略包中的策略</span><span class="sxs-lookup"><span data-stu-id="ccf02-153">Customize policies in a policy package</span></span>

<span data-ttu-id="ccf02-154">你可以通过 "**策略包**" 页面编辑策略的设置，或直接转到 Microsoft 团队管理中心中的 "策略" 页面。</span><span class="sxs-lookup"><span data-stu-id="ccf02-154">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="ccf02-155">在 Microsoft 团队管理中心的左侧导航中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="ccf02-155">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="ccf02-156">单击 "**策略程序包**"，然后单击 "程序包名称" 左侧的 "策略程序包" 进行选择。</span><span class="sxs-lookup"><span data-stu-id="ccf02-156">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="ccf02-157">单击 "策略类型"。</span><span class="sxs-lookup"><span data-stu-id="ccf02-157">Click the policy type.</span></span>  <span data-ttu-id="ccf02-158">例如，单击 "**邮件策略**"。</span><span class="sxs-lookup"><span data-stu-id="ccf02-158">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="ccf02-159">单击要编辑的策略。</span><span class="sxs-lookup"><span data-stu-id="ccf02-159">Click the policy you want to edit.</span></span> <span data-ttu-id="ccf02-160">链接到策略包的策略与策略包的名称相同。</span><span class="sxs-lookup"><span data-stu-id="ccf02-160">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="ccf02-161">进行所需的更改，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="ccf02-161">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ccf02-162">疑难解答</span><span class="sxs-lookup"><span data-stu-id="ccf02-162">Troubleshooting</span></span>

<span data-ttu-id="ccf02-163">**分配策略包时收到错误**</span><span class="sxs-lookup"><span data-stu-id="ccf02-163">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="ccf02-164">如果程序包中的一个或多个策略未成功创建或应用，可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="ccf02-164">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="ccf02-165">将策略程序包重新分配给你的用户。</span><span class="sxs-lookup"><span data-stu-id="ccf02-165">Reassign the policy package to your users.</span></span> <span data-ttu-id="ccf02-166">重试操作通常会修复此问题。</span><span class="sxs-lookup"><span data-stu-id="ccf02-166">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ccf02-167">相关主题</span><span class="sxs-lookup"><span data-stu-id="ccf02-167">Related topics</span></span>

[<span data-ttu-id="ccf02-168">适用于教育机构管理员的 Microsoft 团队策略包</span><span class="sxs-lookup"><span data-stu-id="ccf02-168">Microsoft Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
