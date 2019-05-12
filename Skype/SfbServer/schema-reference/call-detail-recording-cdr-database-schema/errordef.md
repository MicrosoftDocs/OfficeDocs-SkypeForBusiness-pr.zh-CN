---
title: ErrorDef 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef 表存储有关每种类型的可能发生的错误的信息。 每条记录是错误的一种类型。
ms.openlocfilehash: f1edd4595cdd360c0da1e3cd76f5ed4b63ddf46d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901164"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="0e42e-104">ErrorDef 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="0e42e-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0e42e-105">ErrorDef 表存储有关每种类型的可能发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="0e42e-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="0e42e-106">每条记录是错误的一种类型。</span><span class="sxs-lookup"><span data-stu-id="0e42e-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="0e42e-107">**列**</span><span class="sxs-lookup"><span data-stu-id="0e42e-107">**Column**</span></span>|<span data-ttu-id="0e42e-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0e42e-108">**Data Type**</span></span>|<span data-ttu-id="0e42e-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="0e42e-109">**Key/Index**</span></span>|<span data-ttu-id="0e42e-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="0e42e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0e42e-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="0e42e-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="0e42e-112">int</span><span class="sxs-lookup"><span data-stu-id="0e42e-112">int</span></span>  <br/> |<span data-ttu-id="0e42e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0e42e-113">Primary</span></span>  <br/> |<span data-ttu-id="0e42e-114">标识此错误类型的唯一 ID 号。</span><span class="sxs-lookup"><span data-stu-id="0e42e-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="0e42e-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="0e42e-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="0e42e-116">int</span><span class="sxs-lookup"><span data-stu-id="0e42e-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="0e42e-117">与此错误关联的标准 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="0e42e-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="0e42e-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="0e42e-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="0e42e-119">int</span><span class="sxs-lookup"><span data-stu-id="0e42e-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="0e42e-120">Microsoft 诊断 id。</span><span class="sxs-lookup"><span data-stu-id="0e42e-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="0e42e-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="0e42e-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="0e42e-122">Int</span><span class="sxs-lookup"><span data-stu-id="0e42e-122">Int</span></span>  <br/> |<span data-ttu-id="0e42e-123">外</span><span class="sxs-lookup"><span data-stu-id="0e42e-123">Foreign</span></span>  <br/> |<span data-ttu-id="0e42e-124">呼叫类型。</span><span class="sxs-lookup"><span data-stu-id="0e42e-124">Type of the call.</span></span> <span data-ttu-id="0e42e-125">请参阅[CallType 表中的业务服务器 2015 Skype](calltype.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0e42e-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0e42e-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="0e42e-126">**RequestType**</span></span> <br/> |<span data-ttu-id="0e42e-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="0e42e-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="0e42e-128">失败的请求的类型。</span><span class="sxs-lookup"><span data-stu-id="0e42e-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="0e42e-129">使用以下语法，可以是此数据转换为文本格式：</span><span class="sxs-lookup"><span data-stu-id="0e42e-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="0e42e-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="0e42e-130">**ContentType**</span></span> <br/> |<span data-ttu-id="0e42e-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="0e42e-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="0e42e-132">失败的请求的内容类型。</span><span class="sxs-lookup"><span data-stu-id="0e42e-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="0e42e-133">通过将此类，可以是此数据转换为文本格式：</span><span class="sxs-lookup"><span data-stu-id="0e42e-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

