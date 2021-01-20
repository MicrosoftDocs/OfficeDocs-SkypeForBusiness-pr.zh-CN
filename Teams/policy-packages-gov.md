---
title: 适用于政府的 Teams 策略包
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
description: 了解如何为政府组织使用和管理 Teams 策略包。
ms.openlocfilehash: 2841fbf523f49c5784045cc6cf960e846b45aa9b
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909076"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="8877c-103">适用于政府的 Teams 策略包</span><span class="sxs-lookup"><span data-stu-id="8877c-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="8877c-104">Microsoft 365 政府版 GCC High 或 DoD 部署中当前未提供策略包。</span><span class="sxs-lookup"><span data-stu-id="8877c-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="8877c-105">概述</span><span class="sxs-lookup"><span data-stu-id="8877c-105">Overview</span></span>

<span data-ttu-id="8877c-106">Microsoft Teams [中的](manage-policy-packages.md) 策略包是预定义的策略和策略设置的集合，可将其分配给组织中具有类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="8877c-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="8877c-107">策略包可简化并有助于提供一致的策略管理。</span><span class="sxs-lookup"><span data-stu-id="8877c-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="8877c-108">可以自定义程序包中策略的设置以满足用户的需求。</span><span class="sxs-lookup"><span data-stu-id="8877c-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="8877c-109">更改策略包中的策略设置时，分配到该包的所有用户将获取更新的设置。</span><span class="sxs-lookup"><span data-stu-id="8877c-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="8877c-110">可以使用 Microsoft Teams 管理中心或 PowerShell 管理策略包。</span><span class="sxs-lookup"><span data-stu-id="8877c-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="8877c-111">策略包根据包为以下内容预定义策略：</span><span class="sxs-lookup"><span data-stu-id="8877c-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="8877c-112">消息传递</span><span class="sxs-lookup"><span data-stu-id="8877c-112">Messaging</span></span>
- <span data-ttu-id="8877c-113">会议</span><span class="sxs-lookup"><span data-stu-id="8877c-113">Meetings</span></span>
- <span data-ttu-id="8877c-114">通话</span><span class="sxs-lookup"><span data-stu-id="8877c-114">Calling</span></span>
- <span data-ttu-id="8877c-115">应用设置</span><span class="sxs-lookup"><span data-stu-id="8877c-115">App setup</span></span>
- <span data-ttu-id="8877c-116">实时事件</span><span class="sxs-lookup"><span data-stu-id="8877c-116">Live events</span></span>

<span data-ttu-id="8877c-117">Teams 当前包括以下适用于政府的策略包。</span><span class="sxs-lookup"><span data-stu-id="8877c-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="8877c-118">Microsoft Teams 管理中心中的程序包名称</span><span class="sxs-lookup"><span data-stu-id="8877c-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="8877c-119">最适合用于</span><span class="sxs-lookup"><span data-stu-id="8877c-119">Best used for</span></span>|<span data-ttu-id="8877c-120">说明</span><span class="sxs-lookup"><span data-stu-id="8877c-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="8877c-121">公共安全主管</span><span class="sxs-lookup"><span data-stu-id="8877c-121">Public safety officer</span></span>  |<span data-ttu-id="8877c-122">政府组织的公共安全人员</span><span class="sxs-lookup"><span data-stu-id="8877c-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="8877c-123">创建一组适用于组织中公共安全人员的策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="8877c-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="8877c-124">前端管理器</span><span class="sxs-lookup"><span data-stu-id="8877c-124">Frontline manager</span></span>  |<span data-ttu-id="8877c-125">政府组织的一线经理</span><span class="sxs-lookup"><span data-stu-id="8877c-125">Frontline Managers in your government organization</span></span> |<span data-ttu-id="8877c-126">创建一组策略，将这些设置应用到组织的一线经理。</span><span class="sxs-lookup"><span data-stu-id="8877c-126">Creates a set of policies and applies those settings to Frontline Managers in your organization.</span></span>|
|<span data-ttu-id="8877c-127">一线辅助角色</span><span class="sxs-lookup"><span data-stu-id="8877c-127">Frontline worker</span></span>  |<span data-ttu-id="8877c-128">政府组织的一线员工</span><span class="sxs-lookup"><span data-stu-id="8877c-128">Frontline Workers in your government organization</span></span> |<span data-ttu-id="8877c-129">创建一组策略，将这些设置应用到组织的一线员工。</span><span class="sxs-lookup"><span data-stu-id="8877c-129">Creates a set of policies and applies those settings to Frontline Workers in your organization.</span></span>|

![医疗保健策略包的屏幕截图](media/policy-packages-gov.png)

