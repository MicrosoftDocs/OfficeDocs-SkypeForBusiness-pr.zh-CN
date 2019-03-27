---
title: VoIPDetails 视图
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails 视图存储有关对等会话，其中至少一个用户是 VoIP 用户的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 940c3874d5ce8eb8a4d2261de56b8988b6d3a4c9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875551"
---
# <a name="voipdetails-view"></a><span data-ttu-id="0cba8-104">VoIPDetails 视图</span><span class="sxs-lookup"><span data-stu-id="0cba8-104">VoIPDetails view</span></span>
 
<span data-ttu-id="0cba8-105">VoIPDetails 视图存储有关对等会话，其中至少一个用户是 VoIP 用户的信息。</span><span class="sxs-lookup"><span data-stu-id="0cba8-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="0cba8-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="0cba8-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0cba8-107">VoIPDetails 视图还包含[SessionDetails view](sessiondetails-0.md)中的列的所有中下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="0cba8-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="0cba8-108">**列**</span><span class="sxs-lookup"><span data-stu-id="0cba8-108">**Column**</span></span>|<span data-ttu-id="0cba8-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0cba8-109">**Data Type**</span></span>|<span data-ttu-id="0cba8-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="0cba8-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0cba8-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="0cba8-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="0cba8-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="0cba8-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="0cba8-113">启动会话的用户的电话 URI。</span><span class="sxs-lookup"><span data-stu-id="0cba8-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="0cba8-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="0cba8-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="0cba8-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="0cba8-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="0cba8-116">加入会话的用户的电话 URI。</span><span class="sxs-lookup"><span data-stu-id="0cba8-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="0cba8-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="0cba8-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="0cba8-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="0cba8-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="0cba8-119">断开会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="0cba8-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="0cba8-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="0cba8-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="0cba8-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0cba8-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0cba8-122">断开会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="0cba8-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="0cba8-123">请参阅[UriTypes 表](uritypes.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0cba8-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0cba8-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="0cba8-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="0cba8-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0cba8-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0cba8-126">断开会话租户的用户。</span><span class="sxs-lookup"><span data-stu-id="0cba8-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="0cba8-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="0cba8-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="0cba8-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="0cba8-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="0cba8-129">断开会话的用户的电话 URI。</span><span class="sxs-lookup"><span data-stu-id="0cba8-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="0cba8-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="0cba8-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="0cba8-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0cba8-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0cba8-132">启动会话的用户使用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="0cba8-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="0cba8-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="0cba8-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="0cba8-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0cba8-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0cba8-135">加入会话的用户使用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="0cba8-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="0cba8-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="0cba8-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="0cba8-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0cba8-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0cba8-138">启动会话的用户使用的网关。</span><span class="sxs-lookup"><span data-stu-id="0cba8-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="0cba8-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="0cba8-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="0cba8-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0cba8-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0cba8-141">加入会话的用户使用的网关。</span><span class="sxs-lookup"><span data-stu-id="0cba8-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

