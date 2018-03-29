---
title: VoIPDetails 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails 视图存储对等会话，其中至少一个用户是 VoIP 用户有关的信息。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 93c2afb6383817a4d3941d5b427565fb1d0db098
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="voipdetails-view"></a><span data-ttu-id="d6281-104">VoIPDetails 视图</span><span class="sxs-lookup"><span data-stu-id="d6281-104">VoIPDetails view</span></span>
 
<span data-ttu-id="d6281-105">VoIPDetails 视图存储对等会话，其中至少一个用户是 VoIP 用户有关的信息。</span><span class="sxs-lookup"><span data-stu-id="d6281-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="d6281-106">在 Microsoft Lync Server 2013 引入了此视图。</span><span class="sxs-lookup"><span data-stu-id="d6281-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d6281-107">VoIPDetails 视图它包含[SessionDetails 视图](sessiondetails-0.md)中的列的所有除了下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="d6281-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="d6281-108">**列**</span><span class="sxs-lookup"><span data-stu-id="d6281-108">**Column**</span></span>|<span data-ttu-id="d6281-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d6281-109">**Data Type**</span></span>|<span data-ttu-id="d6281-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="d6281-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d6281-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="d6281-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="d6281-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d6281-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d6281-113">电话的启动会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="d6281-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="d6281-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="d6281-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="d6281-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d6281-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d6281-116">电话连接会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="d6281-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="d6281-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="d6281-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="d6281-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d6281-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d6281-119">断开连接会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="d6281-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="d6281-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="d6281-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="d6281-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d6281-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d6281-122">URI 的用户已断开连接的会话的类型。</span><span class="sxs-lookup"><span data-stu-id="d6281-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="d6281-123">[UriTypes 表](uritypes.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="d6281-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d6281-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="d6281-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="d6281-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d6281-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d6281-126">客户端的用户的用户已断开连接的会话。</span><span class="sxs-lookup"><span data-stu-id="d6281-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="d6281-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="d6281-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="d6281-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d6281-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d6281-129">电话断开连接会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="d6281-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="d6281-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="d6281-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="d6281-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d6281-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d6281-132">中介服务器启动该会话的用户的使用。</span><span class="sxs-lookup"><span data-stu-id="d6281-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="d6281-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="d6281-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="d6281-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d6281-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d6281-135">加入会话的用户所使用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="d6281-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="d6281-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="d6281-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="d6281-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d6281-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d6281-138">启动该会话的用户使用的网关。</span><span class="sxs-lookup"><span data-stu-id="d6281-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="d6281-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="d6281-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="d6281-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d6281-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d6281-141">加入会话的用户使用的网关。</span><span class="sxs-lookup"><span data-stu-id="d6281-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

