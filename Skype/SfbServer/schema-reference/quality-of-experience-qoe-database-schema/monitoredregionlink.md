---
title: MonitoredRegionLink 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink 表是一个支持表。 每条记录代表一个两个国家/地区之间的链接。
ms.openlocfilehash: 0df5cd8abe957ed952bdf656a67e1d423cc57f33
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884412"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="626eb-104">MonitoredRegionLink 表</span><span class="sxs-lookup"><span data-stu-id="626eb-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="626eb-105">MonitoredRegionLink 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="626eb-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="626eb-106">每条记录代表一个两个国家/地区之间的链接。</span><span class="sxs-lookup"><span data-stu-id="626eb-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="626eb-107">**列**</span><span class="sxs-lookup"><span data-stu-id="626eb-107">**Column**</span></span>|<span data-ttu-id="626eb-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="626eb-108">**Data Type**</span></span>|<span data-ttu-id="626eb-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="626eb-109">**Key/Index**</span></span>|<span data-ttu-id="626eb-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="626eb-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="626eb-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="626eb-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="626eb-112">int</span><span class="sxs-lookup"><span data-stu-id="626eb-112">int</span></span>  <br/> |<span data-ttu-id="626eb-113">主、 外</span><span class="sxs-lookup"><span data-stu-id="626eb-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="626eb-114">引用自[Region table](region.md)。</span><span class="sxs-lookup"><span data-stu-id="626eb-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="626eb-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="626eb-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="626eb-116">int</span><span class="sxs-lookup"><span data-stu-id="626eb-116">int</span></span>  <br/> |<span data-ttu-id="626eb-117">主、 外</span><span class="sxs-lookup"><span data-stu-id="626eb-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="626eb-118">引用自[Region table](region.md)。</span><span class="sxs-lookup"><span data-stu-id="626eb-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

