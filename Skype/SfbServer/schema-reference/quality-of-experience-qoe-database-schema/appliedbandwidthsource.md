---
title: AppliedBandwidthSource 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource 表是支持表。 每个记录表示一个信息源。
ms.openlocfilehash: e15df92423a3408e3cb8ae40a0788e1f165961df
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="a7533-104">AppliedBandwidthSource 表</span><span class="sxs-lookup"><span data-stu-id="a7533-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="a7533-105">AppliedBandwidthSource 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="a7533-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="a7533-106">每个记录表示一个信息源。</span><span class="sxs-lookup"><span data-stu-id="a7533-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="a7533-107">**列**</span><span class="sxs-lookup"><span data-stu-id="a7533-107">**Column**</span></span>|<span data-ttu-id="a7533-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a7533-108">**Data Type**</span></span>|<span data-ttu-id="a7533-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="a7533-109">**Key/Index**</span></span>|<span data-ttu-id="a7533-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="a7533-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7533-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="a7533-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="a7533-112">int</span><span class="sxs-lookup"><span data-stu-id="a7533-112">int</span></span>  <br/> |<span data-ttu-id="a7533-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a7533-113">Primary</span></span>  <br/> |<span data-ttu-id="a7533-114">标识源的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="a7533-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="a7533-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="a7533-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="a7533-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="a7533-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="a7533-117">唯一</span><span class="sxs-lookup"><span data-stu-id="a7533-117">Unique</span></span>  <br/> |<span data-ttu-id="a7533-118">这是被强加的带宽帽的来源。</span><span class="sxs-lookup"><span data-stu-id="a7533-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="a7533-119">它描述了带宽限制来自何处 （例如，"策略服务器"、"关闭服务器"或"成像设备"）。</span><span class="sxs-lookup"><span data-stu-id="a7533-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

