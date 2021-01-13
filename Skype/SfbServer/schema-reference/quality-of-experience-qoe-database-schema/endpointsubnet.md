---
title: EndpointSubnet 表
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
ms.assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
description: EndpointSubnet 表是一个支持表。 每个记录代表从终结点捕获的一个子网。
ms.openlocfilehash: 9671c7dc269b7f13f0679c6da12b46ea7d7c8b5f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815822"
---
# <a name="endpointsubnet-table"></a><span data-ttu-id="32363-104">EndpointSubnet 表</span><span class="sxs-lookup"><span data-stu-id="32363-104">EndpointSubnet table</span></span>
 
<span data-ttu-id="32363-p102">EndpointSubnet 表是一个支持表。每个记录代表从终结点捕获的一个子网。</span><span class="sxs-lookup"><span data-stu-id="32363-p102">The EndpointSubnet table is a supporting table. Each record represents one subnet captured from endpoints.</span></span> 
  
|<span data-ttu-id="32363-107">**列**</span><span class="sxs-lookup"><span data-stu-id="32363-107">**Column**</span></span>|<span data-ttu-id="32363-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="32363-108">**Data Type**</span></span>|<span data-ttu-id="32363-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="32363-109">**Key/Index**</span></span>|<span data-ttu-id="32363-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="32363-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="32363-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="32363-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="32363-112">int</span><span class="sxs-lookup"><span data-stu-id="32363-112">int</span></span>  <br/> |<span data-ttu-id="32363-113">主、外</span><span class="sxs-lookup"><span data-stu-id="32363-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="32363-114">子网的整数表示形式。</span><span class="sxs-lookup"><span data-stu-id="32363-114">Integer representation for the subnet.</span></span>  <br/> |
|<span data-ttu-id="32363-115">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="32363-115">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="32363-116">datetime</span><span class="sxs-lookup"><span data-stu-id="32363-116">datetime</span></span>  <br/> ||<span data-ttu-id="32363-117">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="32363-117">For internal use only.</span></span>  <br/> |
   

