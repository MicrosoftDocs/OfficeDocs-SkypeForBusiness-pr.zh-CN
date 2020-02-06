---
title: Subnet 表
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: 子网表是支持表。 每条记录表示网络配置设置中定义的一个子网。
ms.openlocfilehash: 562684fdb4df9ac90216489c209754309885fa98
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805200"
---
# <a name="subnet-table"></a><span data-ttu-id="fb98e-104">Subnet 表</span><span class="sxs-lookup"><span data-stu-id="fb98e-104">Subnet table</span></span>
 
<span data-ttu-id="fb98e-105">子网表是支持表。</span><span class="sxs-lookup"><span data-stu-id="fb98e-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="fb98e-106">每条记录表示网络配置设置中定义的一个子网。</span><span class="sxs-lookup"><span data-stu-id="fb98e-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="fb98e-107">**列**</span><span class="sxs-lookup"><span data-stu-id="fb98e-107">**Column**</span></span>|<span data-ttu-id="fb98e-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="fb98e-108">**Data Type**</span></span>|<span data-ttu-id="fb98e-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="fb98e-109">**Key/Index**</span></span>|<span data-ttu-id="fb98e-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="fb98e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fb98e-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="fb98e-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="fb98e-112">int</span><span class="sxs-lookup"><span data-stu-id="fb98e-112">int</span></span>  <br/> |<span data-ttu-id="fb98e-113">主、外部</span><span class="sxs-lookup"><span data-stu-id="fb98e-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="fb98e-114">子网 IP 的整数表示形式。</span><span class="sxs-lookup"><span data-stu-id="fb98e-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="fb98e-115">**SubnetMask**</span><span class="sxs-lookup"><span data-stu-id="fb98e-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="fb98e-116">int</span><span class="sxs-lookup"><span data-stu-id="fb98e-116">int</span></span>  <br/> ||<span data-ttu-id="fb98e-117">子网掩码。</span><span class="sxs-lookup"><span data-stu-id="fb98e-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="fb98e-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="fb98e-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="fb98e-119">int</span><span class="sxs-lookup"><span data-stu-id="fb98e-119">int</span></span>  <br/> |<span data-ttu-id="fb98e-120">外表</span><span class="sxs-lookup"><span data-stu-id="fb98e-120">Foreign</span></span>  <br/> |<span data-ttu-id="fb98e-121">从[UserSite 表](usersite.md)中引用。</span><span class="sxs-lookup"><span data-stu-id="fb98e-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="fb98e-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="fb98e-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="fb98e-123">nvarchar （512）</span><span class="sxs-lookup"><span data-stu-id="fb98e-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="fb98e-124">子网的说明。</span><span class="sxs-lookup"><span data-stu-id="fb98e-124">The description for the subnet.</span></span>  <br/> |
   

