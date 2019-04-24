---
title: DeRegisterType 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType 表是用户的一个静态表，用于存储可能列表取消注册类型，如客户端已启动、 注册过期或客户端停止响应。
ms.openlocfilehash: be6fd10388c9f85315554605fd491aafa9d3a0d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213191"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="dc313-103">DeRegisterType 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="dc313-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dc313-104">DeRegisterType 表是用户的一个静态表，用于存储可能列表取消注册类型，如客户端已启动、 注册过期或客户端停止响应。</span><span class="sxs-lookup"><span data-stu-id="dc313-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="dc313-105">**列**</span><span class="sxs-lookup"><span data-stu-id="dc313-105">**Column**</span></span>|<span data-ttu-id="dc313-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="dc313-106">**Data Type**</span></span>|<span data-ttu-id="dc313-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="dc313-107">**Key/Index**</span></span>|<span data-ttu-id="dc313-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="dc313-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dc313-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="dc313-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="dc313-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="dc313-110">tinyint</span></span>  <br/> |<span data-ttu-id="dc313-111">Primary</span><span class="sxs-lookup"><span data-stu-id="dc313-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="dc313-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="dc313-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="dc313-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dc313-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="dc313-114">允许的值：</span><span class="sxs-lookup"><span data-stu-id="dc313-114">Allowed values:</span></span> <br/>  <span data-ttu-id="dc313-115">0-未知</span><span class="sxs-lookup"><span data-stu-id="dc313-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="dc313-116">1--客户端启动注销</span><span class="sxs-lookup"><span data-stu-id="dc313-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="dc313-117">2--注册过期</span><span class="sxs-lookup"><span data-stu-id="dc313-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="dc313-118">3-客户端崩溃</span><span class="sxs-lookup"><span data-stu-id="dc313-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="dc313-119">4--用户属性已更改</span><span class="sxs-lookup"><span data-stu-id="dc313-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="dc313-120">5 – 首选注册器已更改</span><span class="sxs-lookup"><span data-stu-id="dc313-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="dc313-121">6--旧客户端处于生存模式</span><span class="sxs-lookup"><span data-stu-id="dc313-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

