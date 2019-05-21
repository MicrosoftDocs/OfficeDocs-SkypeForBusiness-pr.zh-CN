---
title: Device 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Device 表是一个支持表, 用于存储有关各种捕获或呈现设备的信息。 表中的每条记录表示一个设备。
ms.openlocfilehash: a73deac9bec6ce4515eaffc256179b10d1f27106
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295004"
---
# <a name="device-table"></a><span data-ttu-id="b8aa0-104">Device 表</span><span class="sxs-lookup"><span data-stu-id="b8aa0-104">Device table</span></span>
 
<span data-ttu-id="b8aa0-105">Device 表是一个支持表, 用于存储有关各种捕获或呈现设备的信息。</span><span class="sxs-lookup"><span data-stu-id="b8aa0-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="b8aa0-106">表中的每条记录表示一个设备。</span><span class="sxs-lookup"><span data-stu-id="b8aa0-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="b8aa0-107">**列**</span><span class="sxs-lookup"><span data-stu-id="b8aa0-107">**Column**</span></span>|<span data-ttu-id="b8aa0-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b8aa0-108">**Data Type**</span></span>|<span data-ttu-id="b8aa0-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="b8aa0-109">**Key/Index**</span></span>|<span data-ttu-id="b8aa0-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="b8aa0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b8aa0-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="b8aa0-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="b8aa0-112">int</span><span class="sxs-lookup"><span data-stu-id="b8aa0-112">int</span></span>  <br/> |<span data-ttu-id="b8aa0-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b8aa0-113">Primary</span></span>  <br/> |<span data-ttu-id="b8aa0-114">标识此设备的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="b8aa0-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="b8aa0-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="b8aa0-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="b8aa0-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b8aa0-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b8aa0-117">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="b8aa0-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="b8aa0-118">设备名称。</span><span class="sxs-lookup"><span data-stu-id="b8aa0-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="b8aa0-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="b8aa0-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="b8aa0-120">bit</span><span class="sxs-lookup"><span data-stu-id="b8aa0-120">bit</span></span>  <br/> |<span data-ttu-id="b8aa0-121">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="b8aa0-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="b8aa0-122">设备类型。</span><span class="sxs-lookup"><span data-stu-id="b8aa0-122">Device type.</span></span> <span data-ttu-id="b8aa0-123">1是捕获设备, 0 是呈现设备。</span><span class="sxs-lookup"><span data-stu-id="b8aa0-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

