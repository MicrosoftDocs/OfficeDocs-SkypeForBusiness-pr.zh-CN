---
title: 医疗保健的团队策略程序包
author: lanachin
ms.author: v-lanac
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
description: 了解如何使用和管理你的医疗保健组织的团队策略包。
ms.openlocfilehash: b8317a7f860d0ab8510a6170b69a50f7a3387ebd
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908511"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="12c1c-103">医疗保健的团队策略程序包</span><span class="sxs-lookup"><span data-stu-id="12c1c-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="12c1c-104">概述</span><span class="sxs-lookup"><span data-stu-id="12c1c-104">Overview</span></span>

<span data-ttu-id="12c1c-105">Microsoft 团队中的 [策略包](manage-policy-packages.md) 是预定义策略和策略设置的集合，可分配给在组织中具有类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="12c1c-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="12c1c-106">策略包可简化并有助于提供一致的策略管理。</span><span class="sxs-lookup"><span data-stu-id="12c1c-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="12c1c-107">你可以自定义程序包中的策略设置以满足你的用户需求。</span><span class="sxs-lookup"><span data-stu-id="12c1c-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="12c1c-108">当您更改策略包中的策略设置时，分配到该程序包的所有用户都将获得更新的设置。</span><span class="sxs-lookup"><span data-stu-id="12c1c-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="12c1c-109">你可以使用 Microsoft 团队管理中心或 PowerShell 管理策略包。</span><span class="sxs-lookup"><span data-stu-id="12c1c-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="12c1c-110">策略程序包针对以下情况预定义策略，具体取决于程序包：</span><span class="sxs-lookup"><span data-stu-id="12c1c-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="12c1c-111">消息传递</span><span class="sxs-lookup"><span data-stu-id="12c1c-111">Messaging</span></span>
- <span data-ttu-id="12c1c-112">会议</span><span class="sxs-lookup"><span data-stu-id="12c1c-112">Meetings</span></span>
- <span data-ttu-id="12c1c-113">通话</span><span class="sxs-lookup"><span data-stu-id="12c1c-113">Calling</span></span>
- <span data-ttu-id="12c1c-114">应用设置</span><span class="sxs-lookup"><span data-stu-id="12c1c-114">App setup</span></span>
- <span data-ttu-id="12c1c-115">实时事件</span><span class="sxs-lookup"><span data-stu-id="12c1c-115">Live events</span></span>

<span data-ttu-id="12c1c-116">团队当前包含以下医疗保健策略程序包。</span><span class="sxs-lookup"><span data-stu-id="12c1c-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="12c1c-117">Microsoft 团队管理中心中的程序包名称</span><span class="sxs-lookup"><span data-stu-id="12c1c-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="12c1c-118">最适合用于</span><span class="sxs-lookup"><span data-stu-id="12c1c-118">Best used for</span></span>|<span data-ttu-id="12c1c-119">说明</span><span class="sxs-lookup"><span data-stu-id="12c1c-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="12c1c-120">医疗保健临床工作者</span><span class="sxs-lookup"><span data-stu-id="12c1c-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="12c1c-121">医疗保健组织中的临床工作者</span><span class="sxs-lookup"><span data-stu-id="12c1c-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="12c1c-122">创建一组策略和策略设置，为临床工作者（如注册的护士、费用护理、医生和社会工作者）提供对聊天、通话、班次管理和会议的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="12c1c-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="12c1c-123">医疗保健信息工作者</span><span class="sxs-lookup"><span data-stu-id="12c1c-123">Healthcare information worker</span></span>  |<span data-ttu-id="12c1c-124">您的医疗保健组织中的信息工作者</span><span class="sxs-lookup"><span data-stu-id="12c1c-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="12c1c-125">创建一组策略和策略设置，提供信息工作者，如 IT 人员、informatics 员工、财务人员和合规性监察官、对聊天、通话和会议的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="12c1c-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="12c1c-126">医疗保健患者聊天室</span><span class="sxs-lookup"><span data-stu-id="12c1c-126">Healthcare patient room</span></span>  |<span data-ttu-id="12c1c-127">患者聊天室设备</span><span class="sxs-lookup"><span data-stu-id="12c1c-127">Patient room devices</span></span>|<span data-ttu-id="12c1c-128">创建一组策略和策略设置，这些策略设置适用于您的医疗保健组织中的患者聊天室。</span><span class="sxs-lookup"><span data-stu-id="12c1c-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![医疗保健策略程序包的屏幕截图](media/policy-packages-healthcare.png)

