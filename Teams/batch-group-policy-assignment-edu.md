---
title: 向学校的大型用户组分配策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: karsmith, angch, cebulnes
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何根据组成员身份或直接通过用于远程学校（teleschool、长途）的批处理作业向你的教育机构中的大型用户组分配策略。
f1keywords: ''
ms.openlocfilehash: 0b4fd804b51fef9537d30230aed400bb0cb7e0aa
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2020
ms.locfileid: "46534075"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="b18ce-103">向学校的大型用户组分配策略</span><span class="sxs-lookup"><span data-stu-id="b18ce-103">Assign policies to large sets of users in your school</span></span>

> [!NOTE]
> <span data-ttu-id="b18ce-104">有关在 Microsoft 团队中分配策略的较大情景，请参阅为[团队中的用户分配策略](assign-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b18ce-104">For the larger story on assigning policies in Microsoft Teams, see [Assign policies to your users in Teams](assign-policies.md).</span></span>

## <a name="overview"></a><span data-ttu-id="b18ce-105">概述</span><span class="sxs-lookup"><span data-stu-id="b18ce-105">Overview</span></span>

<span data-ttu-id="b18ce-106">您是否需要为学生和教育部门提供对 Microsoft 团队中的不同功能的访问权限？</span><span class="sxs-lookup"><span data-stu-id="b18ce-106">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="b18ce-107">你可以按许可证类型快速标识组织中的用户，然后为其分配相应的策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-107">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="b18ce-108">本教程介绍如何为你的学校中的大型用户分配会议策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-108">This tutorial shows you how to assign a meeting policy to large sets of users in your school.</span></span> <span data-ttu-id="b18ce-109">你可以使用 Microsoft 团队管理中心和 PowerShell 分配策略，我们将向你显示两种方法。</span><span class="sxs-lookup"><span data-stu-id="b18ce-109">You can assign policies using the Microsoft Teams admin center and PowerShell and we'll show you both ways.</span></span>

<span data-ttu-id="b18ce-110">你可以将会议策略分配给用户是其成员的安全组，也可以通过批量策略分配将其直接分配给用户。</span><span class="sxs-lookup"><span data-stu-id="b18ce-110">You can assign a meeting policy to a security group that the users are members of or directly to users at scale through a batch policy assignment.</span></span> <span data-ttu-id="b18ce-111">你将了解以下内容：</span><span class="sxs-lookup"><span data-stu-id="b18ce-111">You'll learn how to:</span></span>

- <span data-ttu-id="b18ce-112">**使用[组策略分配](#assign-a-policy-to-a-group)将会议策略分配给安全组（推荐）**。</span><span class="sxs-lookup"><span data-stu-id="b18ce-112">**Use [policy assignment to groups](#assign-a-policy-to-a-group) to assign a meeting policy to a security group (recommended)**.</span></span> <span data-ttu-id="b18ce-113">此方法允许你根据组成员身份分配策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-113">This method lets you assign a policy based on group membership.</span></span> <span data-ttu-id="b18ce-114">可以向安全组或通讯组列表分配策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-114">You can assign a policy to a security group or distribution list.</span></span> <span data-ttu-id="b18ce-115">将成员添加到组或从组中删除成员后，将相应地更新其继承的策略分配。</span><span class="sxs-lookup"><span data-stu-id="b18ce-115">As members are added to or removed from the group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="b18ce-116">我们建议你使用此方法，因为它减少了管理新用户的策略的时间或用户的角色更改时间。</span><span class="sxs-lookup"><span data-stu-id="b18ce-116">We recommend you use this method because it reduces the time to manage policies for new users or when users' roles change.</span></span> <span data-ttu-id="b18ce-117">此方法最适用于最多为50000用户的组，但也可用于更大的组。</span><span class="sxs-lookup"><span data-stu-id="b18ce-117">This method works best for groups of up to 50,000 users but will also work with larger groups.</span></span>

- <span data-ttu-id="b18ce-118">**使用批量[策略分配](assign-policies.md#assign-a-policy-to-a-batch-of-users)将会议策略直接分配给用户**。</span><span class="sxs-lookup"><span data-stu-id="b18ce-118">**Use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy directly to users in bulk**.</span></span> <span data-ttu-id="b18ce-119">你可以一次为多达5000用户分配一个策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-119">You can assign a policy for up to 5,000 users at a time.</span></span> <span data-ttu-id="b18ce-120">如果您有超过5000的用户，则可以提交多个批次。</span><span class="sxs-lookup"><span data-stu-id="b18ce-120">If you have more than 5,000 users, you can submit multiple batches.</span></span> <span data-ttu-id="b18ce-121">使用此方法时，当你拥有新用户时，你需要重新运行批处理分配以将策略分配给这些新用户。</span><span class="sxs-lookup"><span data-stu-id="b18ce-121">With this method, when you have new users, you'll need to re-run the batch assignment to assign the policy to those new users.</span></span>

<span data-ttu-id="b18ce-122">请记住，在团队中，用户将自动获取团队策略类型的全局（组织范围默认）策略，除非你创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-122">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="b18ce-123">由于学生填充通常是最大的一组用户，并且通常会收到限制性最严格的设置，因此我们建议你执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b18ce-123">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="b18ce-124">创建允许核心功能（如私人聊天和会议计划）的自定义策略，并向您的员工和教育部门分配策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-124">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>
- <span data-ttu-id="b18ce-125">将自定义策略分配给教职员工和教育版。</span><span class="sxs-lookup"><span data-stu-id="b18ce-125">Assign the custom policy to your staff and educators.</span></span>
- <span data-ttu-id="b18ce-126">编辑和应用全局（组织范围默认）策略以限制学生的功能。</span><span class="sxs-lookup"><span data-stu-id="b18ce-126">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span>

<span data-ttu-id="b18ce-127">请记住，全局策略将应用于你的学校中的所有用户，直到你创建自定义策略并将其分配给你的员工和教育版。</span><span class="sxs-lookup"><span data-stu-id="b18ce-127">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="b18ce-128">在本教程中，学生将获得全局会议策略，我们会将名为 EducatorMeetingPolicy 的自定义会议策略分配给教职员工和教育版。</span><span class="sxs-lookup"><span data-stu-id="b18ce-128">In this tutorial, students will get the Global meeting policy and we'll assign a custom meeting policy named EducatorMeetingPolicy to staff and educators.</span></span> <span data-ttu-id="b18ce-129">我们假定你已编辑全局策略，以便为学生自定义会议设置，并创建定义教职员工和教育版会议体验的[自定义策略](policy-packages-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="b18ce-129">We assume that you've edited the Global policy to tailor meeting settings for students and [created a custom policy](policy-packages-edu.md) that defines the meeting experience for staff and educators.</span></span>

![团队管理中心中的 "会议策略" 页面的屏幕截图](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="b18ce-131">为组分配策略</span><span class="sxs-lookup"><span data-stu-id="b18ce-131">Assign a policy to a group</span></span>

<span data-ttu-id="b18ce-132">按照以下步骤为你的教职员工和教育版创建一个安全组，然后将名为 EducatorMeetingPolicy 的自定义会议策略分配给该安全组。</span><span class="sxs-lookup"><span data-stu-id="b18ce-132">Follow these steps to create a security group for your staff and educators, and then assign a custom meeting policy named EducatorMeetingPolicy to that security group.</span></span>

### <a name="before-you-get-started"></a><span data-ttu-id="b18ce-133">开始之前</span><span class="sxs-lookup"><span data-stu-id="b18ce-133">Before you get started</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b18ce-134">向组分配策略时，将根据优先级规则将策略分配传播到该组的成员。</span><span class="sxs-lookup"><span data-stu-id="b18ce-134">When you assign a policy to a group, the policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="b18ce-135">例如，如果用户直接分配策略（单独或通过批处理作业），则该策略优先于从组继承的策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-135">For example, if a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence over a policy that's inherited from a group.</span></span> <span data-ttu-id="b18ce-136">这还意味着如果用户具有直接分配给他们的会议策略，则必须先删除该用户的会议策略，然后他们才能从安全组继承会议策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-136">This also means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="b18ce-137">在开始之前，了解[优先级规则](assign-policies.md#precedence-rules)和[组分配的排名](assign-policies.md#group-assignment-ranking)非常重要。</span><span class="sxs-lookup"><span data-stu-id="b18ce-137">Before you get started, it's important to understand [precedence rules](assign-policies.md#precedence-rules) and [group assignment ranking](assign-policies.md#group-assignment-ranking).</span></span> <span data-ttu-id="b18ce-138">**请确保阅读并理解[有关对组的策略分配所需了解](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)的概念**。</span><span class="sxs-lookup"><span data-stu-id="b18ce-138">**Make sure that you read and understand the concepts in [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span></span>

<span data-ttu-id="b18ce-139">您需要完成所有这些步骤，让您的员工和教师从安全组继承会议策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-139">You'll need to complete all these steps for your staff and educators to inherit a meeting policy from a security group.</span></span>

1. <span data-ttu-id="b18ce-140">[创建安全组](#create-security-groups)。</span><span class="sxs-lookup"><span data-stu-id="b18ce-140">[Create security groups](#create-security-groups).</span></span>
2. <span data-ttu-id="b18ce-141">向[安全组分配策略](#assign-a-policy-to-a-security-group)。</span><span class="sxs-lookup"><span data-stu-id="b18ce-141">[Assign a policy to a security group](#assign-a-policy-to-a-security-group).</span></span>
3. <span data-ttu-id="b18ce-142">[删除直接分配给用户的策略](#remove-a-policy-that-was-directly-assigned-to-users)。</span><span class="sxs-lookup"><span data-stu-id="b18ce-142">[Remove a policy that was directly assigned to users](#remove-a-policy-that-was-directly-assigned-to-users).</span></span>

### <a name="create-security-groups"></a><span data-ttu-id="b18ce-143">创建安全组</span><span class="sxs-lookup"><span data-stu-id="b18ce-143">Create security groups</span></span>

<span data-ttu-id="b18ce-144">首先，为您的教职员工和教育版创建一个安全组。</span><span class="sxs-lookup"><span data-stu-id="b18ce-144">First, create a security group for your staff and educators.</span></span>

<span data-ttu-id="b18ce-145">通过[学校数据同步](https://docs.microsoft.com/SchoolDataSync/)（SDS），你可以轻松地在你的学校中[创建教师和学生的安全组](https://docs.microsoft.com/SchoolDataSync/edu-security-groups)。</span><span class="sxs-lookup"><span data-stu-id="b18ce-145">With [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS), you can [easily create security groups educators and students](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) in your school.</span></span> <span data-ttu-id="b18ce-146">我们建议你使用 SDS 创建管理你的学校策略所需的安全组。</span><span class="sxs-lookup"><span data-stu-id="b18ce-146">We recommend that you use SDS to create the security groups you need to manage policies for your school.</span></span>

<span data-ttu-id="b18ce-147">如果你无法在你的环境中部署 SDS，请使用[此 PowerShell 脚本](scripts/powershell-script-security-groups-edu.md)创建两个安全组，一个用于分配有教职员许可证的所有职员和教师，另一个用于分配有学生许可证的学生。</span><span class="sxs-lookup"><span data-stu-id="b18ce-147">If you're unable to deploy SDS within your environment, use [this PowerShell script](scripts/powershell-script-security-groups-edu.md) to create two security groups, one for all staff and educators who have a Faculty license assigned and another for all students who have a Student license assigned.</span></span> <span data-ttu-id="b18ce-148">您需要定期运行此脚本以使组保持最新和最新状态。</span><span class="sxs-lookup"><span data-stu-id="b18ce-148">You'll need to run this script routinely to keep the groups fresh and up to date.</span></span>

### <a name="assign-a-policy-to-a-security-group"></a><span data-ttu-id="b18ce-149">向安全组分配策略</span><span class="sxs-lookup"><span data-stu-id="b18ce-149">Assign a policy to a security group</span></span>

#### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b18ce-150">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="b18ce-150">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="b18ce-151">目前，对使用 Microsoft 团队管理中心的组的策略分配仅适用于团队调用策略、团队呼叫驻留策略、团队策略、团队实时事件策略、团队会议策略和团队消息策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-151">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="b18ce-152">对于其他策略类型，请使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b18ce-152">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="b18ce-153">在 Microsoft 团队管理中心的左侧导航中，转到 "**会议**  >  **会议策略**"。</span><span class="sxs-lookup"><span data-stu-id="b18ce-153">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="b18ce-154">选择 "**组策略分配**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b18ce-154">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="b18ce-155">选择 "**添加组**"，然后在 "向**组分配策略**" 窗格中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b18ce-155">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>

    ![显示会议策略的 "编辑设置" 窗格的屏幕截图](media/batch-group-policy-assignment-edu-group.png)
    1. <span data-ttu-id="b18ce-157">在 "**选择组**" 框中，搜索并添加包含您的教职员工和教育版的安全组。</span><span class="sxs-lookup"><span data-stu-id="b18ce-157">In the **Select a group** box, search for and add the security group that contains your staff and educators.</span></span>
    2. <span data-ttu-id="b18ce-158">在 "**选择排名**" 框中，输入**1**。</span><span class="sxs-lookup"><span data-stu-id="b18ce-158">In the **Select rank** box, enter **1**.</span></span>
    3. <span data-ttu-id="b18ce-159">在 "**选择策略**" 框中，选择 " **EducatorMeetingPolicy**"。</span><span class="sxs-lookup"><span data-stu-id="b18ce-159">In the **Select a policy** box, select **EducatorMeetingPolicy**.</span></span>
    4. <span data-ttu-id="b18ce-160">选择 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="b18ce-160">Select **Apply**.</span></span>

<span data-ttu-id="b18ce-161">若要删除组策略分配，请在 "策略" 页面的 "**组策略分配**" 选项卡上，选择 "组分配"，然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="b18ce-161">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="b18ce-162">若要更改组分配的排名，必须首先删除组策略分配。</span><span class="sxs-lookup"><span data-stu-id="b18ce-162">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="b18ce-163">然后，按照上述步骤将策略分配给组。</span><span class="sxs-lookup"><span data-stu-id="b18ce-163">Then, follow the steps above to assign the policy to a group.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="b18ce-164">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b18ce-164">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="b18ce-165">目前，对使用 PowerShell 的组的策略分配不可用于所有团队策略类型。</span><span class="sxs-lookup"><span data-stu-id="b18ce-165">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="b18ce-166">有关受支持的策略类型列表，请参阅[CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 。</span><span class="sxs-lookup"><span data-stu-id="b18ce-166">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="b18ce-167">安装并连接到 Microsoft 团队 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="b18ce-167">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="b18ce-168">运行以下操作以安装[团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams)（如果尚未安装）。</span><span class="sxs-lookup"><span data-stu-id="b18ce-168">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="b18ce-169">请确保安装1.0.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="b18ce-169">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="b18ce-170">运行以下操作以连接到团队并启动会话。</span><span class="sxs-lookup"><span data-stu-id="b18ce-170">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="b18ce-171">出现提示时，请使用管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="b18ce-171">When you're prompted, sign in using your admin credentials.</span></span>

##### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="b18ce-172">为组分配策略</span><span class="sxs-lookup"><span data-stu-id="b18ce-172">Assign a policy to a group</span></span>

<span data-ttu-id="b18ce-173">运行以下操作，将名为 EducatorMeetingPolicy 的会议策略分配给包含你的教职员工和教育版的安全组，并将工作分配排名设置为1。</span><span class="sxs-lookup"><span data-stu-id="b18ce-173">Run the following to assign the meeting policy named EducatorMeetingPolicy to the security group that contains your staff and educators and set the assignment ranking to 1.</span></span> <span data-ttu-id="b18ce-174">可以通过使用对象 Id、会话初始协议（SIP）地址或电子邮件地址来指定安全组。</span><span class="sxs-lookup"><span data-stu-id="b18ce-174">You can specify a security group by using the object Id, Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="b18ce-175">在此示例中，我们使用电子邮件地址（staff-faculty@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="b18ce-175">In this example, we use an email address (staff-faculty@contoso.com).</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="b18ce-176">删除直接分配给用户的策略</span><span class="sxs-lookup"><span data-stu-id="b18ce-176">Remove a policy that was directly assigned to users</span></span>

<span data-ttu-id="b18ce-177">请记住，如果用户直接分配策略（单独或通过批处理作业），则该策略优先。</span><span class="sxs-lookup"><span data-stu-id="b18ce-177">Remember that if a user was directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="b18ce-178">这意味着，如果用户具有直接分配给他们的会议策略，则必须先删除该用户的会议策略，然后他们才能从安全组继承会议策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-178">This means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="b18ce-179">若要了解详细信息，请参阅[对组的策略分配需要了解的信息](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)。</span><span class="sxs-lookup"><span data-stu-id="b18ce-179">To learn more, see [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span></span>

<span data-ttu-id="b18ce-180">按照以下步骤删除直接分配给你的员工和教育版的会议策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-180">Follow these steps to remove the meeting policy that was directly assigned to your staff and educators.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="b18ce-181">安装并连接到 Microsoft 团队 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="b18ce-181">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="b18ce-182">运行以下操作以安装[团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams)（如果尚未安装）。</span><span class="sxs-lookup"><span data-stu-id="b18ce-182">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="b18ce-183">请确保安装1.0.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="b18ce-183">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="b18ce-184">运行以下操作以连接到团队并启动会话。</span><span class="sxs-lookup"><span data-stu-id="b18ce-184">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="b18ce-185">出现提示时，请使用您用于连接到 Azure AD 的相同管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="b18ce-185">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="b18ce-186">取消分配直接分配给用户的策略</span><span class="sxs-lookup"><span data-stu-id="b18ce-186">Unassign a policy that was directly assigned to users</span></span>

<span data-ttu-id="b18ce-187">运行以下操作以删除直接分配该策略的用户的会议策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-187">Run the following to remove a meeting policy from users who were directly assigned that policy.</span></span> <span data-ttu-id="b18ce-188">你可以通过电子邮件地址或对象 ID 指定用户。</span><span class="sxs-lookup"><span data-stu-id="b18ce-188">You can specify users by email address or object ID.</span></span>

<span data-ttu-id="b18ce-189">在此示例中，将从由其电子邮件地址指定的用户中删除会议策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-189">In this example, the meeting policy is removed from users specified by their email address.</span></span>

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

<span data-ttu-id="b18ce-190">在此示例中，将从名为 user_ids.txt 的文本文件的用户列表中删除会议策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-190">In this example, the meeting policy is removed from the list of users in a text file named user_ids.txt.</span></span> 

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="b18ce-191">获取组的策略分配</span><span class="sxs-lookup"><span data-stu-id="b18ce-191">Get policy assignments for a group</span></span>

<span data-ttu-id="b18ce-192">运行以下操作，查看分配给特定安全组的所有策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-192">Run the following to see all the policies assigned to a specific security group.</span></span> <span data-ttu-id="b18ce-193">请注意，组始终按组 Id 列出，即使其 SIP 地址或电子邮件地址用于分配策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-193">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="b18ce-194">获取分配给用户的策略</span><span class="sxs-lookup"><span data-stu-id="b18ce-194">Get the policies assigned to a user</span></span>

<span data-ttu-id="b18ce-195">运行以下操作，查看分配给特定用户的所有策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-195">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="b18ce-196">下面的示例演示如何获取分配给 reda@contoso.com 的策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-196">The following example shows you how to get the policies that are assigned to reda@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="b18ce-197">为一批用户分配策略</span><span class="sxs-lookup"><span data-stu-id="b18ce-197">Assign a policy to a batch of users</span></span>

<span data-ttu-id="b18ce-198">请按照以下步骤将名为 EducatorMeetingPolicy 的自定义会议策略直接分配给你的员工并批量教育。</span><span class="sxs-lookup"><span data-stu-id="b18ce-198">Follow these steps to assign a custom meeting policy named EducatorMeetingPolicy directly to your staff and educators in bulk.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b18ce-199">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b18ce-199">Using PowerShell</span></span>

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="b18ce-200">连接到适用于 Graph 模块和团队 PowerShell 模块的 Azure AD PowerShell</span><span class="sxs-lookup"><span data-stu-id="b18ce-200">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="b18ce-201">在执行本文中的步骤之前，你需要安装并连接到 Azure AD PowerShell for Graph 模块（以通过其分配的许可证标识用户）和 Microsoft 团队 PowerShell 模块（将策略分配给这些用户）。</span><span class="sxs-lookup"><span data-stu-id="b18ce-201">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="b18ce-202">安装并连接到 Azure AD PowerShell for Graph 模块</span><span class="sxs-lookup"><span data-stu-id="b18ce-202">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="b18ce-203">打开提升了权限的 Windows PowerShell 命令提示符（以管理员身份运行 Windows PowerShell），然后运行以下命令来安装适用于 Graph 模块的 Azure Active Directory PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b18ce-203">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="b18ce-204">运行以下操作以连接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="b18ce-204">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="b18ce-205">出现提示时，请使用管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="b18ce-205">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="b18ce-206">若要了解详细信息，请参阅[连接到 Azure Active Directory PowerShell For Graph 模块](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="b18ce-206">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="b18ce-207">安装并连接到 Microsoft 团队 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="b18ce-207">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="b18ce-208">运行以下操作以安装[团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams)（如果尚未安装）。</span><span class="sxs-lookup"><span data-stu-id="b18ce-208">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="b18ce-209">请确保安装1.0.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="b18ce-209">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="b18ce-210">运行以下操作以连接到团队并启动会话。</span><span class="sxs-lookup"><span data-stu-id="b18ce-210">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="b18ce-211">出现提示时，请使用您用于连接到 Azure AD 的相同管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="b18ce-211">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="identify-your-users"></a><span data-ttu-id="b18ce-212">标识您的用户</span><span class="sxs-lookup"><span data-stu-id="b18ce-212">Identify your users</span></span>

<span data-ttu-id="b18ce-213">首先，运行以下操作以通过许可证类型标识你的员工和教师。</span><span class="sxs-lookup"><span data-stu-id="b18ce-213">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="b18ce-214">这将告诉你组织中使用的 Sku。</span><span class="sxs-lookup"><span data-stu-id="b18ce-214">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="b18ce-215">然后，您可以识别已分配教职员 SKU 的职员和教师。</span><span class="sxs-lookup"><span data-stu-id="b18ce-215">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="b18ce-216">返回：</span><span class="sxs-lookup"><span data-stu-id="b18ce-216">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="b18ce-217">在此示例中，输出显示教职员许可证 SkuId 为 "e97c048c-37a4-45fb-ab50-922fbf07a370"。</span><span class="sxs-lookup"><span data-stu-id="b18ce-217">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="b18ce-218">若要查看教育 Sku 和 SKU Id 的列表，请参阅[教育 sku 参考](sku-reference-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="b18ce-218">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="b18ce-219">接下来，我们运行以下内容来确定拥有此许可证的用户，并将它们一起收集。</span><span class="sxs-lookup"><span data-stu-id="b18ce-219">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="b18ce-220">批量分配策略</span><span class="sxs-lookup"><span data-stu-id="b18ce-220">Assign a policy in bulk</span></span>

<span data-ttu-id="b18ce-221">现在，我们会批量向用户分配适当的策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-221">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="b18ce-222">你可以为其分配或更新策略的最大用户数为每次5000。</span><span class="sxs-lookup"><span data-stu-id="b18ce-222">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="b18ce-223">例如，如果您有超过5000的员工和教育版，则需要提交多个批次。</span><span class="sxs-lookup"><span data-stu-id="b18ce-223">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>

<span data-ttu-id="b18ce-224">运行以下操作，将名为 EducatorMeetingPolicy 的自定义会议策略分配给你的员工和教育版。</span><span class="sxs-lookup"><span data-stu-id="b18ce-224">Run the following to assign a custom meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="b18ce-225">若要批量分配不同的策略类型（如 TeamsMessagingPolicy），你需要更改 ```PolicyType``` 为你分配的策略和 ```PolicyName``` 策略名称。</span><span class="sxs-lookup"><span data-stu-id="b18ce-225">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

#### <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="b18ce-226">获取批量作业的状态</span><span class="sxs-lookup"><span data-stu-id="b18ce-226">Get the status of a bulk assignment</span></span>

<span data-ttu-id="b18ce-227">每个批量分配都将返回一个操作 ID，您可以使用该 ID 跟踪策略分配的进度，或标识可能出现的任何失败。</span><span class="sxs-lookup"><span data-stu-id="b18ce-227">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="b18ce-228">例如，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="b18ce-228">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="b18ce-229">若要查看批处理操作中每个用户的作业状态，请运行以下。</span><span class="sxs-lookup"><span data-stu-id="b18ce-229">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="b18ce-230">每个用户的详细信息都在该 ```UserState``` 属性中。</span><span class="sxs-lookup"><span data-stu-id="b18ce-230">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="b18ce-231">如果用户超过5000个用户，则批量分配策略</span><span class="sxs-lookup"><span data-stu-id="b18ce-231">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="b18ce-232">首先，运行以下内容查看您拥有的职员和教育人数：</span><span class="sxs-lookup"><span data-stu-id="b18ce-232">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="b18ce-233">请运行以下操作以指定第一个5000，然后再指定下一个5000，依此类推，而不是提供整个用户 Id 列表。</span><span class="sxs-lookup"><span data-stu-id="b18ce-233">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="b18ce-234">你可以更改用户 Id 的范围，直到到达用户的完整列表。</span><span class="sxs-lookup"><span data-stu-id="b18ce-234">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="b18ce-235">例如，输入 ```$faculty[0..4999``` 第一个批处理，为第二个批次使用， ```$faculty[5000..9999``` ```$faculty[10000..14999``` 为第三个批处理输入，依此类推。</span><span class="sxs-lookup"><span data-stu-id="b18ce-235">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

#### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="b18ce-236">获取分配给用户的策略</span><span class="sxs-lookup"><span data-stu-id="b18ce-236">Get the policies assigned to a user</span></span>

<span data-ttu-id="b18ce-237">运行以下操作，查看分配给特定用户的所有策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-237">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="b18ce-238">下面的示例演示如何获取分配给 hannah@contoso.com 的策略。</span><span class="sxs-lookup"><span data-stu-id="b18ce-238">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="b18ce-239">常见问题</span><span class="sxs-lookup"><span data-stu-id="b18ce-239">FAQ</span></span>

<span data-ttu-id="b18ce-240">**我不熟悉 PowerShell for 团队。在哪里可以了解更多信息？**</span><span class="sxs-lookup"><span data-stu-id="b18ce-240">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="b18ce-241">有关使用 PowerShell 管理团队的概述，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b18ce-241">For an overview of using PowerShell to manage Teams, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span> <span data-ttu-id="b18ce-242">有关本文中使用的 cmdlet 的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="b18ce-242">For more information about the cmdlets used in this article, see:</span></span>

- [<span data-ttu-id="b18ce-243">新-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="b18ce-243">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [<span data-ttu-id="b18ce-244">CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="b18ce-244">Get-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [<span data-ttu-id="b18ce-245">新-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="b18ce-245">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="b18ce-246">CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="b18ce-246">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="b18ce-247">CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="b18ce-247">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a><span data-ttu-id="b18ce-248">相关主题</span><span class="sxs-lookup"><span data-stu-id="b18ce-248">Related topics</span></span>

- [<span data-ttu-id="b18ce-249">为用户分配策略</span><span class="sxs-lookup"><span data-stu-id="b18ce-249">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="b18ce-250">用于教育的团队政策和政策包</span><span class="sxs-lookup"><span data-stu-id="b18ce-250">Teams policies and policy packages for Education</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="b18ce-251">管理团队中的会议策略</span><span class="sxs-lookup"><span data-stu-id="b18ce-251">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
