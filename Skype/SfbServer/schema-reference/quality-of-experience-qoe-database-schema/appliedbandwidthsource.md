---
title: AppliedBandwidthSource 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource 表是支持表。 每条记录表示一个来源。
ms.openlocfilehash: 6d40701b74dd5e7312a504127675eed686de7321
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295109"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="55823-104">AppliedBandwidthSource 表</span><span class="sxs-lookup"><span data-stu-id="55823-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="55823-105">AppliedBandwidthSource 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="55823-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="55823-106">每条记录表示一个来源。</span><span class="sxs-lookup"><span data-stu-id="55823-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="55823-107">**列**</span><span class="sxs-lookup"><span data-stu-id="55823-107">**Column**</span></span>|<span data-ttu-id="55823-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="55823-108">**Data Type**</span></span>|<span data-ttu-id="55823-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="55823-109">**Key/Index**</span></span>|<span data-ttu-id="55823-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="55823-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="55823-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="55823-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="55823-112">int</span><span class="sxs-lookup"><span data-stu-id="55823-112">int</span></span>  <br/> |<span data-ttu-id="55823-113">Primary</span><span class="sxs-lookup"><span data-stu-id="55823-113">Primary</span></span>  <br/> |<span data-ttu-id="55823-114">标识源的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="55823-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="55823-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="55823-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="55823-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="55823-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="55823-117">唯一</span><span class="sxs-lookup"><span data-stu-id="55823-117">Unique</span></span>  <br/> |<span data-ttu-id="55823-118">这是所强加的带宽上限的来源。</span><span class="sxs-lookup"><span data-stu-id="55823-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="55823-119">它介绍带宽限制的来源 (例如, "策略服务器"、"转换服务器" 或 "模态")。</span><span class="sxs-lookup"><span data-stu-id="55823-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

