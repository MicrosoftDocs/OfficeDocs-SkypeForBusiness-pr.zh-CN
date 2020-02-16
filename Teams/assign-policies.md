---
title: 向 Microsoft 团队中的用户分配策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag
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
description: 了解在 Microsoft 团队中向用户分配策略的不同方法。
f1keywords: ''
ms.openlocfilehash: a4d50f6182441e97f5d7290610e254bd82e91e96
ms.sourcegitcommit: c8d16d5e61d66d7b5e7391a800978b920612ea4d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42052534"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="992ab-103">向 Microsoft 团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="992ab-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="992ab-104">**本文中讨论的两个 Microsoft 团队功能（[批量策略分配](#assign-a-policy-to-a-batch-of-users)和[组策略分配](#assign-a-policy-to-a-group)）当前处于预览版中。**</span><span class="sxs-lookup"><span data-stu-id="992ab-104">**Two of the Microsoft Teams features discussed in this article, [batch policy assignment](#assign-a-policy-to-a-batch-of-users) and [group policy assignment](#assign-a-policy-to-a-group), are currently in preview.**</span></span>

<span data-ttu-id="992ab-105">作为管理员，你可以使用策略来控制你的组织中的用户可以使用的团队功能。</span><span class="sxs-lookup"><span data-stu-id="992ab-105">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="992ab-106">例如，有一些通话策略、会议策略和邮件策略，只需命名。</span><span class="sxs-lookup"><span data-stu-id="992ab-106">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="992ab-107">组织具有不同类型的具有独特需求的用户和你创建和分配的自定义策略，让你可以根据这些需求将策略设置自定义给不同的用户集。</span><span class="sxs-lookup"><span data-stu-id="992ab-107">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="992ab-108">为了便于管理组织中的策略，团队提供了多种方法来为用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-108">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="992ab-109">你可以将策略直接分配给用户，无论是单独的还是通过批处理作业进行缩放，或是用户所属的组。</span><span class="sxs-lookup"><span data-stu-id="992ab-109">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the user is a member of.</span></span> <span data-ttu-id="992ab-110">你还可以使用策略程序包向组织中具有类似角色的用户分配策略的预设集合。</span><span class="sxs-lookup"><span data-stu-id="992ab-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="992ab-111">你选择的选项取决于你正在管理的策略的数量以及你要分配到的用户数。</span><span class="sxs-lookup"><span data-stu-id="992ab-111">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span>

<span data-ttu-id="992ab-112">本文介绍为用户分配策略的不同方法以及用于何时使用的建议方案。</span><span class="sxs-lookup"><span data-stu-id="992ab-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="992ab-113">哪种策略优先？</span><span class="sxs-lookup"><span data-stu-id="992ab-113">Which policy takes precedence?</span></span>

<span data-ttu-id="992ab-114">用户对每个策略类型都有一个有效策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="992ab-115">用户可以直接分配策略，也可以是分配了相同类型策略的一个或多个组的成员。</span><span class="sxs-lookup"><span data-stu-id="992ab-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="992ab-116">在这种情况下，哪些策略优先？</span><span class="sxs-lookup"><span data-stu-id="992ab-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="992ab-117">根据优先级规则确定用户的有效策略，如下所示。</span><span class="sxs-lookup"><span data-stu-id="992ab-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="992ab-118">如果用户直接分配策略（单独或通过批处理作业），则该策略优先。</span><span class="sxs-lookup"><span data-stu-id="992ab-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="992ab-119">在以下示例中，用户的有效策略是 Lincoln 方形会议策略，该策略直接分配给用户。</span><span class="sxs-lookup"><span data-stu-id="992ab-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![图表显示如何直接分配的策略优先](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="992ab-121">如果用户未直接分配给定类型的策略，则分配给用户所属组的策略优先。</span><span class="sxs-lookup"><span data-stu-id="992ab-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="992ab-122">如果用户是多个组的成员，则具有给定策略类型的最高[组分配级别](#group-assignment-ranking)的策略优先。</span><span class="sxs-lookup"><span data-stu-id="992ab-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="992ab-123">在此示例中，用户的有效策略是 Exec 团队和 HD 策略，该策略具有相对于用户所属的其他组的最高工作分配级别，并且还分配有相同策略类型的策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![图表显示了从组继承的策略优先的方式](media/assign-policies-example-group.png)

<span data-ttu-id="992ab-125">如果用户未直接分配策略或不是分配了策略的任何组的成员，则用户将获取该策略类型的全局（组织范围默认）策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="992ab-126">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="992ab-126">Here's an example.</span></span>

![显示全局策略优先级别的图表](media/assign-policies-example-global.png)

<span data-ttu-id="992ab-128">若要了解详细信息，请参阅[优先规则](#precedence-rules)。</span><span class="sxs-lookup"><span data-stu-id="992ab-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="992ab-129">分配策略的方法</span><span class="sxs-lookup"><span data-stu-id="992ab-129">Ways to assign policies</span></span>

<span data-ttu-id="992ab-130">下面概述了为用户分配策略的方法和建议的每种方案。</span><span class="sxs-lookup"><span data-stu-id="992ab-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="992ab-131">单击链接以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="992ab-131">Click the links to learn more.</span></span>

|<span data-ttu-id="992ab-132">执行此操作</span><span class="sxs-lookup"><span data-stu-id="992ab-132">Do this</span></span>  |<span data-ttu-id="992ab-133">If .。。</span><span class="sxs-lookup"><span data-stu-id="992ab-133">If...</span></span>  | <span data-ttu-id="992ab-134">使用 .。。</span><span class="sxs-lookup"><span data-stu-id="992ab-134">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="992ab-135">为单个用户分配策略</span><span class="sxs-lookup"><span data-stu-id="992ab-135">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="992ab-136">您是新的团队新手，只需将一个或几个策略分配给少数几个用户。</span><span class="sxs-lookup"><span data-stu-id="992ab-136">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="992ab-137">Skype for Business Online PowerShell 模块中的 Microsoft 团队管理中心或 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="992ab-137">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="992ab-138">分配策略包</span><span class="sxs-lookup"><span data-stu-id="992ab-138">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="992ab-139">您需要将多个策略分配给组织中具有相同或类似角色的特定用户组。</span><span class="sxs-lookup"><span data-stu-id="992ab-139">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="992ab-140">例如，将教育版（教师）策略包分配给你的学校教师，让他们能够完全访问聊天、通话和会议以及教育（次要学校学生）策略包以限制某些功能，如私人通话。</span><span class="sxs-lookup"><span data-stu-id="992ab-140">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="992ab-141">团队 PowerShell 模块中的 Microsoft 团队管理中心或 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="992ab-141">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="992ab-142">[将策略分配给一批用户](#assign-a-policy-to-a-batch-of-users)（在预览中）</span><span class="sxs-lookup"><span data-stu-id="992ab-142">[Assign a policy to a batch of users](#assign-a-policy-to-a-batch-of-users) (in preview)</span></span>   | <span data-ttu-id="992ab-143">您需要为大型用户组分配策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-143">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="992ab-144">例如，你希望一次为组织中的成百上千个用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-144">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="992ab-145">团队 PowerShell 模块中的 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="992ab-145">PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="992ab-146">为[组分配策略](#assign-a-policy-to-a-group)（在预览中）</span><span class="sxs-lookup"><span data-stu-id="992ab-146">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview)</span></span>   |<span data-ttu-id="992ab-147">您需要根据用户的组成员身份分配策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-147">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="992ab-148">例如，你想要向安全组或组织单位中的所有用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-148">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="992ab-149">团队 PowerShell 模块中的 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="992ab-149">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="992ab-150">将策略包分配给一批用户（即将推出）</span><span class="sxs-lookup"><span data-stu-id="992ab-150">Assign a policy package to a batch of users (coming soon)</span></span> |||
| <span data-ttu-id="992ab-151">将策略包分配给组（即将推出）</span><span class="sxs-lookup"><span data-stu-id="992ab-151">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="992ab-152">为单个用户分配策略</span><span class="sxs-lookup"><span data-stu-id="992ab-152">Assign a policy to individual users</span></span>

<span data-ttu-id="992ab-153">请按照以下步骤将策略分配给单个用户或一次分配给少数几个用户。</span><span class="sxs-lookup"><span data-stu-id="992ab-153">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="992ab-154">使用 Microsoft 团队管理中心</span><span class="sxs-lookup"><span data-stu-id="992ab-154">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="992ab-155">若要为用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="992ab-155">To assign a policy to a user:</span></span>

1. <span data-ttu-id="992ab-156">在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"，然后单击 "用户"。</span><span class="sxs-lookup"><span data-stu-id="992ab-156">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="992ab-157">通过单击用户名左侧的用户选择用户，然后单击 "**编辑设置**"。</span><span class="sxs-lookup"><span data-stu-id="992ab-157">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="992ab-158">选择要分配的策略，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="992ab-158">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="992ab-159">若要一次为多达20名用户分配策略，请参阅[批量编辑团队用户设置](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="992ab-159">To assign a policy to up to 20 users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="992ab-160">或者，您也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="992ab-160">Or, you can also do the following:</span></span>

1. <span data-ttu-id="992ab-161">在 Microsoft 团队管理中心的左侧导航中，转到 "策略" 页面。</span><span class="sxs-lookup"><span data-stu-id="992ab-161">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="992ab-162">通过单击策略名称的左侧，选择要分配的策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-162">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="992ab-163">选择 "**管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="992ab-163">Select **Manage users**.</span></span>
4. <span data-ttu-id="992ab-164">在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="992ab-164">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="992ab-165">对要添加的每个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="992ab-165">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="992ab-166">添加完用户后，请选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="992ab-166">When you're finished adding users, select **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="992ab-167">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="992ab-167">Using PowerShell</span></span>

<span data-ttu-id="992ab-168">每个策略类型都有自己的一组用于管理它的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="992ab-168">Each policy type has it's own set of cmdlets for managing it.</span></span> <span data-ttu-id="992ab-169">使用给定```Grant-```策略类型的 cmdlet 分配策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-169">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="992ab-170">例如，使用```Grant-CsTeamsMeetingPolicy``` cmdlet 向用户分配团队会议策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-170">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="992ab-171">这些 cmdlet 包含在 Skype for Business Online PowerShell 模块中，并记录在[skype for business cmdlet 参考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)中。</span><span class="sxs-lookup"><span data-stu-id="992ab-171">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="992ab-172">下载并安装[Skype For Business Online PowerShell 模块](https://www.microsoft.com/en-us/download/details.aspx?id=39366)（如果尚未安装），然后运行以下操作以连接到 Skype For business online 并启动会话。</span><span class="sxs-lookup"><span data-stu-id="992ab-172">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="992ab-173">在此示例中，我们将名为 "学生会议策略" 的团队会议策略分配给名为 Reda 的用户。</span><span class="sxs-lookup"><span data-stu-id="992ab-173">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="992ab-174">若要了解详细信息，请参阅[通过 PowerShell 管理策略](teams-powershell-overview.md#managing-policies-via-powershell)。</span><span class="sxs-lookup"><span data-stu-id="992ab-174">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="992ab-175">分配策略包</span><span class="sxs-lookup"><span data-stu-id="992ab-175">Assign a policy package</span></span>

<span data-ttu-id="992ab-176">团队中的策略包是预定义策略和策略设置的集合，你可以分配给在你的组织中具有相同或类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="992ab-176">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="992ab-177">每个策略程序包均围绕用户角色进行设计，其中包含支持该角色的典型活动的预定义策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="992ab-177">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="992ab-178">策略包的一些示例是教育版（教师）包和医疗保健（临床工作者）程序包。</span><span class="sxs-lookup"><span data-stu-id="992ab-178">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="992ab-179">向用户分配策略包时，将创建程序包中的策略，然后你可以自定义程序包中每个策略的设置以满足用户需求。</span><span class="sxs-lookup"><span data-stu-id="992ab-179">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="992ab-180">若要了解有关策略程序包的详细信息，包括如何分配和管理它们的分步指导，请参阅[管理团队中的策略程序包](manage-policy-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="992ab-180">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="992ab-181">为一批用户分配策略</span><span class="sxs-lookup"><span data-stu-id="992ab-181">Assign a policy to a batch of users</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]
 
<span data-ttu-id="992ab-182">通过批处理策略分配，您可以一次性为大型用户分配策略，而无需使用脚本。</span><span class="sxs-lookup"><span data-stu-id="992ab-182">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="992ab-183">使用```New-CsBatchPolicyAssignmentOperationd``` cmdlet 提交要分配的一批用户和策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-183">You use the ```New-CsBatchPolicyAssignmentOperationd``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="992ab-184">作业作为后台操作处理，并为每个批处理生成操作 ID。</span><span class="sxs-lookup"><span data-stu-id="992ab-184">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="992ab-185">然后，你可以使用```Get-CsBatchPolicyAssignmentOperation```该 cmdlet 跟踪批处理中作业的进度和状态。</span><span class="sxs-lookup"><span data-stu-id="992ab-185">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="992ab-186">批处理最多可包含20000个用户。</span><span class="sxs-lookup"><span data-stu-id="992ab-186">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="992ab-187">你可以按对象 Id、用户主体名称（UPN）、会话初始协议（SIP）地址或电子邮件地址指定用户。</span><span class="sxs-lookup"><span data-stu-id="992ab-187">You can specify users by their object Id, user principal name (UPN), Session Initiation Protocol (SIP) address, or email address.</span></span>

> [!NOTE]
> <span data-ttu-id="992ab-188">当前，批策略分配不适用于所有团队策略类型。</span><span class="sxs-lookup"><span data-stu-id="992ab-188">Currently, batch policy assignment isn't available for all Teams policy types.</span></span> <span data-ttu-id="992ab-189">有关受支持的策略类型列表，请参阅[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 。</span><span class="sxs-lookup"><span data-stu-id="992ab-189">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="992ab-190">安装并连接到 Microsoft 团队 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="992ab-190">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="992ab-191">这些 cmdlet 位于团队 PowerShell 模块的预发布版本中。</span><span class="sxs-lookup"><span data-stu-id="992ab-191">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="992ab-192">按照以下步骤，首先卸载团队 PowerShell 模块的通用版本（如果已安装），然后从 PowerShell 测试库安装该模块的最新预发布版本。</span><span class="sxs-lookup"><span data-stu-id="992ab-192">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="992ab-193">如果尚未执行此操作，请运行以下操作以将 PowerShell 测试库注册为受信任的来源。</span><span class="sxs-lookup"><span data-stu-id="992ab-193">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="992ab-194">如果你安装了通用版本的团队 PowerShell 模块，请运行以下程序将其卸载。</span><span class="sxs-lookup"><span data-stu-id="992ab-194">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="992ab-195">运行以下操作，从 PowerShell 测试库中安装最新的 Microsoft 团队 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="992ab-195">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="992ab-196">运行以下操作以连接到团队并启动会话。</span><span class="sxs-lookup"><span data-stu-id="992ab-196">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="992ab-197">出现提示时，请使用管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="992ab-197">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="992ab-198">安装并连接到 Azure AD PowerShell for Graph 模块（可选）</span><span class="sxs-lookup"><span data-stu-id="992ab-198">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="992ab-199">你可能还希望[下载并安装适用于 Graph 模块的 AZURE Ad PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) （如果尚未这样做），并连接到 Azure ad，以便你可以检索组织中的用户列表。</span><span class="sxs-lookup"><span data-stu-id="992ab-199">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="992ab-200">运行以下操作以连接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="992ab-200">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="992ab-201">出现提示时，请使用您用于连接到团队的相同管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="992ab-201">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="992ab-202">为一批用户分配策略</span><span class="sxs-lookup"><span data-stu-id="992ab-202">Assign a policy to a batch of users</span></span>

<span data-ttu-id="992ab-203">在此示例中，我们使用```New-CsBatchPolicyAssignmentOperation``` cmdlet 将名为 HR App 设置策略的应用设置策略分配给 Users_ids 文本文件中列出的一批用户。</span><span class="sxs-lookup"><span data-stu-id="992ab-203">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="992ab-204">在此示例中，我们连接到 Azure AD 以检索用户集合，然后将名为 "新员工消息传递策略" 的消息策略分配给使用其 Upn 指定的批用户。</span><span class="sxs-lookup"><span data-stu-id="992ab-204">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their UPNs.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

<span data-ttu-id="992ab-205">若要了解详细信息，请参阅[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)。</span><span class="sxs-lookup"><span data-stu-id="992ab-205">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="992ab-206">获取批处理作业的状态</span><span class="sxs-lookup"><span data-stu-id="992ab-206">Get the status of a batch assignment</span></span>

<span data-ttu-id="992ab-207">运行以下操作以获取批处理作业的状态，其中 OperationId 是由给定批处理的```New-CsBatchPolicyAssignmentOperation``` cmdlet 返回的操作 ID。</span><span class="sxs-lookup"><span data-stu-id="992ab-207">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="992ab-208">如果输出显示发生了错误，请运行以下内容以获取有关```UserState```属性中的错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="992ab-208">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="992ab-209">若要了解详细信息，请参阅[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)。</span><span class="sxs-lookup"><span data-stu-id="992ab-209">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="992ab-210">为组分配策略</span><span class="sxs-lookup"><span data-stu-id="992ab-210">Assign a policy to a group</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="992ab-211">组策略分配允许你向一组用户（如安全组或组织单元）分配策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-211">Group policy assignment lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="992ab-212">根据优先级规则，策略分配将传播到组的成员。</span><span class="sxs-lookup"><span data-stu-id="992ab-212">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="992ab-213">将成员添加到组或从组中删除成员后，将相应地更新其继承的策略分配。</span><span class="sxs-lookup"><span data-stu-id="992ab-213">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="992ab-214">你可以使用```New-CsGroupPolicyAssignment``` cmdlet 向组分配策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-214">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="992ab-215">您可以通过使用对象 Id、SIP 地址或电子邮件地址来指定组。</span><span class="sxs-lookup"><span data-stu-id="992ab-215">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="992ab-216">分配策略时，它将立即分配给组。</span><span class="sxs-lookup"><span data-stu-id="992ab-216">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="992ab-217">但是，请注意，对组成员的策略分配的传播是作为后台操作执行的，可能需要一些时间，具体取决于组的大小。</span><span class="sxs-lookup"><span data-stu-id="992ab-217">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="992ab-218">当从组中取消分配策略时，或者在组中添加或删除成员时，也是如此。</span><span class="sxs-lookup"><span data-stu-id="992ab-218">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!NOTE]
> <span data-ttu-id="992ab-219">当前，组策略分配不适用于所有团队策略类型。</span><span class="sxs-lookup"><span data-stu-id="992ab-219">Currently, group policy assignment isn't available for all Teams policy types.</span></span> <span data-ttu-id="992ab-220">有关受支持的策略类型列表，请参阅[CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 。</span><span class="sxs-lookup"><span data-stu-id="992ab-220">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

### <a name="what-you-need-to-know-about-group-policy-assignment"></a><span data-ttu-id="992ab-221">有关组策略分配的需要了解的信息</span><span class="sxs-lookup"><span data-stu-id="992ab-221">What you need to know about group policy assignment</span></span>

<span data-ttu-id="992ab-222">开始之前，了解优先级规则和组策略分配排名非常重要。</span><span class="sxs-lookup"><span data-stu-id="992ab-222">Before you get started, it's important to understand precedence rules and group policy assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="992ab-223">优先规则</span><span class="sxs-lookup"><span data-stu-id="992ab-223">Precedence rules</span></span>

<span data-ttu-id="992ab-224">对于给定的策略类型，根据以下情况确定用户的有效策略：</span><span class="sxs-lookup"><span data-stu-id="992ab-224">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="992ab-225">直接分配给用户的策略优先于分配给组的任何其他相同类型的策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-225">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="992ab-226">换言之，如果用户直接分配给某一给定类型的策略，则该用户不会从组中继承同一类型的策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-226">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="992ab-227">这还意味着，如果用户具有直接分配给他们的给定类型的策略，则必须从用户处删除该策略，然后才能从组继承同一类型的策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-227">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="992ab-228">如果用户没有直接分配给他们的策略，并且是两个或更多组的成员，并且每个组都分配有相同类型的策略，则用户将继承具有最高级别的组分配的策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-228">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="992ab-229">如果用户不是分配了策略的任何组的成员，则该策略类型的全局（组织范围默认）策略将应用于该用户。</span><span class="sxs-lookup"><span data-stu-id="992ab-229">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="992ab-230">当用户在分配了策略的组中添加或删除时，用户的有效策略将根据这些规则进行更新，从组中取消分配策略，或者删除直接分配给用户的策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-230">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="992ab-231">组分配排名</span><span class="sxs-lookup"><span data-stu-id="992ab-231">Group assignment ranking</span></span>
 
<span data-ttu-id="992ab-232">向组分配策略时，为组分配指定排名。</span><span class="sxs-lookup"><span data-stu-id="992ab-232">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="992ab-233">如果用户是两个或更多组的成员，并且每个组都分配有同一类型的策略，则使用此功能确定用户应继承为其有效策略的策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-233">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="992ab-234">组分配排名相对于相同类型的其他组策略分配。</span><span class="sxs-lookup"><span data-stu-id="992ab-234">The group assignment ranking is relative to other group policy assignments of the same type.</span></span> <span data-ttu-id="992ab-235">例如，如果您正在向两个组分配呼叫策略，则将一个作业的等级设置为1，另一个设置为2，1为最高排名。</span><span class="sxs-lookup"><span data-stu-id="992ab-235">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="992ab-236">组分配排名指明哪些组成员身份比继承的其他组成员更重要或更密切。</span><span class="sxs-lookup"><span data-stu-id="992ab-236">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="992ab-237">例如，你有两个组，存储员工和商店经理。</span><span class="sxs-lookup"><span data-stu-id="992ab-237">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="992ab-238">这两个组都分配有一个团队调用策略，分别存储员工调用策略和存储管理器调用策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-238">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="992ab-239">对于位于两个组中的商店经理，其角色作为经理，其角色与员工的角色更相关，因此分配给应用商店管理员组的呼叫策略应具有更高的排名。</span><span class="sxs-lookup"><span data-stu-id="992ab-239">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="992ab-240">团队</span><span class="sxs-lookup"><span data-stu-id="992ab-240">Group</span></span> |<span data-ttu-id="992ab-241">团队调用策略名称</span><span class="sxs-lookup"><span data-stu-id="992ab-241">Teams calling policy name</span></span>  |<span data-ttu-id="992ab-242">等级</span><span class="sxs-lookup"><span data-stu-id="992ab-242">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="992ab-243">商店经理</span><span class="sxs-lookup"><span data-stu-id="992ab-243">Store Managers</span></span>   |<span data-ttu-id="992ab-244">应用商店经理通话政策</span><span class="sxs-lookup"><span data-stu-id="992ab-244">Store Managers Calling Policy</span></span>         |<span data-ttu-id="992ab-245">1</span><span class="sxs-lookup"><span data-stu-id="992ab-245">1</span></span>|
|<span data-ttu-id="992ab-246">存储员工</span><span class="sxs-lookup"><span data-stu-id="992ab-246">Store Employees</span></span>    |<span data-ttu-id="992ab-247">存储员工通话政策</span><span class="sxs-lookup"><span data-stu-id="992ab-247">Store Employees Calling Policy</span></span>      |<span data-ttu-id="992ab-248">ppls-2</span><span class="sxs-lookup"><span data-stu-id="992ab-248">2</span></span>|

<span data-ttu-id="992ab-249">如果未指定排名，则将为策略分配授予最低级别。</span><span class="sxs-lookup"><span data-stu-id="992ab-249">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="992ab-250">安装并连接到 Microsoft 团队 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="992ab-250">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="992ab-251">这些 cmdlet 位于团队 PowerShell 模块的预发布版本中。</span><span class="sxs-lookup"><span data-stu-id="992ab-251">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="992ab-252">按照以下步骤，首先卸载团队 PowerShell 模块的通用版本（如果已安装），然后从 PowerShell 测试库安装该模块的最新预发布版本。</span><span class="sxs-lookup"><span data-stu-id="992ab-252">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="992ab-253">如果尚未执行此操作，请运行以下操作以将 PowerShell 测试库注册为受信任的来源。</span><span class="sxs-lookup"><span data-stu-id="992ab-253">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="992ab-254">如果你安装了通用版本的团队 PowerShell 模块，请运行以下程序将其卸载。</span><span class="sxs-lookup"><span data-stu-id="992ab-254">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="992ab-255">运行以下操作，从 PowerShell 测试库中安装最新的 Microsoft 团队 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="992ab-255">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="992ab-256">运行以下操作以连接到团队并启动会话。</span><span class="sxs-lookup"><span data-stu-id="992ab-256">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="992ab-257">出现提示时，请使用管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="992ab-257">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="992ab-258">为组分配策略</span><span class="sxs-lookup"><span data-stu-id="992ab-258">Assign a policy to a group</span></span>

<span data-ttu-id="992ab-259">在此示例中，我们使用```New-CsGroupPolicyAssignment``` cmdlet 将名为零售经理会议策略的团队会议策略分配给分配等级为1的组。</span><span class="sxs-lookup"><span data-stu-id="992ab-259">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="992ab-260">若要了解详细信息，请参阅[CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="992ab-260">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="992ab-261">获取组的策略分配</span><span class="sxs-lookup"><span data-stu-id="992ab-261">Get policy assignments for a group</span></span>

<span data-ttu-id="992ab-262">使用```Get-CsGroupPolicyAssignment``` cmdlet 获取分配给组的所有策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-262">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="992ab-263">请注意，组始终按组 Id 列出，即使其 SIP 地址或电子邮件地址用于分配策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-263">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="992ab-264">在此示例中，我们将检索分配给特定组的所有策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-264">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="992ab-265">在此示例中，我们将返回分配有团队会议策略的所有组。</span><span class="sxs-lookup"><span data-stu-id="992ab-265">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="992ab-266">若要了解详细信息，请参阅[CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="992ab-266">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="992ab-267">从组中删除策略</span><span class="sxs-lookup"><span data-stu-id="992ab-267">Remove a policy from a group</span></span>

<span data-ttu-id="992ab-268">使用```Remove-CsGroupPolicyAssignment``` cmdlet 从组中删除策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-268">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="992ab-269">从组中删除策略时，将更新分配给该组的相同类型的其他策略的优先级和较低级别的其他策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-269">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="992ab-270">例如，如果删除分级为2的策略，则级别为3和4的策略将更新，以反映其新排名。</span><span class="sxs-lookup"><span data-stu-id="992ab-270">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="992ab-271">下面的两个表显示了此示例。</span><span class="sxs-lookup"><span data-stu-id="992ab-271">The following two tables show this example.</span></span>

<span data-ttu-id="992ab-272">下面列出了团队会议策略的策略分配和优先级。</span><span class="sxs-lookup"><span data-stu-id="992ab-272">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="992ab-273">组名称</span><span class="sxs-lookup"><span data-stu-id="992ab-273">Group name</span></span>  |<span data-ttu-id="992ab-274">策略名称</span><span class="sxs-lookup"><span data-stu-id="992ab-274">Policy name</span></span>  |<span data-ttu-id="992ab-275">等级</span><span class="sxs-lookup"><span data-stu-id="992ab-275">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="992ab-276">销售</span><span class="sxs-lookup"><span data-stu-id="992ab-276">Sales</span></span>    |<span data-ttu-id="992ab-277">销售政策</span><span class="sxs-lookup"><span data-stu-id="992ab-277">Sales policy</span></span>       | <span data-ttu-id="992ab-278">1</span><span class="sxs-lookup"><span data-stu-id="992ab-278">1</span></span>        |
|<span data-ttu-id="992ab-279">西部区域</span><span class="sxs-lookup"><span data-stu-id="992ab-279">West Region</span></span>     |<span data-ttu-id="992ab-280">West 区域策略</span><span class="sxs-lookup"><span data-stu-id="992ab-280">West Region policy</span></span>         |<span data-ttu-id="992ab-281">ppls-2</span><span class="sxs-lookup"><span data-stu-id="992ab-281">2</span></span>         |
|<span data-ttu-id="992ab-282">单位</span><span class="sxs-lookup"><span data-stu-id="992ab-282">Division</span></span>    |<span data-ttu-id="992ab-283">部门策略</span><span class="sxs-lookup"><span data-stu-id="992ab-283">Division policy</span></span>         |<span data-ttu-id="992ab-284">3</span><span class="sxs-lookup"><span data-stu-id="992ab-284">3</span></span>         |
|<span data-ttu-id="992ab-285">附属</span><span class="sxs-lookup"><span data-stu-id="992ab-285">Subsidiary</span></span>   |<span data-ttu-id="992ab-286">附属政策</span><span class="sxs-lookup"><span data-stu-id="992ab-286">Subsidiary policy</span></span>        |<span data-ttu-id="992ab-287">4</span><span class="sxs-lookup"><span data-stu-id="992ab-287">4</span></span>         |

<span data-ttu-id="992ab-288">如果我们删除 "西部" 区域组中的 "西部" 区域策略，策略分配和优先级将按如下方式更新。</span><span class="sxs-lookup"><span data-stu-id="992ab-288">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="992ab-289">组名称</span><span class="sxs-lookup"><span data-stu-id="992ab-289">Group name</span></span>  |<span data-ttu-id="992ab-290">策略名称</span><span class="sxs-lookup"><span data-stu-id="992ab-290">Policy name</span></span>  |<span data-ttu-id="992ab-291">等级</span><span class="sxs-lookup"><span data-stu-id="992ab-291">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="992ab-292">销售</span><span class="sxs-lookup"><span data-stu-id="992ab-292">Sales</span></span>    |<span data-ttu-id="992ab-293">销售政策</span><span class="sxs-lookup"><span data-stu-id="992ab-293">Sales policy</span></span>       | <span data-ttu-id="992ab-294">1</span><span class="sxs-lookup"><span data-stu-id="992ab-294">1</span></span>        |
|<span data-ttu-id="992ab-295">单位</span><span class="sxs-lookup"><span data-stu-id="992ab-295">Division</span></span>    |<span data-ttu-id="992ab-296">部门策略</span><span class="sxs-lookup"><span data-stu-id="992ab-296">Division policy</span></span>         |<span data-ttu-id="992ab-297">ppls-2</span><span class="sxs-lookup"><span data-stu-id="992ab-297">2</span></span>         |
|<span data-ttu-id="992ab-298">附属</span><span class="sxs-lookup"><span data-stu-id="992ab-298">Subsidiary</span></span>   |<span data-ttu-id="992ab-299">附属政策</span><span class="sxs-lookup"><span data-stu-id="992ab-299">Subsidiary policy</span></span>        |<span data-ttu-id="992ab-300">3</span><span class="sxs-lookup"><span data-stu-id="992ab-300">3</span></span>        |

<span data-ttu-id="992ab-301">在此示例中，我们从组中删除团队会议策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-301">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="992ab-302">若要了解详细信息，请参阅[删除-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="992ab-302">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="992ab-303">更改组的策略分配</span><span class="sxs-lookup"><span data-stu-id="992ab-303">Change a policy assignment for a group</span></span>

<span data-ttu-id="992ab-304">为组分配策略后，可以使用```Set-CsGroupPolicyAssignmentd``` cmdlet 更改该组的策略分配，如下所示：</span><span class="sxs-lookup"><span data-stu-id="992ab-304">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignmentd``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="992ab-305">更改排名</span><span class="sxs-lookup"><span data-stu-id="992ab-305">Change the ranking</span></span>
- <span data-ttu-id="992ab-306">更改给定策略类型的策略</span><span class="sxs-lookup"><span data-stu-id="992ab-306">Change the policy of a given policy type</span></span>
- <span data-ttu-id="992ab-307">更改给定策略类型和排名的策略</span><span class="sxs-lookup"><span data-stu-id="992ab-307">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="992ab-308">在此示例中，我们将组的团队更改为名为 SupportCallPark 的策略，并将工作分配排名设置为3。</span><span class="sxs-lookup"><span data-stu-id="992ab-308">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="992ab-309">若要了解详细信息，请参阅[设置 CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="992ab-309">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="992ab-310">更改用户的有效策略</span><span class="sxs-lookup"><span data-stu-id="992ab-310">Change the effective policy for a user</span></span>

<span data-ttu-id="992ab-311">下面是如何更改直接分配了策略的用户的有效策略的示例。</span><span class="sxs-lookup"><span data-stu-id="992ab-311">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="992ab-312">首先，我们将```Get-CsUserPolicyAssignment``` cmdlet 与```PolicySource```参数结合使用，以获取与用户相关联的团队会议广播策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="992ab-312">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="992ab-313">若要了解详细信息，请参阅[CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="992ab-313">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="992ab-314">输出显示用户直接分配有名为员工事件的团队会议广播策略，该策略优先于分配给用户所属组的名为 "供应商实时事件" 的策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-314">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="992ab-315">现在，我们将从用户中删除 "员工活动" 策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-315">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="992ab-316">这意味着用户不再有团队会议广播策略直接分配给他们，并且将继承分配给用户所属组的供应商实时事件策略。</span><span class="sxs-lookup"><span data-stu-id="992ab-316">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="992ab-317">使用 Skype for Business PowerShell 模块中的以下 cmdlet 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="992ab-317">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="992ab-318">你可以使用团队 Powershell 模块中的以下 cmdlet 通过批处理策略分配以缩放方式执行此操作，其中 $users 是你指定的用户的列表。</span><span class="sxs-lookup"><span data-stu-id="992ab-318">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="related-topics"></a><span data-ttu-id="992ab-319">相关主题</span><span class="sxs-lookup"><span data-stu-id="992ab-319">Related topics</span></span>

- [<span data-ttu-id="992ab-320">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="992ab-320">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)