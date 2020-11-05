---
title: 政府团队政策包
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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理政府组织的团队策略包。
ms.openlocfilehash: 8ef632689cb52180e8fd18cf4047fb9a25150885
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908591"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="52a82-103">政府团队政策包</span><span class="sxs-lookup"><span data-stu-id="52a82-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="52a82-104">策略程序包目前在 Microsoft 365 政府版或 DoD 部署中不可用。</span><span class="sxs-lookup"><span data-stu-id="52a82-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="52a82-105">概述</span><span class="sxs-lookup"><span data-stu-id="52a82-105">Overview</span></span>

<span data-ttu-id="52a82-106">Microsoft 团队中的 [策略包](manage-policy-packages.md) 是预定义策略和策略设置的集合，可分配给在组织中具有类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="52a82-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="52a82-107">策略包可简化并有助于提供一致的策略管理。</span><span class="sxs-lookup"><span data-stu-id="52a82-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="52a82-108">你可以自定义程序包中的策略设置以满足你的用户需求。</span><span class="sxs-lookup"><span data-stu-id="52a82-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="52a82-109">当您更改策略包中的策略设置时，分配到该程序包的所有用户都将获得更新的设置。</span><span class="sxs-lookup"><span data-stu-id="52a82-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="52a82-110">你可以使用 Microsoft 团队管理中心或 PowerShell 管理策略包。</span><span class="sxs-lookup"><span data-stu-id="52a82-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="52a82-111">策略程序包针对以下情况预定义策略，具体取决于程序包：</span><span class="sxs-lookup"><span data-stu-id="52a82-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="52a82-112">消息传递</span><span class="sxs-lookup"><span data-stu-id="52a82-112">Messaging</span></span>
- <span data-ttu-id="52a82-113">会议</span><span class="sxs-lookup"><span data-stu-id="52a82-113">Meetings</span></span>
- <span data-ttu-id="52a82-114">通话</span><span class="sxs-lookup"><span data-stu-id="52a82-114">Calling</span></span>
- <span data-ttu-id="52a82-115">应用设置</span><span class="sxs-lookup"><span data-stu-id="52a82-115">App setup</span></span>
- <span data-ttu-id="52a82-116">实时事件</span><span class="sxs-lookup"><span data-stu-id="52a82-116">Live events</span></span>

<span data-ttu-id="52a82-117">团队当前包括适用于政府的以下政策包。</span><span class="sxs-lookup"><span data-stu-id="52a82-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="52a82-118">Microsoft 团队管理中心中的程序包名称</span><span class="sxs-lookup"><span data-stu-id="52a82-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="52a82-119">最适合用于</span><span class="sxs-lookup"><span data-stu-id="52a82-119">Best used for</span></span>|<span data-ttu-id="52a82-120">说明</span><span class="sxs-lookup"><span data-stu-id="52a82-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="52a82-121">公共安全专员</span><span class="sxs-lookup"><span data-stu-id="52a82-121">Public safety officer</span></span>  |<span data-ttu-id="52a82-122">政府组织中的公共安全官员</span><span class="sxs-lookup"><span data-stu-id="52a82-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="52a82-123">创建一组策略和策略设置，这些策略设置适用于您的组织中的公共安全专员。</span><span class="sxs-lookup"><span data-stu-id="52a82-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="52a82-124">一线管理器</span><span class="sxs-lookup"><span data-stu-id="52a82-124">Firstline manager</span></span>  |<span data-ttu-id="52a82-125">政府组织中的一线经理</span><span class="sxs-lookup"><span data-stu-id="52a82-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="52a82-126">创建一组策略，并将这些设置应用到组织中的一线管理员。</span><span class="sxs-lookup"><span data-stu-id="52a82-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="52a82-127">一线工作人员</span><span class="sxs-lookup"><span data-stu-id="52a82-127">Firstline worker</span></span>  |<span data-ttu-id="52a82-128">您的政府组织中的一线工作者</span><span class="sxs-lookup"><span data-stu-id="52a82-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="52a82-129">创建一组策略，并将这些设置应用于您的组织中的一线工作人员。</span><span class="sxs-lookup"><span data-stu-id="52a82-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![医疗保健策略程序包的屏幕截图](media/policy-packages-gov.png)

