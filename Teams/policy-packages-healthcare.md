---
title: 用于医疗保健的 Teams 策略包
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
description: 了解如何为医疗保健组织使用和管理 Teams 策略包。
ms.openlocfilehash: af6f5923d5c97fc03c77585ba94292264aacc027
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812852"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="da2ff-103">用于医疗保健的 Teams 策略包</span><span class="sxs-lookup"><span data-stu-id="da2ff-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="da2ff-104">概述</span><span class="sxs-lookup"><span data-stu-id="da2ff-104">Overview</span></span>

<span data-ttu-id="da2ff-105">Microsoft Teams [中的](manage-policy-packages.md) 策略包是预定义的策略和策略设置的集合，可将其分配给组织中具有类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="da2ff-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="da2ff-106">策略包可简化并有助于提供一致的策略管理。</span><span class="sxs-lookup"><span data-stu-id="da2ff-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="da2ff-107">可以自定义程序包中策略的设置以满足用户的需求。</span><span class="sxs-lookup"><span data-stu-id="da2ff-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="da2ff-108">更改策略包中的策略设置时，分配到该包的所有用户将获取更新的设置。</span><span class="sxs-lookup"><span data-stu-id="da2ff-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="da2ff-109">可以使用 Microsoft Teams 管理中心或 PowerShell 管理策略包。</span><span class="sxs-lookup"><span data-stu-id="da2ff-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="da2ff-110">策略包根据包为以下内容预定义策略：</span><span class="sxs-lookup"><span data-stu-id="da2ff-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="da2ff-111">消息传递</span><span class="sxs-lookup"><span data-stu-id="da2ff-111">Messaging</span></span>
- <span data-ttu-id="da2ff-112">会议</span><span class="sxs-lookup"><span data-stu-id="da2ff-112">Meetings</span></span>
- <span data-ttu-id="da2ff-113">通话</span><span class="sxs-lookup"><span data-stu-id="da2ff-113">Calling</span></span>
- <span data-ttu-id="da2ff-114">应用设置</span><span class="sxs-lookup"><span data-stu-id="da2ff-114">App setup</span></span>
- <span data-ttu-id="da2ff-115">实时事件</span><span class="sxs-lookup"><span data-stu-id="da2ff-115">Live events</span></span>

<span data-ttu-id="da2ff-116">Teams 当前包括以下医疗保健策略包。</span><span class="sxs-lookup"><span data-stu-id="da2ff-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="da2ff-117">Microsoft Teams 管理中心中的程序包名称</span><span class="sxs-lookup"><span data-stu-id="da2ff-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="da2ff-118">最适合用于</span><span class="sxs-lookup"><span data-stu-id="da2ff-118">Best used for</span></span>|<span data-ttu-id="da2ff-119">说明</span><span class="sxs-lookup"><span data-stu-id="da2ff-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="da2ff-120">医疗保健医生</span><span class="sxs-lookup"><span data-stu-id="da2ff-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="da2ff-121">医疗保健组织的医疗工作者</span><span class="sxs-lookup"><span data-stu-id="da2ff-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="da2ff-122">创建一组策略和策略设置，使注册医生、医生、医生和社交工作者等医疗工作者能够完全访问聊天、呼叫、轮班管理和会议。</span><span class="sxs-lookup"><span data-stu-id="da2ff-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="da2ff-123">医疗保健信息工作者</span><span class="sxs-lookup"><span data-stu-id="da2ff-123">Healthcare information worker</span></span>  |<span data-ttu-id="da2ff-124">医疗保健组织的信息工作者</span><span class="sxs-lookup"><span data-stu-id="da2ff-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="da2ff-125">创建一组策略和策略设置，为信息工作者（例如 IT 人员、信息工作者、财务人员和合规官）提供聊天、呼叫和会议的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="da2ff-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="da2ff-126">医疗保健患者室</span><span class="sxs-lookup"><span data-stu-id="da2ff-126">Healthcare patient room</span></span>  |<span data-ttu-id="da2ff-127">患者房间设备</span><span class="sxs-lookup"><span data-stu-id="da2ff-127">Patient room devices</span></span>|<span data-ttu-id="da2ff-128">创建一组适用于医疗保健组织中患者室的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="da2ff-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![医疗保健策略包的屏幕截图](media/policy-packages-healthcare.png)

