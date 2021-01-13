---
title: 池表
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
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Pool 表是存储有关各种前端池的信息的支持表。表中的每条记录分别表示一个池。
ms.openlocfilehash: e90b9b2a34a184e1d8cdb23dc3d33b1c41367584
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815812"
---
# <a name="pool-table"></a><span data-ttu-id="29e79-104">池表</span><span class="sxs-lookup"><span data-stu-id="29e79-104">Pool table</span></span>
 
<span data-ttu-id="29e79-p102">Pool 表是存储有关各种前端池的信息的支持表。表中的每条记录分别表示一个池。</span><span class="sxs-lookup"><span data-stu-id="29e79-p102">The Pool table is a supporting table that stores information about the various Front End pools. Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="29e79-107">**列**</span><span class="sxs-lookup"><span data-stu-id="29e79-107">**Column**</span></span>|<span data-ttu-id="29e79-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="29e79-108">**Data Type**</span></span>|<span data-ttu-id="29e79-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="29e79-109">**Key/Index**</span></span>|<span data-ttu-id="29e79-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="29e79-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="29e79-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="29e79-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="29e79-112">int</span><span class="sxs-lookup"><span data-stu-id="29e79-112">int</span></span>  <br/> |<span data-ttu-id="29e79-113">主</span><span class="sxs-lookup"><span data-stu-id="29e79-113">Primary</span></span>  <br/> |<span data-ttu-id="29e79-114">标识此池的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="29e79-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="29e79-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="29e79-115">**PoolName**</span></span> <br/> |<span data-ttu-id="29e79-116">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="29e79-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="29e79-117">独特</span><span class="sxs-lookup"><span data-stu-id="29e79-117">Unique</span></span>  <br/> |<span data-ttu-id="29e79-118">池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="29e79-118">Pool FQDN.</span></span>  <br/> |
   

