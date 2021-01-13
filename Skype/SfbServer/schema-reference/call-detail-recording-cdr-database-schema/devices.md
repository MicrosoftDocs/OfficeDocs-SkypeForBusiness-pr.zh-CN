---
title: Skype for Business Server 2015 中的 Devices 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Devices 表是一个支持表。 每条记录存储有关一个设备（桌面电话）的信息。
ms.openlocfilehash: da0d6ea8143fb8c81225e885fba1f05a90e2fda5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831812"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="204e3-104">Skype for Business Server 2015 中的 Devices 表</span><span class="sxs-lookup"><span data-stu-id="204e3-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="204e3-105">Devices 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="204e3-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="204e3-106">每条记录存储有关一个设备（桌面电话）的信息。</span><span class="sxs-lookup"><span data-stu-id="204e3-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="204e3-107">**列**</span><span class="sxs-lookup"><span data-stu-id="204e3-107">**Column**</span></span>|<span data-ttu-id="204e3-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="204e3-108">**Data Type**</span></span>|<span data-ttu-id="204e3-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="204e3-109">**Key/Index**</span></span>|<span data-ttu-id="204e3-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="204e3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="204e3-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="204e3-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="204e3-112">int</span><span class="sxs-lookup"><span data-stu-id="204e3-112">int</span></span>  <br/> |<span data-ttu-id="204e3-113">主</span><span class="sxs-lookup"><span data-stu-id="204e3-113">Primary</span></span>  <br/> |<span data-ttu-id="204e3-114">用于标识此硬件版本的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="204e3-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="204e3-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="204e3-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="204e3-116">int</span><span class="sxs-lookup"><span data-stu-id="204e3-116">int</span></span>  <br/> |<span data-ttu-id="204e3-117">Foreign</span><span class="sxs-lookup"><span data-stu-id="204e3-117">Foreign</span></span>  <br/> |<span data-ttu-id="204e3-118">此设备的制造商。</span><span class="sxs-lookup"><span data-stu-id="204e3-118">Manufacturer of this device.</span></span> <span data-ttu-id="204e3-119">有关详细信息 [，请参阅 Skype for Business Server 2015 中的](manufacturers.md) 制造商表。</span><span class="sxs-lookup"><span data-stu-id="204e3-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="204e3-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="204e3-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="204e3-121">int</span><span class="sxs-lookup"><span data-stu-id="204e3-121">int</span></span>  <br/> |<span data-ttu-id="204e3-122">Foreign</span><span class="sxs-lookup"><span data-stu-id="204e3-122">Foreign</span></span>  <br/> |<span data-ttu-id="204e3-123">此设备的硬件版本。</span><span class="sxs-lookup"><span data-stu-id="204e3-123">Hardware version of this device.</span></span> <span data-ttu-id="204e3-124">有关详细信息， [请参阅 Skype for Business Server 2015 中的 HardwareVersions](hardwareversions.md) 表。</span><span class="sxs-lookup"><span data-stu-id="204e3-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="204e3-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="204e3-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="204e3-126">bigint</span><span class="sxs-lookup"><span data-stu-id="204e3-126">bigint</span></span>  <br/> ||<span data-ttu-id="204e3-127">MAC 地址</span><span class="sxs-lookup"><span data-stu-id="204e3-127">MAC Address</span></span>  <br/> |
   

