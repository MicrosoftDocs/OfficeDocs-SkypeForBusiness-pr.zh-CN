---
title: 向 Microsoft Teams 中的用户分配策略
author: cichur
ms.author: v-cichur
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
description: 了解在 Microsoft Teams 中向用户分配策略的不同方法。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 5d213c53de22994d46e7d7faf54a8dfd687806d7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821302"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="3abb5-103">向 Microsoft Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="3abb5-104">作为管理员，可以使用策略来控制组织中用户可用的 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="3abb5-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="3abb5-105">例如，有调用策略、会议策略和消息传送策略，仅举几例。</span><span class="sxs-lookup"><span data-stu-id="3abb5-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="3abb5-106">组织具有不同类型的用户，具有独特的需求，而创建和分配的自定义策略允许根据这些需求为不同的用户集定制策略设置。</span><span class="sxs-lookup"><span data-stu-id="3abb5-106">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="3abb5-107">为了便于管理组织中策略，Teams 提供了多种方式来向用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-107">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="3abb5-108">可以直接将策略分配给用户，可以单独分配，也可以通过批量分配大规模分配，也可以将策略分配给用户作为其成员的组。</span><span class="sxs-lookup"><span data-stu-id="3abb5-108">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="3abb5-109">还可使用策略包将预设的策略集合分配给组织中具有类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-109">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="3abb5-110">选择的选项取决于要管理的策略数和要分配到的用户数。</span><span class="sxs-lookup"><span data-stu-id="3abb5-110">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="3abb5-111">通过设置全局 (组织范围内的默认) 策略，以便这些策略应用于组织中的最大用户数，只需将策略分配给需要专用策略的用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-111">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="3abb5-112">本文介绍可以将策略分配给用户的不同方式，以及何时使用策略的建议方案。</span><span class="sxs-lookup"><span data-stu-id="3abb5-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="3abb5-113">哪个策略优先？</span><span class="sxs-lookup"><span data-stu-id="3abb5-113">Which policy takes precedence?</span></span>

