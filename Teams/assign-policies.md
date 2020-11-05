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
ms.openlocfilehash: fb9946f9954dc46d9d97137f707b7ad46c797fb9
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908521"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="e5bfb-103">向 Microsoft Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="e5bfb-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="e5bfb-104">作为管理员，你可以使用策略来控制你的组织中的用户可以使用的团队功能。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="e5bfb-105">例如，有一些通话策略、会议策略和邮件策略，只需命名。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="e5bfb-106">组织具有不同类型的具有独特需求的用户和你创建和分配的自定义策略，让你可以根据这些需求将策略设置自定义给不同的用户集。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-106">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="e5bfb-107">为了便于管理组织中的策略，团队提供了多种方法来为用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-107">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="e5bfb-108">你可以将策略直接分配给用户，无论是单独的还是通过批处理作业进行缩放，或是用户是其成员的组。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-108">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="e5bfb-109">你还可以使用策略程序包向组织中具有类似角色的用户分配策略的预设集合。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-109">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="e5bfb-110">你选择的选项取决于你正在管理的策略的数量以及你要分配到的用户数。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-110">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="e5bfb-111">通过设置全局 (组织范围的默认) 策略，以便它们应用于组织中的最大用户数，只需为需要特殊策略的用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-111">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="e5bfb-112">本文介绍为用户分配策略的不同方法以及用于何时使用的建议方案。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="e5bfb-113">哪种策略优先？</span><span class="sxs-lookup"><span data-stu-id="e5bfb-113">Which policy takes precedence?</span></span>

<span data-ttu-id="e5bfb-114">用户对每个策略类型都有一个有效策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="e5bfb-115">用户可以直接分配策略，也可以是分配了相同类型策略的一个或多个组的成员。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="e5bfb-116">在这种情况下，哪些策略优先？</span><span class="sxs-lookup"><span data-stu-id="e5bfb-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="e5bfb-117">根据优先级规则确定用户的有效策略，如下所示。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="e5bfb-118">如果用户直接分配策略 (或通过批处理作业) 分配策略，则该策略优先。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="e5bfb-119">在以下示例中，用户的有效策略是 Lincoln 方形会议策略，该策略直接分配给用户。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![图表显示如何直接分配的策略优先](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="e5bfb-121">如果用户未直接分配给定类型的策略，则分配给用户所属组的策略优先。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="e5bfb-122">如果用户是多个组的成员，则具有给定策略类型的最高 [组分配级别](#group-assignment-ranking) 的策略优先。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="e5bfb-123">在此示例中，用户的有效策略是 Exec 团队和 HD 策略，该策略具有相对于用户所属的其他组的最高工作分配级别，并且还分配有相同策略类型的策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![图表显示了从组继承的策略优先的方式](media/assign-policies-example-group.png)

<span data-ttu-id="e5bfb-125">如果用户未直接分配策略或不是分配了策略的任何组的成员，则用户将获取该策略类型的全局 (组织范围默认) 策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="e5bfb-126">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-126">Here's an example.</span></span>

![显示全局策略优先级别的图表](media/assign-policies-example-global.png)

