---
title: Server 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: 服务器表是支持表。 每个记录表示一台服务器。
ms.openlocfilehash: be48b90cc727ebfd0320b38ac0d89a302dab6b07
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="server-table"></a><span data-ttu-id="8941c-104">Server 表</span><span class="sxs-lookup"><span data-stu-id="8941c-104">Server table</span></span>
 
<span data-ttu-id="8941c-105">服务器表是支持表。</span><span class="sxs-lookup"><span data-stu-id="8941c-105">The Server table is a supporting table.</span></span> <span data-ttu-id="8941c-106">每个记录表示一台服务器。</span><span class="sxs-lookup"><span data-stu-id="8941c-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="8941c-107">**列**</span><span class="sxs-lookup"><span data-stu-id="8941c-107">**Column**</span></span>|<span data-ttu-id="8941c-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8941c-108">**Data Type**</span></span>|<span data-ttu-id="8941c-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="8941c-109">**Key/Index**</span></span>|<span data-ttu-id="8941c-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="8941c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8941c-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="8941c-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="8941c-112">int</span><span class="sxs-lookup"><span data-stu-id="8941c-112">int</span></span>  <br/> |<span data-ttu-id="8941c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8941c-113">Primary</span></span>  <br/> |<span data-ttu-id="8941c-114">用于标识服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="8941c-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="8941c-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="8941c-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="8941c-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8941c-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8941c-117">索引</span><span class="sxs-lookup"><span data-stu-id="8941c-117">index</span></span>  <br/> |<span data-ttu-id="8941c-118">MAC 地址字符串。</span><span class="sxs-lookup"><span data-stu-id="8941c-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="8941c-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="8941c-119">**ServerType**</span></span> <br/> |<span data-ttu-id="8941c-120">int</span><span class="sxs-lookup"><span data-stu-id="8941c-120">int</span></span>  <br/> |<span data-ttu-id="8941c-121">外</span><span class="sxs-lookup"><span data-stu-id="8941c-121">Foreign</span></span>  <br/> |<span data-ttu-id="8941c-122">1： 中介服务器</span><span class="sxs-lookup"><span data-stu-id="8941c-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="8941c-123">2: A / V 会议 Server16394: A / V 边缘 service32769： 网关</span><span class="sxs-lookup"><span data-stu-id="8941c-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="8941c-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="8941c-124">**PoolName**</span></span> <br/> |<span data-ttu-id="8941c-125">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="8941c-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="8941c-126">服务器所属的池。</span><span class="sxs-lookup"><span data-stu-id="8941c-126">Pool the server belongs to.</span></span> <span data-ttu-id="8941c-127">仅适用于 A / V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="8941c-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="8941c-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="8941c-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="8941c-129">datetime</span><span class="sxs-lookup"><span data-stu-id="8941c-129">datetime</span></span>  <br/> ||<span data-ttu-id="8941c-130">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="8941c-130">For internal use only.</span></span>  <br/> |
   

