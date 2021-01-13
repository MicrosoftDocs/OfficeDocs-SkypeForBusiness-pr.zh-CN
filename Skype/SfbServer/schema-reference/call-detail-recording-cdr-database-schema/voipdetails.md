---
title: VoIPDetails 视图
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails 视图存储有关对等会话（其中至少有一个用户是 VoIP 用户）的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: b42fecc7a0f43f86dba2439a373c7013c605a5e0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813072"
---
# <a name="voipdetails-view"></a><span data-ttu-id="69e3b-104">VoIPDetails 视图</span><span class="sxs-lookup"><span data-stu-id="69e3b-104">VoIPDetails view</span></span>
 
<span data-ttu-id="69e3b-105">VoIPDetails 视图存储有关对等会话（其中至少有一个用户是 VoIP 用户）的信息。</span><span class="sxs-lookup"><span data-stu-id="69e3b-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="69e3b-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="69e3b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="69e3b-107">VoIPDetails 视图包含 [SessionDetails](sessiondetails-0.md) 视图中的所有列以及下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="69e3b-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="69e3b-108">**列**</span><span class="sxs-lookup"><span data-stu-id="69e3b-108">**Column**</span></span>|<span data-ttu-id="69e3b-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="69e3b-109">**Data Type**</span></span>|<span data-ttu-id="69e3b-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="69e3b-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="69e3b-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="69e3b-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="69e3b-112">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="69e3b-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="69e3b-113">启动会话的用户的电话 ID。</span><span class="sxs-lookup"><span data-stu-id="69e3b-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="69e3b-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="69e3b-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="69e3b-115">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="69e3b-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="69e3b-116">加入会话的用户的电话 URI。</span><span class="sxs-lookup"><span data-stu-id="69e3b-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="69e3b-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="69e3b-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="69e3b-118">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="69e3b-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="69e3b-119">断开会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="69e3b-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="69e3b-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="69e3b-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="69e3b-121">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="69e3b-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="69e3b-122">断开会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="69e3b-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="69e3b-123">有关详细信息， [请参阅 UriTypes](uritypes.md) 表。</span><span class="sxs-lookup"><span data-stu-id="69e3b-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="69e3b-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="69e3b-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="69e3b-125">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="69e3b-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="69e3b-126">断开会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="69e3b-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="69e3b-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="69e3b-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="69e3b-128">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="69e3b-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="69e3b-129">断开会话的用户的电话 URI。</span><span class="sxs-lookup"><span data-stu-id="69e3b-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="69e3b-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="69e3b-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="69e3b-131">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="69e3b-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="69e3b-132">启动会话的用户使用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="69e3b-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="69e3b-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="69e3b-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="69e3b-134">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="69e3b-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="69e3b-135">加入会话的用户使用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="69e3b-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="69e3b-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="69e3b-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="69e3b-137">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="69e3b-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="69e3b-138">启动会话的用户使用的网关。</span><span class="sxs-lookup"><span data-stu-id="69e3b-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="69e3b-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="69e3b-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="69e3b-140">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="69e3b-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="69e3b-141">加入会话的用户使用的网关。</span><span class="sxs-lookup"><span data-stu-id="69e3b-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

