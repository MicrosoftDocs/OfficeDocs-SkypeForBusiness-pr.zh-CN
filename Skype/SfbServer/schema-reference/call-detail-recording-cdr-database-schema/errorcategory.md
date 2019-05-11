---
title: ErrorCategory 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory 表包含每个 Skype 的业务服务器 2015年诊断分类的友好名称。 默认情况下，业务服务器 2015年的 Skype 使用以下分类：
ms.openlocfilehash: b6226396302353b815138b41b7c19f170a0d6b4d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901085"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="890ca-104">ErrorCategory 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="890ca-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="890ca-105">ErrorCategory 表包含每个 Skype 的业务服务器 2015年诊断分类的友好名称。</span><span class="sxs-lookup"><span data-stu-id="890ca-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="890ca-106">默认情况下，业务服务器 2015年的 Skype 使用以下分类：</span><span class="sxs-lookup"><span data-stu-id="890ca-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="890ca-107">0-成功</span><span class="sxs-lookup"><span data-stu-id="890ca-107">0 -- Success</span></span>
    
- <span data-ttu-id="890ca-108">1--预期失败</span><span class="sxs-lookup"><span data-stu-id="890ca-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="890ca-109">2-意外失败</span><span class="sxs-lookup"><span data-stu-id="890ca-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="890ca-110">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="890ca-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="890ca-111">**列**</span><span class="sxs-lookup"><span data-stu-id="890ca-111">**Column**</span></span>|<span data-ttu-id="890ca-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="890ca-112">**Data Type**</span></span>|<span data-ttu-id="890ca-113">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="890ca-113">**Key/Index**</span></span>|<span data-ttu-id="890ca-114">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="890ca-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="890ca-115">**CategoryId**</span><span class="sxs-lookup"><span data-stu-id="890ca-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="890ca-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="890ca-116">tinyint</span></span>  <br/> |<span data-ttu-id="890ca-117">Primary</span><span class="sxs-lookup"><span data-stu-id="890ca-117">Primary</span></span>  <br/> |<span data-ttu-id="890ca-118">分类的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="890ca-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="890ca-119">**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。</span><span class="sxs-lookup"><span data-stu-id="890ca-119">**Name**</span></span> <br/> |<span data-ttu-id="890ca-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="890ca-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="890ca-121">值和分配给分类的友好名称。</span><span class="sxs-lookup"><span data-stu-id="890ca-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="890ca-122">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="890ca-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="890ca-123">0-成功</span><span class="sxs-lookup"><span data-stu-id="890ca-123">0 -- Success</span></span> <br/>  <span data-ttu-id="890ca-124">1--预期失败</span><span class="sxs-lookup"><span data-stu-id="890ca-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="890ca-125">2-意外失败</span><span class="sxs-lookup"><span data-stu-id="890ca-125">2 - Unexpected failure</span></span> <br/> |
   

