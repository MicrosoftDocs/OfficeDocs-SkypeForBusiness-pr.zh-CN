---
title: DeviceDriver 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: DeviceDriver 表是支持表。 每个记录表示一个捕获设备使用的驱动程序，或导致设备。
ms.openlocfilehash: d5882ba853bd4909863fc5da415c993d4b59ea4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="devicedriver-table"></a><span data-ttu-id="5b48a-104">DeviceDriver 表</span><span class="sxs-lookup"><span data-stu-id="5b48a-104">DeviceDriver table</span></span>
 
<span data-ttu-id="5b48a-105">DeviceDriver 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="5b48a-105">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="5b48a-106">每个记录表示一个捕获设备使用的驱动程序，或导致设备。</span><span class="sxs-lookup"><span data-stu-id="5b48a-106">Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="5b48a-107">**列**</span><span class="sxs-lookup"><span data-stu-id="5b48a-107">**Column**</span></span>|<span data-ttu-id="5b48a-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5b48a-108">**Data Type**</span></span>|<span data-ttu-id="5b48a-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="5b48a-109">**Key/Index**</span></span>|<span data-ttu-id="5b48a-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="5b48a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5b48a-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="5b48a-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="5b48a-112">int</span><span class="sxs-lookup"><span data-stu-id="5b48a-112">int</span></span>  <br/> |<span data-ttu-id="5b48a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5b48a-113">Primary</span></span>  <br/> |<span data-ttu-id="5b48a-114">标识此设备的驱动程序记录的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="5b48a-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="5b48a-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="5b48a-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="5b48a-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="5b48a-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="5b48a-117">唯一</span><span class="sxs-lookup"><span data-stu-id="5b48a-117">unique</span></span>  <br/> |<span data-ttu-id="5b48a-118">设备驱动程序的名称。</span><span class="sxs-lookup"><span data-stu-id="5b48a-118">Device driver name.</span></span>  <br/> |
   

