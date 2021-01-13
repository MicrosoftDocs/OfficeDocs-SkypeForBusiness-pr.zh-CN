---
title: Skype for Business Server 2015 中的 ErrorDef 表
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
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef 表存储有关可能发生的每种类型的错误的信息。 每条记录都是一种类型的错误。
ms.openlocfilehash: 50d7b76e1fc7edb53fbe0b299673b7281a394463
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821722"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="f4d4b-104">Skype for Business Server 2015 中的 ErrorDef 表</span><span class="sxs-lookup"><span data-stu-id="f4d4b-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f4d4b-105">ErrorDef 表存储有关可能发生的每种类型的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="f4d4b-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="f4d4b-106">每条记录都是一种类型的错误。</span><span class="sxs-lookup"><span data-stu-id="f4d4b-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="f4d4b-107">**列**</span><span class="sxs-lookup"><span data-stu-id="f4d4b-107">**Column**</span></span>|<span data-ttu-id="f4d4b-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f4d4b-108">**Data Type**</span></span>|<span data-ttu-id="f4d4b-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="f4d4b-109">**Key/Index**</span></span>|<span data-ttu-id="f4d4b-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="f4d4b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f4d4b-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="f4d4b-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="f4d4b-112">int</span><span class="sxs-lookup"><span data-stu-id="f4d4b-112">int</span></span>  <br/> |<span data-ttu-id="f4d4b-113">主</span><span class="sxs-lookup"><span data-stu-id="f4d4b-113">Primary</span></span>  <br/> |<span data-ttu-id="f4d4b-114">标识此类型错误的唯一 ID 号。</span><span class="sxs-lookup"><span data-stu-id="f4d4b-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="f4d4b-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="f4d4b-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="f4d4b-116">int</span><span class="sxs-lookup"><span data-stu-id="f4d4b-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="f4d4b-117">与此错误关联的标准 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="f4d4b-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="f4d4b-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="f4d4b-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="f4d4b-119">int</span><span class="sxs-lookup"><span data-stu-id="f4d4b-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="f4d4b-120">Microsoft 诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="f4d4b-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="f4d4b-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="f4d4b-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="f4d4b-122">Int</span><span class="sxs-lookup"><span data-stu-id="f4d4b-122">Int</span></span>  <br/> |<span data-ttu-id="f4d4b-123">Foreign</span><span class="sxs-lookup"><span data-stu-id="f4d4b-123">Foreign</span></span>  <br/> |<span data-ttu-id="f4d4b-124">呼叫的类型。</span><span class="sxs-lookup"><span data-stu-id="f4d4b-124">Type of the call.</span></span> <span data-ttu-id="f4d4b-125">有关详细信息， [请参阅 Skype for Business Server 2015](calltype.md) 中的 CallType 表。</span><span class="sxs-lookup"><span data-stu-id="f4d4b-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="f4d4b-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="f4d4b-126">**RequestType**</span></span> <br/> |<span data-ttu-id="f4d4b-127">varbinary (33) </span><span class="sxs-lookup"><span data-stu-id="f4d4b-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="f4d4b-128">失败的请求的类型。</span><span class="sxs-lookup"><span data-stu-id="f4d4b-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="f4d4b-129">可以使用以下语法将此数据转换为文本格式：</span><span class="sxs-lookup"><span data-stu-id="f4d4b-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="f4d4b-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="f4d4b-130">**ContentType**</span></span> <br/> |<span data-ttu-id="f4d4b-131">varbinary (257) </span><span class="sxs-lookup"><span data-stu-id="f4d4b-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="f4d4b-132">失败的请求的内容类型。</span><span class="sxs-lookup"><span data-stu-id="f4d4b-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="f4d4b-133">可以使用以下语法将数据转换为文本格式：</span><span class="sxs-lookup"><span data-stu-id="f4d4b-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