<span data-ttu-id="52a82-131">每个单独策略都被授予策略程序包的名称，以便你可以轻松地识别链接到策略包的策略。</span><span class="sxs-lookup"><span data-stu-id="52a82-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="52a82-132">例如，当您将公共安全专员策略包分配给您的组织中的用户时，将为程序包中的每个策略创建一个名为 PublicSafety_Officer 的策略。</span><span class="sxs-lookup"><span data-stu-id="52a82-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![医疗保健临床工作者程序包中的策略的屏幕截图](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="52a82-134">管理策略包</span><span class="sxs-lookup"><span data-stu-id="52a82-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="52a82-135">查看</span><span class="sxs-lookup"><span data-stu-id="52a82-135">View</span></span>

<span data-ttu-id="52a82-136">在分配程序包之前查看策略包中每个策略的设置。</span><span class="sxs-lookup"><span data-stu-id="52a82-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="52a82-137">在 Microsoft 团队管理中心的左侧导航中，选择 " **策略包** "，选择程序包名称，然后选择 "策略名称"。</span><span class="sxs-lookup"><span data-stu-id="52a82-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages** , select the package name, and then select the policy name.</span></span>

<span data-ttu-id="52a82-138">确定预定义的值是否适合你的组织，或者你是否需要根据组织的需求自定义它们以使其更具限制性或 lenient。</span><span class="sxs-lookup"><span data-stu-id="52a82-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="52a82-139">自定义</span><span class="sxs-lookup"><span data-stu-id="52a82-139">Customize</span></span>

<span data-ttu-id="52a82-140">根据需要自定义策略包中的策略设置，以满足组织的需要。</span><span class="sxs-lookup"><span data-stu-id="52a82-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="52a82-141">对策略设置所做的任何更改都将自动应用到分配了该程序包的用户。</span><span class="sxs-lookup"><span data-stu-id="52a82-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="52a82-142">若要编辑策略包中的策略设置，请在 Microsoft 团队管理中心中，选择 "策略" 程序包，选择要编辑的策略的名称，然后选择 " **编辑** "。</span><span class="sxs-lookup"><span data-stu-id="52a82-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="52a82-143">请记住，你还可以在分配策略包后更改程序包中的策略设置。</span><span class="sxs-lookup"><span data-stu-id="52a82-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="52a82-144">若要了解详细信息，请参阅 [自定义策略包中的策略](manage-policy-packages.md#customize-policies-in-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="52a82-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="52a82-145">分配</span><span class="sxs-lookup"><span data-stu-id="52a82-145">Assign</span></span>

<span data-ttu-id="52a82-146">将策略包分配给用户。</span><span class="sxs-lookup"><span data-stu-id="52a82-146">Assign the policy package to users.</span></span> <span data-ttu-id="52a82-147">如果用户分配了策略，然后你分配了其他策略，则最新作业的优先级将会更高。</span><span class="sxs-lookup"><span data-stu-id="52a82-147">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="52a82-148">将策略包分配给一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="52a82-148">Assign a policy package to one or several users</span></span>

<span data-ttu-id="52a82-149">若要向一个或多个用户分配策略包，请在 Microsoft 团队管理中心的左侧导航中，转到 " **策略程序包** "，然后选择 " **管理用户** "。</span><span class="sxs-lookup"><span data-stu-id="52a82-149">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select **Manage users**.</span></span>  

![如何在管理中心分配策略包的屏幕截图](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="52a82-151">若要了解详细信息，请参阅 [分配策略包](manage-policy-packages.md#assign-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="52a82-151">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="52a82-152">如果用户分配了策略，然后你分配了其他策略，则最新作业的优先级将会更高。</span><span class="sxs-lookup"><span data-stu-id="52a82-152">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="52a82-153">为组分配策略包</span><span class="sxs-lookup"><span data-stu-id="52a82-153">Assign a policy package to a group</span></span>

<span data-ttu-id="52a82-154">**此功能在私人预览版中**</span><span class="sxs-lookup"><span data-stu-id="52a82-154">**This feature is in private preview**</span></span>

<span data-ttu-id="52a82-155">通过将策略包分配给组，你可以将多个策略分配给一组用户，如安全组或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="52a82-155">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="52a82-156">根据优先级规则，策略分配将传播到组的成员。</span><span class="sxs-lookup"><span data-stu-id="52a82-156">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="52a82-157">将成员添加到组或从组中删除成员后，将相应地更新其继承的策略分配。</span><span class="sxs-lookup"><span data-stu-id="52a82-157">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="52a82-158">对于多达50000用户的组，建议使用此方法，但也可使用较大的组。</span><span class="sxs-lookup"><span data-stu-id="52a82-158">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="52a82-159">若要了解详细信息，请参阅向 [组分配策略包](assign-policies.md#assign-a-policy-package-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="52a82-159">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="52a82-160">将策略包分配给大型集 (批处理) 用户</span><span class="sxs-lookup"><span data-stu-id="52a82-160">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="52a82-161">使用批处理策略程序包分配来一次为大型用户分配一个策略包。</span><span class="sxs-lookup"><span data-stu-id="52a82-161">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="52a82-162">使用 [CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet 提交要分配的一批用户和策略包。</span><span class="sxs-lookup"><span data-stu-id="52a82-162">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="52a82-163">作业作为后台操作处理，并为每个批处理生成操作 ID。</span><span class="sxs-lookup"><span data-stu-id="52a82-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="52a82-164">批处理最多可包含5000个用户。</span><span class="sxs-lookup"><span data-stu-id="52a82-164">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="52a82-165">你可以按对象 Id、UPN、SIP 地址或电子邮件地址指定用户。</span><span class="sxs-lookup"><span data-stu-id="52a82-165">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="52a82-166">若要了解详细信息，请参阅向 [一批用户分配策略包](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="52a82-166">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="52a82-167">相关主题</span><span class="sxs-lookup"><span data-stu-id="52a82-167">Related topics</span></span>

[<span data-ttu-id="52a82-168">在 Teams 中管理策略包</span><span class="sxs-lookup"><span data-stu-id="52a82-168">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="52a82-169">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="52a82-169">Assign policies to your users in Teams</span></span>](assign-policies.md) 