<span data-ttu-id="e5bfb-128">若要了解详细信息，请参阅 [优先规则](#precedence-rules)。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="e5bfb-129">分配策略的方法</span><span class="sxs-lookup"><span data-stu-id="e5bfb-129">Ways to assign policies</span></span>

<span data-ttu-id="e5bfb-130">下面概述了为用户分配策略的方法和建议的每种方案。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="e5bfb-131">单击链接以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-131">Click the links to learn more.</span></span>

<span data-ttu-id="e5bfb-132">将策略分配给单个用户或组之前，首先 [设置全局 (组织范围的默认) 策略](#set-the-global-policies) ，以便它们应用于组织中的最大用户数。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-132">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="e5bfb-133">设置全局策略后，你将仅需要为需要特殊策略的用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-133">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="e5bfb-134">要执行的操作</span><span class="sxs-lookup"><span data-stu-id="e5bfb-134">Do this</span></span>  |<span data-ttu-id="e5bfb-135">If .。。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-135">If...</span></span>  | <span data-ttu-id="e5bfb-136">使用 .。。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-136">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="e5bfb-137">为单个用户分配策略</span><span class="sxs-lookup"><span data-stu-id="e5bfb-137">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="e5bfb-138">您是新的团队新手，只需将一个或几个策略分配给少数几个用户。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-138">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="e5bfb-139">Skype for Business Online PowerShell 模块中的 Microsoft 团队管理中心或 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="e5bfb-139">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
|[<span data-ttu-id="e5bfb-140">为组分配策略</span><span class="sxs-lookup"><span data-stu-id="e5bfb-140">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="e5bfb-141">您需要根据用户的组成员身份分配策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-141">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="e5bfb-142">例如，你想要为安全组或通讯组列表中的所有用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-142">For example, you want to assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="e5bfb-143">团队 PowerShell 模块中的 Microsoft 团队管理中心或 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="e5bfb-143">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="e5bfb-144">为一批用户分配策略</span><span class="sxs-lookup"><span data-stu-id="e5bfb-144">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="e5bfb-145">您需要为大型用户组分配策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-145">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="e5bfb-146">例如，你希望一次为组织中的成百上千个用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-146">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="e5bfb-147">团队 PowerShell 模块中的 Microsoft 团队管理中心或 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="e5bfb-147">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="e5bfb-148">为用户分配策略包</span><span class="sxs-lookup"><span data-stu-id="e5bfb-148">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  | <span data-ttu-id="e5bfb-149">您需要将多个策略分配给组织中具有相同或类似角色的特定用户组。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-149">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="e5bfb-150">例如，向学校中的教师分配教育版 (教师) 策略包，让他们能够完全访问聊天、通话和会议以及教育 (次要学生) 策略程序包，以限制某些功能，如私人通话。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-150">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="e5bfb-151">团队 PowerShell 模块中的 Microsoft 团队管理中心或 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="e5bfb-151">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="e5bfb-152">[将策略包分配到](#assign-a-policy-package-to-a-group) 私人预览版中的组 () </span><span class="sxs-lookup"><span data-stu-id="e5bfb-152">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="e5bfb-153">您需要将多个策略分配给组织中具有相同或类似角色的一组用户。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-153">You need to assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="e5bfb-154">例如，你想要向安全组或通讯组列表中的所有用户分配策略包。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-154">For example, you want to assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="e5bfb-155">Microsoft 团队管理中心 (即将推出团队 PowerShell 模块中) 或 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="e5bfb-155">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="e5bfb-156">将策略包分配给一批用户</span><span class="sxs-lookup"><span data-stu-id="e5bfb-156">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="e5bfb-157">您需要为组织中具有相同或类似角色的一批用户分配多个策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-157">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="e5bfb-158">例如，使用批处理作业向学校中的所有教师分配教育 (教师) 策略包，从而为他们提供对聊天、通话和会议的完全访问权限，并将教育 (辅助学校学生) 策略包分配给一批辅助学生，以限制某些功能（如私人通话）。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-158">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="e5bfb-159">团队 PowerShell 模块中的 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="e5bfb-159">PowerShell cmdlets in the Teams PowerShell module</span></span>|


## <a name="set-the-global-policies"></a><span data-ttu-id="e5bfb-160">设置全局策略</span><span class="sxs-lookup"><span data-stu-id="e5bfb-160">Set the global policies</span></span>

<span data-ttu-id="e5bfb-161">请按照以下步骤设置每个策略类型的全局 (组织范围默认) 策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-161">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e5bfb-162">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="e5bfb-162">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="e5bfb-163">在 Microsoft 团队管理中心的左侧导航中，转到要更新的策略类型的 "策略" 页面。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-163">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="e5bfb-164">例如， **团队**  >  **团队策略** 、 **会议**  >  **会议策略** 、 **邮件策略** 或 **语音**  >  **呼叫策略** 。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-164">For example, **Teams** > **Teams policies** , **Meetings** > **Meetings policies** , **Messaging policies** , or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="e5bfb-165">选择 " **全局 (组织范围默认)** 策略" 以查看当前设置。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-165">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="e5bfb-166">根据需要更新策略，然后选择 " **应用** "。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-166">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e5bfb-167">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5bfb-167">Using PowerShell</span></span>

<span data-ttu-id="e5bfb-168">若要使用 PowerShell 设置全局策略，请使用全局标识符。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-168">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="e5bfb-169">首先查看当前全局策略，确定要更改的设置。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-169">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

<span data-ttu-id="e5bfb-170">接下来，根据需要更新全局策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-170">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="e5bfb-171">您只需为要更改的设置指定值。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-171">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="e5bfb-172">为单个用户分配策略</span><span class="sxs-lookup"><span data-stu-id="e5bfb-172">Assign a policy to individual users</span></span>

<span data-ttu-id="e5bfb-173">请按照以下步骤将策略分配给单个用户或一次分配给少数几个用户。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-173">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e5bfb-174">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="e5bfb-174">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="e5bfb-175">若要为用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e5bfb-175">To assign a policy to a user:</span></span>

1. <span data-ttu-id="e5bfb-176">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-176">In the left navigation of the Microsoft Teams admin center, go to **Users** , and then click the user.</span></span>
2. <span data-ttu-id="e5bfb-177">单击用户名的左侧以选择用户，然后单击“编辑设置”。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-177">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="e5bfb-178">选择要分配的策略，然后单击 " **应用** "。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-178">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="e5bfb-179">或者，您也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e5bfb-179">Or, you can also do the following:</span></span>

1. <span data-ttu-id="e5bfb-180">在 Microsoft 团队管理中心的左侧导航中，转到 "策略" 页面。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-180">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="e5bfb-181">通过单击策略名称的左侧，选择要分配的策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-181">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="e5bfb-182">选择“管理用户”。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-182">Select **Manage users**.</span></span>
4. <span data-ttu-id="e5bfb-183">在“ **管理用户** ”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“ **添加** ”。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-183">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="e5bfb-184">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-184">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="e5bfb-185">完成添加用户后，选择 " **应用** "。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-185">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e5bfb-186">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5bfb-186">Using PowerShell</span></span>

<span data-ttu-id="e5bfb-187">每个策略类型都有自己的一组用于管理它的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-187">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="e5bfb-188">使用 ```Grant-``` 给定策略类型的 cmdlet 分配策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-188">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="e5bfb-189">例如，使用 ```Grant-CsTeamsMeetingPolicy``` cmdlet 向用户分配团队会议策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-189">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="e5bfb-190">这些 cmdlet 包含在 Skype for Business Online PowerShell 模块中，并记录在 [skype for business cmdlet 参考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)中。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-190">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="e5bfb-191">如果尚未) ，请下载并安装 [skype For Business Online PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=39366) (，然后运行以下操作以连接到 Skype For business online 并启动会话。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-191">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

> [!NOTE]
> <span data-ttu-id="e5bfb-192">Skype for Business Online 连接器目前是最新团队 PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-192">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="e5bfb-193">如果您使用的是最新的 [团队 PowerShell 公共版本](https://www.powershellgallery.com/packages/MicrosoftTeams/)，则无需安装 Skype For Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-193">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="e5bfb-194">在此示例中，我们将名为 "学生会议策略" 的团队会议策略分配给名为 Reda 的用户。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-194">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="e5bfb-195">若要了解详细信息，请 [通过 PowerShell 阅读管理策略](teams-powershell-managing-teams.md#manage-policies-via-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-195">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="e5bfb-196">为组分配策略</span><span class="sxs-lookup"><span data-stu-id="e5bfb-196">Assign a policy to a group</span></span>

<span data-ttu-id="e5bfb-197">通过向组分配策略，您可以为一组用户分配策略，例如安全组或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-197">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="e5bfb-198">根据优先级规则，策略分配将传播到组的成员。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-198">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="e5bfb-199">将成员添加到组或从组中删除成员后，将相应地更新其继承的策略分配。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-199">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="e5bfb-200">建议对多达50000用户的组分配策略，但它还可用于更大的组。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-200">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="e5bfb-201">分配策略时，它将立即分配给组。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-201">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="e5bfb-202">但是，请注意，对组成员的策略分配的传播是作为后台操作执行的，可能需要一些时间，具体取决于组的大小。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-202">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="e5bfb-203">当从组中取消分配策略时，或者在组中添加或删除成员时，也是如此。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-203">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="e5bfb-204">对组的策略分配需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="e5bfb-204">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="e5bfb-205">在开始之前，了解优先级规则和组分配的排名非常重要。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-205">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="e5bfb-206">优先规则</span><span class="sxs-lookup"><span data-stu-id="e5bfb-206">Precedence rules</span></span>

<span data-ttu-id="e5bfb-207">对于给定的策略类型，根据以下情况确定用户的有效策略：</span><span class="sxs-lookup"><span data-stu-id="e5bfb-207">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="e5bfb-208">直接分配给用户的策略优先于分配给组的任何其他相同类型的策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-208">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="e5bfb-209">换言之，如果用户直接分配给某一给定类型的策略，则该用户不会从组中继承同一类型的策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-209">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="e5bfb-210">这还意味着，如果用户具有直接分配给他们的给定类型的策略，则必须从用户处删除该策略，然后才能从组继承同一类型的策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-210">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="e5bfb-211">如果用户没有直接分配给他们的策略，并且是两个或更多组的成员，并且每个组都分配有相同类型的策略，则用户将继承具有最高级别的组分配的策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-211">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="e5bfb-212">如果用户不是分配了策略的任何组的成员，则全局 (该策略类型的组织范围默认) 策略将应用于该用户。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-212">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="e5bfb-213">当用户在分配了策略的组中添加或删除时，用户的有效策略将根据这些规则进行更新，从组中取消分配策略，或者删除直接分配给用户的策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-213">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="e5bfb-214">组分配排名</span><span class="sxs-lookup"><span data-stu-id="e5bfb-214">Group assignment ranking</span></span>
 
<span data-ttu-id="e5bfb-215">向组分配策略时，为组分配指定排名。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-215">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="e5bfb-216">如果用户是两个或更多组的成员，并且每个组都分配有同一类型的策略，则使用此功能确定用户应继承为其有效策略的策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-216">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="e5bfb-217">组分配排名与同一类型的其他组分配相关。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-217">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="e5bfb-218">例如，如果您正在向两个组分配呼叫策略，则将一个作业的等级设置为1，另一个设置为2，1为最高排名。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-218">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="e5bfb-219">组分配排名指明哪些组成员身份比继承的其他组成员更重要或更密切。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-219">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="e5bfb-220">例如，你有两个组，存储员工和商店经理。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-220">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="e5bfb-221">这两个组都分配有一个团队调用策略，分别存储员工调用策略和存储管理器调用策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-221">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="e5bfb-222">对于位于两个组中的商店经理，其角色作为经理，其角色与员工的角色更相关，因此分配给应用商店管理员组的呼叫策略应具有更高的排名。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-222">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="e5bfb-223">团队</span><span class="sxs-lookup"><span data-stu-id="e5bfb-223">Group</span></span> |<span data-ttu-id="e5bfb-224">团队调用策略名称</span><span class="sxs-lookup"><span data-stu-id="e5bfb-224">Teams calling policy name</span></span>  |<span data-ttu-id="e5bfb-225">等级</span><span class="sxs-lookup"><span data-stu-id="e5bfb-225">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="e5bfb-226">商店经理</span><span class="sxs-lookup"><span data-stu-id="e5bfb-226">Store Managers</span></span>   |<span data-ttu-id="e5bfb-227">应用商店经理通话政策</span><span class="sxs-lookup"><span data-stu-id="e5bfb-227">Store Managers Calling Policy</span></span>         |<span data-ttu-id="e5bfb-228">1</span><span class="sxs-lookup"><span data-stu-id="e5bfb-228">1</span></span>|
|<span data-ttu-id="e5bfb-229">存储员工</span><span class="sxs-lookup"><span data-stu-id="e5bfb-229">Store Employees</span></span>    |<span data-ttu-id="e5bfb-230">存储员工通话政策</span><span class="sxs-lookup"><span data-stu-id="e5bfb-230">Store Employees Calling Policy</span></span>      |<span data-ttu-id="e5bfb-231">2</span><span class="sxs-lookup"><span data-stu-id="e5bfb-231">2</span></span>|

<span data-ttu-id="e5bfb-232">如果未指定排名，则将为策略分配授予最低级别。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-232">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span> 

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e5bfb-233">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="e5bfb-233">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="e5bfb-234">目前，对使用 Microsoft 团队管理中心的组的策略分配仅适用于团队调用策略、团队呼叫驻留策略、团队策略、团队实时事件策略、团队会议策略和团队消息策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-234">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="e5bfb-235">对于其他策略类型，请使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-235">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="e5bfb-236">在 Microsoft 团队管理中心的左侧导航中，转到 "策略类型" 页面。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-236">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="e5bfb-237">例如，转到 " **会议**  >  **会议策略** "。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-237">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="e5bfb-238">选择 " **组策略分配** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-238">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="e5bfb-239">选择 " **添加组** "，然后在 "向 **组分配策略** " 窗格中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e5bfb-239">Select **Add group** , and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="e5bfb-240">搜索并添加要向其分配策略的组。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-240">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="e5bfb-241">为组分配设置排名。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-241">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="e5bfb-242">选择要分配的策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-242">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="e5bfb-243">选择 " **应用** "。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-243">Select **Apply**.</span></span>

<span data-ttu-id="e5bfb-244">若要删除组策略分配，请在 "策略" 页面的 " **组策略分配** " 选项卡上，选择 "组分配"，然后选择 " **删除** "。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-244">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="e5bfb-245">若要更改组分配的排名，必须首先删除组策略分配。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-245">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="e5bfb-246">然后，按照上述步骤将策略分配给组。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-246">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e5bfb-247">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5bfb-247">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="e5bfb-248">目前，对使用 PowerShell 的组的策略分配不可用于所有团队策略类型。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-248">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="e5bfb-249">有关受支持的策略类型列表，请参阅 [CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-249">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="e5bfb-250">安装并连接到 Microsoft 团队 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="e5bfb-250">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="e5bfb-251">有关分步指南，请参阅 [安装团队 PowerShell](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-251">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="e5bfb-252">为一组用户分配策略</span><span class="sxs-lookup"><span data-stu-id="e5bfb-252">Assign a policy to a group of users</span></span>

<span data-ttu-id="e5bfb-253">你可以使用 [CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet 向组分配策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-253">You use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="e5bfb-254">您可以通过使用对象 Id、SIP 地址或电子邮件地址来指定组。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-254">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="e5bfb-255">在此示例中，我们将名为零售经理会议策略的团队会议策略分配给分配等级为1的组。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-255">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="e5bfb-256">获取组的策略分配</span><span class="sxs-lookup"><span data-stu-id="e5bfb-256">Get policy assignments for a group</span></span>

<span data-ttu-id="e5bfb-257">使用 [CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet 获取分配给组的所有策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-257">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="e5bfb-258">请注意，组始终按组 Id 列出，即使其 SIP 地址或电子邮件地址用于分配策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-258">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="e5bfb-259">在此示例中，我们将检索分配给特定组的所有策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-259">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="e5bfb-260">在此示例中，我们将返回分配有团队会议策略的所有组。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-260">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="e5bfb-261">从组中删除策略</span><span class="sxs-lookup"><span data-stu-id="e5bfb-261">Remove a policy from a group</span></span>

<span data-ttu-id="e5bfb-262">使用 [CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet 从组中删除策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-262">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="e5bfb-263">从组中删除策略时，将更新分配给该组的相同类型的其他策略的优先级和较低级别的其他策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-263">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="e5bfb-264">例如，如果删除分级为2的策略，则级别为3和4的策略将更新，以反映其新排名。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-264">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="e5bfb-265">下面的两个表显示了此示例。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-265">The following two tables show this example.</span></span>

<span data-ttu-id="e5bfb-266">下面列出了团队会议策略的策略分配和优先级。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-266">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="e5bfb-267">组名称</span><span class="sxs-lookup"><span data-stu-id="e5bfb-267">Group name</span></span>  |<span data-ttu-id="e5bfb-268">策略名称</span><span class="sxs-lookup"><span data-stu-id="e5bfb-268">Policy name</span></span>  |<span data-ttu-id="e5bfb-269">等级</span><span class="sxs-lookup"><span data-stu-id="e5bfb-269">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="e5bfb-270">销售</span><span class="sxs-lookup"><span data-stu-id="e5bfb-270">Sales</span></span>    |<span data-ttu-id="e5bfb-271">销售政策</span><span class="sxs-lookup"><span data-stu-id="e5bfb-271">Sales policy</span></span>       | <span data-ttu-id="e5bfb-272">1</span><span class="sxs-lookup"><span data-stu-id="e5bfb-272">1</span></span>        |
|<span data-ttu-id="e5bfb-273">西部区域</span><span class="sxs-lookup"><span data-stu-id="e5bfb-273">West Region</span></span>     |<span data-ttu-id="e5bfb-274">West 区域策略</span><span class="sxs-lookup"><span data-stu-id="e5bfb-274">West Region policy</span></span>         |<span data-ttu-id="e5bfb-275">2</span><span class="sxs-lookup"><span data-stu-id="e5bfb-275">2</span></span>         |
|<span data-ttu-id="e5bfb-276">单位</span><span class="sxs-lookup"><span data-stu-id="e5bfb-276">Division</span></span>    |<span data-ttu-id="e5bfb-277">部门策略</span><span class="sxs-lookup"><span data-stu-id="e5bfb-277">Division policy</span></span>         |<span data-ttu-id="e5bfb-278">3</span><span class="sxs-lookup"><span data-stu-id="e5bfb-278">3</span></span>         |
|<span data-ttu-id="e5bfb-279">附属</span><span class="sxs-lookup"><span data-stu-id="e5bfb-279">Subsidiary</span></span>   |<span data-ttu-id="e5bfb-280">附属政策</span><span class="sxs-lookup"><span data-stu-id="e5bfb-280">Subsidiary policy</span></span>        |<span data-ttu-id="e5bfb-281">4</span><span class="sxs-lookup"><span data-stu-id="e5bfb-281">4</span></span>         |

<span data-ttu-id="e5bfb-282">如果我们删除 "西部" 区域组中的 "西部" 区域策略，策略分配和优先级将按如下方式更新。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-282">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="e5bfb-283">组名称</span><span class="sxs-lookup"><span data-stu-id="e5bfb-283">Group name</span></span>  |<span data-ttu-id="e5bfb-284">策略名称</span><span class="sxs-lookup"><span data-stu-id="e5bfb-284">Policy name</span></span>  |<span data-ttu-id="e5bfb-285">等级</span><span class="sxs-lookup"><span data-stu-id="e5bfb-285">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="e5bfb-286">销售</span><span class="sxs-lookup"><span data-stu-id="e5bfb-286">Sales</span></span>    |<span data-ttu-id="e5bfb-287">销售政策</span><span class="sxs-lookup"><span data-stu-id="e5bfb-287">Sales policy</span></span>       | <span data-ttu-id="e5bfb-288">1</span><span class="sxs-lookup"><span data-stu-id="e5bfb-288">1</span></span>        |
|<span data-ttu-id="e5bfb-289">单位</span><span class="sxs-lookup"><span data-stu-id="e5bfb-289">Division</span></span>    |<span data-ttu-id="e5bfb-290">部门策略</span><span class="sxs-lookup"><span data-stu-id="e5bfb-290">Division policy</span></span>         |<span data-ttu-id="e5bfb-291">2</span><span class="sxs-lookup"><span data-stu-id="e5bfb-291">2</span></span>         |
|<span data-ttu-id="e5bfb-292">附属</span><span class="sxs-lookup"><span data-stu-id="e5bfb-292">Subsidiary</span></span>   |<span data-ttu-id="e5bfb-293">附属政策</span><span class="sxs-lookup"><span data-stu-id="e5bfb-293">Subsidiary policy</span></span>        |<span data-ttu-id="e5bfb-294">3</span><span class="sxs-lookup"><span data-stu-id="e5bfb-294">3</span></span>        |

<span data-ttu-id="e5bfb-295">在此示例中，我们从组中删除团队会议策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-295">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="e5bfb-296">更改组的策略分配</span><span class="sxs-lookup"><span data-stu-id="e5bfb-296">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="e5bfb-297">[CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet 将很快可用。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-297">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="e5bfb-298">在此期间，若要更改组策略分配，您可以从组中删除当前策略分配，然后添加新的策略分配。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-298">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="e5bfb-299">为组分配策略后，可以使用 [CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet 更改该组的策略分配，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e5bfb-299">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="e5bfb-300">更改排名</span><span class="sxs-lookup"><span data-stu-id="e5bfb-300">Change the ranking</span></span>
- <span data-ttu-id="e5bfb-301">更改给定策略类型的策略</span><span class="sxs-lookup"><span data-stu-id="e5bfb-301">Change the policy of a given policy type</span></span>
- <span data-ttu-id="e5bfb-302">更改给定策略类型和排名的策略</span><span class="sxs-lookup"><span data-stu-id="e5bfb-302">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="e5bfb-303">在此示例中，我们将组的团队更改为名为 SupportCallPark 的策略，并将工作分配排名设置为3。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-303">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="e5bfb-304">更改用户的有效策略</span><span class="sxs-lookup"><span data-stu-id="e5bfb-304">Change the effective policy for a user</span></span>

<span data-ttu-id="e5bfb-305">下面是如何更改直接分配了策略的用户的有效策略的示例。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-305">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="e5bfb-306">首先，我们将 [CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet 与参数结合使用， ```PolicySource``` 以获取与用户相关联的团队会议广播策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-306">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> 

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="e5bfb-307">输出显示用户直接分配有名为员工事件的团队会议广播策略，该策略优先于分配给用户所属组的名为 "供应商实时事件" 的策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-307">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="e5bfb-308">现在，我们将从用户中删除 "员工活动" 策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-308">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="e5bfb-309">这意味着用户不再有团队会议广播策略直接分配给他们，并且将继承分配给用户所属组的供应商实时事件策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-309">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="e5bfb-310">使用 Skype for Business PowerShell 模块中的以下 cmdlet 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-310">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="e5bfb-311">你可以使用团队 PowerShell 模块中的以下 cmdlet 通过批处理策略分配以缩放方式执行此操作，其中 $users 是你指定的用户的列表。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-311">You can use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="e5bfb-312">为一批用户分配策略</span><span class="sxs-lookup"><span data-stu-id="e5bfb-312">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e5bfb-313">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="e5bfb-313">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="e5bfb-314">要批量向用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e5bfb-314">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="e5bfb-315">在 Microsoft 团队管理中心的左侧导航中，选择 " **用户** "。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-315">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="e5bfb-316">搜索要向其分配策略的用户，或筛选视图以显示所需的用户。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-316">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="e5bfb-317">在 **&#x2713;** （复选标记）列，选择用户。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-317">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="e5bfb-318">若要选择所有用户，请单击表格顶部的 &#x2713;（复选标记）。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-318">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="e5bfb-319">单击“ **编辑设置** ”，执行所需的更改，然后单击“ **应用** ”。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-319">Click **Edit settings** , make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="e5bfb-320">若要查看策略分配的状态，请在单击 " **应用** " 提交策略分配后出现在 " **用户** " 页面顶部的标题中，单击 " **活动日志** "。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-320">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="e5bfb-321">或者，在 Microsoft 团队管理中心的左侧导航中，转到 **仪表板** ，然后在 " **活动日志** " 下单击 " **查看详细信息** "。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-321">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard** , and then under **Activity log** , click **View details**.</span></span> <span data-ttu-id="e5bfb-322">活动日志显示过去30天内通过 Microsoft 团队管理中心向超过20名用户批处理的策略分配。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-322">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="e5bfb-323">若要了解详细信息，请参阅 [在活动日志中查看策略分配](activity-log.md)。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-323">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e5bfb-324">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5bfb-324">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="e5bfb-325">当前，使用 PowerShell 的批策略分配不适用于所有团队策略类型。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-325">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="e5bfb-326">有关受支持的策略类型列表，请参阅 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-326">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="e5bfb-327">通过批处理策略分配，您可以一次性为大型用户分配策略，而无需使用脚本。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-327">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="e5bfb-328">使用 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 提交要分配的一批用户和策略。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-328">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="e5bfb-329">作业作为后台操作处理，并为每个批处理生成操作 ID。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-329">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="e5bfb-330">然后，你可以使用 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet 跟踪批处理中作业的进度和状态。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-330">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="e5bfb-331">你可以按用户的对象 Id 或会话初始协议指定用户 (SIP) 地址。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-331">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="e5bfb-332">请注意，用户的 SIP 地址通常具有与用户主体名称相同的值 (UPN) 或电子邮件地址，但这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-332">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="e5bfb-333">如果用户使用其 UPN 或电子邮件进行了指定，但它的值与 SIP 地址不同，则该用户的策略分配将失败。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-333">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="e5bfb-334">如果批处理包括重复的用户，则在处理之前将从批处理中删除重复项，并且仅为批处理中剩余的唯一用户提供状态。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-334">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="e5bfb-335">批处理最多可包含5000个用户。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-335">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="e5bfb-336">为获得最佳结果，请不要一次提交多个批次。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-336">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="e5bfb-337">允许批完成处理，然后再提交更多批。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-337">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="e5bfb-338">安装并连接到 Microsoft 团队 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="e5bfb-338">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="e5bfb-339">运行以下操作以安装 [Microsoft 团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams)。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-339">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="e5bfb-340">请确保安装1.0.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-340">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="e5bfb-341">运行以下操作以连接到团队并启动会话。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-341">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="e5bfb-342">出现提示时，请使用管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-342">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="e5bfb-343">安装并连接到 Azure AD PowerShell for Graph 模块 (可选) </span><span class="sxs-lookup"><span data-stu-id="e5bfb-343">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="e5bfb-344">如果尚未) 并连接到 Azure AD，你可能还想要 [下载和安装 AZURE Ad PowerShell For Graph 模块](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (，以便你可以检索组织中的用户列表。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-344">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="e5bfb-345">运行以下操作以连接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-345">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="e5bfb-346">出现提示时，请使用您用于连接到团队的相同管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-346">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="e5bfb-347">为一批用户分配策略</span><span class="sxs-lookup"><span data-stu-id="e5bfb-347">Assign a policy to a batch of users</span></span>

<span data-ttu-id="e5bfb-348">在此示例中，我们使用 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 将名为 HR App 设置策略的应用设置策略分配给在 Users_ids 文本文件中列出的一批用户。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-348">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="e5bfb-349">在此示例中，我们连接到 Azure AD 以检索用户集合，然后将名为 "新员工消息策略" 的消息策略分配给使用其 SIP 地址指定的批用户。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-349">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="e5bfb-350">获取批处理作业的状态</span><span class="sxs-lookup"><span data-stu-id="e5bfb-350">Get the status of a batch assignment</span></span>

<span data-ttu-id="e5bfb-351">运行以下操作以获取批处理作业的状态，其中 OperationId 是由给定批处理的 cmdlet 返回的操作 ID ```New-CsBatchPolicyAssignmentOperation``` 。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-351">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="e5bfb-352">如果输出显示发生了错误，请运行以下内容以获取有关属性中的错误的详细信息 ```UserState``` 。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-352">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="e5bfb-353">若要了解详细信息，请参阅 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-353">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="e5bfb-354">为用户分配策略包</span><span class="sxs-lookup"><span data-stu-id="e5bfb-354">Assign a policy package to users</span></span>

<span data-ttu-id="e5bfb-355">团队中的策略包是预定义策略和策略设置的集合，你可以分配给在你的组织中具有相同或类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-355">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="e5bfb-356">每个策略程序包均围绕用户角色进行设计，其中包含支持该角色的典型活动的预定义策略和策略设置。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-356">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="e5bfb-357"> (教师) 程序包和医疗保健 (临床工作者) 程序包中，策略包的一些示例是教育版。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-357">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="e5bfb-358">若要了解详细信息，请参阅 [管理团队中的策略包](manage-policy-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-358">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="e5bfb-359">为一个用户分配策略包</span><span class="sxs-lookup"><span data-stu-id="e5bfb-359">Assign a policy package to one user</span></span>

1. <span data-ttu-id="e5bfb-360">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-360">In the left navigation of the Microsoft Teams admin center, go to **Users** , and then click the user.</span></span>
2. <span data-ttu-id="e5bfb-361">在用户的页面上，单击 " **策略** "，然后单击 " **策略程序包** " 旁边的 " **编辑** "。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-361">On the user's page, click **Policies** , and then next to **Policy package** , click **Edit**.</span></span>
3. <span data-ttu-id="e5bfb-362">在 " **分配策略包** " 窗格中，选择要分配的程序包，然后单击 " **保存** "。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-362">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="e5bfb-363">向多个用户分配策略包</span><span class="sxs-lookup"><span data-stu-id="e5bfb-363">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="e5bfb-364">在 Microsoft 团队管理中心的左侧导航中，转到 " **策略程序包** "，然后通过单击程序包名称左侧的 "选择要分配的策略包"。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-364">In the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="e5bfb-365">单击 " **管理用户** "。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-365">Click **Manage users**.</span></span>
3. <span data-ttu-id="e5bfb-366">在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-366">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="e5bfb-367">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-367">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="e5bfb-368">添加完用户后，单击 " **保存** "。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-368">When you're finished adding users, click **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="e5bfb-369">为组分配策略包</span><span class="sxs-lookup"><span data-stu-id="e5bfb-369">Assign a policy package to a group</span></span>

<span data-ttu-id="e5bfb-370">**此功能在私人预览版中**</span><span class="sxs-lookup"><span data-stu-id="e5bfb-370">**This feature is in private preview**</span></span>

<span data-ttu-id="e5bfb-371">通过将策略包分配给组，你可以将多个策略分配给一组用户，如安全组或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-371">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="e5bfb-372">根据优先级规则，策略分配将传播到组的成员。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-372">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="e5bfb-373">将成员添加到组或从组中删除成员后，将相应地更新其继承的策略分配。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-373">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="e5bfb-374">对于多达50000用户的组，建议使用组的策略包分配，但它还可用于更大的组。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-374">Policy package assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span> 

<span data-ttu-id="e5bfb-375">分配策略包时，它将立即分配给组。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-375">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="e5bfb-376">但是，请注意，对组成员的策略分配的传播是作为后台操作执行的，可能需要一些时间，具体取决于组的大小。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-376">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="e5bfb-377">当从组中取消分配策略时，或者在组中添加或删除成员时，也是如此。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-377">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5bfb-378">在开始之前，了解 [优先级规则](#precedence-rules) 和 [组分配的排名](#group-assignment-ranking)非常重要。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-378">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="e5bfb-379">请务必阅读并理解本文前面的 [策略分配对组的相关信息](#what-you-need-to-know-about-policy-assignment-to-groups) 。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-379">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="using-the-microsoft-teams-admin-center-coming-soon"></a><span data-ttu-id="e5bfb-380">使用 Microsoft 团队管理中心 (即将推出) </span><span class="sxs-lookup"><span data-stu-id="e5bfb-380">Using the Microsoft Teams admin center (coming soon)</span></span>

<span data-ttu-id="e5bfb-381">即将向 Microsoft 团队管理中心中的组分配策略包。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-381">Policy package assignment to groups in the Microsoft Teams admin center is coming soon.</span></span> <span data-ttu-id="e5bfb-382">查看此处查看最新更新。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-382">Check back here for the latest updates.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e5bfb-383">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5bfb-383">Using PowerShell</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="e5bfb-384">安装并连接到 Microsoft 团队 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="e5bfb-384">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="e5bfb-385">有关分步指南，请参阅 [安装团队 PowerShell](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-385">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="e5bfb-386">将策略包分配给一组用户</span><span class="sxs-lookup"><span data-stu-id="e5bfb-386">Assign a policy package to a group of users</span></span>

<span data-ttu-id="e5bfb-387">你可以使用 [CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet 向组分配策略包。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-387">You use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="e5bfb-388">您可以通过使用对象 Id、SIP 地址或电子邮件地址来指定组。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-388">You can specify a group by using the object Id, SIP address, or email address.</span></span> <span data-ttu-id="e5bfb-389">分配策略包时，为策略包中的每个策略类型指定 [组分配的排序](#group-assignment-ranking) 。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-389">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span> 

<span data-ttu-id="e5bfb-390">在此示例中，我们将 Education_Teacher 策略包分配给一个组，其作业排名为1的 TeamsAppSetupPolicy 和 TeamsMeetingBroadcastPolicy，级别为2的 TeamsMeetingPolicy。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-390">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="e5bfb-391">将策略包分配给一批用户</span><span class="sxs-lookup"><span data-stu-id="e5bfb-391">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="e5bfb-392">通过批处理策略程序包分配，您可以一次性为大型用户分配策略包，而无需使用脚本。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-392">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="e5bfb-393">使用 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 提交要分配的一批用户和策略包。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-393">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="e5bfb-394">作业作为后台操作处理，并为每个批处理生成操作 ID。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-394">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="e5bfb-395">然后，你可以使用 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet 跟踪批处理中作业的进度和状态。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-395">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="e5bfb-396">你可以按用户的对象 Id 或会话初始协议指定用户 (SIP) 地址。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-396">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="e5bfb-397">请注意，用户的 SIP 地址通常具有与用户主体名称相同的值 (UPN) 或电子邮件地址，但这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-397">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="e5bfb-398">如果用户使用其 UPN 或电子邮件进行了指定，但它的值与 SIP 地址不同，则该用户的策略分配将失败。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-398">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="e5bfb-399">如果批处理包括重复的用户，则在处理之前将从批处理中删除重复项，并且仅为批处理中剩余的唯一用户提供状态。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-399">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="e5bfb-400">批处理最多可包含5000个用户。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-400">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="e5bfb-401">为获得最佳结果，请不要一次提交多个批次。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-401">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="e5bfb-402">允许批完成处理，然后再提交更多批。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-402">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="e5bfb-403">安装并连接到 Microsoft 团队 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="e5bfb-403">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="e5bfb-404">如果尚未) ，请运行以下操作以安装 [Microsoft 团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams) (。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-404">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="e5bfb-405">请确保安装1.0.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-405">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="e5bfb-406">运行以下操作以连接到团队并启动会话。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-406">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="e5bfb-407">出现提示时，请使用管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-407">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="e5bfb-408">将策略包分配给一批用户</span><span class="sxs-lookup"><span data-stu-id="e5bfb-408">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="e5bfb-409">在此示例中，我们使用 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 将 Education_PrimaryStudent 策略包分配给一批用户。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-409">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="e5bfb-410">获取批处理作业的状态</span><span class="sxs-lookup"><span data-stu-id="e5bfb-410">Get the status of a batch assignment</span></span>

<span data-ttu-id="e5bfb-411">运行以下操作以获取批处理作业的状态，其中 OperationId 是由给定批处理的 cmdlet 返回的操作 ID ```New-CsBatchPolicyAssignmentOperation``` 。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-411">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="e5bfb-412">如果输出显示发生了错误，请运行以下内容以获取有关属性中的错误的详细信息 ```UserState``` 。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-412">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="e5bfb-413">若要了解详细信息，请参阅 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)。</span><span class="sxs-lookup"><span data-stu-id="e5bfb-413">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="e5bfb-414">相关主题</span><span class="sxs-lookup"><span data-stu-id="e5bfb-414">Related topics</span></span>

[<span data-ttu-id="e5bfb-415">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="e5bfb-415">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
