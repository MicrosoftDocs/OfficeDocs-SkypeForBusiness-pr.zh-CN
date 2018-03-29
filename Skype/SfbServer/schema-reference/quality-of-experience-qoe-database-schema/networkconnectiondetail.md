---
title: NetworkConnectionDetail 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail 表映射到网络连接标识符体验质量数据库中的其他位置使用的网络连接类型。 在 Microsoft Lync Server 2013 引入了此表。
ms.openlocfilehash: cc1eb91d3c633ed9455a0476b613430dfa8e3d6b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="033ac-104">NetworkConnectionDetail 表</span><span class="sxs-lookup"><span data-stu-id="033ac-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="033ac-105">NetworkConnectionDetail 表映射到网络连接标识符体验质量数据库中的其他位置使用的网络连接类型。</span><span class="sxs-lookup"><span data-stu-id="033ac-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="033ac-106">在 Microsoft Lync Server 2013 引入了此表。</span><span class="sxs-lookup"><span data-stu-id="033ac-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="033ac-107">**列**</span><span class="sxs-lookup"><span data-stu-id="033ac-107">**Column**</span></span>|<span data-ttu-id="033ac-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="033ac-108">**Data Type**</span></span>|<span data-ttu-id="033ac-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="033ac-109">**Key/Index**</span></span>|<span data-ttu-id="033ac-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="033ac-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="033ac-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="033ac-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="033ac-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="033ac-112">tinyint</span></span>  <br/> |<span data-ttu-id="033ac-113">Primary</span><span class="sxs-lookup"><span data-stu-id="033ac-113">Primary</span></span>  <br/> |<span data-ttu-id="033ac-114">网络连接类型的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="033ac-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="033ac-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="033ac-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="033ac-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="033ac-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="033ac-117">唯一</span><span class="sxs-lookup"><span data-stu-id="033ac-117">Unique</span></span>  <br/> |<span data-ttu-id="033ac-118">对应于 NetworkConnectionDetailKey 的网络连接类型。</span><span class="sxs-lookup"><span data-stu-id="033ac-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="033ac-119">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="033ac-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="033ac-120">0--有线</span><span class="sxs-lookup"><span data-stu-id="033ac-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="033ac-121">1-WiFi</span><span class="sxs-lookup"><span data-stu-id="033ac-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="033ac-122">2-以太网</span><span class="sxs-lookup"><span data-stu-id="033ac-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="033ac-123">3-MobileBB</span><span class="sxs-lookup"><span data-stu-id="033ac-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="033ac-124">4-其他</span><span class="sxs-lookup"><span data-stu-id="033ac-124">4 -- Other</span></span>  <br/> <span data-ttu-id="033ac-125">5 — 隧道</span><span class="sxs-lookup"><span data-stu-id="033ac-125">5 -- Tunnel</span></span>  <br/> |
   

