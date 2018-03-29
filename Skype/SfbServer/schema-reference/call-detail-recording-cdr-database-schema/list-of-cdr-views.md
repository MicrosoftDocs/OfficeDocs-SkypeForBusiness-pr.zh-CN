---
title: CDR 视图的列表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: 视图，可以方便地访问信息用于从 CDR 数据库返回数据的最常见方案。 建议使用视图，以便生成自定义报表，而不是使用实际的 CDR 数据库表;这是因为数据库视图会更容易保持向后兼容与将来的发行版。
ms.openlocfilehash: d0ccf227af5bf205acd57660ca9cc51ba27e103e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-cdr-views"></a><span data-ttu-id="a75f4-104">CDR 视图的列表</span><span class="sxs-lookup"><span data-stu-id="a75f4-104">List of CDR views</span></span>
 
<span data-ttu-id="a75f4-105">视图，可以方便地访问信息用于从 CDR 数据库返回数据的最常见方案。</span><span class="sxs-lookup"><span data-stu-id="a75f4-105">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="a75f4-106">建议使用视图，以便生成自定义报表，而不是使用实际的 CDR 数据库表;这是因为数据库视图会更容易保持向后兼容与将来的发行版。</span><span class="sxs-lookup"><span data-stu-id="a75f4-106">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that's because the database views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="a75f4-107">**视图名称**</span><span class="sxs-lookup"><span data-stu-id="a75f4-107">**View Name**</span></span>|<span data-ttu-id="a75f4-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="a75f4-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a75f4-109">ClientVersions 视图</span><span class="sxs-lookup"><span data-stu-id="a75f4-109">ClientVersions view</span></span>](clientversions-0.md) <br/> |<span data-ttu-id="a75f4-110">返回有关客户端信息通信会话中使用的软件/设备。</span><span class="sxs-lookup"><span data-stu-id="a75f4-110">Returns information about the client software/devices used in a communication session.</span></span>  <br/> |
|[<span data-ttu-id="a75f4-111">ConferenceMessageCount 视图</span><span class="sxs-lookup"><span data-stu-id="a75f4-111">ConferenceMessageCount view</span></span>](conferencemessagecount-0.md) <br/> |<span data-ttu-id="a75f4-112">返回有关在会议中的用户发送的邮件数。</span><span class="sxs-lookup"><span data-stu-id="a75f4-112">Returns information about the number of messages sent by users in a conference.</span></span>  <br/> |
|[<span data-ttu-id="a75f4-113">查看会议</span><span class="sxs-lookup"><span data-stu-id="a75f4-113">Conferences view</span></span>](conferences-0.md) <br/> |<span data-ttu-id="a75f4-114">返回会议信息，包括开始时间、 结束时间和会议组织者。</span><span class="sxs-lookup"><span data-stu-id="a75f4-114">Returns conference information, including start time, end time, and conference organizer.</span></span>  <br/> |
|[<span data-ttu-id="a75f4-115">ConferenceSessionDetails 视图</span><span class="sxs-lookup"><span data-stu-id="a75f4-115">ConferenceSessionDetails view</span></span>](conferencesessiondetails.md) <br/> |<span data-ttu-id="a75f4-116">对于所有会议会话，包括开始和结束时间、 用户 Id、 响应代码和诊断的 Id 返回会话的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a75f4-116">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span>  <br/> |
|[<span data-ttu-id="a75f4-117">ConferenceUris 视图</span><span class="sxs-lookup"><span data-stu-id="a75f4-117">ConferenceUris view</span></span>](conferenceuris-0.md) <br/> |<span data-ttu-id="a75f4-118">在会议中返回 Uri 使用的会议有关的信息</span><span class="sxs-lookup"><span data-stu-id="a75f4-118">Returns information about conference URIs used in a conference</span></span>  <br/> |
|[<span data-ttu-id="a75f4-119">ErrorReport 视图</span><span class="sxs-lookup"><span data-stu-id="a75f4-119">ErrorReport view</span></span>](errorreport-0.md) <br/> |<span data-ttu-id="a75f4-120">返回有关在会话期间发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="a75f4-120">Returns information about errors that occurred during a session.</span></span>  <br/> |
|[<span data-ttu-id="a75f4-121">FileTransfers 视图</span><span class="sxs-lookup"><span data-stu-id="a75f4-121">FileTransfers view</span></span>](filetransfers.md) <br/> |<span data-ttu-id="a75f4-122">返回有关文件传输会话，包括的文件的名称和传输是否已被接受的拒绝，或者取消。</span><span class="sxs-lookup"><span data-stu-id="a75f4-122">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span>  <br/> |
|[<span data-ttu-id="a75f4-123">FocusJoinsAndLeaves 视图</span><span class="sxs-lookup"><span data-stu-id="a75f4-123">FocusJoinsAndLeaves view</span></span>](focusjoinsandleaves-0.md) <br/> |<span data-ttu-id="a75f4-124">返回有关大会的信息联接和休假活动。</span><span class="sxs-lookup"><span data-stu-id="a75f4-124">Returns information about conference join and leave activities.</span></span>  <br/> |
|[<span data-ttu-id="a75f4-125">McuJoinsAndLeaves 视图</span><span class="sxs-lookup"><span data-stu-id="a75f4-125">McuJoinsAndLeaves view</span></span>](mcujoinsandleaves-0.md) <br/> |<span data-ttu-id="a75f4-126">返回组合参加会议有关的信息，并将的活动 （每个参加会议配合相应的会议保留）。</span><span class="sxs-lookup"><span data-stu-id="a75f4-126">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span>  <br/> |
|[<span data-ttu-id="a75f4-127">Mcu 视图</span><span class="sxs-lookup"><span data-stu-id="a75f4-127">Mcus view</span></span>](mcus-0.md) <br/> |<span data-ttu-id="a75f4-128">返回会议服务器有关的信息。</span><span class="sxs-lookup"><span data-stu-id="a75f4-128">Returns information about Conferencing servers.</span></span>  <br/> |
|[<span data-ttu-id="a75f4-129">媒体视图</span><span class="sxs-lookup"><span data-stu-id="a75f4-129">Media view</span></span>](media-0.md) <br/> |<span data-ttu-id="a75f4-130">返回信息的对等通信会话中使用的媒体类型。</span><span class="sxs-lookup"><span data-stu-id="a75f4-130">Returns information about the types of media used in peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="a75f4-131">ProgressReport 视图</span><span class="sxs-lookup"><span data-stu-id="a75f4-131">ProgressReport view</span></span>](progressreport-0.md) <br/> |<span data-ttu-id="a75f4-132">返回有关已完成的会话的信息。</span><span class="sxs-lookup"><span data-stu-id="a75f4-132">Returns information about completed sessions.</span></span>  <br/> |
|[<span data-ttu-id="a75f4-133">注册视图</span><span class="sxs-lookup"><span data-stu-id="a75f4-133">Registration view</span></span>](registration-0.md) <br/> |<span data-ttu-id="a75f4-134">返回与 Skype 的注册有关的业务服务器 2015年的信息。</span><span class="sxs-lookup"><span data-stu-id="a75f4-134">Returns information about registrations with Skype for Business Server 2015.</span></span>  <br/> |
|[<span data-ttu-id="a75f4-135">SessionDetails 视图</span><span class="sxs-lookup"><span data-stu-id="a75f4-135">SessionDetails view</span></span>](sessiondetails-0.md) <br/> |<span data-ttu-id="a75f4-136">返回有关对等会话，包括 VoIP VoIP 电话联络、 两方的 IM 会话或其他对等通信会话的信息。</span><span class="sxs-lookup"><span data-stu-id="a75f4-136">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="a75f4-137">用户视图</span><span class="sxs-lookup"><span data-stu-id="a75f4-137">User view</span></span>](user.md) <br/> |<span data-ttu-id="a75f4-138">返回有关参加通信会话的用户的信息。</span><span class="sxs-lookup"><span data-stu-id="a75f4-138">Returns information about the users who have participated in communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="a75f4-139">VoIPDetails 视图</span><span class="sxs-lookup"><span data-stu-id="a75f4-139">VoIPDetails view</span></span>](voipdetails.md) <br/> |<span data-ttu-id="a75f4-140">返回用于对等会话涉及至少一个 VoIP （IO 配音） 用户的信息。</span><span class="sxs-lookup"><span data-stu-id="a75f4-140">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span>  <br/> |
   

