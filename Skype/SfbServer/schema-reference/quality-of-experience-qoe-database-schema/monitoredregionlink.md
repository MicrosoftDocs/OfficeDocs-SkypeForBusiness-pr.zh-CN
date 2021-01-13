---
title: MonitoredRegionLink 表
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink 表是一个支持表。 每条记录表示两个国家/地区之间的一个链接。
ms.openlocfilehash: f30ba249f89a2247e0e03c71fc97f05e69c59bcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806342"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="3079f-104">MonitoredRegionLink 表</span><span class="sxs-lookup"><span data-stu-id="3079f-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="3079f-105">MonitoredRegionLink 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="3079f-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="3079f-106">每条记录表示两个国家/地区之间的一个链接。</span><span class="sxs-lookup"><span data-stu-id="3079f-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="3079f-107">**列**</span><span class="sxs-lookup"><span data-stu-id="3079f-107">**Column**</span></span>|<span data-ttu-id="3079f-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3079f-108">**Data Type**</span></span>|<span data-ttu-id="3079f-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="3079f-109">**Key/Index**</span></span>|<span data-ttu-id="3079f-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="3079f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3079f-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="3079f-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="3079f-112">int</span><span class="sxs-lookup"><span data-stu-id="3079f-112">int</span></span>  <br/> |<span data-ttu-id="3079f-113">主、外</span><span class="sxs-lookup"><span data-stu-id="3079f-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3079f-114">从 Region 表 [引用](region.md)。</span><span class="sxs-lookup"><span data-stu-id="3079f-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="3079f-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="3079f-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="3079f-116">int</span><span class="sxs-lookup"><span data-stu-id="3079f-116">int</span></span>  <br/> |<span data-ttu-id="3079f-117">主、外</span><span class="sxs-lookup"><span data-stu-id="3079f-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3079f-118">从 Region 表 [引用](region.md)。</span><span class="sxs-lookup"><span data-stu-id="3079f-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

