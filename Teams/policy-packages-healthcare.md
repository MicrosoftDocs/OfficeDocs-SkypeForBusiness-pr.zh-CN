---
title: Teams 医疗保健策略包
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 了解如何使用和管理适用于医疗保健组织的 Teams 策略包。
ms.openlocfilehash: 830b8fc5f6938f84f188f5f5d732a3ecfd6eb5b1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117760"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="9c9df-103">Teams 医疗保健策略包</span><span class="sxs-lookup"><span data-stu-id="9c9df-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="9c9df-104">概述</span><span class="sxs-lookup"><span data-stu-id="9c9df-104">Overview</span></span>

<span data-ttu-id="9c9df-105">Microsoft Teams 中的[策略包](manage-policy-packages.md)是一组预定义的策略和策略设置，你可以将其分配给组织中具有类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="9c9df-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="9c9df-106">策略包可简化并有助于提供一致的策略管理。</span><span class="sxs-lookup"><span data-stu-id="9c9df-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="9c9df-107">你可以自定义包中策略的设置以满足用户的需求。</span><span class="sxs-lookup"><span data-stu-id="9c9df-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="9c9df-108">当你更改策略包中策略的设置时，分配了该包的所有用户均会获得更新后的设置。</span><span class="sxs-lookup"><span data-stu-id="9c9df-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="9c9df-109">你可以使用 Microsoft Teams 管理中心或 PowerShell 管理策略包。</span><span class="sxs-lookup"><span data-stu-id="9c9df-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="9c9df-110">策略包针对以下各项预定义了策略，具体内容因策略包而异：</span><span class="sxs-lookup"><span data-stu-id="9c9df-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="9c9df-111">消息传递</span><span class="sxs-lookup"><span data-stu-id="9c9df-111">Messaging</span></span>
- <span data-ttu-id="9c9df-112">会议</span><span class="sxs-lookup"><span data-stu-id="9c9df-112">Meetings</span></span>
- <span data-ttu-id="9c9df-113">通话</span><span class="sxs-lookup"><span data-stu-id="9c9df-113">Calling</span></span>
- <span data-ttu-id="9c9df-114">应用设置</span><span class="sxs-lookup"><span data-stu-id="9c9df-114">App setup</span></span>
- <span data-ttu-id="9c9df-115">实时事件</span><span class="sxs-lookup"><span data-stu-id="9c9df-115">Live events</span></span>

<span data-ttu-id="9c9df-116">Teams 当前包括以下医疗保健策略包。</span><span class="sxs-lookup"><span data-stu-id="9c9df-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="9c9df-117">Microsoft Teams 管理中心中的策略包名称</span><span class="sxs-lookup"><span data-stu-id="9c9df-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="9c9df-118">最适合用于</span><span class="sxs-lookup"><span data-stu-id="9c9df-118">Best used for</span></span>|<span data-ttu-id="9c9df-119">说明</span><span class="sxs-lookup"><span data-stu-id="9c9df-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="9c9df-120">医疗保健临床工作者</span><span class="sxs-lookup"><span data-stu-id="9c9df-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="9c9df-121">医疗保健组织的临床工作者</span><span class="sxs-lookup"><span data-stu-id="9c9df-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="9c9df-122">创建一组策略和策略设置，以使临床工作者（例如注册护士、护士长、医师和社会工作者）可以完全访问聊天、通话、轮班管理和会议。</span><span class="sxs-lookup"><span data-stu-id="9c9df-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="9c9df-123">医疗保健信息工作者</span><span class="sxs-lookup"><span data-stu-id="9c9df-123">Healthcare information worker</span></span>  |<span data-ttu-id="9c9df-124">医疗保健组织的信息工作者</span><span class="sxs-lookup"><span data-stu-id="9c9df-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="9c9df-125">创建一组策略和策略设置，以使信息工作者（例如 IT 人员、信息学人员、财务人员和合规专员）可以完全访问聊天、通话和会议。</span><span class="sxs-lookup"><span data-stu-id="9c9df-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="9c9df-126">医疗保健病房</span><span class="sxs-lookup"><span data-stu-id="9c9df-126">Healthcare patient room</span></span>  |<span data-ttu-id="9c9df-127">病房设备</span><span class="sxs-lookup"><span data-stu-id="9c9df-127">Patient room devices</span></span>|<span data-ttu-id="9c9df-128">创建一组适用于医疗保健组织中病房的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="9c9df-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![医疗保健策略包的屏幕截图](media/policy-packages-healthcare.png)

