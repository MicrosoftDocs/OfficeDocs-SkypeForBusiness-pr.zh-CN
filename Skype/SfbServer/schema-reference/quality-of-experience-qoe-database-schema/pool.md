---
title: Pool 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: 池表是一个支持的表来存储有关各种前端池的信息。 每个表中的记录表示一个池。
ms.openlocfilehash: 8ce54d4b0a20fa405f34bb14b3eecb9ad395884e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="pool-table"></a><span data-ttu-id="c0826-104">Pool 表</span><span class="sxs-lookup"><span data-stu-id="c0826-104">Pool table</span></span>
 
<span data-ttu-id="c0826-105">池表是一个支持的表来存储有关各种前端池的信息。</span><span class="sxs-lookup"><span data-stu-id="c0826-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="c0826-106">每个表中的记录表示一个池。</span><span class="sxs-lookup"><span data-stu-id="c0826-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="c0826-107">**列**</span><span class="sxs-lookup"><span data-stu-id="c0826-107">**Column**</span></span>|<span data-ttu-id="c0826-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c0826-108">**Data Type**</span></span>|<span data-ttu-id="c0826-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="c0826-109">**Key/Index**</span></span>|<span data-ttu-id="c0826-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="c0826-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c0826-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="c0826-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="c0826-112">int</span><span class="sxs-lookup"><span data-stu-id="c0826-112">int</span></span>  <br/> |<span data-ttu-id="c0826-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c0826-113">Primary</span></span>  <br/> |<span data-ttu-id="c0826-114">标识此池的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="c0826-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="c0826-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="c0826-115">**PoolName**</span></span> <br/> |<span data-ttu-id="c0826-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c0826-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c0826-117">唯一</span><span class="sxs-lookup"><span data-stu-id="c0826-117">Unique</span></span>  <br/> |<span data-ttu-id="c0826-118">池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c0826-118">Pool FQDN.</span></span>  <br/> |
   