<span data-ttu-id="3abb5-114">用户针对每种策略类型都有一个有效策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="3abb5-115">有可能是直接为用户分配了策略，并且该用户也是分配了相同类型的策略的一个或多个组的成员。</span><span class="sxs-lookup"><span data-stu-id="3abb5-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="3abb5-116">在这些类型的方案中，哪个策略优先？</span><span class="sxs-lookup"><span data-stu-id="3abb5-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="3abb5-117">用户的有效策略根据优先级规则确定，如下所示。</span><span class="sxs-lookup"><span data-stu-id="3abb5-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="3abb5-118">如果直接为用户分配了策略 (单个策略，或者通过批处理分配) 策略优先。</span><span class="sxs-lookup"><span data-stu-id="3abb5-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="3abb5-119">在下面的示例中，用户的有效策略是直接分配给用户的 Square Square 会议策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![显示直接分配的策略如何优先的示意图](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="3abb5-121">如果未直接为用户分配给定类型的策略，则分配给该用户是其中一个成员的组的策略优先。</span><span class="sxs-lookup"><span data-stu-id="3abb5-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="3abb5-122">如果用户是多个组的成员，则给定策略类型具有最高 [组分配排名](#group-assignment-ranking) 的策略优先。</span><span class="sxs-lookup"><span data-stu-id="3abb5-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="3abb5-123">本示例中，用户的有效策略是 Exec Teams 和 HD 策略，相对于用户所参与的其他组，该策略具有最高的分配排名，并且还分配了相同策略类型的策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![显示从组继承的策略如何优先的示意图](media/assign-policies-example-group.png)

<span data-ttu-id="3abb5-125">如果用户未直接分配策略，或者不是任何已分配策略的组的成员，该用户会获取该策略类型的全局 (组织范围默认) 策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="3abb5-126">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="3abb5-126">Here's an example.</span></span>

![显示全局策略如何优先的示意图](media/assign-policies-example-global.png)

<span data-ttu-id="3abb5-128">若要了解有关详细信息，请参阅["优先顺序规则"。](#precedence-rules)</span><span class="sxs-lookup"><span data-stu-id="3abb5-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="3abb5-129">分配策略的方法</span><span class="sxs-lookup"><span data-stu-id="3abb5-129">Ways to assign policies</span></span>

<span data-ttu-id="3abb5-130">下面概述了如何向用户分配策略，以及为每个用户分配策略的建议方案。</span><span class="sxs-lookup"><span data-stu-id="3abb5-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="3abb5-131">单击链接了解详情。</span><span class="sxs-lookup"><span data-stu-id="3abb5-131">Click the links to learn more.</span></span>

<span data-ttu-id="3abb5-132">在将策略分配给单个用户或组之前，请首先设置全局 (组织范围内的默认 [) 策略](#set-the-global-policies) ，以便它们适用于组织中的最多用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-132">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="3abb5-133">设置全局策略后，只需将策略分配给需要专用策略的用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-133">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="3abb5-134">要执行的操作</span><span class="sxs-lookup"><span data-stu-id="3abb5-134">Do this</span></span>  |<span data-ttu-id="3abb5-135">如果...</span><span class="sxs-lookup"><span data-stu-id="3abb5-135">If...</span></span>  | <span data-ttu-id="3abb5-136">使用...</span><span class="sxs-lookup"><span data-stu-id="3abb5-136">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="3abb5-137">向单个用户分配策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-137">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="3abb5-138">你是 Teams 的新用户，刚刚入门，或者只需向少量用户分配一个或多个策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-138">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="3abb5-139">Skype for Business Online PowerShell 模块中的 Microsoft Teams 管理中心或 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="3abb5-139">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
|[<span data-ttu-id="3abb5-140">向组分配策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-140">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="3abb5-141">需要根据用户的组成员身份分配策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-141">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="3abb5-142">例如，想要将策略分配给安全组或通讯组列表中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-142">For example, you want to assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="3abb5-143">Teams PowerShell 模块中的 Microsoft Teams 管理中心或 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="3abb5-143">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="3abb5-144">向一批用户分配策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-144">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="3abb5-145">需要将策略分配给大量用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-145">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="3abb5-146">例如，想要一次向组织中数百或数千个用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-146">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="3abb5-147">Teams PowerShell 模块中的 Microsoft Teams 管理中心或 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="3abb5-147">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="3abb5-148">向用户分配策略包</span><span class="sxs-lookup"><span data-stu-id="3abb5-148">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  | <span data-ttu-id="3abb5-149">需要为组织中具有相同或类似角色的特定用户集分配多个策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-149">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="3abb5-150">例如，将教育 (教师) 策略包分配给学校中的教师，以授予他们完全访问聊天、通话和会议以及教育 (中学生) 策略包，以限制某些功能（如私人通话）。</span><span class="sxs-lookup"><span data-stu-id="3abb5-150">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="3abb5-151">Teams PowerShell 模块中的 Microsoft Teams 管理中心或 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="3abb5-151">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="3abb5-152">[在个人预览版中将](#assign-a-policy-package-to-a-group) (包分配给组) </span><span class="sxs-lookup"><span data-stu-id="3abb5-152">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="3abb5-153">需要将多个策略分配给组织中具有相同或类似角色的一组用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-153">You need to assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="3abb5-154">例如，想要将策略包分配给安全组或通讯组列表中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-154">For example, you want to assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="3abb5-155">Microsoft Teams 管理中心 (即将推出) PowerShell 模块中的 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="3abb5-155">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="3abb5-156">将策略包分配给一批用户</span><span class="sxs-lookup"><span data-stu-id="3abb5-156">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="3abb5-157">需要将多个策略分配给组织中具有相同或类似角色的一批用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-157">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="3abb5-158">例如，使用批处理作业将教育 (教师) 策略包分配给学校的所有教师，让他们完全访问聊天、通话和会议，并将教育 (中学生) 策略包分配给一批中学生，以限制某些功能（如私人呼叫）。</span><span class="sxs-lookup"><span data-stu-id="3abb5-158">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="3abb5-159">Teams PowerShell 模块中的 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="3abb5-159">PowerShell cmdlets in the Teams PowerShell module</span></span>|


## <a name="set-the-global-policies"></a><span data-ttu-id="3abb5-160">设置全局策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-160">Set the global policies</span></span>

<span data-ttu-id="3abb5-161">按照以下步骤设置全局策略 (每个策略类型的组织) 默认策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-161">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3abb5-162">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="3abb5-162">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="3abb5-163">在 Microsoft Teams 管理中心的左侧导航中，转到要更新的策略类型的策略页面。</span><span class="sxs-lookup"><span data-stu-id="3abb5-163">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="3abb5-164">例如  >  **，Teams 策略、\*\*\*\*会议**  >  **策略**、**消息传递策略** 或 **语音**  >  **呼叫策略**。</span><span class="sxs-lookup"><span data-stu-id="3abb5-164">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="3abb5-165">选择 **全局 (组织范围内的默认)** 策略以查看当前设置。</span><span class="sxs-lookup"><span data-stu-id="3abb5-165">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="3abb5-166">根据需要更新策略，然后选择"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="3abb5-166">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3abb5-167">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3abb5-167">Using PowerShell</span></span>

<span data-ttu-id="3abb5-168">若要使用 PowerShell 设置全局策略，请使用全局标识符。</span><span class="sxs-lookup"><span data-stu-id="3abb5-168">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="3abb5-169">首先查看当前全局策略，确定要更改的设置。</span><span class="sxs-lookup"><span data-stu-id="3abb5-169">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="3abb5-170">接下来，根据需要更新全局策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-170">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="3abb5-171">只需指定要更改的设置的值。</span><span class="sxs-lookup"><span data-stu-id="3abb5-171">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="3abb5-172">向单个用户分配策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-172">Assign a policy to individual users</span></span>

<span data-ttu-id="3abb5-173">请按照以下步骤将策略分配给单个用户或一次分配给少量用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-173">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3abb5-174">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="3abb5-174">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="3abb5-175">将策略分配给用户：</span><span class="sxs-lookup"><span data-stu-id="3abb5-175">To assign a policy to a user:</span></span>

1. <span data-ttu-id="3abb5-176">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-176">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="3abb5-177">单击用户名的左侧以选择用户，然后单击“编辑设置”。</span><span class="sxs-lookup"><span data-stu-id="3abb5-177">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="3abb5-178">选择要分配的策略，然后单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="3abb5-178">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="3abb5-179">或者，还可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3abb5-179">Or, you can also do the following:</span></span>

1. <span data-ttu-id="3abb5-180">在 Microsoft Teams 管理中心的左侧导航栏中，转到策略页面。</span><span class="sxs-lookup"><span data-stu-id="3abb5-180">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="3abb5-181">单击策略名称左侧，选择要分配的策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-181">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="3abb5-182">选择“管理用户”。</span><span class="sxs-lookup"><span data-stu-id="3abb5-182">Select **Manage users**.</span></span>
4. <span data-ttu-id="3abb5-183">在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="3abb5-183">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="3abb5-184">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="3abb5-184">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="3abb5-185">添加完用户后，选择"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="3abb5-185">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3abb5-186">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3abb5-186">Using PowerShell</span></span>

<span data-ttu-id="3abb5-187">每个策略类型都有其自己的一组 cmdlet 用于管理它。</span><span class="sxs-lookup"><span data-stu-id="3abb5-187">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="3abb5-188">使用 ```Grant-``` 给定策略类型的 cmdlet 分配策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-188">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="3abb5-189">例如，使用 ```Grant-CsTeamsMeetingPolicy``` cmdlet 向用户分配 Teams 会议策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-189">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="3abb5-190">这些 cmdlet 包含在 Skype for Business Online PowerShell 模块中，并记录在 [Skype for Business cmdlet 参考中](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="3abb5-190">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="3abb5-191">下载并安装 [Skype for Business Online PowerShell](https://www.microsoft.com/download/details.aspx?id=39366) (（如果尚未安装) ，然后运行以下代码连接到 Skype for Business Online 并启动会话。</span><span class="sxs-lookup"><span data-stu-id="3abb5-191">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

> [!NOTE]
> <span data-ttu-id="3abb5-192">Skype for Business Online 连接器当前是最新 Teams PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="3abb5-192">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="3abb5-193">如果你使用的是最新的 [Teams PowerShell 公共](https://www.powershellgallery.com/packages/MicrosoftTeams/)版本，则无需安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="3abb5-193">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="3abb5-194">本示例将名为"学生会议策略"的 Teams 会议策略分配给名为 Reda 的用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-194">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="3abb5-195">若要了解有关详细信息，请阅读"通过[PowerShell 管理策略"。](teams-powershell-managing-teams.md#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="3abb5-195">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="3abb5-196">向组分配策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-196">Assign a policy to a group</span></span>

<span data-ttu-id="3abb5-197">通过向组分配策略，可以将策略分配给一组用户，例如安全组或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="3abb5-197">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="3abb5-198">根据优先级规则，将策略分配传播到组中的成员。</span><span class="sxs-lookup"><span data-stu-id="3abb5-198">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="3abb5-199">将成员添加到组或从组中删除成员时，将相应更新其继承的策略分配。</span><span class="sxs-lookup"><span data-stu-id="3abb5-199">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="3abb5-200">建议对最多 50，000 名用户的组分配组的策略分配，但也适用于较大的组。</span><span class="sxs-lookup"><span data-stu-id="3abb5-200">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="3abb5-201">分配策略时，会立即将其分配给组。</span><span class="sxs-lookup"><span data-stu-id="3abb5-201">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="3abb5-202">但是，请注意，将策略分配传播到组的成员以后台操作执行，并且可能需要一些时间，具体取决于组的大小。</span><span class="sxs-lookup"><span data-stu-id="3abb5-202">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="3abb5-203">从组取消分配策略时，或者将成员添加到组或从组中删除成员时，也是如此。</span><span class="sxs-lookup"><span data-stu-id="3abb5-203">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="3abb5-204">组策略分配仅传播到作为组的直接成员的用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-204">Group policy assignments are only propagated to users that are direct members of the group.</span></span> <span data-ttu-id="3abb5-205">分配不会传播到嵌套组的成员。</span><span class="sxs-lookup"><span data-stu-id="3abb5-205">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="3abb5-206">有关向组分配策略的需知信息</span><span class="sxs-lookup"><span data-stu-id="3abb5-206">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="3abb5-207">在开始使用之前，必须了解优先级规则和组分配排名。</span><span class="sxs-lookup"><span data-stu-id="3abb5-207">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="3abb5-208">优先级规则</span><span class="sxs-lookup"><span data-stu-id="3abb5-208">Precedence rules</span></span>

<span data-ttu-id="3abb5-209">对于给定的策略类型，根据以下条件确定用户的有效策略：</span><span class="sxs-lookup"><span data-stu-id="3abb5-209">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="3abb5-210">直接分配给用户的策略优先于分配给组的相同类型的其他任何策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-210">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="3abb5-211">换言之，如果直接为用户分配了给定类型的策略，该用户不会从组继承相同类型的策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-211">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="3abb5-212">这也意味着，如果用户具有直接分配给他们的给定类型的策略，则你必须从用户中删除该策略，然后他们才能从组继承相同类型的策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-212">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="3abb5-213">如果用户没有直接分配的策略，并且是两个或多个组的成员，并且每个组分配的策略类型相同，则用户继承排名最高的组分配策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-213">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="3abb5-214">如果用户不是分配有策略的任何组的成员，则适用于该策略类型的全局 (组织范围默认) 策略将应用于该用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-214">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="3abb5-215">在向分配了策略的组添加或删除用户、从组取消分配策略或者删除直接分配给用户的策略时，将按照这些规则更新用户的有效策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-215">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="3abb5-216">组分配排名</span><span class="sxs-lookup"><span data-stu-id="3abb5-216">Group assignment ranking</span></span>
 
<span data-ttu-id="3abb5-217">将策略分配给组时，请指定组分配的排名。</span><span class="sxs-lookup"><span data-stu-id="3abb5-217">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="3abb5-218">这用于确定如果用户是两个或多个组的成员，并且为每个组分配了相同类型的策略，则用户应继承哪个策略作为有效策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-218">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="3abb5-219">组分配排名相对于相同类型的其他组分配。</span><span class="sxs-lookup"><span data-stu-id="3abb5-219">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="3abb5-220">例如，如果要将调用策略分配给两个组，将一个分配的排名设置为 1，将另一个分配设置为 2，其中 1 是最高排名。</span><span class="sxs-lookup"><span data-stu-id="3abb5-220">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="3abb5-221">组分配排名指示哪个组成员身份比有关继承的其他组成员身份更重要或更相关。</span><span class="sxs-lookup"><span data-stu-id="3abb5-221">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="3abb5-222">例如，你有两个组："应用商店员工"和"应用商店经理"。</span><span class="sxs-lookup"><span data-stu-id="3abb5-222">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="3abb5-223">这两个组分别分配有 Teams 呼叫策略、应用商店员工呼叫策略和应用商店经理呼叫策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-223">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="3abb5-224">对于这两个组的应用商店管理员，其经理角色比作为员工的角色更相关，因此分配给"应用商店经理"组的呼叫策略应具有更高的排名。</span><span class="sxs-lookup"><span data-stu-id="3abb5-224">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="3abb5-225">组</span><span class="sxs-lookup"><span data-stu-id="3abb5-225">Group</span></span> |<span data-ttu-id="3abb5-226">调用策略名称的团队</span><span class="sxs-lookup"><span data-stu-id="3abb5-226">Teams calling policy name</span></span>  |<span data-ttu-id="3abb5-227">等级</span><span class="sxs-lookup"><span data-stu-id="3abb5-227">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="3abb5-228">应用商店经理</span><span class="sxs-lookup"><span data-stu-id="3abb5-228">Store Managers</span></span>   |<span data-ttu-id="3abb5-229">应用商店管理员调用策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-229">Store Managers Calling Policy</span></span>         |<span data-ttu-id="3abb5-230">1</span><span class="sxs-lookup"><span data-stu-id="3abb5-230">1</span></span>|
|<span data-ttu-id="3abb5-231">应用商店员工</span><span class="sxs-lookup"><span data-stu-id="3abb5-231">Store Employees</span></span>    |<span data-ttu-id="3abb5-232">应用商店员工呼叫策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-232">Store Employees Calling Policy</span></span>      |<span data-ttu-id="3abb5-233">2</span><span class="sxs-lookup"><span data-stu-id="3abb5-233">2</span></span>|

<span data-ttu-id="3abb5-234">如果未指定排名，则策略分配会获得最低的排名。</span><span class="sxs-lookup"><span data-stu-id="3abb5-234">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span> 

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3abb5-235">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="3abb5-235">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="3abb5-236">目前，使用 Microsoft Teams 管理中心向组分配策略仅适用于 Teams 通话策略、Teams 通话公园策略、Teams 策略、Teams 实时事件策略、Teams 会议策略和 Teams 消息传送策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-236">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="3abb5-237">对于其他策略类型，请使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3abb5-237">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="3abb5-238">在 Microsoft Teams 管理中心的左侧导航中，转到策略类型页面。</span><span class="sxs-lookup"><span data-stu-id="3abb5-238">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="3abb5-239">例如，转到 **"会议**  >  **策略"。**</span><span class="sxs-lookup"><span data-stu-id="3abb5-239">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="3abb5-240">选择" **组策略分配"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3abb5-240">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="3abb5-241">选择 **"添加** 组"，然后在"将策略 **分配到组"窗格中** 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3abb5-241">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="3abb5-242">搜索并添加要为其分配策略的组。</span><span class="sxs-lookup"><span data-stu-id="3abb5-242">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="3abb5-243">设置组分配的排名。</span><span class="sxs-lookup"><span data-stu-id="3abb5-243">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="3abb5-244">选择要分配的策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-244">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="3abb5-245">选择 **"应用"。**</span><span class="sxs-lookup"><span data-stu-id="3abb5-245">Select **Apply**.</span></span>

<span data-ttu-id="3abb5-246">若要删除组策略分配，请在策略页的"组策略分配"选项卡上，选择组分配，然后选择"**删除"。**</span><span class="sxs-lookup"><span data-stu-id="3abb5-246">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="3abb5-247">若要更改组分配的排名，首先必须删除组策略分配。</span><span class="sxs-lookup"><span data-stu-id="3abb5-247">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="3abb5-248">然后，按照上述步骤将策略分配给组。</span><span class="sxs-lookup"><span data-stu-id="3abb5-248">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3abb5-249">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3abb5-249">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="3abb5-250">目前，并非所有 Teams 策略类型都支持使用 PowerShell 向组分配策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-250">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="3abb5-251">有关[支持的策略类型列表，请参阅 New-CsGroupPolicyAssignment。](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)</span><span class="sxs-lookup"><span data-stu-id="3abb5-251">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="3abb5-252">安装并连接到 Microsoft Teams PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="3abb5-252">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="3abb5-253">有关分步指南，请参阅"安装[Teams PowerShell"。](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="3abb5-253">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="3abb5-254">向一组用户分配策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-254">Assign a policy to a group of users</span></span>

<span data-ttu-id="3abb5-255">使用 [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet 将策略分配给组。</span><span class="sxs-lookup"><span data-stu-id="3abb5-255">You use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="3abb5-256">可以使用对象 ID、SIP 地址或电子邮件地址指定组。</span><span class="sxs-lookup"><span data-stu-id="3abb5-256">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="3abb5-257">本示例将名为"零售经理会议策略"的 Teams 会议策略分配给作业排名为 1 的组。</span><span class="sxs-lookup"><span data-stu-id="3abb5-257">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="3abb5-258">获取组的策略分配</span><span class="sxs-lookup"><span data-stu-id="3abb5-258">Get policy assignments for a group</span></span>

<span data-ttu-id="3abb5-259">使用 [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet 获取分配给组的所有策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-259">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="3abb5-260">请注意，组 ID 始终按组 ID 列出组，即使其 SIP 地址或电子邮件地址用于分配策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-260">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="3abb5-261">本示例检索分配给特定组的所有策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-261">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="3abb5-262">本示例返回分配有 Teams 会议策略的所有组。</span><span class="sxs-lookup"><span data-stu-id="3abb5-262">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="3abb5-263">从组中删除策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-263">Remove a policy from a group</span></span>

<span data-ttu-id="3abb5-264">使用 [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet 从组中删除策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-264">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="3abb5-265">从组中删除策略时，会更新分配给该组且排名较低的相同类型其他策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="3abb5-265">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="3abb5-266">例如，如果删除排名为 2 的策略，则排名为 3 和 4 的策略会更新以反映其新排名。</span><span class="sxs-lookup"><span data-stu-id="3abb5-266">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="3abb5-267">以下两个表显示了此示例。</span><span class="sxs-lookup"><span data-stu-id="3abb5-267">The following two tables show this example.</span></span>

<span data-ttu-id="3abb5-268">下面是 Teams 会议策略的策略分配和优先级列表。</span><span class="sxs-lookup"><span data-stu-id="3abb5-268">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="3abb5-269">组名称</span><span class="sxs-lookup"><span data-stu-id="3abb5-269">Group name</span></span>  |<span data-ttu-id="3abb5-270">策略名称</span><span class="sxs-lookup"><span data-stu-id="3abb5-270">Policy name</span></span>  |<span data-ttu-id="3abb5-271">等级</span><span class="sxs-lookup"><span data-stu-id="3abb5-271">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="3abb5-272">销售</span><span class="sxs-lookup"><span data-stu-id="3abb5-272">Sales</span></span>    |<span data-ttu-id="3abb5-273">销售策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-273">Sales policy</span></span>       | <span data-ttu-id="3abb5-274">1</span><span class="sxs-lookup"><span data-stu-id="3abb5-274">1</span></span>        |
|<span data-ttu-id="3abb5-275">西部区域</span><span class="sxs-lookup"><span data-stu-id="3abb5-275">West Region</span></span>     |<span data-ttu-id="3abb5-276">"西部区域"策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-276">West Region policy</span></span>         |<span data-ttu-id="3abb5-277">2</span><span class="sxs-lookup"><span data-stu-id="3abb5-277">2</span></span>         |
|<span data-ttu-id="3abb5-278">除法</span><span class="sxs-lookup"><span data-stu-id="3abb5-278">Division</span></span>    |<span data-ttu-id="3abb5-279">分区策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-279">Division policy</span></span>         |<span data-ttu-id="3abb5-280">3</span><span class="sxs-lookup"><span data-stu-id="3abb5-280">3</span></span>         |
|<span data-ttu-id="3abb5-281">子公司</span><span class="sxs-lookup"><span data-stu-id="3abb5-281">Subsidiary</span></span>   |<span data-ttu-id="3abb5-282">子公司策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-282">Subsidiary policy</span></span>        |<span data-ttu-id="3abb5-283">4</span><span class="sxs-lookup"><span data-stu-id="3abb5-283">4</span></span>         |

<span data-ttu-id="3abb5-284">如果从"西部区域"组中删除"西部区域"策略，策略分配和优先级将更新如下。</span><span class="sxs-lookup"><span data-stu-id="3abb5-284">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="3abb5-285">组名称</span><span class="sxs-lookup"><span data-stu-id="3abb5-285">Group name</span></span>  |<span data-ttu-id="3abb5-286">策略名称</span><span class="sxs-lookup"><span data-stu-id="3abb5-286">Policy name</span></span>  |<span data-ttu-id="3abb5-287">等级</span><span class="sxs-lookup"><span data-stu-id="3abb5-287">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="3abb5-288">销售</span><span class="sxs-lookup"><span data-stu-id="3abb5-288">Sales</span></span>    |<span data-ttu-id="3abb5-289">销售策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-289">Sales policy</span></span>       | <span data-ttu-id="3abb5-290">1</span><span class="sxs-lookup"><span data-stu-id="3abb5-290">1</span></span>        |
|<span data-ttu-id="3abb5-291">除法</span><span class="sxs-lookup"><span data-stu-id="3abb5-291">Division</span></span>    |<span data-ttu-id="3abb5-292">分区策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-292">Division policy</span></span>         |<span data-ttu-id="3abb5-293">2</span><span class="sxs-lookup"><span data-stu-id="3abb5-293">2</span></span>         |
|<span data-ttu-id="3abb5-294">子公司</span><span class="sxs-lookup"><span data-stu-id="3abb5-294">Subsidiary</span></span>   |<span data-ttu-id="3abb5-295">子公司策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-295">Subsidiary policy</span></span>        |<span data-ttu-id="3abb5-296">3</span><span class="sxs-lookup"><span data-stu-id="3abb5-296">3</span></span>        |

<span data-ttu-id="3abb5-297">本示例从组中删除 Teams 会议策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-297">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="3abb5-298">更改组的策略分配</span><span class="sxs-lookup"><span data-stu-id="3abb5-298">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="3abb5-299">[即将推出 Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3abb5-299">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="3abb5-300">在此期间，若要更改组策略分配，可以从组中删除当前策略分配，然后添加新的策略分配。</span><span class="sxs-lookup"><span data-stu-id="3abb5-300">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="3abb5-301">将策略分配到组后，可以使用 [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet 更改该组的策略分配，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3abb5-301">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="3abb5-302">更改排名</span><span class="sxs-lookup"><span data-stu-id="3abb5-302">Change the ranking</span></span>
- <span data-ttu-id="3abb5-303">更改给定策略类型的策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-303">Change the policy of a given policy type</span></span>
- <span data-ttu-id="3abb5-304">更改给定策略类型和排名的策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-304">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="3abb5-305">本示例将组的 Teams 呼叫公园策略更改为名为 SupportCallPark 的策略，将分配排名更改为 3。</span><span class="sxs-lookup"><span data-stu-id="3abb5-305">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="3abb5-306">更改用户的有效策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-306">Change the effective policy for a user</span></span>

<span data-ttu-id="3abb5-307">以下示例演示了如何更改直接分配了策略的用户的有效策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-307">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="3abb5-308">首先，我们将 [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet 与参数一起用于获取与用户关联的 Teams 会议直播 ```PolicySource``` 策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3abb5-308">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> 

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="3abb5-309">输出显示，直接为用户分配了名为"员工事件"的 Teams 会议直播策略，该策略优先于分配给用户所属组的名为"供应商实时事件"的策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-309">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="3abb5-310">现在，从用户中删除"员工事件"策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-310">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="3abb5-311">这意味着用户不再直接分配 Teams 会议直播策略，并将继承分配给用户所属组的供应商实时事件策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-311">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="3abb5-312">在 Skype for Business PowerShell 模块中使用以下 cmdlet 完成此操作。</span><span class="sxs-lookup"><span data-stu-id="3abb5-312">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="3abb5-313">可以在 Teams PowerShell 模块中使用以下 cmdlet 通过批处理策略分配（其中 $users指定用户列表）大规模地执行此操作。</span><span class="sxs-lookup"><span data-stu-id="3abb5-313">You can use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="3abb5-314">向一批用户分配策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-314">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3abb5-315">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="3abb5-315">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="3abb5-316">将策略批量分配给用户：</span><span class="sxs-lookup"><span data-stu-id="3abb5-316">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="3abb5-317">在 Microsoft Teams 管理中心的左侧导航栏中，选择"**用户"。**</span><span class="sxs-lookup"><span data-stu-id="3abb5-317">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="3abb5-318">搜索要为其分配策略的用户，或筛选视图以显示想要的用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-318">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="3abb5-319">在 **&#x2713;**（复选标记）列，选择用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-319">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="3abb5-320">若要选择所有用户，请单击表格顶部的 &#x2713;（复选标记）。</span><span class="sxs-lookup"><span data-stu-id="3abb5-320">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="3abb5-321">单击“**编辑设置**”，执行所需的更改，然后单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="3abb5-321">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="3abb5-322">若要查看策略分配的状态，请单击"应用"以提交策略分配后，在"用户"页面顶部出现的横幅中，单击 **"活动日志"。**</span><span class="sxs-lookup"><span data-stu-id="3abb5-322">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="3abb5-323">或者，在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"** 仪表板"，然后在"活动日志"下单击"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="3abb5-323">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="3abb5-324">活动日志显示过去 30 天内通过 Microsoft Teams 管理中心向超过 20 个用户批处理的策略分配。</span><span class="sxs-lookup"><span data-stu-id="3abb5-324">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="3abb5-325">若要了解有关详细信息，[请参阅"活动日志"中的"查看策略分配"。](activity-log.md)</span><span class="sxs-lookup"><span data-stu-id="3abb5-325">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3abb5-326">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3abb5-326">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="3abb5-327">目前，并非所有 Teams 策略类型都支持使用 PowerShell 的批处理策略分配。</span><span class="sxs-lookup"><span data-stu-id="3abb5-327">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="3abb5-328">有关[支持的策略类型列表，请参阅 New-CsBatchPolicyAssignmentOperation。](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="3abb5-328">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="3abb5-329">使用批处理策略分配，可以一次将一个策略分配给大量用户，而无需使用脚本。</span><span class="sxs-lookup"><span data-stu-id="3abb5-329">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="3abb5-330">使用 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 提交一批用户和要分配的策略。</span><span class="sxs-lookup"><span data-stu-id="3abb5-330">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="3abb5-331">作业将作为后台操作处理，并为每个批处理生成操作 ID。</span><span class="sxs-lookup"><span data-stu-id="3abb5-331">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="3abb5-332">然后，可以使用 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet 跟踪批处理中分配的进度和状态。</span><span class="sxs-lookup"><span data-stu-id="3abb5-332">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="3abb5-333">可以按用户的对象 ID 或会话启动协议 (SIP) 地址。</span><span class="sxs-lookup"><span data-stu-id="3abb5-333">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="3abb5-334">请注意，用户的 SIP 地址通常具有与 UPN (或电子邮件地址) 用户主体名称相同的值，但这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="3abb5-334">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="3abb5-335">如果用户是使用其 UPN 或电子邮件指定的，但其值不同于其 SIP 地址，则用户的策略分配将失败。</span><span class="sxs-lookup"><span data-stu-id="3abb5-335">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="3abb5-336">如果批处理包含重复用户，则在处理之前将从批处理中删除重复项，并且只会为批中剩余的唯一用户提供状态。</span><span class="sxs-lookup"><span data-stu-id="3abb5-336">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="3abb5-337">批处理最多可包含 5,000 个用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-337">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="3abb5-338">为获得最佳结果，请勿一次提交多个批次。</span><span class="sxs-lookup"><span data-stu-id="3abb5-338">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="3abb5-339">允许批在提交更多批之前完成处理。</span><span class="sxs-lookup"><span data-stu-id="3abb5-339">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="3abb5-340">安装并连接到 Microsoft Teams PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="3abb5-340">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="3abb5-341">运行以下代码以安装 [Microsoft Teams PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams)。</span><span class="sxs-lookup"><span data-stu-id="3abb5-341">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="3abb5-342">请确保安装版本 1.0.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="3abb5-342">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="3abb5-343">运行以下代码以连接到 Teams 并启动会话。</span><span class="sxs-lookup"><span data-stu-id="3abb5-343">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="3abb5-344">系统提示时，使用管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="3abb5-344">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="3abb5-345">安装并连接到 Azure AD PowerShell for Graph 模块 (可选) </span><span class="sxs-lookup"><span data-stu-id="3abb5-345">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="3abb5-346">可能还需要下载并安装 [Azure AD PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 模块 (（如果尚未) 并连接到 Azure AD，以便可以检索组织中用户的列表。</span><span class="sxs-lookup"><span data-stu-id="3abb5-346">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="3abb5-347">运行以下代码以连接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="3abb5-347">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="3abb5-348">系统提示时，使用连接到 Teams 时所使用的相同管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="3abb5-348">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="3abb5-349">向一批用户分配策略</span><span class="sxs-lookup"><span data-stu-id="3abb5-349">Assign a policy to a batch of users</span></span>

<span data-ttu-id="3abb5-350">本示例使用 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 将名为 HR 应用设置策略的应用设置策略分配给 Users_ids.text 文件中列出的一批用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-350">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="3abb5-351">本示例连接到 Azure AD 以检索用户集合，然后将名为"新员工消息传送策略"的消息策略分配给使用其 SIP 地址指定的一批用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-351">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="3abb5-352">获取批处理分配的状态</span><span class="sxs-lookup"><span data-stu-id="3abb5-352">Get the status of a batch assignment</span></span>

<span data-ttu-id="3abb5-353">运行以下代码获取批处理分配的状态，其中 OperationId 是 cmdlet 为给定批返回的操作 ```New-CsBatchPolicyAssignmentOperation``` ID。</span><span class="sxs-lookup"><span data-stu-id="3abb5-353">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="3abb5-354">如果输出显示出错，请运行以下命令，获取有关属性中错误 ```UserState``` 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3abb5-354">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="3abb5-355">若要了解有关详细信息，请参阅[Get-CsBatchPolicyAssignmentOperation。](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="3abb5-355">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="3abb5-356">向用户分配策略包</span><span class="sxs-lookup"><span data-stu-id="3abb5-356">Assign a policy package to users</span></span>

<span data-ttu-id="3abb5-357">Teams 中的策略包是预定义的策略和策略设置的集合，可将其分配给组织中具有相同或类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-357">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="3abb5-358">每个策略包围绕用户角色设计，包括预定义的策略和策略设置，这些策略设置支持该角色的典型活动。</span><span class="sxs-lookup"><span data-stu-id="3abb5-358">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="3abb5-359">策略包的一些示例包括教育 (教师) 包和医疗保健 (辅助) 包。</span><span class="sxs-lookup"><span data-stu-id="3abb5-359">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="3abb5-360">若要了解有关详细信息，请参阅["在 Teams 中管理策略包"。](manage-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="3abb5-360">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="3abb5-361">将策略包分配给一个用户</span><span class="sxs-lookup"><span data-stu-id="3abb5-361">Assign a policy package to one user</span></span>

1. <span data-ttu-id="3abb5-362">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-362">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="3abb5-363">在用户的页面上，单击"策略"，然后在"策略包"**旁边单击"** 编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="3abb5-363">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="3abb5-364">在"**分配策略包"** 窗格中，选择要分配的包，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="3abb5-364">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="3abb5-365">将策略包分配给多个用户</span><span class="sxs-lookup"><span data-stu-id="3abb5-365">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="3abb5-366">在 Microsoft Teams 管理中心的左侧导航栏中，转到"策略包"，然后单击程序包名称左侧，选择要分配的策略包。</span><span class="sxs-lookup"><span data-stu-id="3abb5-366">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="3abb5-367">单击 **"管理用户"。**</span><span class="sxs-lookup"><span data-stu-id="3abb5-367">Click **Manage users**.</span></span>
3. <span data-ttu-id="3abb5-368">在“管理用户”窗格中，按显示名称或用户名搜索用户，选择用户名，然后单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="3abb5-368">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="3abb5-369">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="3abb5-369">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="3abb5-370">添加完用户后，单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="3abb5-370">When you're finished adding users, click **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="3abb5-371">将策略包分配给组。</span><span class="sxs-lookup"><span data-stu-id="3abb5-371">Assign a policy package to a group</span></span>

<span data-ttu-id="3abb5-372">**此功能在私有预览版中**</span><span class="sxs-lookup"><span data-stu-id="3abb5-372">**This feature is in private preview**</span></span>

<span data-ttu-id="3abb5-373">通过将策略包分配到组，可将多个策略分配给一组用户，例如安全组或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="3abb5-373">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="3abb5-374">根据优先级规则，将策略分配传播到组中的成员。</span><span class="sxs-lookup"><span data-stu-id="3abb5-374">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="3abb5-375">将成员添加到组或从组中删除成员时，将相应更新其继承的策略分配。</span><span class="sxs-lookup"><span data-stu-id="3abb5-375">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="3abb5-376">建议最多包含 50，000 名用户的组分配组的策略包分配，但它也将用于较大的组。</span><span class="sxs-lookup"><span data-stu-id="3abb5-376">Policy package assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span> 

<span data-ttu-id="3abb5-377">分配策略包时，会立即将其分配给组。</span><span class="sxs-lookup"><span data-stu-id="3abb5-377">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="3abb5-378">但是，请注意，将策略分配传播到组的成员以后台操作执行，并且可能需要一些时间，具体取决于组的大小。</span><span class="sxs-lookup"><span data-stu-id="3abb5-378">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="3abb5-379">从组取消分配策略时，或者将成员添加到组或从组中删除成员时，也是如此。</span><span class="sxs-lookup"><span data-stu-id="3abb5-379">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3abb5-380">在开始使用之前，必须了解优先级[规则和](#precedence-rules)[组分配排名](#group-assignment-ranking)。</span><span class="sxs-lookup"><span data-stu-id="3abb5-380">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="3abb5-381">请务必阅读并理解本文前面部分有关组[](#what-you-need-to-know-about-policy-assignment-to-groups)的策略分配需了解的概念。</span><span class="sxs-lookup"><span data-stu-id="3abb5-381">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="using-the-microsoft-teams-admin-center-coming-soon"></a><span data-ttu-id="3abb5-382">使用 Microsoft Teams 管理中心 (即将推出) </span><span class="sxs-lookup"><span data-stu-id="3abb5-382">Using the Microsoft Teams admin center (coming soon)</span></span>

<span data-ttu-id="3abb5-383">Microsoft Teams 管理中心中组的策略包分配即将推出。</span><span class="sxs-lookup"><span data-stu-id="3abb5-383">Policy package assignment to groups in the Microsoft Teams admin center is coming soon.</span></span> <span data-ttu-id="3abb5-384">请返回此处查看最新更新。</span><span class="sxs-lookup"><span data-stu-id="3abb5-384">Check back here for the latest updates.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3abb5-385">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3abb5-385">Using PowerShell</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="3abb5-386">安装并连接到 Microsoft Teams PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="3abb5-386">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="3abb5-387">有关分步指南，请参阅"安装[Teams PowerShell"。](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="3abb5-387">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="3abb5-388">将策略包分配给一组用户</span><span class="sxs-lookup"><span data-stu-id="3abb5-388">Assign a policy package to a group of users</span></span>

<span data-ttu-id="3abb5-389">使用 [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet 将策略包分配到组。</span><span class="sxs-lookup"><span data-stu-id="3abb5-389">You use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="3abb5-390">可以使用对象 ID、SIP 地址或电子邮件地址指定组。</span><span class="sxs-lookup"><span data-stu-id="3abb5-390">You can specify a group by using the object Id, SIP address, or email address.</span></span> <span data-ttu-id="3abb5-391">分配策略包时，请为策略 [包中的](#group-assignment-ranking) 每种策略类型指定组分配排名。</span><span class="sxs-lookup"><span data-stu-id="3abb5-391">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span> 

<span data-ttu-id="3abb5-392">本示例将 Education_Teacher 策略包分配给一个组，TeamsAppSetupPolicy 和 TeamsMeetingBroadcastPolicy 的分配排名为 1，TeamsMeetingPolicy 的排名为 2。</span><span class="sxs-lookup"><span data-stu-id="3abb5-392">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="3abb5-393">将策略包分配给一批用户</span><span class="sxs-lookup"><span data-stu-id="3abb5-393">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="3abb5-394">使用批处理策略包分配，可以一次将一个策略包分配给大量用户，而无需使用脚本。</span><span class="sxs-lookup"><span data-stu-id="3abb5-394">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="3abb5-395">使用 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 提交一批用户和要分配的策略包。</span><span class="sxs-lookup"><span data-stu-id="3abb5-395">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="3abb5-396">作业将作为后台操作处理，并为每个批处理生成操作 ID。</span><span class="sxs-lookup"><span data-stu-id="3abb5-396">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="3abb5-397">然后，可以使用 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet 跟踪批处理中分配的进度和状态。</span><span class="sxs-lookup"><span data-stu-id="3abb5-397">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="3abb5-398">可以按用户的对象 ID 或会话启动协议 (SIP) 地址。</span><span class="sxs-lookup"><span data-stu-id="3abb5-398">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="3abb5-399">请注意，用户的 SIP 地址通常具有与 UPN (或电子邮件地址) 用户主体名称相同的值，但这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="3abb5-399">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="3abb5-400">如果用户是使用其 UPN 或电子邮件指定的，但其值不同于其 SIP 地址，则用户的策略分配将失败。</span><span class="sxs-lookup"><span data-stu-id="3abb5-400">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="3abb5-401">如果批处理包含重复用户，则在处理之前将从批处理中删除重复项，并且只会为批中剩余的唯一用户提供状态。</span><span class="sxs-lookup"><span data-stu-id="3abb5-401">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="3abb5-402">批处理最多可包含 5,000 个用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-402">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="3abb5-403">为获得最佳结果，请勿一次提交多个批次。</span><span class="sxs-lookup"><span data-stu-id="3abb5-403">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="3abb5-404">允许批在提交更多批之前完成处理。</span><span class="sxs-lookup"><span data-stu-id="3abb5-404">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="3abb5-405">安装并连接到 Microsoft Teams PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="3abb5-405">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="3abb5-406">运行以下代码，安装 [Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (（如果尚未) ）。</span><span class="sxs-lookup"><span data-stu-id="3abb5-406">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="3abb5-407">请确保安装版本 1.0.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="3abb5-407">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="3abb5-408">运行以下代码以连接到 Teams 并启动会话。</span><span class="sxs-lookup"><span data-stu-id="3abb5-408">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="3abb5-409">系统提示时，使用管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="3abb5-409">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="3abb5-410">将策略包分配给一批用户</span><span class="sxs-lookup"><span data-stu-id="3abb5-410">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="3abb5-411">本示例使用 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet 将 Education_PrimaryStudent 策略包分配给一批用户。</span><span class="sxs-lookup"><span data-stu-id="3abb5-411">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="3abb5-412">获取批处理分配的状态</span><span class="sxs-lookup"><span data-stu-id="3abb5-412">Get the status of a batch assignment</span></span>

<span data-ttu-id="3abb5-413">运行以下代码获取批处理分配的状态，其中 OperationId 是 cmdlet 为给定批返回的操作 ```New-CsBatchPolicyAssignmentOperation``` ID。</span><span class="sxs-lookup"><span data-stu-id="3abb5-413">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="3abb5-414">如果输出显示出错，请运行以下命令，获取有关属性中错误 ```UserState``` 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3abb5-414">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="3abb5-415">若要了解有关详细信息，请参阅[Get-CsBatchPolicyAssignmentOperation。](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="3abb5-415">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="3abb5-416">相关主题</span><span class="sxs-lookup"><span data-stu-id="3abb5-416">Related topics</span></span>

[<span data-ttu-id="3abb5-417">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="3abb5-417">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
