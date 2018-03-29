---
title: EndpointSubnet 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
description: EndpointSubnet 表是支持表。 每个记录表示终结点从捕获的一个子网。
ms.openlocfilehash: 71df1d94fd8aa74969249090f7f1d4a21939bcd2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="endpointsubnet-table"></a><span data-ttu-id="e779d-104">EndpointSubnet 表</span><span class="sxs-lookup"><span data-stu-id="e779d-104">EndpointSubnet table</span></span>
 
<span data-ttu-id="e779d-105">EndpointSubnet 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="e779d-105">The EndpointSubnet table is a supporting table.</span></span> <span data-ttu-id="e779d-106">每个记录表示终结点从捕获的一个子网。</span><span class="sxs-lookup"><span data-stu-id="e779d-106">Each record represents one subnet captured from endpoints.</span></span> 
  
|<span data-ttu-id="e779d-107">**列**</span><span class="sxs-lookup"><span data-stu-id="e779d-107">**Column**</span></span>|<span data-ttu-id="e779d-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e779d-108">**Data Type**</span></span>|<span data-ttu-id="e779d-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="e779d-109">**Key/Index**</span></span>|<span data-ttu-id="e779d-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="e779d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e779d-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="e779d-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="e779d-112">int</span><span class="sxs-lookup"><span data-stu-id="e779d-112">int</span></span>  <br/> |<span data-ttu-id="e779d-113">主键和外</span><span class="sxs-lookup"><span data-stu-id="e779d-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e779d-114">整数表示的子网。</span><span class="sxs-lookup"><span data-stu-id="e779d-114">Integer representation for the subnet.</span></span>  <br/> |
|<span data-ttu-id="e779d-115">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="e779d-115">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="e779d-116">datetime</span><span class="sxs-lookup"><span data-stu-id="e779d-116">datetime</span></span>  <br/> ||<span data-ttu-id="e779d-117">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="e779d-117">For internal use only.</span></span>  <br/> |
   

