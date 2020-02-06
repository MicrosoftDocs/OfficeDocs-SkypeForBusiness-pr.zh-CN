---
title: CDR 视图列表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: 视图提供了一种简单的方法来访问有关用于从 CDR 数据库返回数据的最常见方案的信息。 建议使用视图生成自定义报表，而不是使用实际的 CDR 数据库表;这是因为数据库视图更有可能保持与未来版本的向后兼容性。
ms.openlocfilehash: 78bf18fe51cea8937de44c72b39f7c1b81c75544
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815120"
---
# <a name="list-of-cdr-views"></a><span data-ttu-id="ffdda-104">CDR 视图列表</span><span class="sxs-lookup"><span data-stu-id="ffdda-104">List of CDR views</span></span>
 
<span data-ttu-id="ffdda-105">视图提供了一种简单的方法来访问有关用于从 CDR 数据库返回数据的最常见方案的信息。</span><span class="sxs-lookup"><span data-stu-id="ffdda-105">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="ffdda-106">建议使用视图生成自定义报表，而不是使用实际的 CDR 数据库表;这是因为数据库视图更有可能保持与未来版本的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="ffdda-106">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that's because the database views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="ffdda-107">**视图名称**</span><span class="sxs-lookup"><span data-stu-id="ffdda-107">**View Name**</span></span>|<span data-ttu-id="ffdda-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="ffdda-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="ffdda-109">ClientVersions 视图</span><span class="sxs-lookup"><span data-stu-id="ffdda-109">ClientVersions view</span></span>](clientversions-0.md) <br/> |<span data-ttu-id="ffdda-110">返回有关在通信会话中使用的客户端软件/设备的信息。</span><span class="sxs-lookup"><span data-stu-id="ffdda-110">Returns information about the client software/devices used in a communication session.</span></span>  <br/> |
|[<span data-ttu-id="ffdda-111">ConferenceMessageCount 视图</span><span class="sxs-lookup"><span data-stu-id="ffdda-111">ConferenceMessageCount view</span></span>](conferencemessagecount-0.md) <br/> |<span data-ttu-id="ffdda-112">返回有关会议中用户发送的邮件数的信息。</span><span class="sxs-lookup"><span data-stu-id="ffdda-112">Returns information about the number of messages sent by users in a conference.</span></span>  <br/> |
|[<span data-ttu-id="ffdda-113">会议视图</span><span class="sxs-lookup"><span data-stu-id="ffdda-113">Conferences view</span></span>](conferences-0.md) <br/> |<span data-ttu-id="ffdda-114">返回会议信息，包括 "开始时间"、"结束时间" 和 "会议组织者"。</span><span class="sxs-lookup"><span data-stu-id="ffdda-114">Returns conference information, including start time, end time, and conference organizer.</span></span>  <br/> |
|[<span data-ttu-id="ffdda-115">ConferenceSessionDetails 视图</span><span class="sxs-lookup"><span data-stu-id="ffdda-115">ConferenceSessionDetails view</span></span>](conferencesessiondetails.md) <br/> |<span data-ttu-id="ffdda-116">返回所有会议会话的会话详细信息，包括开始和结束时间、用户 Id、响应代码和诊断 Id。</span><span class="sxs-lookup"><span data-stu-id="ffdda-116">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span>  <br/> |
|[<span data-ttu-id="ffdda-117">ConferenceUris 视图</span><span class="sxs-lookup"><span data-stu-id="ffdda-117">ConferenceUris view</span></span>](conferenceuris-0.md) <br/> |<span data-ttu-id="ffdda-118">返回有关会议中使用的会议 Uri 的信息</span><span class="sxs-lookup"><span data-stu-id="ffdda-118">Returns information about conference URIs used in a conference</span></span>  <br/> |
|[<span data-ttu-id="ffdda-119">ErrorReport 视图</span><span class="sxs-lookup"><span data-stu-id="ffdda-119">ErrorReport view</span></span>](errorreport-0.md) <br/> |<span data-ttu-id="ffdda-120">返回有关会话期间发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="ffdda-120">Returns information about errors that occurred during a session.</span></span>  <br/> |
|[<span data-ttu-id="ffdda-121">FileTransfers 视图</span><span class="sxs-lookup"><span data-stu-id="ffdda-121">FileTransfers view</span></span>](filetransfers.md) <br/> |<span data-ttu-id="ffdda-122">返回有关文件传输会话的信息，包括文件名以及是否接受、拒绝或取消传输。</span><span class="sxs-lookup"><span data-stu-id="ffdda-122">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span>  <br/> |
|[<span data-ttu-id="ffdda-123">FocusJoinsAndLeaves 视图</span><span class="sxs-lookup"><span data-stu-id="ffdda-123">FocusJoinsAndLeaves view</span></span>](focusjoinsandleaves-0.md) <br/> |<span data-ttu-id="ffdda-124">返回有关会议加入和退出活动的信息。</span><span class="sxs-lookup"><span data-stu-id="ffdda-124">Returns information about conference join and leave activities.</span></span>  <br/> |
|[<span data-ttu-id="ffdda-125">McuJoinsAndLeaves 视图</span><span class="sxs-lookup"><span data-stu-id="ffdda-125">McuJoinsAndLeaves view</span></span>](mcujoinsandleaves-0.md) <br/> |<span data-ttu-id="ffdda-126">返回有关会议加入和退出活动的组合信息（每个会议联接与相应的会议休假配对）。</span><span class="sxs-lookup"><span data-stu-id="ffdda-126">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span>  <br/> |
|[<span data-ttu-id="ffdda-127">Mcus 视图</span><span class="sxs-lookup"><span data-stu-id="ffdda-127">Mcus view</span></span>](mcus-0.md) <br/> |<span data-ttu-id="ffdda-128">返回有关会议服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="ffdda-128">Returns information about Conferencing servers.</span></span>  <br/> |
|[<span data-ttu-id="ffdda-129">媒体视图</span><span class="sxs-lookup"><span data-stu-id="ffdda-129">Media view</span></span>](media-0.md) <br/> |<span data-ttu-id="ffdda-130">返回有关对等通信会话中使用的媒体类型的信息。</span><span class="sxs-lookup"><span data-stu-id="ffdda-130">Returns information about the types of media used in peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="ffdda-131">ProgressReport 视图</span><span class="sxs-lookup"><span data-stu-id="ffdda-131">ProgressReport view</span></span>](progressreport-0.md) <br/> |<span data-ttu-id="ffdda-132">返回有关已完成会话的信息。</span><span class="sxs-lookup"><span data-stu-id="ffdda-132">Returns information about completed sessions.</span></span>  <br/> |
|[<span data-ttu-id="ffdda-133">注册视图</span><span class="sxs-lookup"><span data-stu-id="ffdda-133">Registration view</span></span>](registration-0.md) <br/> |<span data-ttu-id="ffdda-134">返回有关 Skype for business Server 2015 的注册信息。</span><span class="sxs-lookup"><span data-stu-id="ffdda-134">Returns information about registrations with Skype for Business Server 2015.</span></span>  <br/> |
|[<span data-ttu-id="ffdda-135">SessionDetails 视图</span><span class="sxs-lookup"><span data-stu-id="ffdda-135">SessionDetails view</span></span>](sessiondetails-0.md) <br/> |<span data-ttu-id="ffdda-136">返回有关对等会话的信息，包括 VoIP-VoIP 电话呼叫、两方 IM 会话或其他对等通信会话。</span><span class="sxs-lookup"><span data-stu-id="ffdda-136">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="ffdda-137">用户视图</span><span class="sxs-lookup"><span data-stu-id="ffdda-137">User view</span></span>](user.md) <br/> |<span data-ttu-id="ffdda-138">返回有关参与通信会话的用户的信息。</span><span class="sxs-lookup"><span data-stu-id="ffdda-138">Returns information about the users who have participated in communication sessions.</span></span>  <br/> |
|[<span data-ttu-id="ffdda-139">VoIPDetails 视图</span><span class="sxs-lookup"><span data-stu-id="ffdda-139">VoIPDetails view</span></span>](voipdetails.md) <br/> |<span data-ttu-id="ffdda-140">返回至少涉及一个 VoIP （通过 IO 的语音）用户的对等会话的信息。</span><span class="sxs-lookup"><span data-stu-id="ffdda-140">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span>  <br/> |
   

