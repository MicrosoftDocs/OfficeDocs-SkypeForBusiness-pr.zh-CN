---
title: 清除缓存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: '摘要: 了解 "清除缓存" 操作, 该操作是 "调用质量" 仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。'
ms.openlocfilehash: 38648e1a910f93a30bd6da8807321acad0330e62
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274833"
---
# <a name="clear-cache"></a><span data-ttu-id="0c832-104">清除缓存</span><span class="sxs-lookup"><span data-stu-id="0c832-104">Clear Cache</span></span>
 
<span data-ttu-id="0c832-105">**摘要:** 了解 "清除缓存" 操作, 该操作是 "调用质量" 仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="0c832-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="0c832-106">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="0c832-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="0c832-107">"清除缓存" 操作是 "调用质量" 仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="0c832-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="0c832-108">清除缓存</span><span class="sxs-lookup"><span data-stu-id="0c832-108">Clear Cache</span></span>

<span data-ttu-id="0c832-109">清除缓存操作在服务器上删除查询和数据的缓存。</span><span class="sxs-lookup"><span data-stu-id="0c832-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="0c832-110">这将重置缓存, 随后将从 QoE 多维数据集中获取新请求的新数据。</span><span class="sxs-lookup"><span data-stu-id="0c832-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="0c832-111">**种**</span><span class="sxs-lookup"><span data-stu-id="0c832-111">**Method**</span></span>|<span data-ttu-id="0c832-112">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="0c832-112">**Request URI**</span></span>|<span data-ttu-id="0c832-113">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="0c832-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0c832-114">发布</span><span class="sxs-lookup"><span data-stu-id="0c832-114">POST</span></span>  <br/> |<span data-ttu-id="0c832-115">https://\<portal\>/QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="0c832-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="0c832-116">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="0c832-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="0c832-117">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="0c832-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="0c832-118">**请求标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="0c832-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0c832-119">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="0c832-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="0c832-120">**响应**-响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="0c832-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="0c832-121">**状态代码**-成功的操作返回状态代码 200 (OK)。</span><span class="sxs-lookup"><span data-stu-id="0c832-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="0c832-122">**响应标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="0c832-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0c832-123">**响应正文**-无。</span><span class="sxs-lookup"><span data-stu-id="0c832-123">**Response Body** - None.</span></span>
  