<span data-ttu-id="9c9df-130">将为每个单独的策略提供策略包的名称，以便你可以轻松识别链接到该策略包的策略。</span><span class="sxs-lookup"><span data-stu-id="9c9df-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="9c9df-131">例如，当你将医疗保健临床工作者策略包分配给组织中的临床医师时，系统将为该策略包中的每个策略创建一个名为 Healthcare_ClinicalWorker 的策略。</span><span class="sxs-lookup"><span data-stu-id="9c9df-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![医疗保健临床工作者策略包中策略的屏幕截图](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="9c9df-133">开始使用策略包</span><span class="sxs-lookup"><span data-stu-id="9c9df-133">Get started with policy packages</span></span>

<span data-ttu-id="9c9df-134">若要开始使用医疗保健策略包，请在 Microsoft 管理中心载入中心上选择“**医疗保健**”，然后选择“**按角色分配策略设置**”。</span><span class="sxs-lookup"><span data-stu-id="9c9df-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare**, and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="9c9df-135">准备好开始使用后，请确定要将组织中的个人分配给哪些策略包。</span><span class="sxs-lookup"><span data-stu-id="9c9df-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="9c9df-136">选择“**查看策略详细信息**”，以了解有关策略包中的特定策略及其各自设置的更多信息。</span><span class="sxs-lookup"><span data-stu-id="9c9df-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="9c9df-137">分配后可在 Teams 管理中心中[自定义](manage-policy-packages.md#customize-policies-in-a-policy-package)这些设置。</span><span class="sxs-lookup"><span data-stu-id="9c9df-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="9c9df-138">选择要分配的一个或多个包，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="9c9df-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="9c9df-139">可以搜索人员并将其添加到最适合其角色的策略包。</span><span class="sxs-lookup"><span data-stu-id="9c9df-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="9c9df-140">不能一次将一个人分配给多个策略包。</span><span class="sxs-lookup"><span data-stu-id="9c9df-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="9c9df-141">将人员添加到正确的策略包后，请单击“**完成**”以最终确定你所做的选择。</span><span class="sxs-lookup"><span data-stu-id="9c9df-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="9c9df-142">可在 Microsoft Teams 管理中心中继续自定义和管理策略包。</span><span class="sxs-lookup"><span data-stu-id="9c9df-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="9c9df-143">管理策略包</span><span class="sxs-lookup"><span data-stu-id="9c9df-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="9c9df-144">查看</span><span class="sxs-lookup"><span data-stu-id="9c9df-144">View</span></span>

<span data-ttu-id="9c9df-145">在分配包前查看策略包中每个策略的设置。</span><span class="sxs-lookup"><span data-stu-id="9c9df-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="9c9df-146">在 Microsoft Teams 管理中心的左侧导航栏中，转至“**策略包**”，选择策略包名称，然后选择策略名称。</span><span class="sxs-lookup"><span data-stu-id="9c9df-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="9c9df-147">确定预定义值是否适合你的组织，或是否需要根据组织的需求对其进行自定义，使其更具限制性或更宽松。</span><span class="sxs-lookup"><span data-stu-id="9c9df-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="9c9df-148">自定义</span><span class="sxs-lookup"><span data-stu-id="9c9df-148">Customize</span></span>

<span data-ttu-id="9c9df-149">根据需要自定义策略包中的策略设置，满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="9c9df-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="9c9df-150">对策略设置所做的任何更改都将自动应用到已分配了该包的用户。</span><span class="sxs-lookup"><span data-stu-id="9c9df-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="9c9df-151">若要编辑策略包中某个策略的设置，请在 Microsoft Teams 管理中心的左侧导航栏中，转至“**策略包**”，选择策略包，选择要编辑的策略的名称，然后选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="9c9df-151">To edit the settings of a policy in a policy package, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="9c9df-152">请记住，在分配策略包之后，你还可以更改包中的策略设置。</span><span class="sxs-lookup"><span data-stu-id="9c9df-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="9c9df-153">若要了解详细信息，请参阅[自定义策略包](manage-policy-packages.md#customize-policies-in-a-policy-package)中的策略。</span><span class="sxs-lookup"><span data-stu-id="9c9df-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span>

### <a name="assign"></a><span data-ttu-id="9c9df-154">分配</span><span class="sxs-lookup"><span data-stu-id="9c9df-154">Assign</span></span>

<span data-ttu-id="9c9df-p110">将策略包分配给用户。如果用户已分配策略，稍后又分配了另一个策略，则最近分配的优先级将会更高。</span><span class="sxs-lookup"><span data-stu-id="9c9df-p110">Assign the policy package to users. If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="9c9df-157">向一个或多个用户分配策略包</span><span class="sxs-lookup"><span data-stu-id="9c9df-157">Assign a policy package to one or several users</span></span>

<span data-ttu-id="9c9df-158">若要将策略包分配给一个或多个用户，请在 Microsoft Teams 管理中心的左侧导航中，转到 **策略包**，然后选择 **管理用户**。</span><span class="sxs-lookup"><span data-stu-id="9c9df-158">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![有关如何在管理中心分配策略包的屏幕截图](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="9c9df-160">若要了解详细信息，请参阅[分配策略包](manage-policy-packages.md#assign-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="9c9df-160">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="9c9df-161">如果用户已分配策略，稍后又分配了另一个策略，则最近分配的优先级将会更高。</span><span class="sxs-lookup"><span data-stu-id="9c9df-161">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="9c9df-162">将策略包分配给组。</span><span class="sxs-lookup"><span data-stu-id="9c9df-162">Assign a policy package to a group</span></span>

<span data-ttu-id="9c9df-163">**此功能在私有预览版中**</span><span class="sxs-lookup"><span data-stu-id="9c9df-163">**This feature is in private preview**</span></span>

<span data-ttu-id="9c9df-164">通过将策略包分配到组，可将多个策略分配给一组用户，例如安全组或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="9c9df-164">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="9c9df-165">根据优先级规则，将策略分配传播到组中的成员。</span><span class="sxs-lookup"><span data-stu-id="9c9df-165">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="9c9df-166">将成员添加到组或从组中删除成员时，将相应更新其继承的策略分配。</span><span class="sxs-lookup"><span data-stu-id="9c9df-166">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="9c9df-167">建议将此方法用于最多 50,000 个用户的组，但也可使用更大的组。</span><span class="sxs-lookup"><span data-stu-id="9c9df-167">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="9c9df-168">若要了解详细信息，请参阅[将策略包分配到组](assign-policies.md#assign-a-policy-package-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="9c9df-168">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="9c9df-169">向大型组（批处理）分配策略包</span><span class="sxs-lookup"><span data-stu-id="9c9df-169">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="9c9df-170">使用批处理策略包分配，每次向大型用户组分配策略包。</span><span class="sxs-lookup"><span data-stu-id="9c9df-170">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="9c9df-171">使用 [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet 提交要分配的一批用户和策略包。</span><span class="sxs-lookup"><span data-stu-id="9c9df-171">You use the [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="9c9df-172">作业将作为后台操作处理，并为每个批处理生成操作 ID。</span><span class="sxs-lookup"><span data-stu-id="9c9df-172">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="9c9df-173">批处理最多可包含 5,000 个用户。</span><span class="sxs-lookup"><span data-stu-id="9c9df-173">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="9c9df-174">可通过对象 Id、UPN、SIP 地址或电子邮件地址指定用户。</span><span class="sxs-lookup"><span data-stu-id="9c9df-174">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="9c9df-175">若要了解详细信息，请参阅[将策略包分配给批次用户](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="9c9df-175">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9c9df-176">相关主题</span><span class="sxs-lookup"><span data-stu-id="9c9df-176">Related topics</span></span>

[<span data-ttu-id="9c9df-177">在 Teams 中管理策略包</span><span class="sxs-lookup"><span data-stu-id="9c9df-177">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="9c9df-178">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="9c9df-178">Assign policies to your users in Teams</span></span>](assign-policies.md)