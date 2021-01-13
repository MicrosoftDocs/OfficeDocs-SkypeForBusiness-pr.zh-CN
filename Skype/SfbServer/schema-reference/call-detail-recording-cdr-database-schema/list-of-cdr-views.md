---
title: CDR 视图列表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: 可通过视图轻松访问有关用于从 CDR 数据库返回数据的最常见方案的信息。 建议您使用视图来生成自定义报告，而不是使用实际的 CDR 数据库表;这是因为数据库视图更有可能保持与将来版本的向后兼容性。
ms.openlocfilehash: 0a3b40c9b31bb521075e78a1a8d46479200249d5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813152"
---
# <a name="list-of-cdr-views"></a><span data-ttu-id="72bd5-104">CDR 视图列表</span><span class="sxs-lookup"><span data-stu-id="72bd5-104">List of CDR views</span></span>
 
<span data-ttu-id="72bd5-105">可通过视图轻松访问有关用于从 CDR 数据库返回数据的最常见方案的信息。</span><span class="sxs-lookup"><span data-stu-id="72bd5-105">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="72bd5-106">建议您使用视图来生成自定义报告，而不是使用实际的 CDR 数据库表;这是因为数据库视图更有可能保持与将来版本的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="72bd5-106">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that's because the database views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="72bd5-107">**视图名称**</span><span class="sxs-lookup"><span data-stu-id="72bd5-107">**View Name**</span></span>|<span data-ttu-id="72bd5-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="72bd5-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="72bd5-109">ClientVersions 视图</span><span class="sxs-lookup"><span data-stu-id="72bd5-109">ClientVersions view</span></span>](clientversions-0.md) <br/> |<span data-ttu-id="72bd5-110">返回通信会话中使用的客户端软件/设备的相关信息。</span><span class="sxs-lookup"><span data-stu-id="72bd5-110">Returns information about the client software/devices used in a communication session.</span></span>  <br/> |
|[<span data-ttu-id="72bd5-111">ConferenceMessageCount 视图</span><span class="sxs-lookup"><span data-stu-id="72bd5-111">ConferenceMessageCount view</span></span>](conferencemessagecount-0.md) <br/> |<span data-ttu-id="72bd5-112">返回会议中的用户发送的消息数的相关信息。</span><span class="sxs-lookup"><span data-stu-id="72bd5-112">Returns information about the number of messages sent by users in a conference.</span></span>  <br/> |
|[<span data-ttu-id="72bd5-113">会议视图</span><span class="sxs-lookup"><span data-stu-id="72bd5-113">Conferences view</span></span>](conferences-0.md) <br/> |<span data-ttu-id="72bd5-114">返回会议信息，包括开始时间、结束时间和会议组织者。</span><span class="sxs-lookup"><span data-stu-id="72bd5-114">Returns conference information, including start time, end time, and conference organizer.</span></span>  <br/> |
|[<span data-ttu-id="72bd5-115">ConferenceSessionDetails 视图</span><span class="sxs-lookup"><span data-stu-id="72bd5-115">ConferenceSessionDetails view</span></span>](conferencesessiondetails.md) <br/> |<span data-ttu-id="72bd5-116">返回所有会议会话的会话详细信息，包括开始和结束时间、用户 ID、响应代码和诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="72bd5-116">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span>  <br/> |
|[<span data-ttu-id="72bd5-117">ConferenceUris 视图</span><span class="sxs-lookup"><span data-stu-id="72bd5-117">ConferenceUris view</span></span>](conferenceuris-0.md) <br/> |<span data-ttu-id="72bd5-118">返回会议中使用的会议 URI 的相关信息</span><span class="sxs-lookup"><span data-stu-id="72bd5-118">Returns information about conference URIs used in a conference</span></span>  <br/> |
|[<span data-ttu-id="72bd5-119">ErrorReport 视图</span><span class="sxs-lookup"><span data-stu-id="72bd5-119">ErrorReport view</span></span>](errorreport-0.md) <br/> |<span data-ttu-id="72bd5-120">返回会话期间发生的错误的相关信息。</span><span class="sxs-lookup"><span data-stu-id="72bd5-120">Returns information about errors that occurred during a session.</span></span>  <br/> |
|[<span data-ttu-id="72bd5-121">FileTransfers 视图</span><span class="sxs-lookup"><span data-stu-id="72bd5-121">FileTransfers view</span></span>](filetransfers.md) <br/> |<span data-ttu-id="72bd5-122">返回文件传输会话的相关信息，包括文件名以及是接受、拒绝还是取消传输。</span><span class="sxs-lookup"><span data-stu-id="72bd5-122">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span>  <br/> |
|[<span data-ttu-id="72bd5-123">FocusJoinsAndLeaves 视图</span><span class="sxs-lookup"><span data-stu-id="72bd5-123">FocusJoinsAndLeaves view</span></span>](focusjoinsandleaves-0.md) <br/> |<span data-ttu-id="72bd5-124">返回有关会议加入和离开活动的信息。</span><span class="sxs-lookup"><span data-stu-id="72bd5-124">Returns information about conference join and leave activities.</span></span>  <br/> |
|[<span data-ttu-id="72bd5-125">McuJoinsAndLeaves 视图</span><span class="sxs-lookup"><span data-stu-id="72bd5-125">McuJoinsAndLeaves view</span></span>](mcujoinsandleaves-0.md) <br/> |<span data-ttu-id="72bd5-126">返回有关会议加入和离开活动的组合信息（每个会议加入与相应的会议离开配对）。</span><span class="sxs-lookup"><span data-stu-id="72bd5-126">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span>  <br/> |
|[<span data-ttu-id="72bd5-127">Mcus 视图</span><span class="sxs-lookup"><span data-stu-id="72bd5-127">Mcus view</span></span>](mcus-0.md) <br/> |<span data-ttu-id="72bd5-128">返回有关会议服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="72bd5-128">Returns information about Conferencing servers.</span></span>  <br/> |
|[<span data-ttu-id="72bd5-129">媒体视图</span><span class="sxs-lookup"><span data-stu-id="72bd5-129">Media view</span></span>](media-0.md) <br/> |<span data-ttu-id="72bd5-130">返回有关对等通信会话中使用的媒体类型的信息。</span><span class="sxs-lookup"><span data-stu-id="72bd5-130">Returns information about the types of media used in peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="72bd5-131">ProgressReport 视图</span><span class="sxs-lookup"><span data-stu-id="72bd5-131">ProgressReport view</span></span>](progressreport-0.md) <br/> |<span data-ttu-id="72bd5-132">返回有关已完成会话的信息。</span><span class="sxs-lookup"><span data-stu-id="72bd5-132">Returns information about completed sessions.</span></span>  <br/> |
|[<span data-ttu-id="72bd5-133">注册视图</span><span class="sxs-lookup"><span data-stu-id="72bd5-133">Registration view</span></span>](registration-0.md) <br/> |<span data-ttu-id="72bd5-134">返回有关使用 Skype for Business Server 2015 注册的信息。</span><span class="sxs-lookup"><span data-stu-id="72bd5-134">Returns information about registrations with Skype for Business Server 2015.</span></span>  <br/> |
|[<span data-ttu-id="72bd5-135">SessionDetails 视图</span><span class="sxs-lookup"><span data-stu-id="72bd5-135">SessionDetails view</span></span>](sessiondetails-0.md) <br/> |<span data-ttu-id="72bd5-136">返回有关对等会话的信息，包括 VoIP-VoIP 电话呼叫、双方 IM 会话或其他对等通信会话。</span><span class="sxs-lookup"><span data-stu-id="72bd5-136">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="72bd5-137">用户视图</span><span class="sxs-lookup"><span data-stu-id="72bd5-137">User view</span></span>](user.md) <br/> |<span data-ttu-id="72bd5-138">返回参与通信会话的用户的相关信息。</span><span class="sxs-lookup"><span data-stu-id="72bd5-138">Returns information about the users who have participated in communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="72bd5-139">VoIPDetails 视图</span><span class="sxs-lookup"><span data-stu-id="72bd5-139">VoIPDetails view</span></span>](voipdetails.md) <br/> |<span data-ttu-id="72bd5-140">返回至少包括一个 VoIP (Voice over IO) 用户的对等会话的相关信息。</span><span class="sxs-lookup"><span data-stu-id="72bd5-140">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span>  <br/> |
   

