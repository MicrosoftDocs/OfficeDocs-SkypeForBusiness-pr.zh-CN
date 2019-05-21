---
title: NetworkConnectionDetail 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail 表将网络连接类型映射到 "体验质量" 数据库中其他位置使用的网络连接标识符。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: c13725e7df8a164766faa6847fc8097a24a9df53
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294815"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="33c56-104">NetworkConnectionDetail 表</span><span class="sxs-lookup"><span data-stu-id="33c56-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="33c56-105">NetworkConnectionDetail 表将网络连接类型映射到 "体验质量" 数据库中其他位置使用的网络连接标识符。</span><span class="sxs-lookup"><span data-stu-id="33c56-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="33c56-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="33c56-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="33c56-107">**列**</span><span class="sxs-lookup"><span data-stu-id="33c56-107">**Column**</span></span>|<span data-ttu-id="33c56-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="33c56-108">**Data Type**</span></span>|<span data-ttu-id="33c56-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="33c56-109">**Key/Index**</span></span>|<span data-ttu-id="33c56-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="33c56-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="33c56-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="33c56-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="33c56-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="33c56-112">tinyint</span></span>  <br/> |<span data-ttu-id="33c56-113">Primary</span><span class="sxs-lookup"><span data-stu-id="33c56-113">Primary</span></span>  <br/> |<span data-ttu-id="33c56-114">网络连接类型的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="33c56-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="33c56-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="33c56-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="33c56-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="33c56-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="33c56-117">唯一</span><span class="sxs-lookup"><span data-stu-id="33c56-117">Unique</span></span>  <br/> |<span data-ttu-id="33c56-118">与 NetworkConnectionDetailKey 对应的网络连接类型。</span><span class="sxs-lookup"><span data-stu-id="33c56-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="33c56-119">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="33c56-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="33c56-120">0--有线</span><span class="sxs-lookup"><span data-stu-id="33c56-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="33c56-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="33c56-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="33c56-122">2--以太网</span><span class="sxs-lookup"><span data-stu-id="33c56-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="33c56-123">3--MobileBB</span><span class="sxs-lookup"><span data-stu-id="33c56-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="33c56-124">4--其他</span><span class="sxs-lookup"><span data-stu-id="33c56-124">4 -- Other</span></span>  <br/> <span data-ttu-id="33c56-125">5--隧道</span><span class="sxs-lookup"><span data-stu-id="33c56-125">5 -- Tunnel</span></span>  <br/> |
   

