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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource 表是支持表。 每条记录表示一个来源。
ms.openlocfilehash: 875f6d105a2fef0bf710e57ec389bee4f2613c66
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811440"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="b0358-104">AppliedBandwidthSource 表</span><span class="sxs-lookup"><span data-stu-id="b0358-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="b0358-105">AppliedBandwidthSource 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="b0358-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="b0358-106">每条记录表示一个来源。</span><span class="sxs-lookup"><span data-stu-id="b0358-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="b0358-107">**列**</span><span class="sxs-lookup"><span data-stu-id="b0358-107">**Column**</span></span>|<span data-ttu-id="b0358-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b0358-108">**Data Type**</span></span>|<span data-ttu-id="b0358-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="b0358-109">**Key/Index**</span></span>|<span data-ttu-id="b0358-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="b0358-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b0358-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="b0358-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="b0358-112">int</span><span class="sxs-lookup"><span data-stu-id="b0358-112">int</span></span>  <br/> |<span data-ttu-id="b0358-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b0358-113">Primary</span></span>  <br/> |<span data-ttu-id="b0358-114">标识源的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="b0358-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="b0358-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="b0358-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="b0358-116">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="b0358-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="b0358-117">唯一</span><span class="sxs-lookup"><span data-stu-id="b0358-117">Unique</span></span>  <br/> |<span data-ttu-id="b0358-118">这是所强加的带宽上限的来源。</span><span class="sxs-lookup"><span data-stu-id="b0358-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="b0358-119">它介绍带宽限制的来源（例如，"策略服务器"、"转换服务器" 或 "模态"）。</span><span class="sxs-lookup"><span data-stu-id="b0358-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

