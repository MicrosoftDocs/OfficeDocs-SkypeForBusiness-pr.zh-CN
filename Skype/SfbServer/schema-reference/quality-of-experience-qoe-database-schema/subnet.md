---
title: Subnet 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: 子网表是支持表。 每个记录都表示一个网络配置设置中定义的子网。
ms.openlocfilehash: ed54341e66c3370086047eb9b073d2560172a261
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="subnet-table"></a><span data-ttu-id="bf3f4-104">Subnet 表</span><span class="sxs-lookup"><span data-stu-id="bf3f4-104">Subnet table</span></span>
 
<span data-ttu-id="bf3f4-105">子网表是支持表。</span><span class="sxs-lookup"><span data-stu-id="bf3f4-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="bf3f4-106">每个记录都表示一个网络配置设置中定义的子网。</span><span class="sxs-lookup"><span data-stu-id="bf3f4-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="bf3f4-107">**列**</span><span class="sxs-lookup"><span data-stu-id="bf3f4-107">**Column**</span></span>|<span data-ttu-id="bf3f4-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="bf3f4-108">**Data Type**</span></span>|<span data-ttu-id="bf3f4-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="bf3f4-109">**Key/Index**</span></span>|<span data-ttu-id="bf3f4-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="bf3f4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bf3f4-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="bf3f4-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="bf3f4-112">int</span><span class="sxs-lookup"><span data-stu-id="bf3f4-112">int</span></span>  <br/> |<span data-ttu-id="bf3f4-113">主键和外</span><span class="sxs-lookup"><span data-stu-id="bf3f4-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="bf3f4-114">子网 IP 的整数表示形式。</span><span class="sxs-lookup"><span data-stu-id="bf3f4-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="bf3f4-115">**子网掩码**</span><span class="sxs-lookup"><span data-stu-id="bf3f4-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="bf3f4-116">int</span><span class="sxs-lookup"><span data-stu-id="bf3f4-116">int</span></span>  <br/> ||<span data-ttu-id="bf3f4-117">子网掩码。</span><span class="sxs-lookup"><span data-stu-id="bf3f4-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="bf3f4-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="bf3f4-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="bf3f4-119">int</span><span class="sxs-lookup"><span data-stu-id="bf3f4-119">int</span></span>  <br/> |<span data-ttu-id="bf3f4-120">外</span><span class="sxs-lookup"><span data-stu-id="bf3f4-120">Foreign</span></span>  <br/> |<span data-ttu-id="bf3f4-121">从[UserSite 表](usersite.md)引用。</span><span class="sxs-lookup"><span data-stu-id="bf3f4-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="bf3f4-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="bf3f4-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="bf3f4-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="bf3f4-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="bf3f4-124">子网的描述。</span><span class="sxs-lookup"><span data-stu-id="bf3f4-124">The description for the subnet.</span></span>  <br/> |
   

