---
title: 实时事件录制策略
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 了解实时事件录制策略。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9c808e4ae4e27e48c14c45711ef80ffd1c812125
ms.sourcegitcommit: 3fc6fb528806f967bdc80671761cd45c32db6516
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51383966"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="ba51e-103">Microsoft Teams 中的实时事件录制策略</span><span class="sxs-lookup"><span data-stu-id="ba51e-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="ba51e-104">有几个选项用于录制 Microsoft Teams 实时事件。</span><span class="sxs-lookup"><span data-stu-id="ba51e-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="ba51e-105">录制选项是使用录制策略设置的。</span><span class="sxs-lookup"><span data-stu-id="ba51e-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="ba51e-106">本文介绍各种设置。</span><span class="sxs-lookup"><span data-stu-id="ba51e-106">This article describes the various settings.</span></span>

<span data-ttu-id="ba51e-107">录制选项是使用 PowerShell 命令 [Set-CsTeamsMeetingBroadcastPolicy 设置的](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="ba51e-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps).</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="ba51e-108">计划和选项行为</span><span class="sxs-lookup"><span data-stu-id="ba51e-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="ba51e-109">安排实时事件录制时，有两个组织者选项：</span><span class="sxs-lookup"><span data-stu-id="ba51e-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="ba51e-110">录制者与演示者可用</span><span class="sxs-lookup"><span data-stu-id="ba51e-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="ba51e-111">录制文件：提供录制文件，制作者和演示者可在事件结束后下载该文件。</span><span class="sxs-lookup"><span data-stu-id="ba51e-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="ba51e-112">可用于与会者的录制</span><span class="sxs-lookup"><span data-stu-id="ba51e-112">Recording available for attendees</span></span>

  - <span data-ttu-id="ba51e-113">DVR：使用 DVR (数字) ，与会者可以在活动期间后退和暂停</span><span class="sxs-lookup"><span data-stu-id="ba51e-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="ba51e-114">VOD：使用 VOD (点播) ，与会者可以在活动结束后观看</span><span class="sxs-lookup"><span data-stu-id="ba51e-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="ba51e-115">广播录制策略设置</span><span class="sxs-lookup"><span data-stu-id="ba51e-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="ba51e-116">作为广播策略的一部分，有一个设置可以切换为为实时事件打开或关闭录制。</span><span class="sxs-lookup"><span data-stu-id="ba51e-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="ba51e-117">录制者与演示者可用</span><span class="sxs-lookup"><span data-stu-id="ba51e-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="ba51e-118">可用于与会者的录制</span><span class="sxs-lookup"><span data-stu-id="ba51e-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="ba51e-119">始终记录</span><span class="sxs-lookup"><span data-stu-id="ba51e-119">Always record</span></span>               | <span data-ttu-id="ba51e-120">已禁用和已选择</span><span class="sxs-lookup"><span data-stu-id="ba51e-120">Disabled and selected</span></span>                                | <span data-ttu-id="ba51e-121">启用和选择</span><span class="sxs-lookup"><span data-stu-id="ba51e-121">Enabled and selected</span></span>         |
| <span data-ttu-id="ba51e-122">组织者可以录制或不录制</span><span class="sxs-lookup"><span data-stu-id="ba51e-122">Organizer can record or not</span></span> | <span data-ttu-id="ba51e-123">默认情况下启用和选择</span><span class="sxs-lookup"><span data-stu-id="ba51e-123">Enabled and selected by default</span></span>                  | <span data-ttu-id="ba51e-124">默认情况下启用和选择</span><span class="sxs-lookup"><span data-stu-id="ba51e-124">Enabled and selected by default</span></span>   |
| <span data-ttu-id="ba51e-125">从不录制</span><span class="sxs-lookup"><span data-stu-id="ba51e-125">Never record</span></span>               | <span data-ttu-id="ba51e-126">已禁用且未选中</span><span class="sxs-lookup"><span data-stu-id="ba51e-126">Disabled and not selected</span></span>                            | <span data-ttu-id="ba51e-127">已启用且未选中</span><span class="sxs-lookup"><span data-stu-id="ba51e-127">Enabled and not selected</span></span>      |

<span data-ttu-id="ba51e-128">当策略设置为"始终 **记录"** 时，策略页具有以下选定选项：</span><span class="sxs-lookup"><span data-stu-id="ba51e-128">When the policy is set to **Always record**, the policy page has the following selected options:</span></span>

<span data-ttu-id="ba51e-129">![实时事件策略设置](../media/live-event-recording-policy.png "Microsoft Teams 管理中心中的实时事件策略设置屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="ba51e-129">![live events policy settings](../media/live-event-recording-policy.png "Screen shot of live events policy settings in the Microsoft Teams admin center")</span></span>

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="ba51e-130">存储和持久性行为</span><span class="sxs-lookup"><span data-stu-id="ba51e-130">Storage and persistence behavior</span></span>

| <span data-ttu-id="ba51e-131">选项</span><span class="sxs-lookup"><span data-stu-id="ba51e-131">Option</span></span>                                       | <span data-ttu-id="ba51e-132">省/市/自治区</span><span class="sxs-lookup"><span data-stu-id="ba51e-132">State</span></span>   | <span data-ttu-id="ba51e-133">DVR</span><span class="sxs-lookup"><span data-stu-id="ba51e-133">DVR</span></span>                                                   | <span data-ttu-id="ba51e-134">VOD</span><span class="sxs-lookup"><span data-stu-id="ba51e-134">VOD</span></span>                                                     | <span data-ttu-id="ba51e-135">录制</span><span class="sxs-lookup"><span data-stu-id="ba51e-135">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="ba51e-136">可供制作者和演示者使用的记录</span><span class="sxs-lookup"><span data-stu-id="ba51e-136">Recording available to producers and presenters</span></span> | <span data-ttu-id="ba51e-137">选中</span><span class="sxs-lookup"><span data-stu-id="ba51e-137">Selected</span></span>     | <span data-ttu-id="ba51e-138">DVR 可用，AZURE 媒体服务 (AMS) 存储 180 天</span><span class="sxs-lookup"><span data-stu-id="ba51e-138">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="ba51e-139">与会者可以访问和观看活动</span><span class="sxs-lookup"><span data-stu-id="ba51e-139">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="ba51e-140">未选中</span><span class="sxs-lookup"><span data-stu-id="ba51e-140">Not Selected</span></span> | <span data-ttu-id="ba51e-141">DVR 可用，AMS 资产存储 180 天</span><span class="sxs-lookup"><span data-stu-id="ba51e-141">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="ba51e-142">结束后，与会者无法访问事件</span><span class="sxs-lookup"><span data-stu-id="ba51e-142">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="ba51e-143">已禁用 (未选中) </span><span class="sxs-lookup"><span data-stu-id="ba51e-143">Disabled (Not selected)</span></span>|<span data-ttu-id="ba51e-144">DVR 可用，事件后将删除 AMS 资产</span><span class="sxs-lookup"><span data-stu-id="ba51e-144">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="ba51e-145">结束后，与会者无法访问事件</span><span class="sxs-lookup"><span data-stu-id="ba51e-145">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="ba51e-146">可供制作者和演示者使用的记录</span><span class="sxs-lookup"><span data-stu-id="ba51e-146">Recording available to producers and presenters</span></span> | <span data-ttu-id="ba51e-147">选中</span><span class="sxs-lookup"><span data-stu-id="ba51e-147">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="ba51e-148">创建并存储 MP4</span><span class="sxs-lookup"><span data-stu-id="ba51e-148">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="ba51e-149">未选中</span><span class="sxs-lookup"><span data-stu-id="ba51e-149">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="ba51e-150">未创建任何文件</span><span class="sxs-lookup"><span data-stu-id="ba51e-150">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="ba51e-151">相关主题</span><span class="sxs-lookup"><span data-stu-id="ba51e-151">Related topics</span></span>

- [<span data-ttu-id="ba51e-152">什么是 Teams 实时活动?</span><span class="sxs-lookup"><span data-stu-id="ba51e-152">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="ba51e-153">规划 Teams 实时事件</span><span class="sxs-lookup"><span data-stu-id="ba51e-153">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="ba51e-154">配置 Teams 实时事件设置</span><span class="sxs-lookup"><span data-stu-id="ba51e-154">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="ba51e-155">Teams 云会议录制</span><span class="sxs-lookup"><span data-stu-id="ba51e-155">Teams clouds meeting recording</span></span>](../cloud-recording.md)