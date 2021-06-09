---
title: Teams政府部署策略包
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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理Teams组织的策略包。
ms.openlocfilehash: 41ae937323b37948c03128efd565f40c02bbd6a2
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796866"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="0c013-103">Teams政府部署策略包</span><span class="sxs-lookup"><span data-stu-id="0c013-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="0c013-104">目前，在政府高级部署Microsoft 365 DoD GCC策略包不可用。</span><span class="sxs-lookup"><span data-stu-id="0c013-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="0c013-105">概述</span><span class="sxs-lookup"><span data-stu-id="0c013-105">Overview</span></span>

<span data-ttu-id="0c013-106">Microsoft Teams 中的[策略包](manage-policy-packages.md)是一组预定义的策略和策略设置，你可以将其分配给组织中具有类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="0c013-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="0c013-107">策略包可简化并有助于提供一致的策略管理。</span><span class="sxs-lookup"><span data-stu-id="0c013-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="0c013-108">你可以自定义包中策略的设置以满足用户的需求。</span><span class="sxs-lookup"><span data-stu-id="0c013-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="0c013-109">当你更改策略包中策略的设置时，分配了该包的所有用户均会获得更新后的设置。</span><span class="sxs-lookup"><span data-stu-id="0c013-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="0c013-110">你可以使用 Microsoft Teams 管理中心或 PowerShell 管理策略包。</span><span class="sxs-lookup"><span data-stu-id="0c013-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="0c013-111">策略包针对以下各项预定义了策略，具体内容因策略包而异：</span><span class="sxs-lookup"><span data-stu-id="0c013-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="0c013-112">消息传递</span><span class="sxs-lookup"><span data-stu-id="0c013-112">Messaging</span></span>
- <span data-ttu-id="0c013-113">会议</span><span class="sxs-lookup"><span data-stu-id="0c013-113">Meetings</span></span>
- <span data-ttu-id="0c013-114">通话</span><span class="sxs-lookup"><span data-stu-id="0c013-114">Calling</span></span>
- <span data-ttu-id="0c013-115">应用设置</span><span class="sxs-lookup"><span data-stu-id="0c013-115">App setup</span></span>
- <span data-ttu-id="0c013-116">实时事件</span><span class="sxs-lookup"><span data-stu-id="0c013-116">Live events</span></span>

<span data-ttu-id="0c013-117">Teams包括以下政府策略包。</span><span class="sxs-lookup"><span data-stu-id="0c013-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="0c013-118">Microsoft Teams 管理中心中的策略包名称</span><span class="sxs-lookup"><span data-stu-id="0c013-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="0c013-119">最适合用于</span><span class="sxs-lookup"><span data-stu-id="0c013-119">Best used for</span></span>|<span data-ttu-id="0c013-120">说明</span><span class="sxs-lookup"><span data-stu-id="0c013-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="0c013-121">公共安全人员</span><span class="sxs-lookup"><span data-stu-id="0c013-121">Public safety officer</span></span>  |<span data-ttu-id="0c013-122">政府组织的公共安全人员</span><span class="sxs-lookup"><span data-stu-id="0c013-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="0c013-123">创建一组适用于组织中公共安全人员的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="0c013-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="0c013-124">前端管理器</span><span class="sxs-lookup"><span data-stu-id="0c013-124">Frontline manager</span></span>  |<span data-ttu-id="0c013-125">政府组织的一线经理</span><span class="sxs-lookup"><span data-stu-id="0c013-125">Frontline Managers in your government organization</span></span> |<span data-ttu-id="0c013-126">创建一组策略，将这些设置应用到组织的一线经理。</span><span class="sxs-lookup"><span data-stu-id="0c013-126">Creates a set of policies and applies those settings to Frontline Managers in your organization.</span></span>|
|<span data-ttu-id="0c013-127">一线辅助角色</span><span class="sxs-lookup"><span data-stu-id="0c013-127">Frontline worker</span></span>  |<span data-ttu-id="0c013-128">政府组织的一线员工</span><span class="sxs-lookup"><span data-stu-id="0c013-128">Frontline Workers in your government organization</span></span> |<span data-ttu-id="0c013-129">创建一组策略，将这些设置应用到组织的一线员工。</span><span class="sxs-lookup"><span data-stu-id="0c013-129">Creates a set of policies and applies those settings to Frontline Workers in your organization.</span></span>|

![医疗保健策略包的屏幕截图](media/policy-packages-gov.png)

