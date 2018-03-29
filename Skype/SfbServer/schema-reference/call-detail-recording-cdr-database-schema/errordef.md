---
title: 在业务服务器 2015年的 Skype 的 ErrorDef 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef 表用来存储有关每种可能发生的错误的信息。 每个记录是错误的一种类型。
ms.openlocfilehash: 4583e1130d257a99d075f2dec0dea80ee6b1390c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="7f6d8-104">在业务服务器 2015年的 Skype 的 ErrorDef 表</span><span class="sxs-lookup"><span data-stu-id="7f6d8-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7f6d8-105">ErrorDef 表用来存储有关每种可能发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="7f6d8-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="7f6d8-106">每个记录是错误的一种类型。</span><span class="sxs-lookup"><span data-stu-id="7f6d8-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="7f6d8-107">**列**</span><span class="sxs-lookup"><span data-stu-id="7f6d8-107">**Column**</span></span>|<span data-ttu-id="7f6d8-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7f6d8-108">**Data Type**</span></span>|<span data-ttu-id="7f6d8-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="7f6d8-109">**Key/Index**</span></span>|<span data-ttu-id="7f6d8-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="7f6d8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7f6d8-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="7f6d8-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="7f6d8-112">int</span><span class="sxs-lookup"><span data-stu-id="7f6d8-112">int</span></span>  <br/> |<span data-ttu-id="7f6d8-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7f6d8-113">Primary</span></span>  <br/> |<span data-ttu-id="7f6d8-114">唯一 ID 号标识这种类型的错误。</span><span class="sxs-lookup"><span data-stu-id="7f6d8-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="7f6d8-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="7f6d8-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="7f6d8-116">int</span><span class="sxs-lookup"><span data-stu-id="7f6d8-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="7f6d8-117">与此错误关联的标准 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="7f6d8-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="7f6d8-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="7f6d8-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="7f6d8-119">int</span><span class="sxs-lookup"><span data-stu-id="7f6d8-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="7f6d8-120">Microsoft 诊断程序 id。</span><span class="sxs-lookup"><span data-stu-id="7f6d8-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="7f6d8-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="7f6d8-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="7f6d8-122">Int</span><span class="sxs-lookup"><span data-stu-id="7f6d8-122">Int</span></span>  <br/> |<span data-ttu-id="7f6d8-123">外</span><span class="sxs-lookup"><span data-stu-id="7f6d8-123">Foreign</span></span>  <br/> |<span data-ttu-id="7f6d8-124">调用的类型。</span><span class="sxs-lookup"><span data-stu-id="7f6d8-124">Type of the call.</span></span> <span data-ttu-id="7f6d8-125">[业务服务器 2015年的 Skype 在 CallType 表](calltype.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="7f6d8-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="7f6d8-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="7f6d8-126">**RequestType**</span></span> <br/> |<span data-ttu-id="7f6d8-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="7f6d8-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="7f6d8-128">失败的请求的类型。</span><span class="sxs-lookup"><span data-stu-id="7f6d8-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="7f6d8-129">此数据可以转换为文本格式，使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="7f6d8-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="7f6d8-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="7f6d8-130">**ContentType**</span></span> <br/> |<span data-ttu-id="7f6d8-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="7f6d8-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="7f6d8-132">失败的请求的内容类型。</span><span class="sxs-lookup"><span data-stu-id="7f6d8-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="7f6d8-133">通过使用此 syntaxt，此数据可以转换为文本格式：</span><span class="sxs-lookup"><span data-stu-id="7f6d8-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

