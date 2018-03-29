---
title: 在 Skype 的业务服务器 2015年设备表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: 设备表是一个支持的表。 每个记录都存储着一个设备 （桌面电话） 的信息。
ms.openlocfilehash: c7a5a5933d4fe2e465faf039a8ac2ed2a65fa563
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="0dc27-104">在 Skype 的业务服务器 2015年设备表</span><span class="sxs-lookup"><span data-stu-id="0dc27-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0dc27-105">设备表是一个支持的表。</span><span class="sxs-lookup"><span data-stu-id="0dc27-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="0dc27-106">每个记录都存储着一个设备 （桌面电话） 的信息。</span><span class="sxs-lookup"><span data-stu-id="0dc27-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="0dc27-107">**列**</span><span class="sxs-lookup"><span data-stu-id="0dc27-107">**Column**</span></span>|<span data-ttu-id="0dc27-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0dc27-108">**Data Type**</span></span>|<span data-ttu-id="0dc27-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="0dc27-109">**Key/Index**</span></span>|<span data-ttu-id="0dc27-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="0dc27-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0dc27-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="0dc27-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="0dc27-112">int</span><span class="sxs-lookup"><span data-stu-id="0dc27-112">int</span></span>  <br/> |<span data-ttu-id="0dc27-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0dc27-113">Primary</span></span>  <br/> |<span data-ttu-id="0dc27-114">标识此硬件版本的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="0dc27-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="0dc27-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="0dc27-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="0dc27-116">int</span><span class="sxs-lookup"><span data-stu-id="0dc27-116">int</span></span>  <br/> |<span data-ttu-id="0dc27-117">外</span><span class="sxs-lookup"><span data-stu-id="0dc27-117">Foreign</span></span>  <br/> |<span data-ttu-id="0dc27-118">此设备的制造商。</span><span class="sxs-lookup"><span data-stu-id="0dc27-118">Manufacturer of this device.</span></span> <span data-ttu-id="0dc27-119">[制造商在 Skype 的业务服务器 2015年的表](manufacturers.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="0dc27-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0dc27-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="0dc27-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="0dc27-121">int</span><span class="sxs-lookup"><span data-stu-id="0dc27-121">int</span></span>  <br/> |<span data-ttu-id="0dc27-122">外</span><span class="sxs-lookup"><span data-stu-id="0dc27-122">Foreign</span></span>  <br/> |<span data-ttu-id="0dc27-123">此设备的硬件版本。</span><span class="sxs-lookup"><span data-stu-id="0dc27-123">Hardware version of this device.</span></span> <span data-ttu-id="0dc27-124">[业务服务器 2015年的 Skype 在 HardwareVersions 表](hardwareversions.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="0dc27-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0dc27-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="0dc27-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="0dc27-126">bigint</span><span class="sxs-lookup"><span data-stu-id="0dc27-126">bigint</span></span>  <br/> ||<span data-ttu-id="0dc27-127">MAC 地址</span><span class="sxs-lookup"><span data-stu-id="0dc27-127">MAC Address</span></span>  <br/> |
   

