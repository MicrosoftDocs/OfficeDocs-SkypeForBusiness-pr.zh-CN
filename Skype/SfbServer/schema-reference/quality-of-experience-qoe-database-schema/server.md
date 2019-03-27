---
title: Server 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Server 表是一个支持表。 每条记录代表一个服务器。
ms.openlocfilehash: 877743f5d589cd4fea34039786b33bd410069bb3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874306"
---
# <a name="server-table"></a><span data-ttu-id="da817-104">Server 表</span><span class="sxs-lookup"><span data-stu-id="da817-104">Server table</span></span>
 
<span data-ttu-id="da817-105">Server 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="da817-105">The Server table is a supporting table.</span></span> <span data-ttu-id="da817-106">每条记录代表一个服务器。</span><span class="sxs-lookup"><span data-stu-id="da817-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="da817-107">**列**</span><span class="sxs-lookup"><span data-stu-id="da817-107">**Column**</span></span>|<span data-ttu-id="da817-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="da817-108">**Data Type**</span></span>|<span data-ttu-id="da817-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="da817-109">**Key/Index**</span></span>|<span data-ttu-id="da817-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="da817-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="da817-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="da817-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="da817-112">int</span><span class="sxs-lookup"><span data-stu-id="da817-112">int</span></span>  <br/> |<span data-ttu-id="da817-113">Primary</span><span class="sxs-lookup"><span data-stu-id="da817-113">Primary</span></span>  <br/> |<span data-ttu-id="da817-114">标识服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="da817-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="da817-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="da817-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="da817-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="da817-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="da817-117">索引</span><span class="sxs-lookup"><span data-stu-id="da817-117">index</span></span>  <br/> |<span data-ttu-id="da817-118">MAC 地址字符串。</span><span class="sxs-lookup"><span data-stu-id="da817-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="da817-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="da817-119">**ServerType**</span></span> <br/> |<span data-ttu-id="da817-120">int</span><span class="sxs-lookup"><span data-stu-id="da817-120">int</span></span>  <br/> |<span data-ttu-id="da817-121">外</span><span class="sxs-lookup"><span data-stu-id="da817-121">Foreign</span></span>  <br/> |<span data-ttu-id="da817-122">1： 中介服务器</span><span class="sxs-lookup"><span data-stu-id="da817-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="da817-123">2: A / V 会议 Server16394: A / V 边缘服务 32769： 网关</span><span class="sxs-lookup"><span data-stu-id="da817-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="da817-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="da817-124">**PoolName**</span></span> <br/> |<span data-ttu-id="da817-125">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="da817-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="da817-126">服务器所属的池。</span><span class="sxs-lookup"><span data-stu-id="da817-126">Pool the server belongs to.</span></span> <span data-ttu-id="da817-127">仅适用于 A / V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="da817-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="da817-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="da817-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="da817-129">datetime</span><span class="sxs-lookup"><span data-stu-id="da817-129">datetime</span></span>  <br/> ||<span data-ttu-id="da817-130">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="da817-130">For internal use only.</span></span>  <br/> |
   

