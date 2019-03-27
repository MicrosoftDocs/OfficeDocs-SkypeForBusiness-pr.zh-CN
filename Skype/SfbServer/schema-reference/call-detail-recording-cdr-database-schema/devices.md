---
title: Devices 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Devices 表是一个支持表。 每个记录存储设备 （桌面电话） 的信息。
ms.openlocfilehash: f770f19fb94bf25bdb4c13e74dc41e05f6674788
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881700"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="56d26-104">Devices 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="56d26-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="56d26-105">Devices 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="56d26-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="56d26-106">每个记录存储设备 （桌面电话） 的信息。</span><span class="sxs-lookup"><span data-stu-id="56d26-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="56d26-107">**列**</span><span class="sxs-lookup"><span data-stu-id="56d26-107">**Column**</span></span>|<span data-ttu-id="56d26-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="56d26-108">**Data Type**</span></span>|<span data-ttu-id="56d26-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="56d26-109">**Key/Index**</span></span>|<span data-ttu-id="56d26-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="56d26-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="56d26-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="56d26-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="56d26-112">int</span><span class="sxs-lookup"><span data-stu-id="56d26-112">int</span></span>  <br/> |<span data-ttu-id="56d26-113">Primary</span><span class="sxs-lookup"><span data-stu-id="56d26-113">Primary</span></span>  <br/> |<span data-ttu-id="56d26-114">标识此硬件版本的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="56d26-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="56d26-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="56d26-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="56d26-116">int</span><span class="sxs-lookup"><span data-stu-id="56d26-116">int</span></span>  <br/> |<span data-ttu-id="56d26-117">外</span><span class="sxs-lookup"><span data-stu-id="56d26-117">Foreign</span></span>  <br/> |<span data-ttu-id="56d26-118">此设备的制造商。</span><span class="sxs-lookup"><span data-stu-id="56d26-118">Manufacturer of this device.</span></span> <span data-ttu-id="56d26-119">请参阅[Manufacturers 表中的业务服务器 2015 Skype](manufacturers.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="56d26-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="56d26-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="56d26-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="56d26-121">int</span><span class="sxs-lookup"><span data-stu-id="56d26-121">int</span></span>  <br/> |<span data-ttu-id="56d26-122">外</span><span class="sxs-lookup"><span data-stu-id="56d26-122">Foreign</span></span>  <br/> |<span data-ttu-id="56d26-123">此设备硬件版本。</span><span class="sxs-lookup"><span data-stu-id="56d26-123">Hardware version of this device.</span></span> <span data-ttu-id="56d26-124">请参阅[HardwareVersions 表中的业务服务器 2015 Skype](hardwareversions.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="56d26-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="56d26-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="56d26-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="56d26-126">bigint</span><span class="sxs-lookup"><span data-stu-id="56d26-126">bigint</span></span>  <br/> ||<span data-ttu-id="56d26-127">MAC 地址</span><span class="sxs-lookup"><span data-stu-id="56d26-127">MAC Address</span></span>  <br/> |
   

