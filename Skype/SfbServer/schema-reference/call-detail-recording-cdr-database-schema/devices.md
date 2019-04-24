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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213163"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a9367-104">Devices 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="a9367-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a9367-105">Devices 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="a9367-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="a9367-106">每个记录存储设备 （桌面电话） 的信息。</span><span class="sxs-lookup"><span data-stu-id="a9367-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="a9367-107">**列**</span><span class="sxs-lookup"><span data-stu-id="a9367-107">**Column**</span></span>|<span data-ttu-id="a9367-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a9367-108">**Data Type**</span></span>|<span data-ttu-id="a9367-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="a9367-109">**Key/Index**</span></span>|<span data-ttu-id="a9367-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="a9367-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a9367-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="a9367-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="a9367-112">int</span><span class="sxs-lookup"><span data-stu-id="a9367-112">int</span></span>  <br/> |<span data-ttu-id="a9367-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a9367-113">Primary</span></span>  <br/> |<span data-ttu-id="a9367-114">标识此硬件版本的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="a9367-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="a9367-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="a9367-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="a9367-116">int</span><span class="sxs-lookup"><span data-stu-id="a9367-116">int</span></span>  <br/> |<span data-ttu-id="a9367-117">外</span><span class="sxs-lookup"><span data-stu-id="a9367-117">Foreign</span></span>  <br/> |<span data-ttu-id="a9367-118">此设备的制造商。</span><span class="sxs-lookup"><span data-stu-id="a9367-118">Manufacturer of this device.</span></span> <span data-ttu-id="a9367-119">请参阅[Manufacturers 表中的业务服务器 2015 Skype](manufacturers.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a9367-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a9367-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="a9367-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="a9367-121">int</span><span class="sxs-lookup"><span data-stu-id="a9367-121">int</span></span>  <br/> |<span data-ttu-id="a9367-122">外</span><span class="sxs-lookup"><span data-stu-id="a9367-122">Foreign</span></span>  <br/> |<span data-ttu-id="a9367-123">此设备硬件版本。</span><span class="sxs-lookup"><span data-stu-id="a9367-123">Hardware version of this device.</span></span> <span data-ttu-id="a9367-124">请参阅[HardwareVersions 表中的业务服务器 2015 Skype](hardwareversions.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a9367-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a9367-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="a9367-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="a9367-126">bigint</span><span class="sxs-lookup"><span data-stu-id="a9367-126">bigint</span></span>  <br/> ||<span data-ttu-id="a9367-127">MAC 地址</span><span class="sxs-lookup"><span data-stu-id="a9367-127">MAC Address</span></span>  <br/> |
   

