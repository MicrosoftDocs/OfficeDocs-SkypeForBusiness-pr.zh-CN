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
localization_priority: Normal
ms.assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
description: EndpointSubnet 表是支持表。 每条记录表示一个从终结点捕获的子网。
ms.openlocfilehash: b8a8e62178919da72082f99acad7798f3935a5ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294948"
---
# <a name="endpointsubnet-table"></a><span data-ttu-id="3b34e-104">EndpointSubnet 表</span><span class="sxs-lookup"><span data-stu-id="3b34e-104">EndpointSubnet table</span></span>
 
<span data-ttu-id="3b34e-105">EndpointSubnet 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="3b34e-105">The EndpointSubnet table is a supporting table.</span></span> <span data-ttu-id="3b34e-106">每条记录表示一个从终结点捕获的子网。</span><span class="sxs-lookup"><span data-stu-id="3b34e-106">Each record represents one subnet captured from endpoints.</span></span> 
  
|<span data-ttu-id="3b34e-107">**列**</span><span class="sxs-lookup"><span data-stu-id="3b34e-107">**Column**</span></span>|<span data-ttu-id="3b34e-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3b34e-108">**Data Type**</span></span>|<span data-ttu-id="3b34e-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="3b34e-109">**Key/Index**</span></span>|<span data-ttu-id="3b34e-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="3b34e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3b34e-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="3b34e-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="3b34e-112">int</span><span class="sxs-lookup"><span data-stu-id="3b34e-112">int</span></span>  <br/> |<span data-ttu-id="3b34e-113">主、外部</span><span class="sxs-lookup"><span data-stu-id="3b34e-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3b34e-114">子网的整数表示形式。</span><span class="sxs-lookup"><span data-stu-id="3b34e-114">Integer representation for the subnet.</span></span>  <br/> |
|<span data-ttu-id="3b34e-115">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="3b34e-115">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="3b34e-116">datetime</span><span class="sxs-lookup"><span data-stu-id="3b34e-116">datetime</span></span>  <br/> ||<span data-ttu-id="3b34e-117">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="3b34e-117">For internal use only.</span></span>  <br/> |
   

