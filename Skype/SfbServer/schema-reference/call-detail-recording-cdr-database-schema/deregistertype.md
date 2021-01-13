---
title: Skype for Business Server 2015 中的 DeRegisterType 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType 表是一个静态表，用于存储可能的用户注销类型（如"客户端已启动"、"注册已过期"或"客户端停止响应"）的列表。
ms.openlocfilehash: 388aebc1ac180e1298addd54859cff6759b28be0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816072"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9e329-103">Skype for Business Server 2015 中的 DeRegisterType 表</span><span class="sxs-lookup"><span data-stu-id="9e329-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9e329-104">DeRegisterType 表是一个静态表，用于存储可能的用户注销类型（如"客户端已启动"、"注册已过期"或"客户端停止响应"）的列表。</span><span class="sxs-lookup"><span data-stu-id="9e329-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="9e329-105">**列**</span><span class="sxs-lookup"><span data-stu-id="9e329-105">**Column**</span></span>|<span data-ttu-id="9e329-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9e329-106">**Data Type**</span></span>|<span data-ttu-id="9e329-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="9e329-107">**Key/Index**</span></span>|<span data-ttu-id="9e329-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="9e329-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9e329-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="9e329-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="9e329-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="9e329-110">tinyint</span></span>  <br/> |<span data-ttu-id="9e329-111">主</span><span class="sxs-lookup"><span data-stu-id="9e329-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="9e329-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="9e329-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="9e329-113">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="9e329-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="9e329-114">允许的值：</span><span class="sxs-lookup"><span data-stu-id="9e329-114">Allowed values:</span></span> <br/>  <span data-ttu-id="9e329-115">0 -- 未知</span><span class="sxs-lookup"><span data-stu-id="9e329-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="9e329-116">1 -- 客户端启动的取消注册</span><span class="sxs-lookup"><span data-stu-id="9e329-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="9e329-117">2 -- 注册过期</span><span class="sxs-lookup"><span data-stu-id="9e329-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="9e329-118">3 - 客户端崩溃</span><span class="sxs-lookup"><span data-stu-id="9e329-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="9e329-119">4 -- 用户属性已更改</span><span class="sxs-lookup"><span data-stu-id="9e329-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="9e329-120">5 - 首选注册器已更改</span><span class="sxs-lookup"><span data-stu-id="9e329-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="9e329-121">6 -- 旧客户端处于生存模式</span><span class="sxs-lookup"><span data-stu-id="9e329-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

