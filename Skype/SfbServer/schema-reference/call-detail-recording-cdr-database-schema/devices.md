---
title: Devices 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Devices 表是一个支持表。 每个记录存储设备 （桌面电话） 的信息。
ms.openlocfilehash: efd0894a36e02948a3a8cd9f3465dcdbd30f3e2d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901092"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="b5ea3-104">Devices 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="b5ea3-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b5ea3-105">Devices 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="b5ea3-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="b5ea3-106">每个记录存储设备 （桌面电话） 的信息。</span><span class="sxs-lookup"><span data-stu-id="b5ea3-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="b5ea3-107">**列**</span><span class="sxs-lookup"><span data-stu-id="b5ea3-107">**Column**</span></span>|<span data-ttu-id="b5ea3-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b5ea3-108">**Data Type**</span></span>|<span data-ttu-id="b5ea3-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="b5ea3-109">**Key/Index**</span></span>|<span data-ttu-id="b5ea3-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="b5ea3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b5ea3-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="b5ea3-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="b5ea3-112">int</span><span class="sxs-lookup"><span data-stu-id="b5ea3-112">int</span></span>  <br/> |<span data-ttu-id="b5ea3-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b5ea3-113">Primary</span></span>  <br/> |<span data-ttu-id="b5ea3-114">标识此硬件版本的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="b5ea3-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="b5ea3-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="b5ea3-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="b5ea3-116">int</span><span class="sxs-lookup"><span data-stu-id="b5ea3-116">int</span></span>  <br/> |<span data-ttu-id="b5ea3-117">外</span><span class="sxs-lookup"><span data-stu-id="b5ea3-117">Foreign</span></span>  <br/> |<span data-ttu-id="b5ea3-118">此设备的制造商。</span><span class="sxs-lookup"><span data-stu-id="b5ea3-118">Manufacturer of this device.</span></span> <span data-ttu-id="b5ea3-119">请参阅[Manufacturers 表中的业务服务器 2015 Skype](manufacturers.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b5ea3-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b5ea3-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="b5ea3-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="b5ea3-121">int</span><span class="sxs-lookup"><span data-stu-id="b5ea3-121">int</span></span>  <br/> |<span data-ttu-id="b5ea3-122">外</span><span class="sxs-lookup"><span data-stu-id="b5ea3-122">Foreign</span></span>  <br/> |<span data-ttu-id="b5ea3-123">此设备硬件版本。</span><span class="sxs-lookup"><span data-stu-id="b5ea3-123">Hardware version of this device.</span></span> <span data-ttu-id="b5ea3-124">请参阅[HardwareVersions 表中的业务服务器 2015 Skype](hardwareversions.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b5ea3-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b5ea3-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="b5ea3-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="b5ea3-126">bigint</span><span class="sxs-lookup"><span data-stu-id="b5ea3-126">bigint</span></span>  <br/> ||<span data-ttu-id="b5ea3-127">MAC 地址</span><span class="sxs-lookup"><span data-stu-id="b5ea3-127">MAC Address</span></span>  <br/> |
   

