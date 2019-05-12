---
title: Device 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: 设备表是一个支持表，用于存储有关各种捕获的信息或呈现设备。 表中的每条记录代表一个设备。
ms.openlocfilehash: 0b3c27708cd8e9d1b02914e6f2cba414e353609c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920024"
---
# <a name="device-table"></a><span data-ttu-id="5b826-104">Device 表</span><span class="sxs-lookup"><span data-stu-id="5b826-104">Device table</span></span>
 
<span data-ttu-id="5b826-105">设备表是一个支持表，用于存储有关各种捕获的信息或呈现设备。</span><span class="sxs-lookup"><span data-stu-id="5b826-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="5b826-106">表中的每条记录代表一个设备。</span><span class="sxs-lookup"><span data-stu-id="5b826-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="5b826-107">**列**</span><span class="sxs-lookup"><span data-stu-id="5b826-107">**Column**</span></span>|<span data-ttu-id="5b826-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5b826-108">**Data Type**</span></span>|<span data-ttu-id="5b826-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="5b826-109">**Key/Index**</span></span>|<span data-ttu-id="5b826-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="5b826-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5b826-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="5b826-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="5b826-112">int</span><span class="sxs-lookup"><span data-stu-id="5b826-112">int</span></span>  <br/> |<span data-ttu-id="5b826-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5b826-113">Primary</span></span>  <br/> |<span data-ttu-id="5b826-114">标识此设备的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="5b826-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="5b826-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="5b826-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="5b826-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5b826-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="5b826-117">DeviceName + DeviceType 是唯一</span><span class="sxs-lookup"><span data-stu-id="5b826-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="5b826-118">设备名称。</span><span class="sxs-lookup"><span data-stu-id="5b826-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="5b826-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="5b826-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="5b826-120">bit</span><span class="sxs-lookup"><span data-stu-id="5b826-120">bit</span></span>  <br/> |<span data-ttu-id="5b826-121">DeviceName + DeviceType 是唯一</span><span class="sxs-lookup"><span data-stu-id="5b826-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="5b826-122">设备类型。</span><span class="sxs-lookup"><span data-stu-id="5b826-122">Device type.</span></span> <span data-ttu-id="5b826-123">1 是捕获设备，0 为呈现设备。</span><span class="sxs-lookup"><span data-stu-id="5b826-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

