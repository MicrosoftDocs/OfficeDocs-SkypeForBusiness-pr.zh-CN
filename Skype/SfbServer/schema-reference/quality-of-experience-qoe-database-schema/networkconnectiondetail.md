---
title: NetworkConnectionDetail 表
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
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail 表可将网络连接类型映射到在体验质量数据库中的其他位置使用的网络连接标识符。 此表在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 2e03e7935370e71a8070ed1882f61ac5480f312e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806302"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="4edac-104">NetworkConnectionDetail 表</span><span class="sxs-lookup"><span data-stu-id="4edac-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="4edac-105">NetworkConnectionDetail 表可将网络连接类型映射到在体验质量数据库中的其他位置使用的网络连接标识符。</span><span class="sxs-lookup"><span data-stu-id="4edac-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="4edac-106">此表在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="4edac-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="4edac-107">**列**</span><span class="sxs-lookup"><span data-stu-id="4edac-107">**Column**</span></span>|<span data-ttu-id="4edac-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4edac-108">**Data Type**</span></span>|<span data-ttu-id="4edac-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="4edac-109">**Key/Index**</span></span>|<span data-ttu-id="4edac-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="4edac-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4edac-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="4edac-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="4edac-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="4edac-112">tinyint</span></span>  <br/> |<span data-ttu-id="4edac-113">主</span><span class="sxs-lookup"><span data-stu-id="4edac-113">Primary</span></span>  <br/> |<span data-ttu-id="4edac-114">网络连接类型的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="4edac-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="4edac-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="4edac-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="4edac-116">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="4edac-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="4edac-117">独特</span><span class="sxs-lookup"><span data-stu-id="4edac-117">Unique</span></span>  <br/> |<span data-ttu-id="4edac-p103">对应于 NetworkConnectionDetailKey 的网络连接类型。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="4edac-p103">Network connection type that corresponds to the NetworkConnectionDetailKey. Allowed values are:</span></span>  <br/> <span data-ttu-id="4edac-120">0 -- 有线</span><span class="sxs-lookup"><span data-stu-id="4edac-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="4edac-121">1 -- WiFi</span><span class="sxs-lookup"><span data-stu-id="4edac-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="4edac-122">2 -- 以太网</span><span class="sxs-lookup"><span data-stu-id="4edac-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="4edac-123">3 -- MobileBB</span><span class="sxs-lookup"><span data-stu-id="4edac-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="4edac-124">4 -- 其他</span><span class="sxs-lookup"><span data-stu-id="4edac-124">4 -- Other</span></span>  <br/> <span data-ttu-id="4edac-125">5 -- 隧道</span><span class="sxs-lookup"><span data-stu-id="4edac-125">5 -- Tunnel</span></span>  <br/> |
   

