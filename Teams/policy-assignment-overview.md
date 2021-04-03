---
title: 在 Teams 中分配策略
author: KarliStites
ms.author: kastites
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
description: 了解在 Microsoft Teams 中向用户和组分配策略和策略包的不同方法。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 00f78b3b134c6741a89c0d7b3f43d32a11c182cc
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574303"
---
# <a name="assign-policies-in-teams--getting-started"></a><span data-ttu-id="726dd-103">在 Teams 中分配策略 - 入门</span><span class="sxs-lookup"><span data-stu-id="726dd-103">Assign policies in Teams – getting started</span></span>

<span data-ttu-id="726dd-104">作为管理员，可以使用策略来控制可供组织中用户使用的 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="726dd-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="726dd-105">例如，有调用策略、会议策略和消息传递策略，仅举几例。</span><span class="sxs-lookup"><span data-stu-id="726dd-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="726dd-106">组织具有不同类型的用户，具有独特的需求。</span><span class="sxs-lookup"><span data-stu-id="726dd-106">Organizations have different types of users with unique needs.</span></span> <span data-ttu-id="726dd-107">通过创建和分配的自定义策略，可以根据这些需求为不同的用户集定制策略设置。</span><span class="sxs-lookup"><span data-stu-id="726dd-107">Custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="726dd-108">为了轻松管理组织中策略，Teams 提供多种方法将策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="726dd-108">To easily manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="726dd-109">将策略直接分配给用户，不管是单独分配还是大规模分配，或者用户作为其成员的组。</span><span class="sxs-lookup"><span data-stu-id="726dd-109">Assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="726dd-110">还可使用策略包将预设的策略集合分配给组织中具有类似角色的用户。</span><span class="sxs-lookup"><span data-stu-id="726dd-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="726dd-111">选择的选项取决于要管理的策略数以及要为其分配策略的用户数。</span><span class="sxs-lookup"><span data-stu-id="726dd-111">The option that you choose depends on the number of policies that you're managing and the number of users you're assigning policies to.</span></span> <span data-ttu-id="726dd-112">全局 (组织范围内的默认) 策略适用于组织中的最多用户。</span><span class="sxs-lookup"><span data-stu-id="726dd-112">Global (Org-wide default) policies apply to the largest number of users in your organization.</span></span> <span data-ttu-id="726dd-113">只需将策略分配给需要专用策略的用户。</span><span class="sxs-lookup"><span data-stu-id="726dd-113">You only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="726dd-114">本文介绍可以将策略分配给用户的不同方法，以及何时使用策略的建议方案。</span><span class="sxs-lookup"><span data-stu-id="726dd-114">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

