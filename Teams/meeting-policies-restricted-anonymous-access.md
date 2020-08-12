---
title: 从用户中删除 RestrictedAnonymousAccess 团队会议策略
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: 了解如何从组织中的用户删除 RestrictedAnonymousAccess 团队会议策略。
ms.openlocfilehash: 12224ec860552b17b6f7fe50396081943955a88c
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640971"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a><span data-ttu-id="9b623-103">从用户中删除 RestrictedAnonymousAccess 团队会议策略</span><span class="sxs-lookup"><span data-stu-id="9b623-103">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>

<span data-ttu-id="9b623-104">Microsoft 团队中的[会议策略](meeting-policies-in-teams.md)用于控制会议参与者对由组织中的用户安排的会议参与者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="9b623-104">[Meeting policies](meeting-policies-in-teams.md) in Microsoft Teams are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> 

<span data-ttu-id="9b623-105">团队包含名为 RestrictedAnonymousAccess 的内置策略，其中包含预定义的设置，其中包括限制匿名用户启动会议的预定义设置。</span><span class="sxs-lookup"><span data-stu-id="9b623-105">Teams includes a built-in policy named RestrictedAnonymousAccess, which contains pre-defined settings that include restricting anonymous users from starting a meeting.</span></span> <span data-ttu-id="9b623-106"> (匿名用户是指没有经过身份验证的用户。 ) 无法通过管理员编辑或更改会议策略中的预定义设置。</span><span class="sxs-lookup"><span data-stu-id="9b623-106">(Anonymous users are users who haven't been authenticated.) The predefined settings in the meeting policy can't be edited or changed by admins.</span></span>

<span data-ttu-id="9b623-107">本文介绍如何使用 PowerShell 从分配了此策略的用户中删除 RestrictedAnonymousAccess 会议策略。</span><span class="sxs-lookup"><span data-stu-id="9b623-107">This article shows you how to use PowerShell to remove the RestrictedAnonymousAccess meeting policy from users who are assigned this policy.</span></span> <span data-ttu-id="9b623-108">若要了解有关如何使用 PowerShell 管理团队的详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="9b623-108">To learn more about how to manage Teams using PowerShell, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="9b623-109">开始前</span><span class="sxs-lookup"><span data-stu-id="9b623-109">Before you start</span></span>

<span data-ttu-id="9b623-110">安装并连接到[Skype For Business PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=39366)。</span><span class="sxs-lookup"><span data-stu-id="9b623-110">Install and connect to the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="9b623-111">有关分步指南，请参阅[安装 Microsoft 团队 PowerShell](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="9b623-111">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a><span data-ttu-id="9b623-112">为你的组织获取团队会议策略分配</span><span class="sxs-lookup"><span data-stu-id="9b623-112">Get the Teams meeting policy assignments for your organization</span></span>

<span data-ttu-id="9b623-113">运行以下操作，获取组织的团队会议策略分配。</span><span class="sxs-lookup"><span data-stu-id="9b623-113">Run the following to get the Teams meeting policy assignments for your organization.</span></span>

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

<span data-ttu-id="9b623-114">在此示例中，返回以下输出，这显示为两个用户分配了 RestrictedAnonymousAccess 会议策略。</span><span class="sxs-lookup"><span data-stu-id="9b623-114">In this example, the following output is returned, which shows that two users are assigned the RestrictedAnonymousAccess meeting policy.</span></span>

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a><span data-ttu-id="9b623-115">取消分配用户的 RestrictedAnonymous 会议策略</span><span class="sxs-lookup"><span data-stu-id="9b623-115">Unassign the RestrictedAnonymous meeting policy from users</span></span>

<span data-ttu-id="9b623-116">若要删除用户的 RestrictedAnonymous 会议策略，你可以使用[CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet （如果你有少量用户 (例如，小于100用户) 。</span><span class="sxs-lookup"><span data-stu-id="9b623-116">To remove the the RestrictedAnonymous meeting policy from users, you can use the [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet if you have a small number of users (for example, less than 100 users).</span></span> <span data-ttu-id="9b623-117">如果您有大量用户 (例如，超过100用户) ，则使用[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet 提交批处理操作将更高效。</span><span class="sxs-lookup"><span data-stu-id="9b623-117">If you have a large number of users (for example, more than 100 users), it's more efficient to use the  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet to submit a batch operation.</span></span>

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a><span data-ttu-id="9b623-118">使用授权 CsTeamsMeeting 策略 cmdlet</span><span class="sxs-lookup"><span data-stu-id="9b623-118">Use the Grant-CsTeamsMeeting Policy cmdlet</span></span>

<span data-ttu-id="9b623-119">运行以下操作以从用户中删除 RestrictedAnonymous 会议策略。</span><span class="sxs-lookup"><span data-stu-id="9b623-119">Run the following to remove the RestrictedAnonymous meeting policy from users.</span></span>

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a><span data-ttu-id="9b623-120">使用 CsBatchPolicyAssignmentOperation cmdlet</span><span class="sxs-lookup"><span data-stu-id="9b623-120">Use the New-CsBatchPolicyAssignmentOperation cmdlet</span></span>

<span data-ttu-id="9b623-121">通过[批处理策略分配](assign-policies.md#assign-a-policy-to-a-batch-of-users)，您可以删除或更新策略的最大用户数为5000。</span><span class="sxs-lookup"><span data-stu-id="9b623-121">With [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users), the maximum number of users for which you can remove or update policies is 5,000 at a time.</span></span> <span data-ttu-id="9b623-122">例如，如果您有超过5000的用户，则需要提交多个批次。</span><span class="sxs-lookup"><span data-stu-id="9b623-122">For example, if you have more than 5,000 users, you'll need to submit multiple batches.</span></span> <span data-ttu-id="9b623-123">为获得最佳结果，请不要一次提交多个批次。</span><span class="sxs-lookup"><span data-stu-id="9b623-123">For best results, do not submit multiple batches at a time.</span></span> <span data-ttu-id="9b623-124">允许批完成处理，然后再提交更多批。</span><span class="sxs-lookup"><span data-stu-id="9b623-124">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="9b623-125">[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) Cmdlet 位于团队 PowerShell 模块中。</span><span class="sxs-lookup"><span data-stu-id="9b623-125">The [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet is in the Teams PowerShell module.</span></span> <span data-ttu-id="9b623-126">在执行这些步骤之前，请安装并连接到[团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams)。</span><span class="sxs-lookup"><span data-stu-id="9b623-126">Before you follow these steps, install and connect to the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="9b623-127">有关分步指南，请参阅[安装 Microsoft 团队 PowerShell](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="9b623-127">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

<span data-ttu-id="9b623-128">运行以下命令以从一批用户中删除 RestrictedAnonymousAccess 会议策略。</span><span class="sxs-lookup"><span data-stu-id="9b623-128">Run the following commands to remove the RestrictedAnonymousAccess meeting policy from a batch of users.</span></span>

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a><span data-ttu-id="9b623-129">获取批处理作业的状态</span><span class="sxs-lookup"><span data-stu-id="9b623-129">Get the status of the batch assignment</span></span>

<span data-ttu-id="9b623-130">每个批处理作业都将返回一个操作 ID，您可以使用该 ID 跟踪作业的进度和状态，并确定可能出现的任何故障。</span><span class="sxs-lookup"><span data-stu-id="9b623-130">Each batch assignment returns an operation ID, which you can use to track the progress and status of the assignments and identify any failures that might occur.</span></span> <span data-ttu-id="9b623-131">例如，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="9b623-131">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

<span data-ttu-id="9b623-132">请确保**ErrorCount**为**0** (零) 和**OverallStatus**已**完成**。</span><span class="sxs-lookup"><span data-stu-id="9b623-132">Make sure the **ErrorCount** is **0** (zero) and **OverallStatus** is **Completed**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9b623-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="9b623-133">Related topics</span></span>

- [<span data-ttu-id="9b623-134">管理团队中的会议策略</span><span class="sxs-lookup"><span data-stu-id="9b623-134">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="9b623-135">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="9b623-135">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="9b623-136">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="9b623-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
