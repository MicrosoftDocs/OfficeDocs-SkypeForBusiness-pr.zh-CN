---
title: EndpointSubnet 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
description: EndpointSubnet 表是支持表。 每条记录表示一个从终结点捕获的子网。
ms.openlocfilehash: dcb80256a8a1fb1fb880021e140a0f037142087f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809340"
---
# <a name="endpointsubnet-table"></a><span data-ttu-id="cd785-104">EndpointSubnet 表</span><span class="sxs-lookup"><span data-stu-id="cd785-104">EndpointSubnet table</span></span>
 
<span data-ttu-id="cd785-105">EndpointSubnet 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="cd785-105">The EndpointSubnet table is a supporting table.</span></span> <span data-ttu-id="cd785-106">每条记录表示一个从终结点捕获的子网。</span><span class="sxs-lookup"><span data-stu-id="cd785-106">Each record represents one subnet captured from endpoints.</span></span> 
  
|<span data-ttu-id="cd785-107">**列**</span><span class="sxs-lookup"><span data-stu-id="cd785-107">**Column**</span></span>|<span data-ttu-id="cd785-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="cd785-108">**Data Type**</span></span>|<span data-ttu-id="cd785-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="cd785-109">**Key/Index**</span></span>|<span data-ttu-id="cd785-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="cd785-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cd785-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="cd785-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="cd785-112">int</span><span class="sxs-lookup"><span data-stu-id="cd785-112">int</span></span>  <br/> |<span data-ttu-id="cd785-113">主、外部</span><span class="sxs-lookup"><span data-stu-id="cd785-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="cd785-114">子网的整数表示形式。</span><span class="sxs-lookup"><span data-stu-id="cd785-114">Integer representation for the subnet.</span></span>  <br/> |
|<span data-ttu-id="cd785-115">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="cd785-115">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="cd785-116">datetime</span><span class="sxs-lookup"><span data-stu-id="cd785-116">datetime</span></span>  <br/> ||<span data-ttu-id="cd785-117">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="cd785-117">For internal use only.</span></span>  <br/> |
   

