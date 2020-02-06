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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink 表是支持表。 每条记录表示两个国家/地区之间的一个链接。
ms.openlocfilehash: a6b92460e2b097460681023f7d6877f02c046bdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807810"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="99a46-104">MonitoredRegionLink 表</span><span class="sxs-lookup"><span data-stu-id="99a46-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="99a46-105">MonitoredRegionLink 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="99a46-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="99a46-106">每条记录表示两个国家/地区之间的一个链接。</span><span class="sxs-lookup"><span data-stu-id="99a46-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="99a46-107">**列**</span><span class="sxs-lookup"><span data-stu-id="99a46-107">**Column**</span></span>|<span data-ttu-id="99a46-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="99a46-108">**Data Type**</span></span>|<span data-ttu-id="99a46-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="99a46-109">**Key/Index**</span></span>|<span data-ttu-id="99a46-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="99a46-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="99a46-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="99a46-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="99a46-112">int</span><span class="sxs-lookup"><span data-stu-id="99a46-112">int</span></span>  <br/> |<span data-ttu-id="99a46-113">主、外部</span><span class="sxs-lookup"><span data-stu-id="99a46-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="99a46-114">从[区域表](region.md)中引用。</span><span class="sxs-lookup"><span data-stu-id="99a46-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="99a46-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="99a46-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="99a46-116">int</span><span class="sxs-lookup"><span data-stu-id="99a46-116">int</span></span>  <br/> |<span data-ttu-id="99a46-117">主、外部</span><span class="sxs-lookup"><span data-stu-id="99a46-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="99a46-118">从[区域表](region.md)中引用。</span><span class="sxs-lookup"><span data-stu-id="99a46-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