<span data-ttu-id="726dd-115">若要详细了解如何 **向用户和组分配** 策略，请参阅 [向用户和组分配策略](assign-policies-users-and-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="726dd-115">For details on how to **assign policies to users and groups**, see [assigning policies to users and groups](assign-policies-users-and-groups.md).</span></span> <span data-ttu-id="726dd-116">若要详细了解如何分配 **策略包，** 请参阅 [分配策略包](assign-policy-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="726dd-116">For details on how to **assign policy packages**, see [assign policy packages](assign-policy-packages.md).</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="726dd-117">哪些策略优先？</span><span class="sxs-lookup"><span data-stu-id="726dd-117">Which policy takes precedence?</span></span>

<span data-ttu-id="726dd-118">用户针对每种策略类型都有一个有效策略。</span><span class="sxs-lookup"><span data-stu-id="726dd-118">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="726dd-119">有可能（甚至有可能）直接为用户分配一个策略，并且该用户也是分配了相同类型的策略的一个或多个组的成员。</span><span class="sxs-lookup"><span data-stu-id="726dd-119">It's possible, or even likely, that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="726dd-120">在这类方案中，哪一种策略优先？</span><span class="sxs-lookup"><span data-stu-id="726dd-120">In these kinds of scenarios, which policy takes precedence?</span></span> <span data-ttu-id="726dd-121">用户的有效策略根据优先级规则确定，如下所示。</span><span class="sxs-lookup"><span data-stu-id="726dd-121">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="726dd-122">如果直接为用户分配了一个策略 (单独分配或通过批处理分配) ，则该策略优先。</span><span class="sxs-lookup"><span data-stu-id="726dd-122">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="726dd-123">在下面的可视化示例中，用户的有效策略是直接分配给用户的"万网百元"会议策略。</span><span class="sxs-lookup"><span data-stu-id="726dd-123">In the following visual example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![显示直接分配的策略如何优先的示意图](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="726dd-125">如果未直接为用户分配给定类型的策略，则分配给该用户是其中一个成员的组的策略优先。</span><span class="sxs-lookup"><span data-stu-id="726dd-125">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="726dd-126">如果用户是多个组的成员，则对于给定策略类型 (组分配) 优先级最高的策略优先。 [](assign-policies-users-and-groups.md#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="726dd-126">If a user is a member of multiple groups, the policy that has the highest ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)) for the given policy type takes precedence.</span></span>

<span data-ttu-id="726dd-127">在此可视示例中，用户的有效策略是 Exec Teams 和 HD 策略，相对于用户所参与的其他组，分配排名最高，并且还分配了相同策略类型的策略。</span><span class="sxs-lookup"><span data-stu-id="726dd-127">In this visual example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![显示从组继承的策略如何优先的示意图](media/assign-policies-example-group.png)

<span data-ttu-id="726dd-129">如果用户未直接分配策略，或者不是任何分配了策略的组的成员，该用户会获取该策略类型的全局 (组织范围默认) 策略。</span><span class="sxs-lookup"><span data-stu-id="726dd-129">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="726dd-130">下面是一个可视示例。</span><span class="sxs-lookup"><span data-stu-id="726dd-130">Here's a visual example.</span></span>

![显示全局策略如何优先的示意图](media/assign-policies-example-global.png)

<span data-ttu-id="726dd-132">有关详细信息，请参阅 ([优先级规则) 。](assign-policies-users-and-groups.md#precedence-rules)</span><span class="sxs-lookup"><span data-stu-id="726dd-132">To learn more, see ([Precedence rules](assign-policies-users-and-groups.md#precedence-rules)).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="726dd-133">分配策略的方法</span><span class="sxs-lookup"><span data-stu-id="726dd-133">Ways to assign policies</span></span>

<span data-ttu-id="726dd-134">下面概述了如何向用户分配策略，以及为每个用户分配策略的建议方案。</span><span class="sxs-lookup"><span data-stu-id="726dd-134">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="726dd-135">选择链接以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="726dd-135">Select the links to learn more.</span></span>

<span data-ttu-id="726dd-136">在向单个用户或组分配策略之前，请首先设置全局 (组织范围的默认 [) 策略](#set-the-global-policies) ，以便它们适用于组织中的最多用户。</span><span class="sxs-lookup"><span data-stu-id="726dd-136">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="726dd-137">设置全局策略后，只需将策略分配给需要专用策略的用户。</span><span class="sxs-lookup"><span data-stu-id="726dd-137">Once the global policies are set, you'll only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="726dd-138">执行此操作</span><span class="sxs-lookup"><span data-stu-id="726dd-138">Do this</span></span>  |<span data-ttu-id="726dd-139">如果...</span><span class="sxs-lookup"><span data-stu-id="726dd-139">If...</span></span>  | <span data-ttu-id="726dd-140">使用...</span><span class="sxs-lookup"><span data-stu-id="726dd-140">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="726dd-141">向单个用户分配策略</span><span class="sxs-lookup"><span data-stu-id="726dd-141">Assign a policy to individual users</span></span>](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | <span data-ttu-id="726dd-142">你是 Teams 的新用户，刚刚入门，或者只需向少量用户分配一个或多个策略。</span><span class="sxs-lookup"><span data-stu-id="726dd-142">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="726dd-143">Teams PowerShell 模块中的 Microsoft Teams 管理中心或 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="726dd-143">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>
|[<span data-ttu-id="726dd-144">向组分配策略</span><span class="sxs-lookup"><span data-stu-id="726dd-144">Assign a policy to a group</span></span>](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |<span data-ttu-id="726dd-145">根据用户的组成员身份分配策略。</span><span class="sxs-lookup"><span data-stu-id="726dd-145">Assign policies based on a user's group membership.</span></span> <span data-ttu-id="726dd-146">例如，将策略分配给安全组或通讯组列表中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="726dd-146">For example, assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="726dd-147">Teams PowerShell 模块中的 Microsoft Teams 管理中心或 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="726dd-147">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="726dd-148">向一批用户分配策略</span><span class="sxs-lookup"><span data-stu-id="726dd-148">Assign a policy to a batch of users</span></span>](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="726dd-149">将策略分配给大量用户。</span><span class="sxs-lookup"><span data-stu-id="726dd-149">Assign policies to large sets of users.</span></span> <span data-ttu-id="726dd-150">例如，一次向组织中数百或数千个用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="726dd-150">For example, assign a policy to hundreds or thousands of users in your organization at a time.</span></span> |<span data-ttu-id="726dd-151">Teams PowerShell 模块中的 Microsoft Teams 管理中心或 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="726dd-151">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="726dd-152">向用户分配策略包</span><span class="sxs-lookup"><span data-stu-id="726dd-152">Assign a policy package to users</span></span>](assign-policy-packages.md#assign-a-policy-package-to-users)  |<span data-ttu-id="726dd-153">将多个策略分配给组织中具有相同或类似角色的特定用户集。</span><span class="sxs-lookup"><span data-stu-id="726dd-153">Assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="726dd-154">例如，将教育 (教师) 策略包分配给学校的教师，让他们完全访问聊天、通话和会议。</span><span class="sxs-lookup"><span data-stu-id="726dd-154">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="726dd-155">将教育 (中学生) 策略包分配给中学生，以限制某些功能，例如私人通话。</span><span class="sxs-lookup"><span data-stu-id="726dd-155">Assign the Education (Secondary school student) policy package to secondary students to limit certain capabilities such as private calling.</span></span>  |<span data-ttu-id="726dd-156">Teams PowerShell 模块中的 Microsoft Teams 管理中心或 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="726dd-156">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="726dd-157">[在个人预览版中将策略包](assign-policy-packages.md#assign-a-policy-package-to-a-group) (组) </span><span class="sxs-lookup"><span data-stu-id="726dd-157">[Assign a policy package to a group](assign-policy-packages.md#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="726dd-158">将多个策略分配给组织中具有相同或类似角色的一组用户。</span><span class="sxs-lookup"><span data-stu-id="726dd-158">Assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="726dd-159">例如，将策略包分配给安全组或通讯组列表中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="726dd-159">For example, assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="726dd-160">Microsoft Teams 管理中心 (即将) Teams PowerShell 模块中的 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="726dd-160">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="726dd-161">将策略包分配给一批用户</span><span class="sxs-lookup"><span data-stu-id="726dd-161">Assign a policy package to a batch of users</span></span>](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="726dd-162">将多个策略分配给组织中具有相同或类似角色的一批用户。</span><span class="sxs-lookup"><span data-stu-id="726dd-162">Assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="726dd-163">例如，使用批处理分配 (教师) 策略包，让他们完全访问聊天、通话和会议。</span><span class="sxs-lookup"><span data-stu-id="726dd-163">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="726dd-164">将教育 (中学生) 策略包分配给一批辅助学生，以限制某些功能，例如私人通话。</span><span class="sxs-lookup"><span data-stu-id="726dd-164">Assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities such as private calling.</span></span>|<span data-ttu-id="726dd-165">Teams PowerShell 模块中的 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="726dd-165">PowerShell cmdlets in the Teams PowerShell module</span></span>|

## <a name="set-the-global-policies"></a><span data-ttu-id="726dd-166">设置全局策略</span><span class="sxs-lookup"><span data-stu-id="726dd-166">Set the global policies</span></span>

<span data-ttu-id="726dd-167">按照以下步骤设置每个策略 (组织范围的) 策略。</span><span class="sxs-lookup"><span data-stu-id="726dd-167">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="726dd-168">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="726dd-168">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="726dd-169">在 Microsoft Teams 管理中心的左侧导航栏中，转到要更新的策略类型的策略页。</span><span class="sxs-lookup"><span data-stu-id="726dd-169">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="726dd-170">例如 **，Teams**  >  **Teams 策略**、**会议**  >  **策略、\*\*\*\*消息策略** 或 **语音**  >  **呼叫策略**。</span><span class="sxs-lookup"><span data-stu-id="726dd-170">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="726dd-171">选择 **"全局 (组织范围的默认**) 策略以查看当前设置。</span><span class="sxs-lookup"><span data-stu-id="726dd-171">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="726dd-172">根据需要更新策略，然后选择"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="726dd-172">Update the policy as needed, and then select **Apply**.</span></span>

![在 Teams 管理中心更新全局策略](media/assign-globalpolicy.png)

### <a name="using-powershell"></a><span data-ttu-id="726dd-174">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="726dd-174">Using PowerShell</span></span>

<span data-ttu-id="726dd-175">若要使用 PowerShell 设置全局策略，请使用全局标识符。</span><span class="sxs-lookup"><span data-stu-id="726dd-175">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="726dd-176">首先查看当前全局策略，确定要更改的设置。</span><span class="sxs-lookup"><span data-stu-id="726dd-176">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="726dd-177">接下来，根据需要更新全局策略。</span><span class="sxs-lookup"><span data-stu-id="726dd-177">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="726dd-178">只需为要更改的设置指定值。</span><span class="sxs-lookup"><span data-stu-id="726dd-178">You only need to specify values for the settings that you want to change.</span></span>

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="726dd-179">在活动日志中查看策略分配</span><span class="sxs-lookup"><span data-stu-id="726dd-179">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="726dd-180">在 Microsoft Teams 管理中心向用户分配策略时，可以在活动日志中查看这些策略分配的状态。</span><span class="sxs-lookup"><span data-stu-id="726dd-180">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="726dd-181">"活动日志"显示过去 30 天内通过 Microsoft Teams 管理中心向超过 20 个用户批量分配的策略。</span><span class="sxs-lookup"><span data-stu-id="726dd-181">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="726dd-182">请记住，活动日志不会显示策略包分配、通过 Microsoft Teams 管理中心向少于 20 名用户的批次显示策略分配，或者通过 PowerShell 显示策略分配。</span><span class="sxs-lookup"><span data-stu-id="726dd-182">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

!["活动日志"页的屏幕截图](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="726dd-184">在活动日志中查看策略分配活动</span><span class="sxs-lookup"><span data-stu-id="726dd-184">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="726dd-185">在活动日志中查看策略分配：</span><span class="sxs-lookup"><span data-stu-id="726dd-185">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="726dd-186">在 Microsoft Teams 管理中心的左侧导航栏中，转到"仪表板 **"，然后在**"活动 **日志**"下选择"**查看详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="726dd-186">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="726dd-187">可以查看所有策略分配或按状态筛选列表，以只显示未启动、正在进行或 **已完成的分配**。 </span><span class="sxs-lookup"><span data-stu-id="726dd-187">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="726dd-188">你将看到有关每个作业的以下信息：</span><span class="sxs-lookup"><span data-stu-id="726dd-188">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="726dd-189">**名称**：策略分配的名称。</span><span class="sxs-lookup"><span data-stu-id="726dd-189">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="726dd-190">单击该链接可查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="726dd-190">Click the link to view more details.</span></span> <span data-ttu-id="726dd-191">这包括策略分配到的用户数，以及已完成、进行中和未启动的分配数。</span><span class="sxs-lookup"><span data-stu-id="726dd-191">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="726dd-192">还将看到批处理中的用户列表，以及每个用户的状态和结果。</span><span class="sxs-lookup"><span data-stu-id="726dd-192">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="726dd-193">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="726dd-193">Here's an example:</span></span>

        ![屏幕截图](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="726dd-195">**已提交**：提交策略分配的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="726dd-195">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="726dd-196">**完成时间**：完成策略分配的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="726dd-196">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="726dd-197">**影响：** 批中的用户数。</span><span class="sxs-lookup"><span data-stu-id="726dd-197">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="726dd-198">**总体状态**：策略分配的状态。</span><span class="sxs-lookup"><span data-stu-id="726dd-198">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="726dd-199">还可以从"用户"页 **访问活动日志** 。</span><span class="sxs-lookup"><span data-stu-id="726dd-199">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="726dd-200">单击" **应用** "提交批量策略分配后，页面顶部显示一个横幅。</span><span class="sxs-lookup"><span data-stu-id="726dd-200">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="726dd-201">单击 **横幅中的** "活动日志"链接。</span><span class="sxs-lookup"><span data-stu-id="726dd-201">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="726dd-202">相关主题</span><span class="sxs-lookup"><span data-stu-id="726dd-202">Related topics</span></span>

- [<span data-ttu-id="726dd-203">将策略分配给用户和组</span><span class="sxs-lookup"><span data-stu-id="726dd-203">Assign policies to users and groups</span></span>](assign-policies-users-and-groups.md)
- [<span data-ttu-id="726dd-204">将策略包分配给用户和组</span><span class="sxs-lookup"><span data-stu-id="726dd-204">Assign policy packages to users and groups</span></span>](assign-policy-packages.md)
- [<span data-ttu-id="726dd-205">使用策略管理 Teams</span><span class="sxs-lookup"><span data-stu-id="726dd-205">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="726dd-206">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="726dd-206">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)