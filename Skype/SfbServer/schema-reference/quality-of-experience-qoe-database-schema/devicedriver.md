---
title: DeviceDriver 表
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
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: DeviceDriver 表是一个支持表。 每条记录都代表捕获设备或呈现设备所使用的一个驱动程序。
ms.openlocfilehash: 1f83bfd014fa5fb49f4d0f900e01aeecfe2b5f46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823072"
---
# <a name="devicedriver-table"></a><span data-ttu-id="d7667-104">DeviceDriver 表</span><span class="sxs-lookup"><span data-stu-id="d7667-104">DeviceDriver table</span></span>
 
<span data-ttu-id="d7667-p102">DeviceDriver 表是一个支持表。每条记录都代表捕获设备或呈现设备所使用的一个驱动程序。</span><span class="sxs-lookup"><span data-stu-id="d7667-p102">The DeviceDriver table is a supporting table. Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="d7667-107">**列**</span><span class="sxs-lookup"><span data-stu-id="d7667-107">**Column**</span></span>|<span data-ttu-id="d7667-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d7667-108">**Data Type**</span></span>|<span data-ttu-id="d7667-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="d7667-109">**Key/Index**</span></span>|<span data-ttu-id="d7667-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="d7667-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d7667-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="d7667-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="d7667-112">int</span><span class="sxs-lookup"><span data-stu-id="d7667-112">int</span></span>  <br/> |<span data-ttu-id="d7667-113">主</span><span class="sxs-lookup"><span data-stu-id="d7667-113">Primary</span></span>  <br/> |<span data-ttu-id="d7667-114">用于标识此设备驱动程序记录的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="d7667-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="d7667-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="d7667-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="d7667-116">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="d7667-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="d7667-117">unique</span><span class="sxs-lookup"><span data-stu-id="d7667-117">unique</span></span>  <br/> |<span data-ttu-id="d7667-118">设备驱动程序的名称。</span><span class="sxs-lookup"><span data-stu-id="d7667-118">Device driver name.</span></span>  <br/> |
   

