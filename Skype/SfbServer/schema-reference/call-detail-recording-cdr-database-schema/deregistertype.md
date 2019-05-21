---
title: Skype for Business Server 2015 中的 DeRegisterType 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType 表是一个静态表, 用于存储可能的用户取消注册类型的列表, 例如 "客户端启动"、"注册过期" 或 "客户端已停止响应"。
ms.openlocfilehash: 794f8f98ffe20cd69b63fd2084fee38ed055d40f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296348"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d5ca4-103">Skype for Business Server 2015 中的 DeRegisterType 表</span><span class="sxs-lookup"><span data-stu-id="d5ca4-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d5ca4-104">DeRegisterType 表是一个静态表, 用于存储可能的用户取消注册类型的列表, 例如 "客户端启动"、"注册过期" 或 "客户端已停止响应"。</span><span class="sxs-lookup"><span data-stu-id="d5ca4-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="d5ca4-105">**列**</span><span class="sxs-lookup"><span data-stu-id="d5ca4-105">**Column**</span></span>|<span data-ttu-id="d5ca4-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d5ca4-106">**Data Type**</span></span>|<span data-ttu-id="d5ca4-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="d5ca4-107">**Key/Index**</span></span>|<span data-ttu-id="d5ca4-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="d5ca4-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d5ca4-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="d5ca4-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="d5ca4-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="d5ca4-110">tinyint</span></span>  <br/> |<span data-ttu-id="d5ca4-111">Primary</span><span class="sxs-lookup"><span data-stu-id="d5ca4-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="d5ca4-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="d5ca4-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="d5ca4-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d5ca4-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="d5ca4-114">允许的值:</span><span class="sxs-lookup"><span data-stu-id="d5ca4-114">Allowed values:</span></span> <br/>  <span data-ttu-id="d5ca4-115">0--未知</span><span class="sxs-lookup"><span data-stu-id="d5ca4-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="d5ca4-116">1--客户发起的取消注册</span><span class="sxs-lookup"><span data-stu-id="d5ca4-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="d5ca4-117">2--注册已过期</span><span class="sxs-lookup"><span data-stu-id="d5ca4-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="d5ca4-118">3-客户端崩溃</span><span class="sxs-lookup"><span data-stu-id="d5ca4-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="d5ca4-119">4--用户属性已更改</span><span class="sxs-lookup"><span data-stu-id="d5ca4-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="d5ca4-120">5-首选注册机构已更改</span><span class="sxs-lookup"><span data-stu-id="d5ca4-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="d5ca4-121">6--处于生存模式的旧客户端</span><span class="sxs-lookup"><span data-stu-id="d5ca4-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

