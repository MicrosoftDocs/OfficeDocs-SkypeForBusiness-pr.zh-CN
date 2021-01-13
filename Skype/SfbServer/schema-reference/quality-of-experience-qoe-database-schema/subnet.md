---
title: Subnet 表
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Subnet 表是一个支持表。 每条记录均表示网络配置设置中定义的一个子网。
ms.openlocfilehash: b4683c654d5d188d2f5096dd7ec9da124001f68b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831332"
---
# <a name="subnet-table"></a><span data-ttu-id="8b2da-104">Subnet 表</span><span class="sxs-lookup"><span data-stu-id="8b2da-104">Subnet table</span></span>
 
<span data-ttu-id="8b2da-p102">Subnet 表是一个支持表。每条记录均表示网络配置设置中定义的一个子网。</span><span class="sxs-lookup"><span data-stu-id="8b2da-p102">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="8b2da-107">**列**</span><span class="sxs-lookup"><span data-stu-id="8b2da-107">**Column**</span></span>|<span data-ttu-id="8b2da-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8b2da-108">**Data Type**</span></span>|<span data-ttu-id="8b2da-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="8b2da-109">**Key/Index**</span></span>|<span data-ttu-id="8b2da-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="8b2da-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8b2da-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="8b2da-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="8b2da-112">int</span><span class="sxs-lookup"><span data-stu-id="8b2da-112">int</span></span>  <br/> |<span data-ttu-id="8b2da-113">主、外</span><span class="sxs-lookup"><span data-stu-id="8b2da-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="8b2da-114">子网 IP 的整数表示形式。</span><span class="sxs-lookup"><span data-stu-id="8b2da-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="8b2da-115">**SubnetMask**</span><span class="sxs-lookup"><span data-stu-id="8b2da-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="8b2da-116">int</span><span class="sxs-lookup"><span data-stu-id="8b2da-116">int</span></span>  <br/> ||<span data-ttu-id="8b2da-117">子网掩码。</span><span class="sxs-lookup"><span data-stu-id="8b2da-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="8b2da-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="8b2da-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="8b2da-119">int</span><span class="sxs-lookup"><span data-stu-id="8b2da-119">int</span></span>  <br/> |<span data-ttu-id="8b2da-120">Foreign</span><span class="sxs-lookup"><span data-stu-id="8b2da-120">Foreign</span></span>  <br/> |<span data-ttu-id="8b2da-121">引用自 [UserSite 表](usersite.md)。</span><span class="sxs-lookup"><span data-stu-id="8b2da-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="8b2da-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="8b2da-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="8b2da-123">nvarchar (512) </span><span class="sxs-lookup"><span data-stu-id="8b2da-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="8b2da-124">子网的说明。</span><span class="sxs-lookup"><span data-stu-id="8b2da-124">The description for the subnet.</span></span>  <br/> |
   

