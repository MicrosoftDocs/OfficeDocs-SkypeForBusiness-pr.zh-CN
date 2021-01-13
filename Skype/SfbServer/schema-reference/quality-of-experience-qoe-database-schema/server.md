---
title: 服务器表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Server 表是一个支持表。 每个记录表示一台服务器。
ms.openlocfilehash: 7f26ed9053c65acb8cfd2e586edbd77fdfa7472b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802702"
---
# <a name="server-table"></a><span data-ttu-id="4f87c-104">服务器表</span><span class="sxs-lookup"><span data-stu-id="4f87c-104">Server table</span></span>
 
<span data-ttu-id="4f87c-p102">Server 表是一个支持表。每个记录表示一台服务器。</span><span class="sxs-lookup"><span data-stu-id="4f87c-p102">The Server table is a supporting table. Each record represents one server.</span></span> 
  
|<span data-ttu-id="4f87c-107">**列**</span><span class="sxs-lookup"><span data-stu-id="4f87c-107">**Column**</span></span>|<span data-ttu-id="4f87c-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4f87c-108">**Data Type**</span></span>|<span data-ttu-id="4f87c-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="4f87c-109">**Key/Index**</span></span>|<span data-ttu-id="4f87c-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="4f87c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4f87c-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="4f87c-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="4f87c-112">int</span><span class="sxs-lookup"><span data-stu-id="4f87c-112">int</span></span>  <br/> |<span data-ttu-id="4f87c-113">主</span><span class="sxs-lookup"><span data-stu-id="4f87c-113">Primary</span></span>  <br/> |<span data-ttu-id="4f87c-114">标识服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="4f87c-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="4f87c-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="4f87c-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="4f87c-116">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="4f87c-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4f87c-117">index</span><span class="sxs-lookup"><span data-stu-id="4f87c-117">index</span></span>  <br/> |<span data-ttu-id="4f87c-118">MAC 地址字符串。</span><span class="sxs-lookup"><span data-stu-id="4f87c-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="4f87c-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="4f87c-119">**ServerType**</span></span> <br/> |<span data-ttu-id="4f87c-120">int</span><span class="sxs-lookup"><span data-stu-id="4f87c-120">int</span></span>  <br/> |<span data-ttu-id="4f87c-121">Foreign</span><span class="sxs-lookup"><span data-stu-id="4f87c-121">Foreign</span></span>  <br/> |<span data-ttu-id="4f87c-122">1：中介服务器</span><span class="sxs-lookup"><span data-stu-id="4f87c-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="4f87c-123">2：A/V 会议服务器 16394：A/V 边缘服务 32769：网关</span><span class="sxs-lookup"><span data-stu-id="4f87c-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="4f87c-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="4f87c-124">**PoolName**</span></span> <br/> |<span data-ttu-id="4f87c-125">nvarchar (512) </span><span class="sxs-lookup"><span data-stu-id="4f87c-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="4f87c-p103">服务器所属的池。仅适用于 A/V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="4f87c-p103">Pool the server belongs to. Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="4f87c-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="4f87c-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="4f87c-129">datetime</span><span class="sxs-lookup"><span data-stu-id="4f87c-129">datetime</span></span>  <br/> ||<span data-ttu-id="4f87c-130">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="4f87c-130">For internal use only.</span></span>  <br/> |
   

