---
title: Server 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: 服务器表是支持表。 每条记录代表一台服务器。
ms.openlocfilehash: e57bb96fd715d67a5b6676a2399dc520f08bac96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41806130"
---
# <a name="server-table"></a><span data-ttu-id="6bef3-104">Server 表</span><span class="sxs-lookup"><span data-stu-id="6bef3-104">Server table</span></span>
 
<span data-ttu-id="6bef3-105">服务器表是支持表。</span><span class="sxs-lookup"><span data-stu-id="6bef3-105">The Server table is a supporting table.</span></span> <span data-ttu-id="6bef3-106">每条记录代表一台服务器。</span><span class="sxs-lookup"><span data-stu-id="6bef3-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="6bef3-107">**列**</span><span class="sxs-lookup"><span data-stu-id="6bef3-107">**Column**</span></span>|<span data-ttu-id="6bef3-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="6bef3-108">**Data Type**</span></span>|<span data-ttu-id="6bef3-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="6bef3-109">**Key/Index**</span></span>|<span data-ttu-id="6bef3-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="6bef3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6bef3-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="6bef3-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="6bef3-112">int</span><span class="sxs-lookup"><span data-stu-id="6bef3-112">int</span></span>  <br/> |<span data-ttu-id="6bef3-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6bef3-113">Primary</span></span>  <br/> |<span data-ttu-id="6bef3-114">标识服务器的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="6bef3-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="6bef3-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="6bef3-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="6bef3-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6bef3-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6bef3-117">食指</span><span class="sxs-lookup"><span data-stu-id="6bef3-117">index</span></span>  <br/> |<span data-ttu-id="6bef3-118">MAC 地址字符串。</span><span class="sxs-lookup"><span data-stu-id="6bef3-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="6bef3-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="6bef3-119">**ServerType**</span></span> <br/> |<span data-ttu-id="6bef3-120">int</span><span class="sxs-lookup"><span data-stu-id="6bef3-120">int</span></span>  <br/> |<span data-ttu-id="6bef3-121">外表</span><span class="sxs-lookup"><span data-stu-id="6bef3-121">Foreign</span></span>  <br/> |<span data-ttu-id="6bef3-122">1：中介服务器</span><span class="sxs-lookup"><span data-stu-id="6bef3-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="6bef3-123">2： a/V 会议 Server16394： A/V 边缘 service32769： Gateway</span><span class="sxs-lookup"><span data-stu-id="6bef3-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="6bef3-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="6bef3-124">**PoolName**</span></span> <br/> |<span data-ttu-id="6bef3-125">nvarchar （512）</span><span class="sxs-lookup"><span data-stu-id="6bef3-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="6bef3-126">服务器所属的池。</span><span class="sxs-lookup"><span data-stu-id="6bef3-126">Pool the server belongs to.</span></span> <span data-ttu-id="6bef3-127">仅适用于 A/V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="6bef3-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="6bef3-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="6bef3-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="6bef3-129">datetime</span><span class="sxs-lookup"><span data-stu-id="6bef3-129">datetime</span></span>  <br/> ||<span data-ttu-id="6bef3-130">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="6bef3-130">For internal use only.</span></span>  <br/> |
   

