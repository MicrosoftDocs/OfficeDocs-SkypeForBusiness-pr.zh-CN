---
title: Subnet 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Subnet 表是一个支持表。 每条记录代表一个网络配置设置中定义的子网。
ms.openlocfilehash: aa91202bfb46a96f86ea3a631be3b964a17a6058
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880474"
---
# <a name="subnet-table"></a><span data-ttu-id="062c8-104">Subnet 表</span><span class="sxs-lookup"><span data-stu-id="062c8-104">Subnet table</span></span>
 
<span data-ttu-id="062c8-105">Subnet 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="062c8-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="062c8-106">每条记录代表一个网络配置设置中定义的子网。</span><span class="sxs-lookup"><span data-stu-id="062c8-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="062c8-107">**列**</span><span class="sxs-lookup"><span data-stu-id="062c8-107">**Column**</span></span>|<span data-ttu-id="062c8-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="062c8-108">**Data Type**</span></span>|<span data-ttu-id="062c8-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="062c8-109">**Key/Index**</span></span>|<span data-ttu-id="062c8-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="062c8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="062c8-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="062c8-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="062c8-112">int</span><span class="sxs-lookup"><span data-stu-id="062c8-112">int</span></span>  <br/> |<span data-ttu-id="062c8-113">主、 外</span><span class="sxs-lookup"><span data-stu-id="062c8-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="062c8-114">子网 IP 的整数表示形式。</span><span class="sxs-lookup"><span data-stu-id="062c8-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="062c8-115">**子网掩码**</span><span class="sxs-lookup"><span data-stu-id="062c8-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="062c8-116">int</span><span class="sxs-lookup"><span data-stu-id="062c8-116">int</span></span>  <br/> ||<span data-ttu-id="062c8-117">子网掩码。</span><span class="sxs-lookup"><span data-stu-id="062c8-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="062c8-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="062c8-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="062c8-119">int</span><span class="sxs-lookup"><span data-stu-id="062c8-119">int</span></span>  <br/> |<span data-ttu-id="062c8-120">外</span><span class="sxs-lookup"><span data-stu-id="062c8-120">Foreign</span></span>  <br/> |<span data-ttu-id="062c8-121">引用[自 UserSite table](usersite.md)。</span><span class="sxs-lookup"><span data-stu-id="062c8-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="062c8-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="062c8-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="062c8-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="062c8-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="062c8-124">子网的描述。</span><span class="sxs-lookup"><span data-stu-id="062c8-124">The description for the subnet.</span></span>  <br/> |
   

