---
title: 在业务服务器 2015年的 Skype 的 DeRegisterType 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType 表则存储可能的用户列表的静态表取消注册类型，例如客户机启动的、 注册过期，或客户端停止响应。
ms.openlocfilehash: 97b342a8d0175da0517aa36e0fea477e32df4dd9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="45f5d-103">在业务服务器 2015年的 Skype 的 DeRegisterType 表</span><span class="sxs-lookup"><span data-stu-id="45f5d-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="45f5d-104">DeRegisterType 表则存储可能的用户列表的静态表取消注册类型，例如客户机启动的、 注册过期，或客户端停止响应。</span><span class="sxs-lookup"><span data-stu-id="45f5d-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="45f5d-105">**列**</span><span class="sxs-lookup"><span data-stu-id="45f5d-105">**Column**</span></span>|<span data-ttu-id="45f5d-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="45f5d-106">**Data Type**</span></span>|<span data-ttu-id="45f5d-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="45f5d-107">**Key/Index**</span></span>|<span data-ttu-id="45f5d-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="45f5d-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="45f5d-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="45f5d-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="45f5d-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="45f5d-110">tinyint</span></span>  <br/> |<span data-ttu-id="45f5d-111">Primary</span><span class="sxs-lookup"><span data-stu-id="45f5d-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="45f5d-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="45f5d-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="45f5d-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="45f5d-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="45f5d-114">允许的值：</span><span class="sxs-lookup"><span data-stu-id="45f5d-114">Allowed values:</span></span> <br/>  <span data-ttu-id="45f5d-115">0--未知</span><span class="sxs-lookup"><span data-stu-id="45f5d-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="45f5d-116">1-客户机启动注销</span><span class="sxs-lookup"><span data-stu-id="45f5d-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="45f5d-117">2-注册过期</span><span class="sxs-lookup"><span data-stu-id="45f5d-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="45f5d-118">3-客户端崩溃</span><span class="sxs-lookup"><span data-stu-id="45f5d-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="45f5d-119">4-用户属性已更改</span><span class="sxs-lookup"><span data-stu-id="45f5d-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="45f5d-120">5-首选注册器更改</span><span class="sxs-lookup"><span data-stu-id="45f5d-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="45f5d-121">在生存模式下 6-旧客户端</span><span class="sxs-lookup"><span data-stu-id="45f5d-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

