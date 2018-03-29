---
title: Device 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: 设备表是一个支持的表来存储有关各种捕获的信息，或呈现设备。 每个表中的记录表示一台设备。
ms.openlocfilehash: 346ea171b9a0c1b7a874b65a68b582c4167c57fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="device-table"></a><span data-ttu-id="c2c49-104">Device 表</span><span class="sxs-lookup"><span data-stu-id="c2c49-104">Device table</span></span>
 
<span data-ttu-id="c2c49-105">设备表是一个支持的表来存储有关各种捕获的信息，或呈现设备。</span><span class="sxs-lookup"><span data-stu-id="c2c49-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="c2c49-106">每个表中的记录表示一台设备。</span><span class="sxs-lookup"><span data-stu-id="c2c49-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="c2c49-107">**列**</span><span class="sxs-lookup"><span data-stu-id="c2c49-107">**Column**</span></span>|<span data-ttu-id="c2c49-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c2c49-108">**Data Type**</span></span>|<span data-ttu-id="c2c49-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="c2c49-109">**Key/Index**</span></span>|<span data-ttu-id="c2c49-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="c2c49-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c2c49-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="c2c49-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="c2c49-112">int</span><span class="sxs-lookup"><span data-stu-id="c2c49-112">int</span></span>  <br/> |<span data-ttu-id="c2c49-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c2c49-113">Primary</span></span>  <br/> |<span data-ttu-id="c2c49-114">标识该设备的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="c2c49-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="c2c49-115">**设备名称**</span><span class="sxs-lookup"><span data-stu-id="c2c49-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="c2c49-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c2c49-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c2c49-117">设备名称 + 数据库是唯一</span><span class="sxs-lookup"><span data-stu-id="c2c49-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="c2c49-118">设备名称。</span><span class="sxs-lookup"><span data-stu-id="c2c49-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="c2c49-119">**数据库**</span><span class="sxs-lookup"><span data-stu-id="c2c49-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="c2c49-120">bit</span><span class="sxs-lookup"><span data-stu-id="c2c49-120">bit</span></span>  <br/> |<span data-ttu-id="c2c49-121">设备名称 + 数据库是唯一</span><span class="sxs-lookup"><span data-stu-id="c2c49-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="c2c49-122">设备类型。</span><span class="sxs-lookup"><span data-stu-id="c2c49-122">Device type.</span></span> <span data-ttu-id="c2c49-123">1 为捕获设备，0 是呈现的设备。</span><span class="sxs-lookup"><span data-stu-id="c2c49-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

