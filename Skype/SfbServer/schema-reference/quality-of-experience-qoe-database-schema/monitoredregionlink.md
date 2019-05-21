---
title: MonitoredRegionLink 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink 表是支持表。 每条记录表示两个国家/地区之间的一个链接。
ms.openlocfilehash: fdace97e0a7c9685f59471074cca64ede4fcc63d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294871"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="ed90b-104">MonitoredRegionLink 表</span><span class="sxs-lookup"><span data-stu-id="ed90b-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="ed90b-105">MonitoredRegionLink 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="ed90b-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="ed90b-106">每条记录表示两个国家/地区之间的一个链接。</span><span class="sxs-lookup"><span data-stu-id="ed90b-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="ed90b-107">**列**</span><span class="sxs-lookup"><span data-stu-id="ed90b-107">**Column**</span></span>|<span data-ttu-id="ed90b-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ed90b-108">**Data Type**</span></span>|<span data-ttu-id="ed90b-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="ed90b-109">**Key/Index**</span></span>|<span data-ttu-id="ed90b-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="ed90b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ed90b-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="ed90b-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="ed90b-112">int</span><span class="sxs-lookup"><span data-stu-id="ed90b-112">int</span></span>  <br/> |<span data-ttu-id="ed90b-113">主、外部</span><span class="sxs-lookup"><span data-stu-id="ed90b-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ed90b-114">从[区域表](region.md)中引用。</span><span class="sxs-lookup"><span data-stu-id="ed90b-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="ed90b-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="ed90b-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="ed90b-116">int</span><span class="sxs-lookup"><span data-stu-id="ed90b-116">int</span></span>  <br/> |<span data-ttu-id="ed90b-117">主、外部</span><span class="sxs-lookup"><span data-stu-id="ed90b-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ed90b-118">从[区域表](region.md)中引用。</span><span class="sxs-lookup"><span data-stu-id="ed90b-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