<span data-ttu-id="0c013-131">将为每个单独的策略提供策略包的名称，以便你可以轻松识别链接到该策略包的策略。</span><span class="sxs-lookup"><span data-stu-id="0c013-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="0c013-132">例如，将"公共安全人员"策略包分配给组织中用户时，PublicSafety_Officer包中每个策略创建名为 PublicSafety_Officer 的策略。</span><span class="sxs-lookup"><span data-stu-id="0c013-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![医疗保健临床工作者策略包中策略的屏幕截图](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="0c013-134">管理策略包</span><span class="sxs-lookup"><span data-stu-id="0c013-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="0c013-135">查看</span><span class="sxs-lookup"><span data-stu-id="0c013-135">View</span></span>

<span data-ttu-id="0c013-136">在分配包前查看策略包中每个策略的设置。</span><span class="sxs-lookup"><span data-stu-id="0c013-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="0c013-137">在 Microsoft Teams 管理中心的左侧导航栏中，依次选择 **策略包**、程序包名称，然后选择策略名称。</span><span class="sxs-lookup"><span data-stu-id="0c013-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="0c013-138">确定预定义值是否适合你的组织，或是否需要根据组织的需求对其进行自定义，使其更具限制性或更宽松。</span><span class="sxs-lookup"><span data-stu-id="0c013-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="0c013-139">自定义</span><span class="sxs-lookup"><span data-stu-id="0c013-139">Customize</span></span>

<span data-ttu-id="0c013-140">根据需要自定义策略包中的策略设置，满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="0c013-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="0c013-141">对策略设置所做的任何更改都将自动应用到已分配了该包的用户。</span><span class="sxs-lookup"><span data-stu-id="0c013-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="0c013-142">若要编辑策略包中的策略设置，请在 Microsoft Teams 管理中心中，依次选择策略包、要编辑的策略的名称，然后选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="0c013-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="0c013-143">请记住，在分配策略包之后，你还可以更改包中的策略设置。</span><span class="sxs-lookup"><span data-stu-id="0c013-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="0c013-144">若要了解详细信息，请参阅[自定义策略包](manage-policy-packages.md#customize-policies-in-a-policy-package)中的策略。</span><span class="sxs-lookup"><span data-stu-id="0c013-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="0c013-145">分配</span><span class="sxs-lookup"><span data-stu-id="0c013-145">Assign</span></span>

<span data-ttu-id="0c013-p106">将策略包分配给用户。如果用户已分配策略，稍后又分配了另一个策略，则最近分配的优先级将会更高。</span><span class="sxs-lookup"><span data-stu-id="0c013-p106">Assign the policy package to users. If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

> [!NOTE]
> <span data-ttu-id="0c013-148">每个用户都需要高级通信加载项才能接收自定义策略包分配。</span><span class="sxs-lookup"><span data-stu-id="0c013-148">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="0c013-149">有关详细信息，请参阅适用于 Microsoft Teams[的高级通信Microsoft Teams。](/microsoftteams/teams-add-on-licensing/advanced-communications)</span><span class="sxs-lookup"><span data-stu-id="0c013-149">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="0c013-150">向一个或多个用户分配策略包</span><span class="sxs-lookup"><span data-stu-id="0c013-150">Assign a policy package to one or several users</span></span>

<span data-ttu-id="0c013-151">若要将策略包分配给一个或多个用户，请在 Microsoft Teams 管理中心的左侧导航中，转到 **策略包**，然后选择 **管理用户**。</span><span class="sxs-lookup"><span data-stu-id="0c013-151">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![有关如何在管理中心分配策略包的屏幕截图](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="0c013-153">若要了解详细信息，请参阅[分配策略包](manage-policy-packages.md#assign-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="0c013-153">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="0c013-154">如果用户已分配策略，稍后又分配了另一个策略，则最近分配的优先级将会更高。</span><span class="sxs-lookup"><span data-stu-id="0c013-154">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="0c013-155">将策略包分配给组。</span><span class="sxs-lookup"><span data-stu-id="0c013-155">Assign a policy package to a group</span></span>

<span data-ttu-id="0c013-156">**此功能在私有预览版中**</span><span class="sxs-lookup"><span data-stu-id="0c013-156">**This feature is in private preview**</span></span>

<span data-ttu-id="0c013-157">通过将策略包分配到组，可将多个策略分配给一组用户，例如安全组或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="0c013-157">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="0c013-158">根据优先级规则，将策略分配传播到组中的成员。</span><span class="sxs-lookup"><span data-stu-id="0c013-158">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="0c013-159">将成员添加到组或从组中删除成员时，将相应更新其继承的策略分配。</span><span class="sxs-lookup"><span data-stu-id="0c013-159">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="0c013-160">建议将此方法用于最多 50,000 个用户的组，但也可使用更大的组。</span><span class="sxs-lookup"><span data-stu-id="0c013-160">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="0c013-161">若要了解详细信息，请参阅[将策略包分配到组](assign-policies.md#assign-a-policy-package-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="0c013-161">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="0c013-162">向大型组（批处理）分配策略包</span><span class="sxs-lookup"><span data-stu-id="0c013-162">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="0c013-163">使用批处理策略包分配，每次向大型用户组分配策略包。</span><span class="sxs-lookup"><span data-stu-id="0c013-163">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="0c013-164">使用 [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet 提交要分配的一批用户和策略包。</span><span class="sxs-lookup"><span data-stu-id="0c013-164">You use the [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="0c013-165">作业将作为后台操作处理，并为每个批处理生成操作 ID。</span><span class="sxs-lookup"><span data-stu-id="0c013-165">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="0c013-166">批处理最多可包含 5,000 个用户。</span><span class="sxs-lookup"><span data-stu-id="0c013-166">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="0c013-167">可通过对象 Id、UPN、SIP 地址或电子邮件地址指定用户。</span><span class="sxs-lookup"><span data-stu-id="0c013-167">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="0c013-168">若要了解详细信息，请参阅[将策略包分配给批次用户](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="0c013-168">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0c013-169">相关主题</span><span class="sxs-lookup"><span data-stu-id="0c013-169">Related topics</span></span>

[<span data-ttu-id="0c013-170">在 Teams 中管理策略包</span><span class="sxs-lookup"><span data-stu-id="0c013-170">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="0c013-171">将策略包分配给用户和组</span><span class="sxs-lookup"><span data-stu-id="0c013-171">Assign policy packages to users and groups</span></span>](assign-policy-packages.md)
