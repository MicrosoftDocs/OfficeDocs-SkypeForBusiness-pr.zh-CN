---
title: 设备表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Device 表是一个支持表，用于存储有关各种捕获或呈现设备的信息。该表中的每个记录都代表一台设备。
ms.openlocfilehash: 818458e41c71398f3df11ac9a47eeee0841c6dca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814742"
---
# <a name="device-table"></a><span data-ttu-id="7b605-104">设备表</span><span class="sxs-lookup"><span data-stu-id="7b605-104">Device table</span></span>
 
<span data-ttu-id="7b605-p102">Device 表是一个支持表，用于存储有关各种捕获或呈现设备的信息。该表中的每个记录都代表一台设备。</span><span class="sxs-lookup"><span data-stu-id="7b605-p102">The Device table is a supporting table that stores information about the various capture or render devices. Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="7b605-107">**列**</span><span class="sxs-lookup"><span data-stu-id="7b605-107">**Column**</span></span>|<span data-ttu-id="7b605-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7b605-108">**Data Type**</span></span>|<span data-ttu-id="7b605-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="7b605-109">**Key/Index**</span></span>|<span data-ttu-id="7b605-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="7b605-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7b605-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="7b605-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="7b605-112">int</span><span class="sxs-lookup"><span data-stu-id="7b605-112">int</span></span>  <br/> |<span data-ttu-id="7b605-113">主</span><span class="sxs-lookup"><span data-stu-id="7b605-113">Primary</span></span>  <br/> |<span data-ttu-id="7b605-114">标识此设备的唯一数字。</span><span class="sxs-lookup"><span data-stu-id="7b605-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="7b605-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="7b605-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="7b605-116">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="7b605-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="7b605-117">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="7b605-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="7b605-118">设备名称。</span><span class="sxs-lookup"><span data-stu-id="7b605-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="7b605-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="7b605-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="7b605-120">bit</span><span class="sxs-lookup"><span data-stu-id="7b605-120">bit</span></span>  <br/> |<span data-ttu-id="7b605-121">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="7b605-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="7b605-p103">设备类型。1 是捕获设备。0 是呈现设备。</span><span class="sxs-lookup"><span data-stu-id="7b605-p103">Device type. 1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

