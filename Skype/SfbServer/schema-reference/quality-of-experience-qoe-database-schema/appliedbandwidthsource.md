---
title: AppliedBandwidthSource 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource 表是一个支持表。 每条记录代表一个源。
ms.openlocfilehash: 2fed25b6ca2218cb8b7300507b5c8258b2c29798
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212353"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="30750-104">AppliedBandwidthSource 表</span><span class="sxs-lookup"><span data-stu-id="30750-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="30750-105">AppliedBandwidthSource 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="30750-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="30750-106">每条记录代表一个源。</span><span class="sxs-lookup"><span data-stu-id="30750-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="30750-107">**列**</span><span class="sxs-lookup"><span data-stu-id="30750-107">**Column**</span></span>|<span data-ttu-id="30750-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="30750-108">**Data Type**</span></span>|<span data-ttu-id="30750-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="30750-109">**Key/Index**</span></span>|<span data-ttu-id="30750-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="30750-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="30750-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="30750-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="30750-112">int</span><span class="sxs-lookup"><span data-stu-id="30750-112">int</span></span>  <br/> |<span data-ttu-id="30750-113">Primary</span><span class="sxs-lookup"><span data-stu-id="30750-113">Primary</span></span>  <br/> |<span data-ttu-id="30750-114">标识来源的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="30750-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="30750-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="30750-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="30750-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="30750-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="30750-117">唯一</span><span class="sxs-lookup"><span data-stu-id="30750-117">Unique</span></span>  <br/> |<span data-ttu-id="30750-118">这是带宽帽正在施加的源。</span><span class="sxs-lookup"><span data-stu-id="30750-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="30750-119">它介绍了其中的带宽限制来自 （例如，"策略服务器"、"打开服务器"或"形式"）。</span><span class="sxs-lookup"><span data-stu-id="30750-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

