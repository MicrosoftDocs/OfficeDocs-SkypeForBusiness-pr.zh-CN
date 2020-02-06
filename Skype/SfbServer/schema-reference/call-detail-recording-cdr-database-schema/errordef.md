---
title: Skype for Business Server 2015 中的 ErrorDef 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef 表存储可能出现的每种类型的错误的相关信息。 每条记录是一种类型的错误。
ms.openlocfilehash: f686692bee334c0927b6e8342cfb7152b3e54f0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815230"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="13e8e-104">Skype for Business Server 2015 中的 ErrorDef 表</span><span class="sxs-lookup"><span data-stu-id="13e8e-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="13e8e-105">ErrorDef 表存储可能出现的每种类型的错误的相关信息。</span><span class="sxs-lookup"><span data-stu-id="13e8e-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="13e8e-106">每条记录是一种类型的错误。</span><span class="sxs-lookup"><span data-stu-id="13e8e-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="13e8e-107">**列**</span><span class="sxs-lookup"><span data-stu-id="13e8e-107">**Column**</span></span>|<span data-ttu-id="13e8e-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="13e8e-108">**Data Type**</span></span>|<span data-ttu-id="13e8e-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="13e8e-109">**Key/Index**</span></span>|<span data-ttu-id="13e8e-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="13e8e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="13e8e-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="13e8e-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="13e8e-112">int</span><span class="sxs-lookup"><span data-stu-id="13e8e-112">int</span></span>  <br/> |<span data-ttu-id="13e8e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="13e8e-113">Primary</span></span>  <br/> |<span data-ttu-id="13e8e-114">标识此类型错误的唯一 ID 号。</span><span class="sxs-lookup"><span data-stu-id="13e8e-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="13e8e-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="13e8e-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="13e8e-116">int</span><span class="sxs-lookup"><span data-stu-id="13e8e-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="13e8e-117">与此错误相关联的标准 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="13e8e-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="13e8e-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="13e8e-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="13e8e-119">int</span><span class="sxs-lookup"><span data-stu-id="13e8e-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="13e8e-120">Microsoft 诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="13e8e-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="13e8e-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="13e8e-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="13e8e-122">整形</span><span class="sxs-lookup"><span data-stu-id="13e8e-122">Int</span></span>  <br/> |<span data-ttu-id="13e8e-123">外表</span><span class="sxs-lookup"><span data-stu-id="13e8e-123">Foreign</span></span>  <br/> |<span data-ttu-id="13e8e-124">通话的类型。</span><span class="sxs-lookup"><span data-stu-id="13e8e-124">Type of the call.</span></span> <span data-ttu-id="13e8e-125">有关详细信息，请参阅[Skype For Business Server 2015 中的 CallType 表](calltype.md)。</span><span class="sxs-lookup"><span data-stu-id="13e8e-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="13e8e-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="13e8e-126">**RequestType**</span></span> <br/> |<span data-ttu-id="13e8e-127">varbinary （33）</span><span class="sxs-lookup"><span data-stu-id="13e8e-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="13e8e-128">失败的请求类型。</span><span class="sxs-lookup"><span data-stu-id="13e8e-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="13e8e-129">可以使用以下语法将此数据转换为文本格式：</span><span class="sxs-lookup"><span data-stu-id="13e8e-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="13e8e-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="13e8e-130">**ContentType**</span></span> <br/> |<span data-ttu-id="13e8e-131">varbinary （257）</span><span class="sxs-lookup"><span data-stu-id="13e8e-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="13e8e-132">失败的请求的内容类型。</span><span class="sxs-lookup"><span data-stu-id="13e8e-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="13e8e-133">可使用此 syntaxt 将此数据转换为文本格式：</span><span class="sxs-lookup"><span data-stu-id="13e8e-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

