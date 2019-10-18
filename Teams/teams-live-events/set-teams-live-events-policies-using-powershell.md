---
title: 使用 PowerShell 在 Microsoft Teams 中设置实时事件策略
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 有关如何使用 PowerShell 设置团队中的策略以控制哪些人可以在你的组织中拥有实时事件以及他们创建的事件中可用的功能的示例
appliesto:
- Microsoft Teams
ms.openlocfilehash: d9f96adcf4aa40b93b89b99013b9bc5ca466c25b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570164"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="c5118-103">使用 PowerShell 在 Microsoft Teams 中设置实时事件策略</span><span class="sxs-lookup"><span data-stu-id="c5118-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="c5118-104">你可以使用以下 Windows PowerShell cmdlet 为团队中的实时事件设置和分配策略设置：</span><span class="sxs-lookup"><span data-stu-id="c5118-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="c5118-105">CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="c5118-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="c5118-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="c5118-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="c5118-107">新-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="c5118-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="c5118-108">授权-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="c5118-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="c5118-109">下面是一些示例。</span><span class="sxs-lookup"><span data-stu-id="c5118-109">Here are some examples.</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="c5118-110">允许用户安排实时事件</span><span class="sxs-lookup"><span data-stu-id="c5118-110">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="c5118-111">这些示例适用于团队中生成的事件。</span><span class="sxs-lookup"><span data-stu-id="c5118-111">These examples are for events produced in Teams.</span></span> <span data-ttu-id="c5118-112">对于使用外部应用或设备生成的事件，必须执行其他步骤。</span><span class="sxs-lookup"><span data-stu-id="c5118-112">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="c5118-113">有关详细信息，请参阅[使用户能够计划使用外部应用或设备生成的事件](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)。</span><span class="sxs-lookup"><span data-stu-id="c5118-113">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="c5118-114">**允许用户安排实时事件**</span><span class="sxs-lookup"><span data-stu-id="c5118-114">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="c5118-115">如果向用户分配了全局策略，请运行并验证*AllowBroadcastScheduling*参数是否设置为*True*：</span><span class="sxs-lookup"><span data-stu-id="c5118-115">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="c5118-116">然后，将该用户分配给全局策略，运行：</span><span class="sxs-lookup"><span data-stu-id="c5118-116">Then assign the user to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="c5118-117">用户方案</span><span class="sxs-lookup"><span data-stu-id="c5118-117">User scenarios</span></span>
<span data-ttu-id="c5118-118">**希望组织中的所有用户都能够安排实时事件**</span><span class="sxs-lookup"><span data-stu-id="c5118-118">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="c5118-119">如果向用户分配了全局策略，请运行并验证*AllowBroadcastScheduling* \* 是否设置为*True*：</span><span class="sxs-lookup"><span data-stu-id="c5118-119">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="c5118-120">如果向用户分配了全局策略之外的策略，请运行并验证 *-AllowBroadcastScheduling*是否设置为*True*：</span><span class="sxs-lookup"><span data-stu-id="c5118-120">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="c5118-121">**你希望在你的组织中禁用实时事件计划**</span><span class="sxs-lookup"><span data-stu-id="c5118-121">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="c5118-122">禁用实时事件调度，运行：</span><span class="sxs-lookup"><span data-stu-id="c5118-122">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="c5118-123">将组织中的所有用户分配给全局策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="c5118-123">Assign all users in your organization to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="c5118-124">**您希望大量用户能够安排实时事件，并防止一组用户安排实时事件**</span><span class="sxs-lookup"><span data-stu-id="c5118-124">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="c5118-125">运行并验证*AllowBroadcastScheduling*是否设置为*True*：</span><span class="sxs-lookup"><span data-stu-id="c5118-125">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="c5118-126">然后，将一个或用户分配给全局策略，运行：</span><span class="sxs-lookup"><span data-stu-id="c5118-126">Then assign a user or users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="c5118-127">创建不允许安排实时事件的新策略，运行：</span><span class="sxs-lookup"><span data-stu-id="c5118-127">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="c5118-128">禁用实时事件调度，运行：</span><span class="sxs-lookup"><span data-stu-id="c5118-128">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="c5118-129">然后将用户分配给此策略，运行：</span><span class="sxs-lookup"><span data-stu-id="c5118-129">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="c5118-130">**您希望为大量用户禁用实时事件调度，并允许一组用户安排它们**</span><span class="sxs-lookup"><span data-stu-id="c5118-130">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="c5118-131">禁用实时事件调度，运行：</span><span class="sxs-lookup"><span data-stu-id="c5118-131">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="c5118-132">然后将这些用户分配给全局策略，运行：</span><span class="sxs-lookup"><span data-stu-id="c5118-132">Then assign those users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="c5118-133">创建允许实时事件调度的策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="c5118-133">Create a policy to allow live events scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="c5118-134">启用实时事件调度，运行：</span><span class="sxs-lookup"><span data-stu-id="c5118-134">Enable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="c5118-135">然后将用户分配给此策略，运行：</span><span class="sxs-lookup"><span data-stu-id="c5118-135">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="c5118-136">设置可以加入实时事件的人员</span><span class="sxs-lookup"><span data-stu-id="c5118-136">Set who can join live events</span></span>
 
<span data-ttu-id="c5118-137">将全局策略设置为允许用户创建所有人（包括匿名用户）都可以出席的事件，请运行：</span><span class="sxs-lookup"><span data-stu-id="c5118-137">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="c5118-138">设置实时事件的录制选项</span><span class="sxs-lookup"><span data-stu-id="c5118-138">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="c5118-139">此设置仅适用于团队中产生的事件。</span><span class="sxs-lookup"><span data-stu-id="c5118-139">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="c5118-140">将全局策略设置为禁用实时事件的录制：</span><span class="sxs-lookup"><span data-stu-id="c5118-140">Set the global policy to disable recording for live events:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="c5118-141">在实时事件中设置实时字幕和副标题</span><span class="sxs-lookup"><span data-stu-id="c5118-141">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="c5118-142">此设置仅适用于团队中产生的事件。</span><span class="sxs-lookup"><span data-stu-id="c5118-142">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="c5118-143">设置全局策略，为活动与会者打开实时字幕和副标题（脚本）：</span><span class="sxs-lookup"><span data-stu-id="c5118-143">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="c5118-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="c5118-144">Related topics</span></span>
- [<span data-ttu-id="c5118-145">设置 Teams 实时事件</span><span class="sxs-lookup"><span data-stu-id="c5118-145">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)


