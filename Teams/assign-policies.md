---
title: 向 Microsoft Teams 中的用户分配策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
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
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: aa63a0cc7ce24390228cc9d87adf054348c6522d
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350036"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="33d29-103">向 Microsoft Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="33d29-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="33d29-104">**本文中讨论的 Microsoft 团队功能之一，目前仅在私人预览版中提供了[对组的策略分配](#assign-a-policy-to-a-group)。此功能的 Powershell cmdlet 位于预发布团队 PowerShell 模块中。**</span><span class="sxs-lookup"><span data-stu-id="33d29-104">**One of the Microsoft Teams features discussed in this article, [policy assignment to groups](#assign-a-policy-to-a-group), is currently only available in private preview. The Powershell cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span> <span data-ttu-id="33d29-105">若要保持在此功能的 "发布" 状态的顶部，请查看[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185)。</span><span class="sxs-lookup"><span data-stu-id="33d29-105">To stay on top of the release status of this feature, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span></span>

<span data-ttu-id="33d29-106">作为管理员，你可以使用策略来控制你的组织中的用户可以使用的团队功能。</span><span class="sxs-lookup"><span data-stu-id="33d29-106">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="33d29-107">例如，有一些通话策略、会议策略和邮件策略，只需命名。</span><span class="sxs-lookup"><span data-stu-id="33d29-107">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="33d29-108">组织具有不同类型的具有独特需求的用户和你创建和分配的自定义策略，让你可以根据这些需求将策略设置自定义给不同的用户集。</span><span class="sxs-lookup"><span data-stu-id="33d29-108">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="33d29-109">为了便于管理组织中的策略，团队提供了多种方法来为用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-109">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="33d29-110">你可以将策略直接分配给用户，无论是单独的还是通过批处理作业进行缩放，或是用户所属的组。</span><span class="sxs-lookup"><span data-stu-id="33d29-110">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the user is a member of.</span></span> <span data-ttu-id="33d29-111">你还可以使用策略程序包向组织中具有类似角色的用户分配策略的预设集合。</span><span class="sxs-lookup"><span data-stu-id="33d29-111">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="33d29-112">你选择的选项取决于你正在管理的策略的数量以及你要分配到的用户数。</span><span class="sxs-lookup"><span data-stu-id="33d29-112">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span>

<span data-ttu-id="33d29-113">本文介绍为用户分配策略的不同方法以及用于何时使用的建议方案。</span><span class="sxs-lookup"><span data-stu-id="33d29-113">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="33d29-114">哪种策略优先？</span><span class="sxs-lookup"><span data-stu-id="33d29-114">Which policy takes precedence?</span></span>

<span data-ttu-id="33d29-115">用户对每个策略类型都有一个有效策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-115">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="33d29-116">用户可以直接分配策略，也可以是分配了相同类型策略的一个或多个组的成员。</span><span class="sxs-lookup"><span data-stu-id="33d29-116">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="33d29-117">在这种情况下，哪些策略优先？</span><span class="sxs-lookup"><span data-stu-id="33d29-117">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="33d29-118">根据优先级规则确定用户的有效策略，如下所示。</span><span class="sxs-lookup"><span data-stu-id="33d29-118">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="33d29-119">如果用户直接分配策略（单独或通过批处理作业），则该策略优先。</span><span class="sxs-lookup"><span data-stu-id="33d29-119">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="33d29-120">在以下示例中，用户的有效策略是 Lincoln 方形会议策略，该策略直接分配给用户。</span><span class="sxs-lookup"><span data-stu-id="33d29-120">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![图表显示如何直接分配的策略优先](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="33d29-122">如果用户未直接分配给定类型的策略，则分配给用户所属组的策略优先。</span><span class="sxs-lookup"><span data-stu-id="33d29-122">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="33d29-123">如果用户是多个组的成员，则具有给定策略类型的最高[组分配级别](#group-assignment-ranking)的策略优先。</span><span class="sxs-lookup"><span data-stu-id="33d29-123">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="33d29-124">在此示例中，用户的有效策略是 Exec 团队和 HD 策略，该策略具有相对于用户所属的其他组的最高工作分配级别，并且还分配有相同策略类型的策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-124">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![图表显示了从组继承的策略优先的方式](media/assign-policies-example-group.png)

<span data-ttu-id="33d29-126">如果用户未直接分配策略或不是分配了策略的任何组的成员，则用户将获取该策略类型的全局（组织范围默认）策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-126">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="33d29-127">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="33d29-127">Here's an example.</span></span>

![显示全局策略优先级别的图表](media/assign-policies-example-global.png)

<span data-ttu-id="33d29-129">若要了解详细信息，请参阅[优先规则](#precedence-rules)。</span><span class="sxs-lookup"><span data-stu-id="33d29-129">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="33d29-130">分配策略的方法</span><span class="sxs-lookup"><span data-stu-id="33d29-130">Ways to assign policies</span></span>

<span data-ttu-id="33d29-131">下面概述了为用户分配策略的方法和建议的每种方案。</span><span class="sxs-lookup"><span data-stu-id="33d29-131">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="33d29-132">单击链接以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="33d29-132">Click the links to learn more.</span></span>

|<span data-ttu-id="33d29-133">要执行的操作</span><span class="sxs-lookup"><span data-stu-id="33d29-133">Do this</span></span>  |<span data-ttu-id="33d29-134">If .。。</span><span class="sxs-lookup"><span data-stu-id="33d29-134">If...</span></span>  | <span data-ttu-id="33d29-135">使用 .。。</span><span class="sxs-lookup"><span data-stu-id="33d29-135">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="33d29-136">为单个用户分配策略</span><span class="sxs-lookup"><span data-stu-id="33d29-136">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="33d29-137">您是新的团队新手，只需将一个或几个策略分配给少数几个用户。</span><span class="sxs-lookup"><span data-stu-id="33d29-137">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="33d29-138">Skype for Business Online PowerShell 模块中的 Microsoft 团队管理中心或 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="33d29-138">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="33d29-139">分配策略包</span><span class="sxs-lookup"><span data-stu-id="33d29-139">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="33d29-140">您需要将多个策略分配给组织中具有相同或类似角色的特定用户组。</span><span class="sxs-lookup"><span data-stu-id="33d29-140">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="33d29-141">例如，将教育版（教师）策略包分配给你的学校教师，让他们能够完全访问聊天、通话和会议以及教育（次要学校学生）策略包，以限制某些功能，如私人通话。</span><span class="sxs-lookup"><span data-stu-id="33d29-141">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="33d29-142">团队 PowerShell 模块中的 Microsoft 团队管理中心或 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="33d29-142">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="33d29-143">为一批用户分配策略</span><span class="sxs-lookup"><span data-stu-id="33d29-143">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="33d29-144">您需要为大型用户组分配策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-144">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="33d29-145">例如，你希望一次为组织中的成百上千个用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-145">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="33d29-146">团队 PowerShell 模块中的 Microsoft 团队管理中心或 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="33d29-146">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="33d29-147">为[组分配策略](#assign-a-policy-to-a-group)（在预览中）</span><span class="sxs-lookup"><span data-stu-id="33d29-147">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview)</span></span>   |<span data-ttu-id="33d29-148">您需要根据用户的组成员身份分配策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-148">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="33d29-149">例如，你想要向安全组或组织单位中的所有用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-149">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="33d29-150">团队 PowerShell 模块中的 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="33d29-150">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="33d29-151">将策略包分配给一批用户</span><span class="sxs-lookup"><span data-stu-id="33d29-151">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="33d29-152">您需要为组织中具有相同或类似角色的一批用户分配多个策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-152">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="33d29-153">例如，使用批处理作业将教育版（教师）策略包分配给你的学校中的所有教师，让他们能够完全访问聊天、通话和会议，并将教育（次要学校学生）策略包分配给一批次要学生，以限制某些功能（如私人通话）。</span><span class="sxs-lookup"><span data-stu-id="33d29-153">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="33d29-154">团队 PowerShell 模块中的 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="33d29-154">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="33d29-155">将策略包分配给组（即将推出）</span><span class="sxs-lookup"><span data-stu-id="33d29-155">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="33d29-156">为单个用户分配策略</span><span class="sxs-lookup"><span data-stu-id="33d29-156">Assign a policy to individual users</span></span>

<span data-ttu-id="33d29-157">请按照以下步骤将策略分配给单个用户或一次分配给少数几个用户。</span><span class="sxs-lookup"><span data-stu-id="33d29-157">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="33d29-158">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="33d29-158">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="33d29-159">若要为用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="33d29-159">To assign a policy to a user:</span></span>

1. <span data-ttu-id="33d29-160">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="33d29-160">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="33d29-161">单击用户名的左侧以选择用户，然后单击“编辑设置”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="33d29-161">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="33d29-162">选择要分配的策略，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="33d29-162">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="33d29-163">或者，您也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="33d29-163">Or, you can also do the following:</span></span>

1. <span data-ttu-id="33d29-164">在 Microsoft 团队管理中心的左侧导航中，转到 "策略" 页面。</span><span class="sxs-lookup"><span data-stu-id="33d29-164">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="33d29-165">通过单击策略名称的左侧，选择要分配的策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-165">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="33d29-166">选择“管理用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="33d29-166">Select **Manage users**.</span></span>
4. <span data-ttu-id="33d29-167">在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="33d29-167">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="33d29-168">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="33d29-168">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="33d29-169">添加完用户后，请选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="33d29-169">When you're finished adding users, select **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="33d29-170">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="33d29-170">Using PowerShell</span></span>

<span data-ttu-id="33d29-171">每个策略类型都有自己的一组用于管理它的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="33d29-171">Each policy type has it's own set of cmdlets for managing it.</span></span> <span data-ttu-id="33d29-172">使用 ```Grant-``` 给定策略类型的 cmdlet 分配策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-172">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="33d29-173">例如，使用 ```Grant-CsTeamsMeetingPolicy``` cmdlet 向用户分配团队会议策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-173">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="33d29-174">这些 cmdlet 包含在 Skype for Business Online PowerShell 模块中，并记录在[skype for business cmdlet 参考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)中。</span><span class="sxs-lookup"><span data-stu-id="33d29-174">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="33d29-175">下载并安装[Skype For Business Online PowerShell 模块](https://www.microsoft.com/en-us/download/details.aspx?id=39366)（如果尚未安装），然后运行以下操作以连接到 Skype For business online 并启动会话。</span><span class="sxs-lookup"><span data-stu-id="33d29-175">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="33d29-176">在此示例中，我们将名为 "学生会议策略" 的团队会议策略分配给名为 Reda 的用户。</span><span class="sxs-lookup"><span data-stu-id="33d29-176">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="33d29-177">若要了解详细信息，请参阅[通过 PowerShell 管理策略](teams-powershell-overview.md#managing-policies-via-powershell)。</span><span class="sxs-lookup"><span data-stu-id="33d29-177">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="33d29-178">分配策略包</span><span class="sxs-lookup"><span data-stu-id="33d29-178">Assign a policy package</span></span>

<span data-ttu-id="33d29-179">团队中的策略包是预定义策略和策略设置的集合，你可以分配给在你的组织中具有相同或类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="33d29-179">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="33d29-180">每个策略程序包均围绕用户角色进行设计，其中包含支持该角色的典型活动的预定义策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="33d29-180">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="33d29-181">策略包的一些示例是教育版（教师）包和医疗保健（临床工作者）程序包。</span><span class="sxs-lookup"><span data-stu-id="33d29-181">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="33d29-182">向用户分配策略包时，将创建程序包中的策略，然后你可以自定义程序包中每个策略的设置以满足用户需求。</span><span class="sxs-lookup"><span data-stu-id="33d29-182">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="33d29-183">若要了解有关策略程序包的详细信息，包括如何分配和管理它们的分步指导，请参阅[管理团队中的策略程序包](manage-policy-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="33d29-183">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="33d29-184">为一批用户分配策略</span><span class="sxs-lookup"><span data-stu-id="33d29-184">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="33d29-185">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="33d29-185">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="33d29-186">要批量向用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="33d29-186">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="33d29-187">在 Microsoft 团队管理中心的左侧导航中，选择 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="33d29-187">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="33d29-188">搜索要向其分配策略的用户，或筛选视图以显示所需的用户。</span><span class="sxs-lookup"><span data-stu-id="33d29-188">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="33d29-189">在 " **&#x2713;** " （复选标记）列中，选择用户。</span><span class="sxs-lookup"><span data-stu-id="33d29-189">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="33d29-190">若要选择 "所有用户"，请单击表格顶部的 "&#x2713;" （复选标记）。</span><span class="sxs-lookup"><span data-stu-id="33d29-190">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="33d29-191">单击 "**编辑设置**"，进行所需的更改，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="33d29-191">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="33d29-192">若要查看策略分配的状态，请在单击 "**应用**" 提交策略分配后出现在 "**用户**" 页面顶部的标题中，单击 "**活动日志**"。</span><span class="sxs-lookup"><span data-stu-id="33d29-192">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="33d29-193">或者，在 Microsoft 团队管理中心的左侧导航中，转到**仪表板**，然后在 "**活动日志**" 下单击 "**查看详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="33d29-193">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="33d29-194">活动日志显示过去30天内通过 Microsoft 团队管理中心向超过20名用户批处理的策略分配。</span><span class="sxs-lookup"><span data-stu-id="33d29-194">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="33d29-195">若要了解详细信息，请参阅[在活动日志中查看策略分配](activity-log.md)。</span><span class="sxs-lookup"><span data-stu-id="33d29-195">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="33d29-196">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="33d29-196">Using PowerShell</span></span>
 
<span data-ttu-id="33d29-197">通过批处理策略分配，您可以一次性为大型用户分配策略，而无需使用脚本。</span><span class="sxs-lookup"><span data-stu-id="33d29-197">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="33d29-198">使用 ```New-CsBatchPolicyAssignmentOperationd``` cmdlet 提交要分配的一批用户和策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-198">You use the ```New-CsBatchPolicyAssignmentOperationd``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="33d29-199">作业作为后台操作处理，并为每个批处理生成操作 ID。</span><span class="sxs-lookup"><span data-stu-id="33d29-199">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="33d29-200">然后，你可以使用该 ```Get-CsBatchPolicyAssignmentOperation``` cmdlet 跟踪批处理中作业的进度和状态。</span><span class="sxs-lookup"><span data-stu-id="33d29-200">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="33d29-201">批处理最多可包含20000个用户。</span><span class="sxs-lookup"><span data-stu-id="33d29-201">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="33d29-202">你可以按对象 Id、用户主体名称（UPN）、会话初始协议（SIP）地址或电子邮件地址指定用户。</span><span class="sxs-lookup"><span data-stu-id="33d29-202">You can specify users by their object Id, user principal name (UPN), Session Initiation Protocol (SIP) address, or email address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33d29-203">我们当前建议你一次为每批5000用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-203">We're currently recommending that you assign policies in batches of 5,000 users at a time.</span></span> <span data-ttu-id="33d29-204">在增加需求的这些时间内，你可能会遇到处理时间方面的延迟。</span><span class="sxs-lookup"><span data-stu-id="33d29-204">During these times of increased demand, you may experience delays in processing times.</span></span> <span data-ttu-id="33d29-205">为了将这些增加的处理时间的影响降到最低，我们建议你向5000用户提交较小的批处理大小，并且仅在上一个批处理完成后再提交。</span><span class="sxs-lookup"><span data-stu-id="33d29-205">To minimize the impact of these increased processing times, we suggest that you submit smaller batch sizes of up to 5,000 users, and submit each batch only after the previous one is completed.</span></span> <span data-ttu-id="33d29-206">在正常工作时间内提交批还会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="33d29-206">Submitting batches outside your regular business hours can also help.</span></span>

> [!NOTE]
> <span data-ttu-id="33d29-207">当前，批策略分配不适用于所有团队策略类型。</span><span class="sxs-lookup"><span data-stu-id="33d29-207">Currently, batch policy assignment isn't available for all Teams policy types.</span></span> <span data-ttu-id="33d29-208">有关受支持的策略类型列表，请参阅[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 。</span><span class="sxs-lookup"><span data-stu-id="33d29-208">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="33d29-209">安装并连接到 Microsoft 团队 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="33d29-209">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="33d29-210">运行以下操作以安装[Microsoft 团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams)。</span><span class="sxs-lookup"><span data-stu-id="33d29-210">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="33d29-211">请确保安装1.0.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="33d29-211">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="33d29-212">运行以下操作以连接到团队并启动会话。</span><span class="sxs-lookup"><span data-stu-id="33d29-212">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="33d29-213">出现提示时，请使用管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="33d29-213">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="33d29-214">安装并连接到 Azure AD PowerShell for Graph 模块（可选）</span><span class="sxs-lookup"><span data-stu-id="33d29-214">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="33d29-215">你可能还希望[下载并安装适用于 Graph 模块的 AZURE Ad PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) （如果尚未这样做），并连接到 Azure ad，以便你可以检索组织中的用户列表。</span><span class="sxs-lookup"><span data-stu-id="33d29-215">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="33d29-216">运行以下操作以连接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="33d29-216">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="33d29-217">出现提示时，请使用您用于连接到团队的相同管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="33d29-217">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="33d29-218">为一批用户分配策略</span><span class="sxs-lookup"><span data-stu-id="33d29-218">Assign a policy to a batch of users</span></span>

<span data-ttu-id="33d29-219">在此示例中，我们使用 ```New-CsBatchPolicyAssignmentOperation``` cmdlet 将名为 HR App 设置策略的应用设置策略分配给 Users_ids 文本文件中列出的一批用户。</span><span class="sxs-lookup"><span data-stu-id="33d29-219">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="33d29-220">在此示例中，我们连接到 Azure AD 以检索用户集合，然后将名为 "新员工消息传递策略" 的消息策略分配给使用其 Upn 指定的批用户。</span><span class="sxs-lookup"><span data-stu-id="33d29-220">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their UPNs.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

<span data-ttu-id="33d29-221">若要了解详细信息，请参阅[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)。</span><span class="sxs-lookup"><span data-stu-id="33d29-221">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="33d29-222">获取批处理作业的状态</span><span class="sxs-lookup"><span data-stu-id="33d29-222">Get the status of a batch assignment</span></span>

<span data-ttu-id="33d29-223">运行以下操作以获取批处理作业的状态，其中 OperationId 是由给定批处理的 cmdlet 返回的操作 ID ```New-CsBatchPolicyAssignmentOperation``` 。</span><span class="sxs-lookup"><span data-stu-id="33d29-223">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="33d29-224">如果输出显示发生了错误，请运行以下内容以获取有关属性中的错误的详细信息 ```UserState``` 。</span><span class="sxs-lookup"><span data-stu-id="33d29-224">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="33d29-225">若要了解详细信息，请参阅[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)。</span><span class="sxs-lookup"><span data-stu-id="33d29-225">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="33d29-226">为组分配策略</span><span class="sxs-lookup"><span data-stu-id="33d29-226">Assign a policy to a group</span></span>

<span data-ttu-id="33d29-227">**对组的策略分配当前仅在专用预览中可用。此功能的 cmdlet 位于预发布团队 PowerShell 模块中。**</span><span class="sxs-lookup"><span data-stu-id="33d29-227">**Policy assignment to groups is currently only available in private preview. The cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span>

<span data-ttu-id="33d29-228">通过向组分配策略，你可以为一组用户（如安全组或组织单位）分配策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-228">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="33d29-229">根据优先级规则，策略分配将传播到组的成员。</span><span class="sxs-lookup"><span data-stu-id="33d29-229">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="33d29-230">将成员添加到组或从组中删除成员后，将相应地更新其继承的策略分配。</span><span class="sxs-lookup"><span data-stu-id="33d29-230">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="33d29-231">你可以使用 ```New-CsGroupPolicyAssignment``` cmdlet 向组分配策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-231">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="33d29-232">您可以通过使用对象 Id、SIP 地址或电子邮件地址来指定组。</span><span class="sxs-lookup"><span data-stu-id="33d29-232">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="33d29-233">分配策略时，它将立即分配给组。</span><span class="sxs-lookup"><span data-stu-id="33d29-233">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="33d29-234">但是，请注意，对组成员的策略分配的传播是作为后台操作执行的，可能需要一些时间，具体取决于组的大小。</span><span class="sxs-lookup"><span data-stu-id="33d29-234">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="33d29-235">当从组中取消分配策略时，或者在组中添加或删除成员时，也是如此。</span><span class="sxs-lookup"><span data-stu-id="33d29-235">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!NOTE]
> <span data-ttu-id="33d29-236">目前，对组的策略分配对所有团队策略类型不可用。</span><span class="sxs-lookup"><span data-stu-id="33d29-236">Currently, policy assignment to groups isn't available for all Teams policy types.</span></span> <span data-ttu-id="33d29-237">有关受支持的策略类型列表，请参阅[CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 。</span><span class="sxs-lookup"><span data-stu-id="33d29-237">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="33d29-238">对组的策略分配需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="33d29-238">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="33d29-239">在开始之前，了解优先级规则和组分配的排名非常重要。</span><span class="sxs-lookup"><span data-stu-id="33d29-239">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="33d29-240">优先规则</span><span class="sxs-lookup"><span data-stu-id="33d29-240">Precedence rules</span></span>

<span data-ttu-id="33d29-241">对于给定的策略类型，根据以下情况确定用户的有效策略：</span><span class="sxs-lookup"><span data-stu-id="33d29-241">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="33d29-242">直接分配给用户的策略优先于分配给组的任何其他相同类型的策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-242">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="33d29-243">换言之，如果用户直接分配给某一给定类型的策略，则该用户不会从组中继承同一类型的策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-243">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="33d29-244">这还意味着，如果用户具有直接分配给他们的给定类型的策略，则必须从用户处删除该策略，然后才能从组继承同一类型的策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-244">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="33d29-245">如果用户没有直接分配给他们的策略，并且是两个或更多组的成员，并且每个组都分配有相同类型的策略，则用户将继承具有最高级别的组分配的策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-245">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="33d29-246">如果用户不是分配了策略的任何组的成员，则该策略类型的全局（组织范围默认）策略将应用于该用户。</span><span class="sxs-lookup"><span data-stu-id="33d29-246">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="33d29-247">当用户在分配了策略的组中添加或删除时，用户的有效策略将根据这些规则进行更新，从组中取消分配策略，或者删除直接分配给用户的策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-247">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="33d29-248">组分配排名</span><span class="sxs-lookup"><span data-stu-id="33d29-248">Group assignment ranking</span></span>
 
<span data-ttu-id="33d29-249">向组分配策略时，为组分配指定排名。</span><span class="sxs-lookup"><span data-stu-id="33d29-249">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="33d29-250">如果用户是两个或更多组的成员，并且每个组都分配有同一类型的策略，则使用此功能确定用户应继承为其有效策略的策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-250">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="33d29-251">组分配排名与同一类型的其他组分配相关。</span><span class="sxs-lookup"><span data-stu-id="33d29-251">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="33d29-252">例如，如果您正在向两个组分配呼叫策略，则将一个作业的等级设置为1，另一个设置为2，1为最高排名。</span><span class="sxs-lookup"><span data-stu-id="33d29-252">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="33d29-253">组分配排名指明哪些组成员身份比继承的其他组成员更重要或更密切。</span><span class="sxs-lookup"><span data-stu-id="33d29-253">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="33d29-254">例如，你有两个组，存储员工和商店经理。</span><span class="sxs-lookup"><span data-stu-id="33d29-254">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="33d29-255">这两个组都分配有一个团队调用策略，分别存储员工调用策略和存储管理器调用策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-255">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="33d29-256">对于位于两个组中的商店经理，其角色作为经理，其角色与员工的角色更相关，因此分配给应用商店管理员组的呼叫策略应具有更高的排名。</span><span class="sxs-lookup"><span data-stu-id="33d29-256">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="33d29-257">团队</span><span class="sxs-lookup"><span data-stu-id="33d29-257">Group</span></span> |<span data-ttu-id="33d29-258">团队调用策略名称</span><span class="sxs-lookup"><span data-stu-id="33d29-258">Teams calling policy name</span></span>  |<span data-ttu-id="33d29-259">等级</span><span class="sxs-lookup"><span data-stu-id="33d29-259">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="33d29-260">商店经理</span><span class="sxs-lookup"><span data-stu-id="33d29-260">Store Managers</span></span>   |<span data-ttu-id="33d29-261">应用商店经理通话政策</span><span class="sxs-lookup"><span data-stu-id="33d29-261">Store Managers Calling Policy</span></span>         |<span data-ttu-id="33d29-262">1</span><span class="sxs-lookup"><span data-stu-id="33d29-262">1</span></span>|
|<span data-ttu-id="33d29-263">存储员工</span><span class="sxs-lookup"><span data-stu-id="33d29-263">Store Employees</span></span>    |<span data-ttu-id="33d29-264">存储员工通话政策</span><span class="sxs-lookup"><span data-stu-id="33d29-264">Store Employees Calling Policy</span></span>      |<span data-ttu-id="33d29-265">2</span><span class="sxs-lookup"><span data-stu-id="33d29-265">2</span></span>|

<span data-ttu-id="33d29-266">如果未指定排名，则将为策略分配授予最低级别。</span><span class="sxs-lookup"><span data-stu-id="33d29-266">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="33d29-267">安装并连接到 Microsoft 团队 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="33d29-267">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="33d29-268">这些 cmdlet 位于团队 PowerShell 模块的预发布版本中。</span><span class="sxs-lookup"><span data-stu-id="33d29-268">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="33d29-269">按照以下步骤，首先卸载团队 PowerShell 模块的通用版本（如果已安装），然后从 PowerShell 测试库安装该模块的最新预发布版本。</span><span class="sxs-lookup"><span data-stu-id="33d29-269">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="33d29-270">如果尚未执行此操作，请运行以下操作以将 PowerShell 测试库注册为受信任的来源。</span><span class="sxs-lookup"><span data-stu-id="33d29-270">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="33d29-271">如果你安装了通用版本的团队 PowerShell 模块，请运行以下程序将其卸载。</span><span class="sxs-lookup"><span data-stu-id="33d29-271">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="33d29-272">运行以下操作，从 PowerShell 测试库中安装最新的 Microsoft 团队 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="33d29-272">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="33d29-273">运行以下操作以连接到团队并启动会话。</span><span class="sxs-lookup"><span data-stu-id="33d29-273">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="33d29-274">出现提示时，请使用管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="33d29-274">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="33d29-275">为组分配策略</span><span class="sxs-lookup"><span data-stu-id="33d29-275">Assign a policy to a group</span></span>

<span data-ttu-id="33d29-276">在此示例中，我们使用 ```New-CsGroupPolicyAssignment``` cmdlet 将名为零售经理会议策略的团队会议策略分配给分配等级为1的组。</span><span class="sxs-lookup"><span data-stu-id="33d29-276">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="33d29-277">若要了解详细信息，请参阅[CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="33d29-277">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="33d29-278">获取组的策略分配</span><span class="sxs-lookup"><span data-stu-id="33d29-278">Get policy assignments for a group</span></span>

<span data-ttu-id="33d29-279">使用 ```Get-CsGroupPolicyAssignment``` cmdlet 获取分配给组的所有策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-279">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="33d29-280">请注意，组始终按组 Id 列出，即使其 SIP 地址或电子邮件地址用于分配策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-280">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="33d29-281">在此示例中，我们将检索分配给特定组的所有策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-281">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="33d29-282">在此示例中，我们将返回分配有团队会议策略的所有组。</span><span class="sxs-lookup"><span data-stu-id="33d29-282">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="33d29-283">若要了解详细信息，请参阅[CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="33d29-283">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="33d29-284">从组中删除策略</span><span class="sxs-lookup"><span data-stu-id="33d29-284">Remove a policy from a group</span></span>

<span data-ttu-id="33d29-285">使用 ```Remove-CsGroupPolicyAssignment``` cmdlet 从组中删除策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-285">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="33d29-286">从组中删除策略时，将更新分配给该组的相同类型的其他策略的优先级和较低级别的其他策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-286">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="33d29-287">例如，如果删除分级为2的策略，则级别为3和4的策略将更新，以反映其新排名。</span><span class="sxs-lookup"><span data-stu-id="33d29-287">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="33d29-288">下面的两个表显示了此示例。</span><span class="sxs-lookup"><span data-stu-id="33d29-288">The following two tables show this example.</span></span>

<span data-ttu-id="33d29-289">下面列出了团队会议策略的策略分配和优先级。</span><span class="sxs-lookup"><span data-stu-id="33d29-289">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="33d29-290">组名称</span><span class="sxs-lookup"><span data-stu-id="33d29-290">Group name</span></span>  |<span data-ttu-id="33d29-291">策略名称</span><span class="sxs-lookup"><span data-stu-id="33d29-291">Policy name</span></span>  |<span data-ttu-id="33d29-292">等级</span><span class="sxs-lookup"><span data-stu-id="33d29-292">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="33d29-293">销售</span><span class="sxs-lookup"><span data-stu-id="33d29-293">Sales</span></span>    |<span data-ttu-id="33d29-294">销售政策</span><span class="sxs-lookup"><span data-stu-id="33d29-294">Sales policy</span></span>       | <span data-ttu-id="33d29-295">1</span><span class="sxs-lookup"><span data-stu-id="33d29-295">1</span></span>        |
|<span data-ttu-id="33d29-296">西部区域</span><span class="sxs-lookup"><span data-stu-id="33d29-296">West Region</span></span>     |<span data-ttu-id="33d29-297">West 区域策略</span><span class="sxs-lookup"><span data-stu-id="33d29-297">West Region policy</span></span>         |<span data-ttu-id="33d29-298">2</span><span class="sxs-lookup"><span data-stu-id="33d29-298">2</span></span>         |
|<span data-ttu-id="33d29-299">单位</span><span class="sxs-lookup"><span data-stu-id="33d29-299">Division</span></span>    |<span data-ttu-id="33d29-300">部门策略</span><span class="sxs-lookup"><span data-stu-id="33d29-300">Division policy</span></span>         |<span data-ttu-id="33d29-301">3</span><span class="sxs-lookup"><span data-stu-id="33d29-301">3</span></span>         |
|<span data-ttu-id="33d29-302">附属</span><span class="sxs-lookup"><span data-stu-id="33d29-302">Subsidiary</span></span>   |<span data-ttu-id="33d29-303">附属政策</span><span class="sxs-lookup"><span data-stu-id="33d29-303">Subsidiary policy</span></span>        |<span data-ttu-id="33d29-304">4</span><span class="sxs-lookup"><span data-stu-id="33d29-304">4</span></span>         |

<span data-ttu-id="33d29-305">如果我们删除 "西部" 区域组中的 "西部" 区域策略，策略分配和优先级将按如下方式更新。</span><span class="sxs-lookup"><span data-stu-id="33d29-305">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="33d29-306">组名称</span><span class="sxs-lookup"><span data-stu-id="33d29-306">Group name</span></span>  |<span data-ttu-id="33d29-307">策略名称</span><span class="sxs-lookup"><span data-stu-id="33d29-307">Policy name</span></span>  |<span data-ttu-id="33d29-308">等级</span><span class="sxs-lookup"><span data-stu-id="33d29-308">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="33d29-309">销售</span><span class="sxs-lookup"><span data-stu-id="33d29-309">Sales</span></span>    |<span data-ttu-id="33d29-310">销售政策</span><span class="sxs-lookup"><span data-stu-id="33d29-310">Sales policy</span></span>       | <span data-ttu-id="33d29-311">1</span><span class="sxs-lookup"><span data-stu-id="33d29-311">1</span></span>        |
|<span data-ttu-id="33d29-312">单位</span><span class="sxs-lookup"><span data-stu-id="33d29-312">Division</span></span>    |<span data-ttu-id="33d29-313">部门策略</span><span class="sxs-lookup"><span data-stu-id="33d29-313">Division policy</span></span>         |<span data-ttu-id="33d29-314">2</span><span class="sxs-lookup"><span data-stu-id="33d29-314">2</span></span>         |
|<span data-ttu-id="33d29-315">附属</span><span class="sxs-lookup"><span data-stu-id="33d29-315">Subsidiary</span></span>   |<span data-ttu-id="33d29-316">附属政策</span><span class="sxs-lookup"><span data-stu-id="33d29-316">Subsidiary policy</span></span>        |<span data-ttu-id="33d29-317">3</span><span class="sxs-lookup"><span data-stu-id="33d29-317">3</span></span>        |

<span data-ttu-id="33d29-318">在此示例中，我们从组中删除团队会议策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-318">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="33d29-319">若要了解详细信息，请参阅[删除-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="33d29-319">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="33d29-320">更改组的策略分配</span><span class="sxs-lookup"><span data-stu-id="33d29-320">Change a policy assignment for a group</span></span>

<span data-ttu-id="33d29-321">为组分配策略后，可以使用 ```Set-CsGroupPolicyAssignmentd``` cmdlet 更改该组的策略分配，如下所示：</span><span class="sxs-lookup"><span data-stu-id="33d29-321">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignmentd``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="33d29-322">更改排名</span><span class="sxs-lookup"><span data-stu-id="33d29-322">Change the ranking</span></span>
- <span data-ttu-id="33d29-323">更改给定策略类型的策略</span><span class="sxs-lookup"><span data-stu-id="33d29-323">Change the policy of a given policy type</span></span>
- <span data-ttu-id="33d29-324">更改给定策略类型和排名的策略</span><span class="sxs-lookup"><span data-stu-id="33d29-324">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="33d29-325">在此示例中，我们将组的团队更改为名为 SupportCallPark 的策略，并将工作分配排名设置为3。</span><span class="sxs-lookup"><span data-stu-id="33d29-325">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="33d29-326">若要了解详细信息，请参阅[设置 CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="33d29-326">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="33d29-327">更改用户的有效策略</span><span class="sxs-lookup"><span data-stu-id="33d29-327">Change the effective policy for a user</span></span>

<span data-ttu-id="33d29-328">下面是如何更改直接分配了策略的用户的有效策略的示例。</span><span class="sxs-lookup"><span data-stu-id="33d29-328">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="33d29-329">首先，我们将 ```Get-CsUserPolicyAssignment``` cmdlet 与参数结合使用， ```PolicySource``` 以获取与用户相关联的团队会议广播策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="33d29-329">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="33d29-330">若要了解详细信息，请参阅[CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="33d29-330">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="33d29-331">输出显示用户直接分配有名为员工事件的团队会议广播策略，该策略优先于分配给用户所属组的名为 "供应商实时事件" 的策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-331">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="33d29-332">现在，我们将从用户中删除 "员工活动" 策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-332">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="33d29-333">这意味着用户不再有团队会议广播策略直接分配给他们，并且将继承分配给用户所属组的供应商实时事件策略。</span><span class="sxs-lookup"><span data-stu-id="33d29-333">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="33d29-334">使用 Skype for Business PowerShell 模块中的以下 cmdlet 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="33d29-334">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="33d29-335">你可以使用团队 Powershell 模块中的以下 cmdlet 通过批处理策略分配以缩放方式执行此操作，其中 $users 是你指定的用户的列表。</span><span class="sxs-lookup"><span data-stu-id="33d29-335">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="33d29-336">将策略包分配给一批用户</span><span class="sxs-lookup"><span data-stu-id="33d29-336">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="33d29-337">通过批处理策略程序包分配，您可以一次性为大型用户分配策略包，而无需使用脚本。</span><span class="sxs-lookup"><span data-stu-id="33d29-337">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="33d29-338">使用 ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet 提交要分配的一批用户和策略包。</span><span class="sxs-lookup"><span data-stu-id="33d29-338">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="33d29-339">作业作为后台操作处理，并为每个批处理生成操作 ID。</span><span class="sxs-lookup"><span data-stu-id="33d29-339">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="33d29-340">然后，你可以使用该 ```Get-CsBatchPolicyAssignmentOperation``` cmdlet 跟踪批处理中作业的进度和状态。</span><span class="sxs-lookup"><span data-stu-id="33d29-340">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="33d29-341">批处理最多可包含20000个用户。</span><span class="sxs-lookup"><span data-stu-id="33d29-341">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="33d29-342">你可以按对象 Id、UPN、SIP 地址或电子邮件地址指定用户。</span><span class="sxs-lookup"><span data-stu-id="33d29-342">You can specify users by their object Id, UPN, SIP address, or email address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33d29-343">我们当前建议你一次为每批5000用户分配策略包。</span><span class="sxs-lookup"><span data-stu-id="33d29-343">We're currently recommending that you assign policy packages in batches of 5,000 users at a time.</span></span> <span data-ttu-id="33d29-344">在增加需求的这些时间内，你可能会遇到处理时间方面的延迟。</span><span class="sxs-lookup"><span data-stu-id="33d29-344">During these times of increased demand, you may experience delays in processing times.</span></span> <span data-ttu-id="33d29-345">为了将这些增加的处理时间的影响降到最低，我们建议你向5000用户提交较小的批处理大小，并且仅在上一个批处理完成后再提交。</span><span class="sxs-lookup"><span data-stu-id="33d29-345">To minimize the impact of these increased processing times, we suggest that you submit smaller batch sizes of up to 5,000 users, and submit each batch only after the previous one is completed.</span></span> <span data-ttu-id="33d29-346">在正常工作时间内提交批还会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="33d29-346">Submitting batches outside your regular business hours can also help.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="33d29-347">安装并连接到 Microsoft 团队 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="33d29-347">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="33d29-348">运行以下操作以安装[Microsoft 团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams)（如果尚未安装）。</span><span class="sxs-lookup"><span data-stu-id="33d29-348">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="33d29-349">请确保安装1.0.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="33d29-349">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="33d29-350">运行以下操作以连接到团队并启动会话。</span><span class="sxs-lookup"><span data-stu-id="33d29-350">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="33d29-351">出现提示时，请使用管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="33d29-351">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="33d29-352">将策略包分配给一批用户</span><span class="sxs-lookup"><span data-stu-id="33d29-352">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="33d29-353">在此示例中，我们使用 ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet 将 Education_PrimaryStudent 策略包分配给一批用户。</span><span class="sxs-lookup"><span data-stu-id="33d29-353">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="33d29-354">若要了解详细信息，请参阅[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)。</span><span class="sxs-lookup"><span data-stu-id="33d29-354">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="33d29-355">获取批处理作业的状态</span><span class="sxs-lookup"><span data-stu-id="33d29-355">Get the status of a batch assignment</span></span>

<span data-ttu-id="33d29-356">运行以下操作以获取批处理作业的状态，其中 OperationId 是由给定批处理的 cmdlet 返回的操作 ID ```New-CsBatchPolicyAssignmentOperation``` 。</span><span class="sxs-lookup"><span data-stu-id="33d29-356">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="33d29-357">如果输出显示发生了错误，请运行以下内容以获取有关属性中的错误的详细信息 ```UserState``` 。</span><span class="sxs-lookup"><span data-stu-id="33d29-357">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="33d29-358">若要了解详细信息，请参阅[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)。</span><span class="sxs-lookup"><span data-stu-id="33d29-358">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="33d29-359">相关主题</span><span class="sxs-lookup"><span data-stu-id="33d29-359">Related topics</span></span>

- [<span data-ttu-id="33d29-360">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="33d29-360">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)