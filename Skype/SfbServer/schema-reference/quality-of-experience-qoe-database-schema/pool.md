---
title: Pool 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Pool 表是一个支持表, 用于存储各种前端池的相关信息。 表中的每条记录表示一个池。
ms.openlocfilehash: c101a10d40292c89c29e108739195a97fa22e5c0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294801"
---
# <a name="pool-table"></a><span data-ttu-id="2ee6c-104">Pool 表</span><span class="sxs-lookup"><span data-stu-id="2ee6c-104">Pool table</span></span>
 
<span data-ttu-id="2ee6c-105">Pool 表是一个支持表, 用于存储各种前端池的相关信息。</span><span class="sxs-lookup"><span data-stu-id="2ee6c-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="2ee6c-106">表中的每条记录表示一个池。</span><span class="sxs-lookup"><span data-stu-id="2ee6c-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="2ee6c-107">**列**</span><span class="sxs-lookup"><span data-stu-id="2ee6c-107">**Column**</span></span>|<span data-ttu-id="2ee6c-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="2ee6c-108">**Data Type**</span></span>|<span data-ttu-id="2ee6c-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="2ee6c-109">**Key/Index**</span></span>|<span data-ttu-id="2ee6c-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="2ee6c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2ee6c-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="2ee6c-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="2ee6c-112">int</span><span class="sxs-lookup"><span data-stu-id="2ee6c-112">int</span></span>  <br/> |<span data-ttu-id="2ee6c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="2ee6c-113">Primary</span></span>  <br/> |<span data-ttu-id="2ee6c-114">标识此池的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="2ee6c-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="2ee6c-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="2ee6c-115">**PoolName**</span></span> <br/> |<span data-ttu-id="2ee6c-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ee6c-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="2ee6c-117">唯一</span><span class="sxs-lookup"><span data-stu-id="2ee6c-117">Unique</span></span>  <br/> |<span data-ttu-id="2ee6c-118">池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2ee6c-118">Pool FQDN.</span></span>  <br/> |
   

