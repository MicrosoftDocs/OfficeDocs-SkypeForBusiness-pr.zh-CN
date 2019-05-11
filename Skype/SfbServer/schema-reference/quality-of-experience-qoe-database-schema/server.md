---
title: Server 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Server 表是一个支持表。 每条记录代表一个服务器。
ms.openlocfilehash: c0031e7181bb39895edadc40748f61626621f00e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920129"
---
# <a name="server-table"></a><span data-ttu-id="872ff-104">Server 表</span><span class="sxs-lookup"><span data-stu-id="872ff-104">Server table</span></span>
 
<span data-ttu-id="872ff-105">Server 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="872ff-105">The Server table is a supporting table.</span></span> <span data-ttu-id="872ff-106">每条记录代表一个服务器。</span><span class="sxs-lookup"><span data-stu-id="872ff-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="872ff-107">**列**</span><span class="sxs-lookup"><span data-stu-id="872ff-107">**Column**</span></span>|<span data-ttu-id="872ff-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="872ff-108">**Data Type**</span></span>|<span data-ttu-id="872ff-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="872ff-109">**Key/Index**</span></span>|<span data-ttu-id="872ff-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="872ff-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="872ff-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="872ff-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="872ff-112">int</span><span class="sxs-lookup"><span data-stu-id="872ff-112">int</span></span>  <br/> |<span data-ttu-id="872ff-113">Primary</span><span class="sxs-lookup"><span data-stu-id="872ff-113">Primary</span></span>  <br/> |<span data-ttu-id="872ff-114">标识服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="872ff-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="872ff-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="872ff-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="872ff-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="872ff-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="872ff-117">索引</span><span class="sxs-lookup"><span data-stu-id="872ff-117">index</span></span>  <br/> |<span data-ttu-id="872ff-118">MAC 地址字符串。</span><span class="sxs-lookup"><span data-stu-id="872ff-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="872ff-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="872ff-119">**ServerType**</span></span> <br/> |<span data-ttu-id="872ff-120">int</span><span class="sxs-lookup"><span data-stu-id="872ff-120">int</span></span>  <br/> |<span data-ttu-id="872ff-121">外</span><span class="sxs-lookup"><span data-stu-id="872ff-121">Foreign</span></span>  <br/> |<span data-ttu-id="872ff-122">1： 中介服务器</span><span class="sxs-lookup"><span data-stu-id="872ff-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="872ff-123">2: A / V 会议 Server16394: A / V 边缘服务 32769： 网关</span><span class="sxs-lookup"><span data-stu-id="872ff-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="872ff-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="872ff-124">**PoolName**</span></span> <br/> |<span data-ttu-id="872ff-125">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="872ff-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="872ff-126">服务器所属的池。</span><span class="sxs-lookup"><span data-stu-id="872ff-126">Pool the server belongs to.</span></span> <span data-ttu-id="872ff-127">仅适用于 A / V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="872ff-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="872ff-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="872ff-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="872ff-129">datetime</span><span class="sxs-lookup"><span data-stu-id="872ff-129">datetime</span></span>  <br/> ||<span data-ttu-id="872ff-130">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="872ff-130">For internal use only.</span></span>  <br/> |
   

