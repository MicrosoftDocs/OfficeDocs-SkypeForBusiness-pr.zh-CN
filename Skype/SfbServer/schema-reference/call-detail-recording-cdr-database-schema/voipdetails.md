---
title: VoIPDetails 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails 视图存储有关对等会话的信息，其中至少有一个用户是 VoIP 用户。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 4d3aec4c58c2cb11f21ec6403f7532bcde46b05e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814770"
---
# <a name="voipdetails-view"></a><span data-ttu-id="aeda9-104">VoIPDetails 视图</span><span class="sxs-lookup"><span data-stu-id="aeda9-104">VoIPDetails view</span></span>
 
<span data-ttu-id="aeda9-105">VoIPDetails 视图存储有关对等会话的信息，其中至少有一个用户是 VoIP 用户。</span><span class="sxs-lookup"><span data-stu-id="aeda9-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="aeda9-106">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="aeda9-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aeda9-107">VoIPDetails 视图包含[SessionDetails 视图](sessiondetails-0.md)中的所有列以及下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="aeda9-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="aeda9-108">**列**</span><span class="sxs-lookup"><span data-stu-id="aeda9-108">**Column**</span></span>|<span data-ttu-id="aeda9-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="aeda9-109">**Data Type**</span></span>|<span data-ttu-id="aeda9-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="aeda9-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aeda9-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="aeda9-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="aeda9-112">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="aeda9-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="aeda9-113">启动会话的用户的电话 URI。</span><span class="sxs-lookup"><span data-stu-id="aeda9-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="aeda9-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="aeda9-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="aeda9-115">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="aeda9-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="aeda9-116">加入会话的用户的电话 URI。</span><span class="sxs-lookup"><span data-stu-id="aeda9-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="aeda9-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="aeda9-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="aeda9-118">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="aeda9-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="aeda9-119">断开会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="aeda9-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="aeda9-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="aeda9-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="aeda9-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aeda9-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="aeda9-122">断开会话的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="aeda9-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="aeda9-123">有关详细信息，请参阅[UriTypes 表](uritypes.md)。</span><span class="sxs-lookup"><span data-stu-id="aeda9-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="aeda9-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="aeda9-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="aeda9-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aeda9-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="aeda9-126">断开会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="aeda9-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="aeda9-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="aeda9-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="aeda9-128">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="aeda9-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="aeda9-129">断开会话的用户的电话 URI。</span><span class="sxs-lookup"><span data-stu-id="aeda9-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="aeda9-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="aeda9-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="aeda9-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aeda9-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="aeda9-132">启动会话的用户所使用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="aeda9-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="aeda9-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="aeda9-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="aeda9-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aeda9-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="aeda9-135">加入会话的用户所使用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="aeda9-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="aeda9-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="aeda9-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="aeda9-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aeda9-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="aeda9-138">启动会话的用户所使用的网关。</span><span class="sxs-lookup"><span data-stu-id="aeda9-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="aeda9-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="aeda9-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="aeda9-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aeda9-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="aeda9-141">加入会话的用户所使用的网关。</span><span class="sxs-lookup"><span data-stu-id="aeda9-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