<span data-ttu-id="8877c-131">每个策略都有策略包的名称，因此可以轻松识别链接到策略包的策略。</span><span class="sxs-lookup"><span data-stu-id="8877c-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="8877c-132">例如，将公共安全主管策略包分配给组织中用户时，会PublicSafety_Officer包中每个策略创建名为 PublicSafety_Officer 的策略。</span><span class="sxs-lookup"><span data-stu-id="8877c-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![医疗保健患者包中策略的屏幕截图](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="8877c-134">管理策略包</span><span class="sxs-lookup"><span data-stu-id="8877c-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="8877c-135">查看</span><span class="sxs-lookup"><span data-stu-id="8877c-135">View</span></span>

<span data-ttu-id="8877c-136">在分配包前查看策略包中每个策略的设置。</span><span class="sxs-lookup"><span data-stu-id="8877c-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="8877c-137">在 Microsoft Teams 管理中心的左侧导航栏中，依次选择 **策略包**、程序包名称，然后选择策略名称。</span><span class="sxs-lookup"><span data-stu-id="8877c-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="8877c-138">确定预定义值是否适合你的组织，或是否需要根据组织的需求对其进行自定义，使其更具限制性或更宽松。</span><span class="sxs-lookup"><span data-stu-id="8877c-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="8877c-139">自定义</span><span class="sxs-lookup"><span data-stu-id="8877c-139">Customize</span></span>

<span data-ttu-id="8877c-140">根据需要自定义策略包中的策略设置，满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="8877c-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="8877c-141">对策略设置所做的任何更改都将自动应用到已分配了该包的用户。</span><span class="sxs-lookup"><span data-stu-id="8877c-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="8877c-142">若要编辑策略包中的策略设置，请在 Microsoft Teams 管理中心中，依次选择策略包、要编辑的策略的名称，然后选择 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="8877c-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="8877c-143">请记住，在分配策略包之后，你还可以更改包中的策略设置。</span><span class="sxs-lookup"><span data-stu-id="8877c-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="8877c-144">若要了解详细信息，请参阅[自定义策略包](manage-policy-packages.md#customize-policies-in-a-policy-package)中的策略。</span><span class="sxs-lookup"><span data-stu-id="8877c-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="8877c-145">分配</span><span class="sxs-lookup"><span data-stu-id="8877c-145">Assign</span></span>

<span data-ttu-id="8877c-146">将策略包分配给用户。</span><span class="sxs-lookup"><span data-stu-id="8877c-146">Assign the policy package to users.</span></span> <span data-ttu-id="8877c-147">如果用户已分配策略，稍后又分配了另一个策略，则最近分配的优先级将会更高。</span><span class="sxs-lookup"><span data-stu-id="8877c-147">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="8877c-148">向一个或多个用户分配策略包</span><span class="sxs-lookup"><span data-stu-id="8877c-148">Assign a policy package to one or several users</span></span>

<span data-ttu-id="8877c-149">若要将策略包分配给一个或多个用户，请在 Microsoft Teams 管理中心的左侧导航中，转到 **策略包**，然后选择 **管理用户**。</span><span class="sxs-lookup"><span data-stu-id="8877c-149">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![有关如何在管理中心分配策略包的屏幕截图](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="8877c-151">若要了解详细信息，请参阅[分配策略包](manage-policy-packages.md#assign-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="8877c-151">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="8877c-152">如果用户已分配策略，稍后又分配了另一个策略，则最近分配的优先级将会更高。</span><span class="sxs-lookup"><span data-stu-id="8877c-152">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="8877c-153">将策略包分配给组。</span><span class="sxs-lookup"><span data-stu-id="8877c-153">Assign a policy package to a group</span></span>

<span data-ttu-id="8877c-154">**此功能在私有预览版中**</span><span class="sxs-lookup"><span data-stu-id="8877c-154">**This feature is in private preview**</span></span>

<span data-ttu-id="8877c-155">通过将策略包分配到组，可将多个策略分配给一组用户，例如安全组或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="8877c-155">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="8877c-156">根据优先级规则，将策略分配传播到组中的成员。</span><span class="sxs-lookup"><span data-stu-id="8877c-156">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="8877c-157">将成员添加到组或从组中删除成员时，将相应更新其继承的策略分配。</span><span class="sxs-lookup"><span data-stu-id="8877c-157">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="8877c-158">建议将此方法用于最多 50,000 个用户的组，但也可使用更大的组。</span><span class="sxs-lookup"><span data-stu-id="8877c-158">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="8877c-159">若要了解详细信息，请参阅[将策略包分配到组](assign-policies.md#assign-a-policy-package-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="8877c-159">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="8877c-160">向大型组（批处理）分配策略包</span><span class="sxs-lookup"><span data-stu-id="8877c-160">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="8877c-161">使用批处理策略包分配，每次向大型用户组分配策略包。</span><span class="sxs-lookup"><span data-stu-id="8877c-161">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="8877c-162">使用 [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet 提交要分配的一批用户和策略包。</span><span class="sxs-lookup"><span data-stu-id="8877c-162">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="8877c-163">作业将作为后台操作处理，并为每个批处理生成操作 ID。</span><span class="sxs-lookup"><span data-stu-id="8877c-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="8877c-164">批处理最多可包含 5,000 个用户。</span><span class="sxs-lookup"><span data-stu-id="8877c-164">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="8877c-165">可通过对象 Id、UPN、SIP 地址或电子邮件地址指定用户。</span><span class="sxs-lookup"><span data-stu-id="8877c-165">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="8877c-166">若要了解详细信息，请参阅[将策略包分配给批次用户](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="8877c-166">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8877c-167">相关主题</span><span class="sxs-lookup"><span data-stu-id="8877c-167">Related topics</span></span>

[<span data-ttu-id="8877c-168">在 Teams 中管理策略包</span><span class="sxs-lookup"><span data-stu-id="8877c-168">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="8877c-169">在 Teams 中向用户分配策略</span><span class="sxs-lookup"><span data-stu-id="8877c-169">Assign policies to your users in Teams</span></span>](assign-policies.md) 
