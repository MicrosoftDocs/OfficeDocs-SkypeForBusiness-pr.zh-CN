---
title: 使用 PowerShell 的 Microsoft 团队中设置 live 事件策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
description: 有关如何使用 PowerShell 团队以控制谁可以保留在您的组织和功能的实时事件的设置策略的示例有他们创建的事件
appliesto:
- Microsoft Teams
ms.openlocfilehash: f802c2b67c0a4cd4b0838dd9aeec9c4bbf884968
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26535884"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="f8b01-103">使用 PowerShell 的 Microsoft 团队中设置 live 事件策略</span><span class="sxs-lookup"><span data-stu-id="f8b01-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="f8b01-104">可以使用以下 Windows PowerShell cmdlet 设置并分配的工作组中的实时事件的策略设置：</span><span class="sxs-lookup"><span data-stu-id="f8b01-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="f8b01-105">Get CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="f8b01-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="f8b01-106">设置 CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="f8b01-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="f8b01-107">新 CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="f8b01-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="f8b01-108">授予 CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="f8b01-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="f8b01-109">下面是一些示例。</span><span class="sxs-lookup"><span data-stu-id="f8b01-109">Here's some examples.</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="f8b01-110">允许用户安排 live 事件</span><span class="sxs-lookup"><span data-stu-id="f8b01-110">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="f8b01-111">这些示例供快速入门事件。</span><span class="sxs-lookup"><span data-stu-id="f8b01-111">These examples are for quick start events.</span></span> <span data-ttu-id="f8b01-112">对于外部编码器事件，其他一些的步骤，您必须执行。</span><span class="sxs-lookup"><span data-stu-id="f8b01-112">For external encoder events, there are additional steps you must do.</span></span> <span data-ttu-id="f8b01-113">有关详细信息，请参阅[使用户能够安排外部编码器事件](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events)。</span><span class="sxs-lookup"><span data-stu-id="f8b01-113">For more information, see [Enable users to schedule external encoder events](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events).</span></span>

<span data-ttu-id="f8b01-114">**允许用户安排 live 事件**</span><span class="sxs-lookup"><span data-stu-id="f8b01-114">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="f8b01-115">如果该用户分配全局策略，则运行，并验证*AllowBroadcastScheduling*参数设置为*True*:</span><span class="sxs-lookup"><span data-stu-id="f8b01-115">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="f8b01-116">然后将该用户分配到全局策略中，运行：</span><span class="sxs-lookup"><span data-stu-id="f8b01-116">Then assign the user to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="f8b01-117">用户方案</span><span class="sxs-lookup"><span data-stu-id="f8b01-117">User scenarios</span></span>
<span data-ttu-id="f8b01-118">**您希望组织能够安排 live 事件中的所有用户**</span><span class="sxs-lookup"><span data-stu-id="f8b01-118">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="f8b01-119">如果用户分配全局策略，运行并验证该*AllowBroadcastScheduling* \* 设置为*True*:</span><span class="sxs-lookup"><span data-stu-id="f8b01-119">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="f8b01-120">如果用户分配全局策略之外的策略，则运行，并验证 *-AllowBroadcastScheduling*设置为*True*:</span><span class="sxs-lookup"><span data-stu-id="f8b01-120">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="f8b01-121">**要安排要禁用整个组织的 live 事件**</span><span class="sxs-lookup"><span data-stu-id="f8b01-121">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="f8b01-122">禁用 live 事件计划，请运行：</span><span class="sxs-lookup"><span data-stu-id="f8b01-122">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="f8b01-123">组织中的所有用户都分配全局策略，运行：</span><span class="sxs-lookup"><span data-stu-id="f8b01-123">Assign all users in your organization to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="f8b01-124">**您希望大量用户能够安排 live 事件和安排它们阻止用户组**</span><span class="sxs-lookup"><span data-stu-id="f8b01-124">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="f8b01-125">运行并验证*AllowBroadcastScheduling*设置为*True*:</span><span class="sxs-lookup"><span data-stu-id="f8b01-125">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="f8b01-126">然后将一个用户分配给全局策略，运行：</span><span class="sxs-lookup"><span data-stu-id="f8b01-126">Then assign a user or users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="f8b01-127">创建一个新的策略，不允许安排 live 事件，运行：</span><span class="sxs-lookup"><span data-stu-id="f8b01-127">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingpolicy
```
<span data-ttu-id="f8b01-128">禁用 live 事件计划，请运行：</span><span class="sxs-lookup"><span data-stu-id="f8b01-128">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="f8b01-129">然后将用户分配给此策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="f8b01-129">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
<span data-ttu-id="f8b01-130">**您想要禁用的大量用户安排 live 事件并允许用户安排一组**</span><span class="sxs-lookup"><span data-stu-id="f8b01-130">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="f8b01-131">禁用 live 事件计划，请运行：</span><span class="sxs-lookup"><span data-stu-id="f8b01-131">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="f8b01-132">然后将这些用户分配全局策略，运行：</span><span class="sxs-lookup"><span data-stu-id="f8b01-132">Then assign those users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="f8b01-133">创建策略，以允许安排 live 事件、 运行：</span><span class="sxs-lookup"><span data-stu-id="f8b01-133">Create a policy to allow live events scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="f8b01-134">启用 live 事件日程安排，运行：</span><span class="sxs-lookup"><span data-stu-id="f8b01-134">Enable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="f8b01-135">然后将用户分配给此策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="f8b01-135">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="f8b01-136">设置可以加入 live 事件</span><span class="sxs-lookup"><span data-stu-id="f8b01-136">Set who can join live events</span></span>
 
<span data-ttu-id="f8b01-137">设置全局策略以允许用户创建事件的任何人，包括匿名用户可以参加、 运行：</span><span class="sxs-lookup"><span data-stu-id="f8b01-137">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="f8b01-138">设置的实时事件录音选项</span><span class="sxs-lookup"><span data-stu-id="f8b01-138">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="f8b01-139">此设置只应用于快速入门事件。</span><span class="sxs-lookup"><span data-stu-id="f8b01-139">This setting applies only to quick start events.</span></span>

<span data-ttu-id="f8b01-140">设置要禁用的实时事件记录的全局策略：</span><span class="sxs-lookup"><span data-stu-id="f8b01-140">Set the global policy to disable recording for live events:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-transcription-and-translation-in-live-events-coming-soon"></a><span data-ttu-id="f8b01-141">在 live 事件 （即将推出） 中设置转录和翻译</span><span class="sxs-lookup"><span data-stu-id="f8b01-141">Set transcription and translation in live events (coming soon)</span></span>
> [!NOTE]
> <span data-ttu-id="f8b01-142">此设置只应用于快速入门事件。</span><span class="sxs-lookup"><span data-stu-id="f8b01-142">This setting applies only to quick start events.</span></span> 

<span data-ttu-id="f8b01-143">设置全局策略以启用转录和转换为事件与会者：</span><span class="sxs-lookup"><span data-stu-id="f8b01-143">Set the global policy to turn on transcription and translation on for event attendees:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="f8b01-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="f8b01-144">Related topics</span></span>
- [<span data-ttu-id="f8b01-145">设置团队的实时事件</span><span class="sxs-lookup"><span data-stu-id="f8b01-145">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)


