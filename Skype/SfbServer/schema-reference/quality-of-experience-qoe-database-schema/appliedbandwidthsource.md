---
title: AppliedBandwidthSource 表
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource 表是一个支持表。 每条记录分别表示一个来源。
ms.openlocfilehash: bf7e1be3b98bcd56fea16dbd7aa7171b056a7f3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831402"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="a483e-104">AppliedBandwidthSource 表</span><span class="sxs-lookup"><span data-stu-id="a483e-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="a483e-p102">AppliedBandwidthSource 表是一个支持表。每条记录分别表示一个来源。</span><span class="sxs-lookup"><span data-stu-id="a483e-p102">The AppliedBandwidthSource table is a supporting table. Each record represents one source.</span></span>
  
|<span data-ttu-id="a483e-107">**列**</span><span class="sxs-lookup"><span data-stu-id="a483e-107">**Column**</span></span>|<span data-ttu-id="a483e-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a483e-108">**Data Type**</span></span>|<span data-ttu-id="a483e-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="a483e-109">**Key/Index**</span></span>|<span data-ttu-id="a483e-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="a483e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a483e-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="a483e-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="a483e-112">int</span><span class="sxs-lookup"><span data-stu-id="a483e-112">int</span></span>  <br/> |<span data-ttu-id="a483e-113">主</span><span class="sxs-lookup"><span data-stu-id="a483e-113">Primary</span></span>  <br/> |<span data-ttu-id="a483e-114">标识来源的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="a483e-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="a483e-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="a483e-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="a483e-116">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="a483e-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="a483e-117">独特</span><span class="sxs-lookup"><span data-stu-id="a483e-117">Unique</span></span>  <br/> |<span data-ttu-id="a483e-118">这是所设定的带宽限制的来源。</span><span class="sxs-lookup"><span data-stu-id="a483e-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="a483e-119">它描述带宽限制来自何处 (例如，"Policy Server"、"TURN Server"或"Modality") 。</span><span class="sxs-lookup"><span data-stu-id="a483e-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

