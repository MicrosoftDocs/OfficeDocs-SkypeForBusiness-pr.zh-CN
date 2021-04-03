---
title: 将策略包分配给用户和组
author: KarliStites
ms.author: kastites
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解在 Microsoft Teams 中向用户和组分配策略包的不同方法。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 0266cb5c34a13df0dac62be2258134e553a357d8
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574292"
---
# <a name="assign-policy-packages-to-users-and-groups"></a><span data-ttu-id="02699-103">将策略包分配给用户和组</span><span class="sxs-lookup"><span data-stu-id="02699-103">Assign policy packages to users and groups</span></span>

<span data-ttu-id="02699-104">本文介绍在 Microsoft Teams 中向用户和组分配策略包的不同方法。</span><span class="sxs-lookup"><span data-stu-id="02699-104">This article reviews the different ways to assign policy packages to users and groups in Microsoft Teams.</span></span> <span data-ttu-id="02699-105">阅读之前，请确保已阅读 Teams [中的分配](policy-assignment-overview.md)策略 - 入门。</span><span class="sxs-lookup"><span data-stu-id="02699-105">Before reading, be sure you've read [Assign policies in Teams - getting started](policy-assignment-overview.md).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="02699-106">向用户分配策略包</span><span class="sxs-lookup"><span data-stu-id="02699-106">Assign a policy package to users</span></span>

