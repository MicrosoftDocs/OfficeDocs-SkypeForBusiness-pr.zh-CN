---
title: 为学校中的大量用户分配策略
author: cichur
ms.author: v-cichur
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
description: 了解如何根据组成员身份或直接通过远程学校 (远程学校教师的批处理分配，为教育机构中的大量用户) 策略。
f1keywords: ''
ms.openlocfilehash: f2d36db6a96f6a9a42590ada6600ef38738b30a9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092900"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="b1ac9-103">为学校中的大量用户分配策略</span><span class="sxs-lookup"><span data-stu-id="b1ac9-103">Assign policies to large sets of users in your school</span></span>

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> <span data-ttu-id="b1ac9-104">有关在服务中分配策略的较大Microsoft Teams，请参阅在 Teams[中分配策略](assign-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-104">For the larger story on assigning policies in Microsoft Teams, see [Assign policies to your users in Teams](assign-policies.md).</span></span>

## <a name="overview"></a><span data-ttu-id="b1ac9-105">概述</span><span class="sxs-lookup"><span data-stu-id="b1ac9-105">Overview</span></span>

<span data-ttu-id="b1ac9-106">是否需要为学生和教师提供对应用内不同功能Microsoft Teams？</span><span class="sxs-lookup"><span data-stu-id="b1ac9-106">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="b1ac9-107">可以按许可证类型快速识别组织中用户，然后为其分配适当的策略。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-107">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="b1ac9-108">本教程介绍如何向学校中的大量用户分配会议策略。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-108">This tutorial shows you how to assign a meeting policy to large sets of users in your school.</span></span> <span data-ttu-id="b1ac9-109">可以使用管理中心和 PowerShell Microsoft Teams策略，我们将展示这两种方法。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-109">You can assign policies using the Microsoft Teams admin center and PowerShell and we'll show you both ways.</span></span>

<span data-ttu-id="b1ac9-110">可以将会议策略分配给用户作为成员的安全组，或者直接通过批处理策略分配大规模地将会议策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-110">You can assign a meeting policy to a security group that the users are members of or directly to users at scale through a batch policy assignment.</span></span> <span data-ttu-id="b1ac9-111">你将了解以下内容：</span><span class="sxs-lookup"><span data-stu-id="b1ac9-111">You'll learn how to:</span></span>

- <span data-ttu-id="b1ac9-112">**使用 [组的策略分配](#assign-a-policy-to-a-group)将会议策略分配给安全组 (建议) 。**</span><span class="sxs-lookup"><span data-stu-id="b1ac9-112">**Use [policy assignment to groups](#assign-a-policy-to-a-group) to assign a meeting policy to a security group (recommended)**.</span></span> <span data-ttu-id="b1ac9-113">此方法允许基于组成员身份分配策略。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-113">This method lets you assign a policy based on group membership.</span></span> <span data-ttu-id="b1ac9-114">可以将策略分配到安全组或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-114">You can assign a policy to a security group or distribution list.</span></span> <span data-ttu-id="b1ac9-115">将成员添加到组或删除组时，会相应地更新其继承的策略分配。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-115">As members are added to or removed from the group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="b1ac9-116">我们建议使用此方法，因为这样可以减少管理新用户的策略或用户的角色更改的时间。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-116">We recommend you use this method because it reduces the time to manage policies for new users or when users' roles change.</span></span> <span data-ttu-id="b1ac9-117">此方法最适合最多 50，000 名用户的组，但也适用于较大的组。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-117">This method works best for groups of up to 50,000 users but will also work with larger groups.</span></span>

- <span data-ttu-id="b1ac9-118">**使用 [批处理策略分配](assign-policies.md#assign-a-policy-to-a-batch-of-users) 将会议策略直接批量分配给用户**。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-118">**Use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy directly to users in bulk**.</span></span> <span data-ttu-id="b1ac9-119">一次最多为 5，000 个用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-119">You can assign a policy for up to 5,000 users at a time.</span></span> <span data-ttu-id="b1ac9-120">如果用户数超过 5，000，可以提交多个批次。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-120">If you have more than 5,000 users, you can submit multiple batches.</span></span> <span data-ttu-id="b1ac9-121">使用此方法时，当有新用户时，需要重新运行批处理分配，以将策略分配给这些新用户。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-121">With this method, when you have new users, you'll need to re-run the batch assignment to assign the policy to those new users.</span></span>

<span data-ttu-id="b1ac9-122">请记住，Teams用户会自动获取 Teams 策略类型的全局 (组织范围默认) 策略，除非创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-122">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="b1ac9-123">由于学生群体通常是最大的一组用户，他们通常会收到限制性最严格的设置，因此建议执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b1ac9-123">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="b1ac9-124">创建自定义策略，允许私人聊天和会议计划等核心功能，并将该策略分配给教职员工和教师。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-124">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>
- <span data-ttu-id="b1ac9-125">将自定义策略分配给教职员工和教师。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-125">Assign the custom policy to your staff and educators.</span></span>
- <span data-ttu-id="b1ac9-126">编辑并应用全局 (组织范围内的默认) 策略，以限制学生的功能。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-126">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span>

<span data-ttu-id="b1ac9-127">请记住，在创建自定义策略并将其分配给教职员工和教师之前，全局策略将应用于学校中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-127">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="b1ac9-128">在本教程中，学生将获取全局会议策略，我们将为教职员工和教师分配名为"教师""MeetingPolicy"的自定义会议策略。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-128">In this tutorial, students will get the Global meeting policy and we'll assign a custom meeting policy named EducatorMeetingPolicy to staff and educators.</span></span> <span data-ttu-id="b1ac9-129">我们假定你已编辑全局策略，为学生定制会议设置，并创建了一个[](policy-packages-edu.md)自定义策略，用于定义教职员工和教师的会议体验。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-129">We assume that you've edited the Global policy to tailor meeting settings for students and [created a custom policy](policy-packages-edu.md) that defines the meeting experience for staff and educators.</span></span>

![管理中心内"会议策略"Teams屏幕截图](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="b1ac9-131">向组分配策略</span><span class="sxs-lookup"><span data-stu-id="b1ac9-131">Assign a policy to a group</span></span>

<span data-ttu-id="b1ac9-132">按照以下步骤为教职员工和教师创建安全组，然后将名为"教师""MeetingPolicy"的自定义会议策略分配给该安全组。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-132">Follow these steps to create a security group for your staff and educators, and then assign a custom meeting policy named EducatorMeetingPolicy to that security group.</span></span>

### <a name="before-you-get-started"></a><span data-ttu-id="b1ac9-133">开始之前</span><span class="sxs-lookup"><span data-stu-id="b1ac9-133">Before you get started</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1ac9-134">将策略分配到组时，策略分配将按照优先级规则传播到该组的成员。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-134">When you assign a policy to a group, the policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="b1ac9-135">例如，如果直接为用户分配了策略 (单独分配或批处理分配) ，则该策略优先于从组继承的策略。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-135">For example, if a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence over a policy that's inherited from a group.</span></span> <span data-ttu-id="b1ac9-136">这也意味着，如果用户具有直接分配给他们的会议策略，则你必须从该用户中删除该会议策略，然后他们才能从安全组继承会议策略。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-136">This also means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="b1ac9-137">在开始使用之前，必须了解优先级[规则和](assign-policies.md#precedence-rules)[组分配排名](assign-policies.md#group-assignment-ranking)。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-137">Before you get started, it's important to understand [precedence rules](assign-policies.md#precedence-rules) and [group assignment ranking](assign-policies.md#group-assignment-ranking).</span></span> <span data-ttu-id="b1ac9-138">**请确保阅读并了解有关组的策略分配的信息 [中的概念](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-138">**Make sure that you read and understand the concepts in [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span></span>

<span data-ttu-id="b1ac9-139">你需要完成所有这些步骤，让教职员工和教师从安全组继承会议策略。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-139">You'll need to complete all these steps for your staff and educators to inherit a meeting policy from a security group.</span></span>

1. <span data-ttu-id="b1ac9-140">[创建安全组](#create-security-groups)。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-140">[Create security groups](#create-security-groups).</span></span>
2. <span data-ttu-id="b1ac9-141">[将策略分配给安全组](#assign-a-policy-to-a-security-group)。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-141">[Assign a policy to a security group](#assign-a-policy-to-a-security-group).</span></span>
3. <span data-ttu-id="b1ac9-142">[删除直接分配给用户的策略](#remove-a-policy-that-was-directly-assigned-to-users)。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-142">[Remove a policy that was directly assigned to users](#remove-a-policy-that-was-directly-assigned-to-users).</span></span>

### <a name="create-security-groups"></a><span data-ttu-id="b1ac9-143">创建安全组</span><span class="sxs-lookup"><span data-stu-id="b1ac9-143">Create security groups</span></span>

<span data-ttu-id="b1ac9-144">首先，为教职员工和教师创建安全组。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-144">First, create a security group for your staff and educators.</span></span>

<span data-ttu-id="b1ac9-145">借助[学校数据同步 (](/SchoolDataSync/) SDS) ，可以轻松[创建学校教师和学生](/SchoolDataSync/edu-security-groups)的安全组。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-145">With [School Data Sync](/SchoolDataSync/) (SDS), you can [easily create security groups educators and students](/SchoolDataSync/edu-security-groups) in your school.</span></span> <span data-ttu-id="b1ac9-146">建议使用 SDS 创建管理学校策略所需的安全组。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-146">We recommend that you use SDS to create the security groups you need to manage policies for your school.</span></span>

<span data-ttu-id="b1ac9-147">如果无法在环境中部署 SDS，请使用此 [PowerShell](scripts/powershell-script-security-groups-edu.md) 脚本创建两个安全组，一个安全组用于分配有教职员工许可证的所有教职员工和教师，另一个安全组用于分配有学生许可证的所有学生。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-147">If you're unable to deploy SDS within your environment, use [this PowerShell script](scripts/powershell-script-security-groups-edu.md) to create two security groups, one for all staff and educators who have a Faculty license assigned and another for all students who have a Student license assigned.</span></span> <span data-ttu-id="b1ac9-148">需要定期运行此脚本，使组保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-148">You'll need to run this script routinely to keep the groups fresh and up to date.</span></span>

### <a name="assign-a-policy-to-a-security-group"></a><span data-ttu-id="b1ac9-149">将策略分配给安全组</span><span class="sxs-lookup"><span data-stu-id="b1ac9-149">Assign a policy to a security group</span></span>

#### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b1ac9-150">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="b1ac9-150">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="b1ac9-151">目前，使用 Microsoft Teams 管理中心向组分配策略仅适用于 Teams 呼叫策略、Teams 呼叫公园策略、Teams 策略、Teams 实时事件策略、Teams 会议策略和 Teams 消息策略。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-151">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="b1ac9-152">对于其他策略类型，请使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-152">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="b1ac9-153">在 Microsoft Teams 管理员中心的左侧导航中，转到 **“会议”** > **“会议策略”**。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-153">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="b1ac9-154">选择" **组策略分配"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-154">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="b1ac9-155">选择 **"添加组**"，然后在" **将策略分配到组"窗格中** 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b1ac9-155">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>

    !["编辑设置"窗格的屏幕截图，显示会议策略](media/batch-group-policy-assignment-edu-group.png)
    1. <span data-ttu-id="b1ac9-157">在 **"选择组"** 框中，搜索并添加包含教职员工和教师的安全组。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-157">In the **Select a group** box, search for and add the security group that contains your staff and educators.</span></span>
    2. <span data-ttu-id="b1ac9-158">在"**选择排名"** 框中，输入 **1。**</span><span class="sxs-lookup"><span data-stu-id="b1ac9-158">In the **Select rank** box, enter **1**.</span></span>
    3. <span data-ttu-id="b1ac9-159">在"**选择策略"框中**，选择 **"教师""MeetingPolicy"。**</span><span class="sxs-lookup"><span data-stu-id="b1ac9-159">In the **Select a policy** box, select **EducatorMeetingPolicy**.</span></span>
    4. <span data-ttu-id="b1ac9-160">选择"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="b1ac9-160">Select **Apply**.</span></span>

<span data-ttu-id="b1ac9-161">若要删除组策略分配，请在策略页的"组 **策略** 分配"选项卡上，选择组分配，然后选择"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="b1ac9-161">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="b1ac9-162">若要更改组分配的排名，首先必须删除组策略分配。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-162">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="b1ac9-163">然后，按照上述步骤将策略分配给组。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-163">Then, follow the steps above to assign the policy to a group.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="b1ac9-164">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1ac9-164">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="b1ac9-165">目前，使用 PowerShell 向组分配策略不适用于所有Teams类型。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-165">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="b1ac9-166">有关[支持的策略类型列表，请参阅 New-CsGroupPolicyAssignment。](/powershell/module/teams/new-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="b1ac9-166">See [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="b1ac9-167">安装并连接到 Microsoft Teams PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="b1ac9-167">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="b1ac9-168">运行以下代码，Teams [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams)模块 (（如果尚未) ）。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-168">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="b1ac9-169">请确保安装版本 1.0.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-169">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="b1ac9-170">运行以下代码连接到Teams并启动会话。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-170">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="b1ac9-171">系统提示时，使用管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-171">When you're prompted, sign in using your admin credentials.</span></span>

##### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="b1ac9-172">向组分配策略</span><span class="sxs-lookup"><span data-stu-id="b1ac9-172">Assign a policy to a group</span></span>

<span data-ttu-id="b1ac9-173">运行以下代码，将名为"教师""MeetingPolicy"的会议策略分配给包含教职员工和教师的安全组，并将作业排名设置为 1。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-173">Run the following to assign the meeting policy named EducatorMeetingPolicy to the security group that contains your staff and educators and set the assignment ranking to 1.</span></span> <span data-ttu-id="b1ac9-174">可以使用对象 ID、会话启动协议或 SIP (或电子邮件地址) 安全组。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-174">You can specify a security group by using the object Id, Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="b1ac9-175">本示例使用电子邮件地址 (staff-faculty@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-175">In this example, we use an email address (staff-faculty@contoso.com).</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="b1ac9-176">删除直接分配给用户的策略</span><span class="sxs-lookup"><span data-stu-id="b1ac9-176">Remove a policy that was directly assigned to users</span></span>

<span data-ttu-id="b1ac9-177">请记住，如果直接为用户分配了策略 (单独分配，或者通过批处理分配) ，该策略优先。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-177">Remember that if a user was directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="b1ac9-178">这意味着，如果用户具有直接分配给他们的会议策略，则你必须从该用户中删除该会议策略，然后才能从安全组继承会议策略。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-178">This means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="b1ac9-179">若要了解有关详细信息， [请参阅有关向组分配策略的需知信息](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-179">To learn more, see [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span></span>

<span data-ttu-id="b1ac9-180">请按照以下步骤删除直接分配给教职员工和教师的会议策略。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-180">Follow these steps to remove the meeting policy that was directly assigned to your staff and educators.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="b1ac9-181">安装并连接到 Microsoft Teams PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="b1ac9-181">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="b1ac9-182">运行以下代码，Teams [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams)模块 (（如果尚未) ）。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-182">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="b1ac9-183">请确保安装版本 1.0.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-183">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="b1ac9-184">运行以下代码连接到Teams并启动会话。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-184">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="b1ac9-185">系统提示时，使用用于连接到 Azure AD 的相同管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-185">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="b1ac9-186">取消分配直接分配给用户的策略</span><span class="sxs-lookup"><span data-stu-id="b1ac9-186">Unassign a policy that was directly assigned to users</span></span>

<span data-ttu-id="b1ac9-187">运行以下操作，从直接分配了该策略的用户中删除会议策略。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-187">Run the following to remove a meeting policy from users who were directly assigned that policy.</span></span> <span data-ttu-id="b1ac9-188">可以按电子邮件地址或对象 ID 指定用户。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-188">You can specify users by email address or object ID.</span></span>

<span data-ttu-id="b1ac9-189">此示例中，会议策略已从其电子邮件地址指定的用户中删除。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-189">In this example, the meeting policy is removed from users specified by their email address.</span></span>

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

<span data-ttu-id="b1ac9-190">本示例从名为 user_ids.txt 的文本文件中的用户列表中删除会议user_ids.txt。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-190">In this example, the meeting policy is removed from the list of users in a text file named user_ids.txt.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="b1ac9-191">获取组的策略分配</span><span class="sxs-lookup"><span data-stu-id="b1ac9-191">Get policy assignments for a group</span></span>

<span data-ttu-id="b1ac9-192">运行以下代码，查看分配给特定安全组的所有策略。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-192">Run the following to see all the policies assigned to a specific security group.</span></span> <span data-ttu-id="b1ac9-193">请注意，组始终按组 ID 列出，即使其 SIP 地址或电子邮件地址用于分配策略。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-193">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="b1ac9-194">获取分配给用户的策略</span><span class="sxs-lookup"><span data-stu-id="b1ac9-194">Get the policies assigned to a user</span></span>

<span data-ttu-id="b1ac9-195">运行以下代码，查看分配给特定用户的所有策略。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-195">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="b1ac9-196">以下示例演示如何获取分配给 reda@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-196">The following example shows you how to get the policies that are assigned to reda@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="b1ac9-197">向一批用户分配策略</span><span class="sxs-lookup"><span data-stu-id="b1ac9-197">Assign a policy to a batch of users</span></span>

<span data-ttu-id="b1ac9-198">按照以下步骤将名为"教师""MeetingPolicy"的自定义会议策略直接批量分配给教职员工和教师。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-198">Follow these steps to assign a custom meeting policy named EducatorMeetingPolicy directly to your staff and educators in bulk.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b1ac9-199">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1ac9-199">Using PowerShell</span></span>

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="b1ac9-200">连接 Azure AD PowerShell for Graph 模块和 Teams PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="b1ac9-200">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="b1ac9-201">执行本文中的步骤之前，需要安装并连接到 Azure AD PowerShell for Graph 模块 (，以通过用户分配的许可证) 和 Microsoft Teams PowerShell 模块 (来标识用户，以将策略分配给这些用户) 。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-201">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="b1ac9-202">安装并连接到 Azure AD PowerShell for Graph 模块</span><span class="sxs-lookup"><span data-stu-id="b1ac9-202">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="b1ac9-203">打开提升的 Windows PowerShell 命令提示符 (以管理员 Windows PowerShell 运行) ，然后运行以下命令来安装 Azure Active Directory PowerShell for Graph 模块。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-203">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="b1ac9-204">运行以下代码以连接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-204">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="b1ac9-205">系统提示时，使用管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-205">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="b1ac9-206">若要了解有关详细信息，请参阅连接[PowerShell for Azure Active Directory 模块的 Graph。](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="b1ac9-206">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="b1ac9-207">安装并连接到 Microsoft Teams PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="b1ac9-207">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="b1ac9-208">运行以下代码，Teams [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams)模块 (（如果尚未) ）。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-208">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="b1ac9-209">请确保安装版本 1.0.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-209">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="b1ac9-210">运行以下代码连接到Teams并启动会话。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-210">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="b1ac9-211">系统提示时，使用用于连接到 Azure AD 的相同管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-211">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="identify-your-users"></a><span data-ttu-id="b1ac9-212">标识用户</span><span class="sxs-lookup"><span data-stu-id="b1ac9-212">Identify your users</span></span>

<span data-ttu-id="b1ac9-213">首先，运行以下代码，按许可证类型标识教职员工和教师。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-213">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="b1ac9-214">这可告知组织使用哪些 SKUS。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-214">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="b1ac9-215">然后，可以识别分配了教职员工 SKU 的员工和教师。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-215">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="b1ac9-216">这将返回：</span><span class="sxs-lookup"><span data-stu-id="b1ac9-216">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="b1ac9-217">本示例的输出显示教职员工许可证 SkuId 为"e97c048c-37a4-45fb-ab50-922fbf07a370"。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-217">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="b1ac9-218">若要查看教育 SKU 和 SKU ID 的列表，请参阅 [教育 SKU 参考](sku-reference-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-218">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="b1ac9-219">接下来，运行以下代码来标识拥有此许可证的用户，并收集所有这些用户。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-219">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="b1ac9-220">批量分配策略</span><span class="sxs-lookup"><span data-stu-id="b1ac9-220">Assign a policy in bulk</span></span>

<span data-ttu-id="b1ac9-221">现在，我们将相应的策略批量分配给用户。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-221">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="b1ac9-222">可为其分配或更新策略的最大用户数是一次 5，000。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-222">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="b1ac9-223">例如，如果教职员工和教师超过 5，000 人，则需要提交多个批次。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-223">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>

<span data-ttu-id="b1ac9-224">运行以下代码，将名为"教师""MeetingPolicy"的自定义会议策略分配给教职员工和教师。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-224">Run the following to assign a custom meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="b1ac9-225">若要批量分配不同的策略类型（如 TeamsMessagingPolicy），需要更改为要分配的策略和 ```PolicyType``` ```PolicyName``` 策略名称。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-225">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

#### <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="b1ac9-226">获取批量分配的状态</span><span class="sxs-lookup"><span data-stu-id="b1ac9-226">Get the status of a bulk assignment</span></span>

<span data-ttu-id="b1ac9-227">每个批量分配都返回一个操作 ID，可用于跟踪策略分配的进度或识别可能发生的任何失败。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-227">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="b1ac9-228">例如，运行以下代码：</span><span class="sxs-lookup"><span data-stu-id="b1ac9-228">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="b1ac9-229">若要查看批处理操作中每个用户的分配状态，请运行以下代码。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-229">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="b1ac9-230">每个用户的详细信息均在 ```UserState``` 属性中。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-230">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="b1ac9-231">如果用户数超过 5，000，请批量分配策略</span><span class="sxs-lookup"><span data-stu-id="b1ac9-231">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="b1ac9-232">首先，运行以下代码，查看有多少教职员工和教师：</span><span class="sxs-lookup"><span data-stu-id="b1ac9-232">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="b1ac9-233">不是提供完整的用户 ID 列表，而是运行以下代码来指定前 5，000 个，然后指定接下来的 5，000 个，以此类比。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-233">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="b1ac9-234">可以更改用户 ID 范围，直到到达用户的完整列表。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-234">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="b1ac9-235">例如，输入 作为第一批，使用 作为第二批，输入 作为第三批， ```$faculty[0..4999``` ```$faculty[5000..9999``` ```$faculty[10000..14999``` 等等。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-235">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

#### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="b1ac9-236">获取分配给用户的策略</span><span class="sxs-lookup"><span data-stu-id="b1ac9-236">Get the policies assigned to a user</span></span>

<span data-ttu-id="b1ac9-237">运行以下代码，查看分配给特定用户的所有策略。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-237">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="b1ac9-238">以下示例演示如何获取分配给 hannah@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-238">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="b1ac9-239">常见问题</span><span class="sxs-lookup"><span data-stu-id="b1ac9-239">FAQ</span></span>

<span data-ttu-id="b1ac9-240">**我不熟悉 PowerShell for Teams。在哪里可以了解更多信息？**</span><span class="sxs-lookup"><span data-stu-id="b1ac9-240">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="b1ac9-241">有关使用 PowerShell 管理 Teams 的Teams，请参阅[PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b1ac9-241">For an overview of using PowerShell to manage Teams, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span> <span data-ttu-id="b1ac9-242">有关本文中使用的 cmdlet 详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="b1ac9-242">For more information about the cmdlets used in this article, see:</span></span>

- [<span data-ttu-id="b1ac9-243">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="b1ac9-243">New-CsGroupPolicyAssignment</span></span>](/powershell/module/teams/new-csgrouppolicyassignment)
- [<span data-ttu-id="b1ac9-244">Get-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="b1ac9-244">Get-CsGroupPolicyAssignment</span></span>](/powershell/module/teams/get-csgrouppolicyassignment)
- [<span data-ttu-id="b1ac9-245">New-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="b1ac9-245">New-CsBatchPolicyAssignmentOperation</span></span>](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="b1ac9-246">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="b1ac9-246">Get-CsBatchPolicyAssignmentOperation</span></span>](/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="b1ac9-247">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="b1ac9-247">Get-CsUserPolicyAssignment</span></span>](/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a><span data-ttu-id="b1ac9-248">相关主题</span><span class="sxs-lookup"><span data-stu-id="b1ac9-248">Related topics</span></span>

- [<span data-ttu-id="b1ac9-249">将策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="b1ac9-249">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="b1ac9-250">用于教育的 Teams 策略和策略包</span><span class="sxs-lookup"><span data-stu-id="b1ac9-250">Teams policies and policy packages for Education</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="b1ac9-251">管理 Teams 中的会议策略</span><span class="sxs-lookup"><span data-stu-id="b1ac9-251">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)