<span data-ttu-id="da2ff-130">每个单独的策略都获得策略包的名称，因此可以轻松识别链接到策略包的策略。</span><span class="sxs-lookup"><span data-stu-id="da2ff-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="da2ff-131">例如，将医疗保健医疗医疗工作者策略包分配给组织的医生时，会Healthcare_ClinicalWorker每个策略创建一个名为 Healthcare_ClinicalWorker 的策略。</span><span class="sxs-lookup"><span data-stu-id="da2ff-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![医疗保健患者包中策略的屏幕截图](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="da2ff-133">策略包入门</span><span class="sxs-lookup"><span data-stu-id="da2ff-133">Get started with policy packages</span></span>

<span data-ttu-id="da2ff-134">若要开始使用医疗保健策略包，请在 Microsoft 管理中心载入中心选择 **"** 医疗保健"，然后选择"按角色分配 **策略设置"。**</span><span class="sxs-lookup"><span data-stu-id="da2ff-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare**, and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="da2ff-135">准备好开始后，确定要向组织中个人分配的策略包。</span><span class="sxs-lookup"><span data-stu-id="da2ff-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="da2ff-136">选择 **"查看策略** 详细信息"，了解有关程序包中特定策略及其相应设置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="da2ff-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="da2ff-137">在 [Teams 管理中心](manage-policy-packages.md#customize-policies-in-a-policy-package) 进行分配后，可以自定义这些设置。</span><span class="sxs-lookup"><span data-stu-id="da2ff-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="da2ff-138">选择要分配的一个或多个程序包，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="da2ff-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="da2ff-139">可以搜索人员，并将其添加到最适合其角色的策略包中。</span><span class="sxs-lookup"><span data-stu-id="da2ff-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="da2ff-140">不能一次将一个策略包分配给多个策略包。</span><span class="sxs-lookup"><span data-stu-id="da2ff-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="da2ff-141">将人员添加到正确的策略包后， **完成完成选择** 。</span><span class="sxs-lookup"><span data-stu-id="da2ff-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="da2ff-142">你可以继续在 Microsoft Teams 管理中心自定义和管理策略包。</span><span class="sxs-lookup"><span data-stu-id="da2ff-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="da2ff-143">管理策略包</span><span class="sxs-lookup"><span data-stu-id="da2ff-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="da2ff-144">查看</span><span class="sxs-lookup"><span data-stu-id="da2ff-144">View</span></span>

<span data-ttu-id="da2ff-145">在分配包前查看策略包中每个策略的设置。</span><span class="sxs-lookup"><span data-stu-id="da2ff-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="da2ff-146">在 Microsoft Teams 管理中心的左侧导航栏中，转到"策略包"，选择包名称，然后选择策略名称。</span><span class="sxs-lookup"><span data-stu-id="da2ff-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="da2ff-147">确定预定义值是否适合你的组织，或是否需要根据组织的需求对其进行自定义，使其更具限制性或更宽松。</span><span class="sxs-lookup"><span data-stu-id="da2ff-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="da2ff-148">自定义</span><span class="sxs-lookup"><span data-stu-id="da2ff-148">Customize</span></span>

<span data-ttu-id="da2ff-149">根据需要自定义策略包中的策略设置，满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="da2ff-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="da2ff-150">对策略设置所做的任何更改都将自动应用到已分配了该包的用户。</span><span class="sxs-lookup"><span data-stu-id="da2ff-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="da2ff-151">若要编辑策略包中的策略设置，请在 Microsoft Teams 管理中心的左侧导航栏中，转到"策略包"，选择策略包，选择要编辑的策略的名称，然后选择"编辑"。  </span><span class="sxs-lookup"><span data-stu-id="da2ff-151">To edit the settings of a policy in a policy package, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="da2ff-152">请记住，在分配策略包之后，你还可以更改包中的策略设置。</span><span class="sxs-lookup"><span data-stu-id="da2ff-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="da2ff-153">若要了解详细信息，请参阅[自定义策略包](manage-policy-packages.md#customize-policies-in-a-policy-package)中的策略。</span><span class="sxs-lookup"><span data-stu-id="da2ff-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span>

### <a name="assign"></a><span data-ttu-id="da2ff-154">分配</span><span class="sxs-lookup"><span data-stu-id="da2ff-154">Assign</span></span>

<span data-ttu-id="da2ff-155">将策略包分配给用户。</span><span class="sxs-lookup"><span data-stu-id="da2ff-155">Assign the policy package to users.</span></span> <span data-ttu-id="da2ff-156">如果用户已分配策略，稍后又分配了另一个策略，则最近分配的优先级将会更高。</span><span class="sxs-lookup"><span data-stu-id="da2ff-156">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="da2ff-157">向一个或多个用户分配策略包</span><span class="sxs-lookup"><span data-stu-id="da2ff-157">Assign a policy package to one or several users</span></span>

<span data-ttu-id="da2ff-158">若要将策略包分配给一个或多个用户，请在 Microsoft Teams 管理中心的左侧导航中，转到 **策略包**，然后选择 **管理用户**。</span><span class="sxs-lookup"><span data-stu-id="da2ff-158">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![有关如何在管理中心分配策略包的屏幕截图](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="da2ff-160">若要了解详细信息，请参阅[分配策略包](manage-policy-packages.md#assign-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="da2ff-160">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="da2ff-161">如果用户已分配策略，稍后又分配了另一个策略，则最近分配的优先级将会更高。</span><span class="sxs-lookup"><span data-stu-id="da2ff-161">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="da2ff-162">将策略包分配给组。</span><span class="sxs-lookup"><span data-stu-id="da2ff-162">Assign a policy package to a group</span></span>

<span data-ttu-id="da2ff-163">**此功能在私有预览版中**</span><span class="sxs-lookup"><span data-stu-id="da2ff-163">**This feature is in private preview**</span></span>

<span data-ttu-id="da2ff-164">通过将策略包分配到组，可将多个策略分配给一组用户，例如安全组或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="da2ff-164">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="da2ff-165">根据优先级规则，将策略分配传播到组中的成员。</span><span class="sxs-lookup"><span data-stu-id="da2ff-165">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="da2ff-166">将成员添加到组或从组中删除成员时，将相应更新其继承的策略分配。</span><span class="sxs-lookup"><span data-stu-id="da2ff-166">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="da2ff-167">建议将此方法用于最多 50,000 个用户的组，但也可使用更大的组。</span><span class="sxs-lookup"><span data-stu-id="da2ff-167">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="da2ff-168">若要了解详细信息，请参阅[将策略包分配到组](assign-policies.md#assign-a-policy-package-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="da2ff-168">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="da2ff-169">向大型组（批处理）分配策略包</span><span class="sxs-lookup"><span data-stu-id="da2ff-169">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="da2ff-170">使用批处理策略包分配，每次向大型用户组分配策略包。</span><span class="sxs-lookup"><span data-stu-id="da2ff-170">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="da2ff-171">使用 [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet 提交要分配的一批用户和策略包。</span><span class="sxs-lookup"><span data-stu-id="da2ff-171">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="da2ff-172">作业将作为后台操作处理，并为每个批处理生成操作 ID。</span><span class="sxs-lookup"><span data-stu-id="da2ff-172">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="da2ff-173">批处理最多可包含 5,000 个用户。</span><span class="sxs-lookup"><span data-stu-id="da2ff-173">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="da2ff-174">可通过对象 Id、UPN、SIP 地址或电子邮件地址指定用户。</span><span class="sxs-lookup"><span data-stu-id="da2ff-174">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="da2ff-175">若要了解详细信息，请参阅[将策略包分配给批次用户](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="da2ff-175">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="da2ff-176">相关主题</span><span class="sxs-lookup"><span data-stu-id="da2ff-176">Related topics</span></span>

[<span data-ttu-id="da2ff-177">在 Teams 中管理策略包</span><span class="sxs-lookup"><span data-stu-id="da2ff-177">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="da2ff-178">在 Teams 中向用户分配策略</span><span class="sxs-lookup"><span data-stu-id="da2ff-178">Assign policies to your users in Teams</span></span>](assign-policies.md)
