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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Pool 表是一个支持表，用于存储各种前端池的相关信息。 表中的每条记录表示一个池。
ms.openlocfilehash: 2b6dfb924c3e7a79a323ebbabd90e74ba08ebf04
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807400"
---
# <a name="pool-table"></a><span data-ttu-id="c88d4-104">Pool 表</span><span class="sxs-lookup"><span data-stu-id="c88d4-104">Pool table</span></span>
 
<span data-ttu-id="c88d4-105">Pool 表是一个支持表，用于存储各种前端池的相关信息。</span><span class="sxs-lookup"><span data-stu-id="c88d4-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="c88d4-106">表中的每条记录表示一个池。</span><span class="sxs-lookup"><span data-stu-id="c88d4-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="c88d4-107">**列**</span><span class="sxs-lookup"><span data-stu-id="c88d4-107">**Column**</span></span>|<span data-ttu-id="c88d4-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c88d4-108">**Data Type**</span></span>|<span data-ttu-id="c88d4-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="c88d4-109">**Key/Index**</span></span>|<span data-ttu-id="c88d4-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="c88d4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c88d4-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="c88d4-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="c88d4-112">int</span><span class="sxs-lookup"><span data-stu-id="c88d4-112">int</span></span>  <br/> |<span data-ttu-id="c88d4-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c88d4-113">Primary</span></span>  <br/> |<span data-ttu-id="c88d4-114">标识此池的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="c88d4-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="c88d4-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="c88d4-115">**PoolName**</span></span> <br/> |<span data-ttu-id="c88d4-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c88d4-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c88d4-117">唯一</span><span class="sxs-lookup"><span data-stu-id="c88d4-117">Unique</span></span>  <br/> |<span data-ttu-id="c88d4-118">池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c88d4-118">Pool FQDN.</span></span>  <br/> |
   