<span data-ttu-id="12c1c-130">每个单独策略都被授予策略程序包的名称，以便你可以轻松地识别链接到策略包的策略。</span><span class="sxs-lookup"><span data-stu-id="12c1c-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="12c1c-131">例如，当你将医疗保健临床工作人员策略包分配给你的组织中的临床医生时，将为程序包中的每个策略创建一个名为 Healthcare_ClinicalWorker 的策略。</span><span class="sxs-lookup"><span data-stu-id="12c1c-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![医疗保健临床工作者程序包中的策略的屏幕截图](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="12c1c-133">策略程序包入门</span><span class="sxs-lookup"><span data-stu-id="12c1c-133">Get started with policy packages</span></span>

<span data-ttu-id="12c1c-134">若要开始使用医疗保健策略程序包，请在 Microsoft 管理中心的 "加入中心" 中选择 " **医疗保健** "，然后选择 " **按角色分配策略设置** "。</span><span class="sxs-lookup"><span data-stu-id="12c1c-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare** , and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="12c1c-135">准备好开始使用后，请确定你想要为组织中的个人分配哪些策略包。</span><span class="sxs-lookup"><span data-stu-id="12c1c-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="12c1c-136">选择 " **查看策略详细信息** " 以了解有关程序包中的特定策略及其各自的设置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="12c1c-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="12c1c-137">这些可在团队管理中心中分配后 [进行自定义](manage-policy-packages.md#customize-policies-in-a-policy-package) 。</span><span class="sxs-lookup"><span data-stu-id="12c1c-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="12c1c-138">选择一个或多个要分配的程序包，然后单击 " **下一步** "。</span><span class="sxs-lookup"><span data-stu-id="12c1c-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="12c1c-139">你可以搜索联系人并将其添加到最适合其角色的策略包。</span><span class="sxs-lookup"><span data-stu-id="12c1c-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="12c1c-140">一次无法将一个人分配给多个策略程序包。</span><span class="sxs-lookup"><span data-stu-id="12c1c-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="12c1c-141">将人员添加到正确的策略包后，请 **完成** 最终的选择。</span><span class="sxs-lookup"><span data-stu-id="12c1c-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="12c1c-142">你可以继续自定义和管理 Microsoft 团队管理中心中的策略包。</span><span class="sxs-lookup"><span data-stu-id="12c1c-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="12c1c-143">管理策略包</span><span class="sxs-lookup"><span data-stu-id="12c1c-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="12c1c-144">查看</span><span class="sxs-lookup"><span data-stu-id="12c1c-144">View</span></span>

<span data-ttu-id="12c1c-145">在分配程序包之前查看策略包中每个策略的设置。</span><span class="sxs-lookup"><span data-stu-id="12c1c-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="12c1c-146">在 Microsoft 团队管理中心的左侧导航中，转到 " **策略程序包** "，选择程序包名称，然后选择 "策略名称"。</span><span class="sxs-lookup"><span data-stu-id="12c1c-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages** , select the package name, and then select the policy name.</span></span>

<span data-ttu-id="12c1c-147">确定预定义的值是否适合你的组织，或者你是否需要根据组织的需求自定义它们以使其更具限制性或 lenient。</span><span class="sxs-lookup"><span data-stu-id="12c1c-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="12c1c-148">自定义</span><span class="sxs-lookup"><span data-stu-id="12c1c-148">Customize</span></span>

<span data-ttu-id="12c1c-149">根据需要自定义策略包中的策略设置，以满足组织的需要。</span><span class="sxs-lookup"><span data-stu-id="12c1c-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="12c1c-150">对策略设置所做的任何更改都将自动应用到分配了该程序包的用户。</span><span class="sxs-lookup"><span data-stu-id="12c1c-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="12c1c-151">若要编辑策略包中的策略设置，请在 Microsoft 团队管理中心的左侧导航中，转到 " **策略程序包** "，选择策略程序包，选择要编辑的策略的名称，然后选择 " **编辑** "。</span><span class="sxs-lookup"><span data-stu-id="12c1c-151">To edit the settings of a policy in a policy package, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="12c1c-152">请记住，你还可以在分配策略包后更改程序包中的策略设置。</span><span class="sxs-lookup"><span data-stu-id="12c1c-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="12c1c-153">若要了解详细信息，请参阅 [自定义策略包中的策略](manage-policy-packages.md#customize-policies-in-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="12c1c-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span>

### <a name="assign"></a><span data-ttu-id="12c1c-154">分配</span><span class="sxs-lookup"><span data-stu-id="12c1c-154">Assign</span></span>

<span data-ttu-id="12c1c-155">将策略包分配给用户。</span><span class="sxs-lookup"><span data-stu-id="12c1c-155">Assign the policy package to users.</span></span> <span data-ttu-id="12c1c-156">如果用户分配了策略，然后你分配了其他策略，则最新作业的优先级将会更高。</span><span class="sxs-lookup"><span data-stu-id="12c1c-156">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="12c1c-157">将策略包分配给一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="12c1c-157">Assign a policy package to one or several users</span></span>

<span data-ttu-id="12c1c-158">若要向一个或多个用户分配策略包，请在 Microsoft 团队管理中心的左侧导航中，转到 " **策略程序包** "，然后选择 " **管理用户** "。</span><span class="sxs-lookup"><span data-stu-id="12c1c-158">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select **Manage users**.</span></span>  

![如何在管理中心分配策略包的屏幕截图](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="12c1c-160">若要了解详细信息，请参阅 [分配策略包](manage-policy-packages.md#assign-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="12c1c-160">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="12c1c-161">如果用户分配了策略，然后你分配了其他策略，则最新作业的优先级将会更高。</span><span class="sxs-lookup"><span data-stu-id="12c1c-161">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="12c1c-162">为组分配策略包</span><span class="sxs-lookup"><span data-stu-id="12c1c-162">Assign a policy package to a group</span></span>

<span data-ttu-id="12c1c-163">**此功能在私人预览版中**</span><span class="sxs-lookup"><span data-stu-id="12c1c-163">**This feature is in private preview**</span></span>

<span data-ttu-id="12c1c-164">通过将策略包分配给组，你可以将多个策略分配给一组用户，如安全组或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="12c1c-164">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="12c1c-165">根据优先级规则，策略分配将传播到组的成员。</span><span class="sxs-lookup"><span data-stu-id="12c1c-165">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="12c1c-166">将成员添加到组或从组中删除成员后，将相应地更新其继承的策略分配。</span><span class="sxs-lookup"><span data-stu-id="12c1c-166">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="12c1c-167">对于多达50000用户的组，建议使用此方法，但也可使用较大的组。</span><span class="sxs-lookup"><span data-stu-id="12c1c-167">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="12c1c-168">若要了解详细信息，请参阅向 [组分配策略包](assign-policies.md#assign-a-policy-package-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="12c1c-168">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="12c1c-169">将策略包分配给大型集 (批处理) 用户</span><span class="sxs-lookup"><span data-stu-id="12c1c-169">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="12c1c-170">使用批处理策略程序包分配来一次为大型用户分配一个策略包。</span><span class="sxs-lookup"><span data-stu-id="12c1c-170">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="12c1c-171">使用 [CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet 提交要分配的一批用户和策略包。</span><span class="sxs-lookup"><span data-stu-id="12c1c-171">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="12c1c-172">作业作为后台操作处理，并为每个批处理生成操作 ID。</span><span class="sxs-lookup"><span data-stu-id="12c1c-172">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="12c1c-173">批处理最多可包含5000个用户。</span><span class="sxs-lookup"><span data-stu-id="12c1c-173">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="12c1c-174">你可以按对象 Id、UPN、SIP 地址或电子邮件地址指定用户。</span><span class="sxs-lookup"><span data-stu-id="12c1c-174">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="12c1c-175">若要了解详细信息，请参阅向 [一批用户分配策略包](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="12c1c-175">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="12c1c-176">相关主题</span><span class="sxs-lookup"><span data-stu-id="12c1c-176">Related topics</span></span>

[<span data-ttu-id="12c1c-177">在 Teams 中管理策略包</span><span class="sxs-lookup"><span data-stu-id="12c1c-177">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="12c1c-178">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="12c1c-178">Assign policies to your users in Teams</span></span>](assign-policies.md)
