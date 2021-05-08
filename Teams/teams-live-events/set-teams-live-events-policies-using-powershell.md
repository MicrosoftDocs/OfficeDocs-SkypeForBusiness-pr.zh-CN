---
title: 使用 PowerShell 设置实时事件策略
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 如何使用 PowerShell 在 Teams 中设置策略的示例，以控制谁可以在组织中保存实时事件以及事件可用的功能。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 95b78b520b6978c85715e6dc1c1314ed279a305b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119141"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="71c96-103">使用 PowerShell 在 Microsoft Teams 中设置实时事件策略</span><span class="sxs-lookup"><span data-stu-id="71c96-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="71c96-104">可以使用以下 cmdlet Windows PowerShell为实时事件设置和分配策略Teams：</span><span class="sxs-lookup"><span data-stu-id="71c96-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="71c96-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="71c96-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="71c96-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="71c96-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="71c96-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="71c96-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="71c96-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="71c96-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="71c96-109">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="71c96-109">New-CsGroupPolicyAssignment</span></span>](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

<span data-ttu-id="71c96-110">下面是一些示例。</span><span class="sxs-lookup"><span data-stu-id="71c96-110">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="71c96-111">在运行这些 cmdlet 之前，必须连接到 Skype for Business PowerShell。</span><span class="sxs-lookup"><span data-stu-id="71c96-111">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="71c96-112">有关详细信息，请参阅使用[powerShell Skype for Business管理 Microsoft 365 Office 365 Online。](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="71c96-112">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="71c96-113">允许用户计划实时事件</span><span class="sxs-lookup"><span data-stu-id="71c96-113">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="71c96-114">这些示例适用于在 Teams 中生成的事件。</span><span class="sxs-lookup"><span data-stu-id="71c96-114">These examples are for events produced in Teams.</span></span> <span data-ttu-id="71c96-115">对于使用外部应用或设备生成的事件，必须执行其他步骤。</span><span class="sxs-lookup"><span data-stu-id="71c96-115">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="71c96-116">有关详细信息，请参阅 [允许用户计划使用外部应用或设备生成的事件](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)。</span><span class="sxs-lookup"><span data-stu-id="71c96-116">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="71c96-117">**允许用户计划实时事件**</span><span class="sxs-lookup"><span data-stu-id="71c96-117">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="71c96-118">如果为用户分配了全局策略，请运行 并验证 *AllowBroadcastScheduling* 参数是否设置为 *True：*</span><span class="sxs-lookup"><span data-stu-id="71c96-118">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="71c96-119">然后将用户分配到全局策略，运行：</span><span class="sxs-lookup"><span data-stu-id="71c96-119">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="71c96-120">用户方案</span><span class="sxs-lookup"><span data-stu-id="71c96-120">User scenarios</span></span>
<span data-ttu-id="71c96-121">**希望组织中的所有用户能够安排实时事件**</span><span class="sxs-lookup"><span data-stu-id="71c96-121">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="71c96-122">如果为用户分配了全局策略，请运行 并验证 *AllowBroadcastScheduling* \*是否设置为 *True：*</span><span class="sxs-lookup"><span data-stu-id="71c96-122">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="71c96-123">如果为用户分配了全局策略外的策略，请运行 并验证 *-AllowBroadcastScheduling* 是否设置为 *True：*</span><span class="sxs-lookup"><span data-stu-id="71c96-123">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="71c96-124">**您希望在整个组织中禁用实时事件计划**</span><span class="sxs-lookup"><span data-stu-id="71c96-124">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="71c96-125">禁用实时事件计划，运行：</span><span class="sxs-lookup"><span data-stu-id="71c96-125">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="71c96-126">将组织中所有用户分配到全局策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="71c96-126">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="71c96-127">**您希望大量用户能够计划实时事件，并防止一组用户安排它们**</span><span class="sxs-lookup"><span data-stu-id="71c96-127">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="71c96-128">运行 并验证 *AllowBroadcastScheduling* 是否设置为 *True：*</span><span class="sxs-lookup"><span data-stu-id="71c96-128">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="71c96-129">然后将用户分配到全局策略，运行：</span><span class="sxs-lookup"><span data-stu-id="71c96-129">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="71c96-130">创建不允许计划实时事件的新策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="71c96-130">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="71c96-131">禁用实时事件计划，运行：</span><span class="sxs-lookup"><span data-stu-id="71c96-131">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="71c96-132">然后，将用户分配到此策略，运行：</span><span class="sxs-lookup"><span data-stu-id="71c96-132">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="71c96-133">**希望为大量用户禁用实时事件计划，并允许一组用户计划它们**</span><span class="sxs-lookup"><span data-stu-id="71c96-133">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="71c96-134">禁用实时事件计划，运行：</span><span class="sxs-lookup"><span data-stu-id="71c96-134">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="71c96-135">然后将这些用户分配到全局策略，运行：</span><span class="sxs-lookup"><span data-stu-id="71c96-135">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="71c96-136">创建一个策略以允许实时事件计划，请运行：</span><span class="sxs-lookup"><span data-stu-id="71c96-136">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="71c96-137">启用实时事件计划，运行：</span><span class="sxs-lookup"><span data-stu-id="71c96-137">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="71c96-138">然后，将用户分配到此策略，运行：</span><span class="sxs-lookup"><span data-stu-id="71c96-138">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="71c96-139">设置谁可以加入实时事件</span><span class="sxs-lookup"><span data-stu-id="71c96-139">Set who can join live events</span></span>
 
<span data-ttu-id="71c96-140">设置全局策略以允许用户创建每个人（包括匿名用户）都可以参与、运行的事件：</span><span class="sxs-lookup"><span data-stu-id="71c96-140">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="71c96-141">设置实时事件的录制选项</span><span class="sxs-lookup"><span data-stu-id="71c96-141">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="71c96-142">此设置仅适用于在 Teams 中生成的事件。</span><span class="sxs-lookup"><span data-stu-id="71c96-142">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="71c96-143">设置全局策略以禁用实时事件的录制：</span><span class="sxs-lookup"><span data-stu-id="71c96-143">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="71c96-144">在实时活动中设置实时字幕和字幕</span><span class="sxs-lookup"><span data-stu-id="71c96-144">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="71c96-145">此设置仅适用于在 Teams 中生成的事件。</span><span class="sxs-lookup"><span data-stu-id="71c96-145">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="71c96-146">设置全局策略，为活动与会者启用实时 (字幕) 字幕：</span><span class="sxs-lookup"><span data-stu-id="71c96-146">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="71c96-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="71c96-147">Related topics</span></span>
- [<span data-ttu-id="71c96-148">设置 Teams 实时事件</span><span class="sxs-lookup"><span data-stu-id="71c96-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="71c96-149">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="71c96-149">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)