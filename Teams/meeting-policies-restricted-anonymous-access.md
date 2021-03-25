---
title: 从用户中删除 RestrictedAnonymousAccess Teams 会议策略
author: cichur
ms.author: v-cichur
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
description: 了解如何从组织中用户中删除 RestrictedAnonymousAccess Teams 会议策略。
ms.openlocfilehash: aab4b524ee0c9ab5cab3244a0897730fea0361a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121340"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a><span data-ttu-id="bb4ed-103">从用户中删除 RestrictedAnonymousAccess Teams 会议策略</span><span class="sxs-lookup"><span data-stu-id="bb4ed-103">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>

<span data-ttu-id="bb4ed-104">[](meeting-policies-in-teams.md) Microsoft Teams 中的会议策略用于控制可供会议参与者用于组织中用户安排的会议的功能。</span><span class="sxs-lookup"><span data-stu-id="bb4ed-104">[Meeting policies](meeting-policies-in-teams.md) in Microsoft Teams are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> 

<span data-ttu-id="bb4ed-105">Teams 包括名为 RestrictedAnonymousAccess 的内置策略，其中包含预定义的设置，其中包括限制匿名用户启动会议。</span><span class="sxs-lookup"><span data-stu-id="bb4ed-105">Teams includes a built-in policy named RestrictedAnonymousAccess, which contains pre-defined settings that include restricting anonymous users from starting a meeting.</span></span> <span data-ttu-id="bb4ed-106"> (匿名用户是尚未经过身份验证的用户。) 管理员无法编辑或更改会议策略中的预定义设置。</span><span class="sxs-lookup"><span data-stu-id="bb4ed-106">(Anonymous users are users who haven't been authenticated.) The predefined settings in the meeting policy can't be edited or changed by admins.</span></span>

<span data-ttu-id="bb4ed-107">本文演示如何使用 PowerShell 从分配了此策略的用户中删除 RestrictedAnonymousAccess 会议策略。</span><span class="sxs-lookup"><span data-stu-id="bb4ed-107">This article shows you how to use PowerShell to remove the RestrictedAnonymousAccess meeting policy from users who are assigned this policy.</span></span> <span data-ttu-id="bb4ed-108">若要详细了解如何使用 PowerShell 管理 Teams，请参阅 [Teams PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="bb4ed-108">To learn more about how to manage Teams using PowerShell, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="bb4ed-109">开始前</span><span class="sxs-lookup"><span data-stu-id="bb4ed-109">Before you start</span></span>

<span data-ttu-id="bb4ed-110">安装并连接到 [Skype for Business PowerShell 模块](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bb4ed-110">Install and connect to the [Skype for Business PowerShell module](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).</span></span> <span data-ttu-id="bb4ed-111">有关分步指南，请参阅[安装 Microsoft Teams PowerShell。](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="bb4ed-111">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a><span data-ttu-id="bb4ed-112">获取组织的 Teams 会议策略分配</span><span class="sxs-lookup"><span data-stu-id="bb4ed-112">Get the Teams meeting policy assignments for your organization</span></span>

<span data-ttu-id="bb4ed-113">运行以下代码，获取组织的 Teams 会议策略分配。</span><span class="sxs-lookup"><span data-stu-id="bb4ed-113">Run the following to get the Teams meeting policy assignments for your organization.</span></span>

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

<span data-ttu-id="bb4ed-114">本示例返回以下输出，其中显示为两个用户分配了 RestrictedAnonymousAccess 会议策略。</span><span class="sxs-lookup"><span data-stu-id="bb4ed-114">In this example, the following output is returned, which shows that two users are assigned the RestrictedAnonymousAccess meeting policy.</span></span>

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a><span data-ttu-id="bb4ed-115">从用户取消分配 RestrictedAnonymous 会议策略</span><span class="sxs-lookup"><span data-stu-id="bb4ed-115">Unassign the RestrictedAnonymous meeting policy from users</span></span>

<span data-ttu-id="bb4ed-116">若要从用户中删除 RestrictedAnonymous 会议策略，可以使用 [Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet（如果用户数量较少 (例如，少于 100 个用户) ）。</span><span class="sxs-lookup"><span data-stu-id="bb4ed-116">To remove the the RestrictedAnonymous meeting policy from users, you can use the [Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet if you have a small number of users (for example, less than 100 users).</span></span> <span data-ttu-id="bb4ed-117">如果有大量用户 (例如，超过 100 个用户) ，则使用  [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet 提交批处理操作会更有效。</span><span class="sxs-lookup"><span data-stu-id="bb4ed-117">If you have a large number of users (for example, more than 100 users), it's more efficient to use the  [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet to submit a batch operation.</span></span>

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a><span data-ttu-id="bb4ed-118">使用 Grant-CsTeamsMeeting Policy cmdlet</span><span class="sxs-lookup"><span data-stu-id="bb4ed-118">Use the Grant-CsTeamsMeeting Policy cmdlet</span></span>

<span data-ttu-id="bb4ed-119">运行以下操作，从用户中删除 RestrictedAnonymous 会议策略。</span><span class="sxs-lookup"><span data-stu-id="bb4ed-119">Run the following to remove the RestrictedAnonymous meeting policy from users.</span></span>

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a><span data-ttu-id="bb4ed-120">使用 New-CsBatchPolicyAssignmentOperation cmdlet</span><span class="sxs-lookup"><span data-stu-id="bb4ed-120">Use the New-CsBatchPolicyAssignmentOperation cmdlet</span></span>

<span data-ttu-id="bb4ed-121">使用 [批处理策略分配](assign-policies.md#assign-a-policy-to-a-batch-of-users)时，可以删除或更新策略的最大用户数是一次 5，000。</span><span class="sxs-lookup"><span data-stu-id="bb4ed-121">With [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users), the maximum number of users for which you can remove or update policies is 5,000 at a time.</span></span> <span data-ttu-id="bb4ed-122">例如，如果用户数超过 5，000，则需要提交多个批次。</span><span class="sxs-lookup"><span data-stu-id="bb4ed-122">For example, if you have more than 5,000 users, you'll need to submit multiple batches.</span></span> <span data-ttu-id="bb4ed-123">为获得最佳结果，请勿一次提交多个批。</span><span class="sxs-lookup"><span data-stu-id="bb4ed-123">For best results, do not submit multiple batches at a time.</span></span> <span data-ttu-id="bb4ed-124">允许批处理在提交更多批之前完成处理。</span><span class="sxs-lookup"><span data-stu-id="bb4ed-124">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="bb4ed-125">[New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet 位于 Teams PowerShell 模块中。</span><span class="sxs-lookup"><span data-stu-id="bb4ed-125">The [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet is in the Teams PowerShell module.</span></span> <span data-ttu-id="bb4ed-126">在按照这些步骤操作之前，请安装并连接到 [Teams PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams)。</span><span class="sxs-lookup"><span data-stu-id="bb4ed-126">Before you follow these steps, install and connect to the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="bb4ed-127">有关分步指南，请参阅[安装 Microsoft Teams PowerShell。](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="bb4ed-127">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

<span data-ttu-id="bb4ed-128">运行以下命令，从一批用户中删除 RestrictedAnonymousAccess 会议策略。</span><span class="sxs-lookup"><span data-stu-id="bb4ed-128">Run the following commands to remove the RestrictedAnonymousAccess meeting policy from a batch of users.</span></span>

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a><span data-ttu-id="bb4ed-129">获取批处理分配的状态</span><span class="sxs-lookup"><span data-stu-id="bb4ed-129">Get the status of the batch assignment</span></span>

<span data-ttu-id="bb4ed-130">每个批处理分配都返回一个操作 ID，可用于跟踪分配的进度和状态，并确定可能发生的任何故障。</span><span class="sxs-lookup"><span data-stu-id="bb4ed-130">Each batch assignment returns an operation ID, which you can use to track the progress and status of the assignments and identify any failures that might occur.</span></span> <span data-ttu-id="bb4ed-131">例如，运行以下代码：</span><span class="sxs-lookup"><span data-stu-id="bb4ed-131">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

<span data-ttu-id="bb4ed-132">确保 **ErrorCount** 为 **0** (零) **OverallStatus** 为 **"已完成"。**</span><span class="sxs-lookup"><span data-stu-id="bb4ed-132">Make sure the **ErrorCount** is **0** (zero) and **OverallStatus** is **Completed**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bb4ed-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="bb4ed-133">Related topics</span></span>

- [<span data-ttu-id="bb4ed-134">管理 Teams 中的会议策略</span><span class="sxs-lookup"><span data-stu-id="bb4ed-134">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="bb4ed-135">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="bb4ed-135">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="bb4ed-136">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="bb4ed-136">Assign policies to your users in Teams</span></span>](assign-policies.md)