<span data-ttu-id="02699-107">Teams 中的策略包是预定义的策略和策略设置的集合，可将其分配给组织中具有相同或类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="02699-107">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="02699-108">每个策略包围绕用户角色设计，包括预定义的策略和策略设置，这些策略设置支持该角色的典型活动。</span><span class="sxs-lookup"><span data-stu-id="02699-108">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="02699-109">策略包的一些示例包括教育 (教师) 包和医疗保健 (医疗) 包。</span><span class="sxs-lookup"><span data-stu-id="02699-109">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="02699-110">有关详细信息，请参阅在 [Teams 中管理策略包](manage-policy-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="02699-110">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="02699-111">将策略包分配给一个用户</span><span class="sxs-lookup"><span data-stu-id="02699-111">Assign a policy package to one user</span></span>

1. <span data-ttu-id="02699-112">在 Microsoft Teams 管理中心的左侧导航栏中，转到" **用户"，** 然后选择该用户。</span><span class="sxs-lookup"><span data-stu-id="02699-112">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="02699-113">在用户的页面上，选择"策略 **"，** 然后在"策略包"**旁边** 选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="02699-113">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="02699-114">在"**分配策略包"** 窗格中，选择要分配的包，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="02699-114">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

![向用户分配策略包的 Teams 管理中心屏幕截图](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="02699-116">将策略包分配给多个用户</span><span class="sxs-lookup"><span data-stu-id="02699-116">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="02699-117">在 Microsoft Teams 管理中心的左侧导航中，转到"策略包"，然后单击程序包名称左侧，选择要分配的策略包。</span><span class="sxs-lookup"><span data-stu-id="02699-117">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="02699-118">选择“管理用户”。</span><span class="sxs-lookup"><span data-stu-id="02699-118">Select **Manage users**.</span></span>
3. <span data-ttu-id="02699-119">在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="02699-119">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="02699-120">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="02699-120">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="02699-121">添加完用户后，选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="02699-121">When you're finished adding users, select **Save**.</span></span>

![针对多个用户分配策略包的 Teams 管理中心屏幕截图](media/assign-policypackages-multipleusers.png)

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="02699-123">将策略包分配给组。</span><span class="sxs-lookup"><span data-stu-id="02699-123">Assign a policy package to a group</span></span>

<span data-ttu-id="02699-124">通过将策略包分配到组，可将多个策略分配给一组用户，例如安全组或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="02699-124">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="02699-125">根据优先级规则，将策略分配传播到组中的成员。</span><span class="sxs-lookup"><span data-stu-id="02699-125">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="02699-126">将成员添加到组或从组中删除成员时，将相应更新其继承的策略分配。</span><span class="sxs-lookup"><span data-stu-id="02699-126">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="02699-127">建议最多包含 50，000 个用户组将策略包分配到组，但它也将适用于较大的组。</span><span class="sxs-lookup"><span data-stu-id="02699-127">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="02699-128">分配策略包时，会立即将其分配给组。</span><span class="sxs-lookup"><span data-stu-id="02699-128">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="02699-129">但是，将策略分配传播到组的成员以后台操作方式执行，可能需要一些时间，具体取决于组的大小。</span><span class="sxs-lookup"><span data-stu-id="02699-129">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="02699-130">从组取消分配策略时，或者将成员添加到组或从组中删除成员时，也是如此。</span><span class="sxs-lookup"><span data-stu-id="02699-130">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02699-131">在开始使用之前，必须了解 (规则)  ([组分配) 。](assign-policies-users-and-groups.md#group-assignment-ranking) [](assign-policies-users-and-groups.md#precedence-rules)</span><span class="sxs-lookup"><span data-stu-id="02699-131">Before you get started, it's important to understand ([precedence rules](assign-policies-users-and-groups.md#precedence-rules)) and ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)).</span></span> <span data-ttu-id="02699-132">请务必阅读并了解本文前面 (组的策略分配) 了解哪些信息[](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)。</span><span class="sxs-lookup"><span data-stu-id="02699-132">Make sure you read and understand the concepts in ([What you need to know about policy assignment to groups](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="02699-133">将策略包分配给管理中心中的一组用户</span><span class="sxs-lookup"><span data-stu-id="02699-133">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="02699-134">登录到 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="02699-134">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="02699-135">在左侧导航栏中，转到策略包页。</span><span class="sxs-lookup"><span data-stu-id="02699-135">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="02699-136">选择"组策略分配"选项卡。</span><span class="sxs-lookup"><span data-stu-id="02699-136">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="02699-137">选择 **"添加组**"，然后在"将策略包分配到组"窗格中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="02699-137">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="02699-138">a.</span><span class="sxs-lookup"><span data-stu-id="02699-138">a.</span></span> <span data-ttu-id="02699-139">搜索并添加要为其分配策略包的组。</span><span class="sxs-lookup"><span data-stu-id="02699-139">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="02699-140">b.</span><span class="sxs-lookup"><span data-stu-id="02699-140">b.</span></span> <span data-ttu-id="02699-141">选择策略包。</span><span class="sxs-lookup"><span data-stu-id="02699-141">Select a policy package.</span></span>

    <span data-ttu-id="02699-142">c.</span><span class="sxs-lookup"><span data-stu-id="02699-142">c.</span></span> <span data-ttu-id="02699-143">设置每个策略类型的排名。</span><span class="sxs-lookup"><span data-stu-id="02699-143">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="02699-144">d.</span><span class="sxs-lookup"><span data-stu-id="02699-144">d.</span></span> <span data-ttu-id="02699-145">选择"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="02699-145">Select **Apply**.</span></span>

![显示组策略分配](media/group-pkg-assignment.png)

5. <span data-ttu-id="02699-147">若要管理特定策略类型的排名，请导航到特定策略页。</span><span class="sxs-lookup"><span data-stu-id="02699-147">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="02699-148">若要将策略包重新分配到组，请首先删除组策略分配。</span><span class="sxs-lookup"><span data-stu-id="02699-148">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="02699-149">然后，按照上述步骤将策略包分配到组。</span><span class="sxs-lookup"><span data-stu-id="02699-149">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="02699-150">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="02699-150">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="02699-151">获取 Teams PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="02699-151">Get the Teams PowerShell module</span></span>

<span data-ttu-id="02699-152">有关分步指南，请参阅[安装 Teams PowerShell。](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="02699-152">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="02699-153">将策略包分配给一组用户</span><span class="sxs-lookup"><span data-stu-id="02699-153">Assign a policy package to a group of users</span></span>

<span data-ttu-id="02699-154">使用 [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet 将策略包分配给组。</span><span class="sxs-lookup"><span data-stu-id="02699-154">Use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="02699-155">可以使用对象 ID、SIP 地址或电子邮件地址指定组。</span><span class="sxs-lookup"><span data-stu-id="02699-155">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="02699-156">分配策略包时，请 ([策略包) ](assign-policies-users-and-groups.md#group-assignment-ranking) 策略类型的组分配排名。</span><span class="sxs-lookup"><span data-stu-id="02699-156">When you assign the policy package, specify a ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)) for each policy type in the policy package.</span></span>

<span data-ttu-id="02699-157">本示例将 Education_Teacher 策略包分配给一个组，TeamsAppSetupPolicy 和 TeamsMeetingBroadcastPolicy 的分配排名为 1，TeamsMeetingPolicy 的排名为 2。</span><span class="sxs-lookup"><span data-stu-id="02699-157">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="02699-158">将策略包分配给一批用户</span><span class="sxs-lookup"><span data-stu-id="02699-158">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="02699-159">使用批处理策略包分配，可以一次将策略包分配给大量用户，而无需使用脚本。</span><span class="sxs-lookup"><span data-stu-id="02699-159">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="02699-160">使用 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 提交一批用户和要分配的策略包。</span><span class="sxs-lookup"><span data-stu-id="02699-160">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="02699-161">作业将作为后台操作处理，并为每个批处理生成操作 ID。</span><span class="sxs-lookup"><span data-stu-id="02699-161">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="02699-162">然后，可以使用 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet 跟踪批处理中分配的进度和状态。</span><span class="sxs-lookup"><span data-stu-id="02699-162">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="02699-163">根据用户的对象 ID 或会话启动协议 (SIP) 地址。</span><span class="sxs-lookup"><span data-stu-id="02699-163">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="02699-164">用户的 SIP 地址通常与 UPN (或电子邮件地址 (用户名) 相同，但这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="02699-164">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="02699-165">如果用户是使用其 UPN 或电子邮件指定的，但其值不同于其 SIP 地址，则策略分配将失败。</span><span class="sxs-lookup"><span data-stu-id="02699-165">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="02699-166">如果批处理包含重复用户，则在处理之前将从批处理中删除重复项，并且只会为批中剩余的唯一用户提供状态。</span><span class="sxs-lookup"><span data-stu-id="02699-166">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="02699-167">一个批最多包含 5，000 个用户。</span><span class="sxs-lookup"><span data-stu-id="02699-167">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="02699-168">为获得最佳结果，不要一次提交多个批次。</span><span class="sxs-lookup"><span data-stu-id="02699-168">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="02699-169">允许批处理在提交更多批之前完成处理。</span><span class="sxs-lookup"><span data-stu-id="02699-169">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="02699-170">使用 Teams PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="02699-170">Use the Teams PowerShell module</span></span>

<span data-ttu-id="02699-171">如果尚未安装 Microsoft [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (，请运行以下) 。</span><span class="sxs-lookup"><span data-stu-id="02699-171">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="02699-172">请确保安装版本 1.0.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="02699-172">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="02699-173">运行以下代码以连接到 Teams 并启动会话。</span><span class="sxs-lookup"><span data-stu-id="02699-173">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="02699-174">系统提示时，使用管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="02699-174">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="02699-175">将策略包分配给一批用户</span><span class="sxs-lookup"><span data-stu-id="02699-175">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="02699-176">本示例使用 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 将 Education_PrimaryStudent 策略包分配给一批用户。</span><span class="sxs-lookup"><span data-stu-id="02699-176">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="02699-177">查看批处理分配的状态</span><span class="sxs-lookup"><span data-stu-id="02699-177">See the status of a batch assignment</span></span>

<span data-ttu-id="02699-178">运行以下代码获取批处理分配的状态，其中 OperationId 是 cmdlet 为给定批返回的操作 ```New-CsBatchPolicyAssignmentOperation``` ID。</span><span class="sxs-lookup"><span data-stu-id="02699-178">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="02699-179">如果输出显示发生错误，请运行以下命令，获取有关 属性中的错误 ```UserState``` 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="02699-179">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="02699-180">有关详细信息，请参阅[Get-CsBatchPolicyAssignmentOperation。](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="02699-180">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="02699-181">相关主题</span><span class="sxs-lookup"><span data-stu-id="02699-181">Related topics</span></span>

- [<span data-ttu-id="02699-182">使用策略管理 Teams</span><span class="sxs-lookup"><span data-stu-id="02699-182">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="02699-183">在 Microsoft Teams 中管理策略包</span><span class="sxs-lookup"><span data-stu-id="02699-183">Manage policy packages in Microsoft Teams</span></span>](manage-policy-packages.md)
- [<span data-ttu-id="02699-184">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="02699-184">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="02699-185">在 Teams 中分配策略 - 入门</span><span class="sxs-lookup"><span data-stu-id="02699-185">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)