---
title: Skype for Business Server 2015 中的 "设备" 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: "\"设备\" 表是支持表。 每条记录存储有关一个设备 (桌面电话) 的信息。"
ms.openlocfilehash: 145637b6385677007efa47cd21b3f0ea7d7f88f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296376"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e3c1f-104">Skype for Business Server 2015 中的 "设备" 表</span><span class="sxs-lookup"><span data-stu-id="e3c1f-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e3c1f-105">"设备" 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="e3c1f-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="e3c1f-106">每条记录存储有关一个设备 (桌面电话) 的信息。</span><span class="sxs-lookup"><span data-stu-id="e3c1f-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="e3c1f-107">**列**</span><span class="sxs-lookup"><span data-stu-id="e3c1f-107">**Column**</span></span>|<span data-ttu-id="e3c1f-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e3c1f-108">**Data Type**</span></span>|<span data-ttu-id="e3c1f-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="e3c1f-109">**Key/Index**</span></span>|<span data-ttu-id="e3c1f-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="e3c1f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e3c1f-111">**Keyroutedeventargs.deviceid**</span><span class="sxs-lookup"><span data-stu-id="e3c1f-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="e3c1f-112">int</span><span class="sxs-lookup"><span data-stu-id="e3c1f-112">int</span></span>  <br/> |<span data-ttu-id="e3c1f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e3c1f-113">Primary</span></span>  <br/> |<span data-ttu-id="e3c1f-114">标识此硬件版本的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="e3c1f-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="e3c1f-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="e3c1f-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="e3c1f-116">int</span><span class="sxs-lookup"><span data-stu-id="e3c1f-116">int</span></span>  <br/> |<span data-ttu-id="e3c1f-117">外表</span><span class="sxs-lookup"><span data-stu-id="e3c1f-117">Foreign</span></span>  <br/> |<span data-ttu-id="e3c1f-118">此设备的制造商。</span><span class="sxs-lookup"><span data-stu-id="e3c1f-118">Manufacturer of this device.</span></span> <span data-ttu-id="e3c1f-119">有关详细信息, 请参阅[Skype For Business Server 2015 中的制造商表](manufacturers.md)。</span><span class="sxs-lookup"><span data-stu-id="e3c1f-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e3c1f-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="e3c1f-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="e3c1f-121">int</span><span class="sxs-lookup"><span data-stu-id="e3c1f-121">int</span></span>  <br/> |<span data-ttu-id="e3c1f-122">外表</span><span class="sxs-lookup"><span data-stu-id="e3c1f-122">Foreign</span></span>  <br/> |<span data-ttu-id="e3c1f-123">此设备的硬件版本。</span><span class="sxs-lookup"><span data-stu-id="e3c1f-123">Hardware version of this device.</span></span> <span data-ttu-id="e3c1f-124">有关详细信息, 请参阅[Skype For Business Server 2015 中的 HardwareVersions 表](hardwareversions.md)。</span><span class="sxs-lookup"><span data-stu-id="e3c1f-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e3c1f-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="e3c1f-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="e3c1f-126">bigint</span><span class="sxs-lookup"><span data-stu-id="e3c1f-126">bigint</span></span>  <br/> ||<span data-ttu-id="e3c1f-127">MAC 地址</span><span class="sxs-lookup"><span data-stu-id="e3c1f-127">MAC Address</span></span>  <br/> |
   

