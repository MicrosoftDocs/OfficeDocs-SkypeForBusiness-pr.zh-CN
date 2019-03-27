---
title: Pool 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Pool 表是一个支持表，用于存储有关各种前端池的信息。 表中的每条记录代表一个池。
ms.openlocfilehash: ae8695316bdea6ba858bf9a4d334dc6075b99d50
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874016"
---
# <a name="pool-table"></a><span data-ttu-id="3abac-104">Pool 表</span><span class="sxs-lookup"><span data-stu-id="3abac-104">Pool table</span></span>
 
<span data-ttu-id="3abac-105">Pool 表是一个支持表，用于存储有关各种前端池的信息。</span><span class="sxs-lookup"><span data-stu-id="3abac-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="3abac-106">表中的每条记录代表一个池。</span><span class="sxs-lookup"><span data-stu-id="3abac-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="3abac-107">**列**</span><span class="sxs-lookup"><span data-stu-id="3abac-107">**Column**</span></span>|<span data-ttu-id="3abac-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3abac-108">**Data Type**</span></span>|<span data-ttu-id="3abac-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="3abac-109">**Key/Index**</span></span>|<span data-ttu-id="3abac-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="3abac-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3abac-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="3abac-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="3abac-112">int</span><span class="sxs-lookup"><span data-stu-id="3abac-112">int</span></span>  <br/> |<span data-ttu-id="3abac-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3abac-113">Primary</span></span>  <br/> |<span data-ttu-id="3abac-114">标识此池的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="3abac-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="3abac-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="3abac-115">**PoolName**</span></span> <br/> |<span data-ttu-id="3abac-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3abac-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3abac-117">唯一</span><span class="sxs-lookup"><span data-stu-id="3abac-117">Unique</span></span>  <br/> |<span data-ttu-id="3abac-118">池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3abac-118">Pool FQDN.</span></span>  <br/> |
   

