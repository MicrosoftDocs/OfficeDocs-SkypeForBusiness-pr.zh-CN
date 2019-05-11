---
title: NetworkConnectionDetail 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail 表将网络连接类型映射到其他位置的用户体验质量数据库中使用的网络连接标识符。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: a7095000cc996f2a6430ffcaf8411a2891872938
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919989"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="81250-104">NetworkConnectionDetail 表</span><span class="sxs-lookup"><span data-stu-id="81250-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="81250-105">NetworkConnectionDetail 表将网络连接类型映射到其他位置的用户体验质量数据库中使用的网络连接标识符。</span><span class="sxs-lookup"><span data-stu-id="81250-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="81250-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="81250-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="81250-107">**列**</span><span class="sxs-lookup"><span data-stu-id="81250-107">**Column**</span></span>|<span data-ttu-id="81250-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="81250-108">**Data Type**</span></span>|<span data-ttu-id="81250-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="81250-109">**Key/Index**</span></span>|<span data-ttu-id="81250-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="81250-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="81250-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="81250-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="81250-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="81250-112">tinyint</span></span>  <br/> |<span data-ttu-id="81250-113">Primary</span><span class="sxs-lookup"><span data-stu-id="81250-113">Primary</span></span>  <br/> |<span data-ttu-id="81250-114">网络连接类型的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="81250-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="81250-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="81250-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="81250-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="81250-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="81250-117">唯一</span><span class="sxs-lookup"><span data-stu-id="81250-117">Unique</span></span>  <br/> |<span data-ttu-id="81250-118">对应于 NetworkConnectionDetailKey 的网络连接类型。</span><span class="sxs-lookup"><span data-stu-id="81250-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="81250-119">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="81250-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="81250-120">0-有线</span><span class="sxs-lookup"><span data-stu-id="81250-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="81250-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="81250-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="81250-122">2--以太网</span><span class="sxs-lookup"><span data-stu-id="81250-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="81250-123">3-MobileBB</span><span class="sxs-lookup"><span data-stu-id="81250-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="81250-124">4--其他</span><span class="sxs-lookup"><span data-stu-id="81250-124">4 -- Other</span></span>  <br/> <span data-ttu-id="81250-125">5-隧道</span><span class="sxs-lookup"><span data-stu-id="81250-125">5 -- Tunnel</span></span>  <br/> |
   

