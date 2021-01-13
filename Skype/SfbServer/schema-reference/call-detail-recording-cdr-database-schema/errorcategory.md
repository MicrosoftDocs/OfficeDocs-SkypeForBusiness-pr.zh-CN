---
title: Skype for Business Server 2015 中的 ErrorCategory 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory 表包含每个 Skype for Business Server 2015 诊断分类的友好名称。 默认情况下，Skype for Business Server 2015 使用下列分类：
ms.openlocfilehash: ca3719f6d284cf715be1a87b1c7a5dc04ae84b04
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813142"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="aec29-104">Skype for Business Server 2015 中的 ErrorCategory 表</span><span class="sxs-lookup"><span data-stu-id="aec29-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="aec29-105">ErrorCategory 表包含每个 Skype for Business Server 2015 诊断分类的友好名称。</span><span class="sxs-lookup"><span data-stu-id="aec29-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="aec29-106">默认情况下，Skype for Business Server 2015 使用下列分类：</span><span class="sxs-lookup"><span data-stu-id="aec29-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="aec29-107">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="aec29-107">0 -- Success</span></span>
    
- <span data-ttu-id="aec29-108">1 -- 预期失败</span><span class="sxs-lookup"><span data-stu-id="aec29-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="aec29-109">2 - 意外失败</span><span class="sxs-lookup"><span data-stu-id="aec29-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="aec29-110">此表在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="aec29-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="aec29-111">**列**</span><span class="sxs-lookup"><span data-stu-id="aec29-111">**Column**</span></span>|<span data-ttu-id="aec29-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="aec29-112">**Data Type**</span></span>|<span data-ttu-id="aec29-113">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="aec29-113">**Key/Index**</span></span>|<span data-ttu-id="aec29-114">**Details**</span><span class="sxs-lookup"><span data-stu-id="aec29-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="aec29-115">**CategoryId**</span><span class="sxs-lookup"><span data-stu-id="aec29-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="aec29-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="aec29-116">tinyint</span></span>  <br/> |<span data-ttu-id="aec29-117">主</span><span class="sxs-lookup"><span data-stu-id="aec29-117">Primary</span></span>  <br/> |<span data-ttu-id="aec29-118">分类的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="aec29-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="aec29-119">**名称**</span><span class="sxs-lookup"><span data-stu-id="aec29-119">**Name**</span></span> <br/> |<span data-ttu-id="aec29-120">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="aec29-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="aec29-p103">分配给分类的值和友好名称。允许的值有：</span><span class="sxs-lookup"><span data-stu-id="aec29-p103">Value and friendly name assigned to the classification. Allowed values are:</span></span> <br/>  <span data-ttu-id="aec29-123">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="aec29-123">0 -- Success</span></span> <br/>  <span data-ttu-id="aec29-124">1 -- 预期失败</span><span class="sxs-lookup"><span data-stu-id="aec29-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="aec29-125">2 - 意外失败</span><span class="sxs-lookup"><span data-stu-id="aec29-125">2 - Unexpected failure</span></span> <br/> |
   

