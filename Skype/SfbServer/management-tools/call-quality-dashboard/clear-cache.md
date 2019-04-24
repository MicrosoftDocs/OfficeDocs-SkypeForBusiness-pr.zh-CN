---
title: 清除缓存
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 摘要： 了解如何清除缓存操作，它是用于呼叫的质量仪表板的数据 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: c2371a7f99eb37e8e01be919bf6c31b0c9a452cb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32195549"
---
# <a name="clear-cache"></a><span data-ttu-id="37393-104">清除缓存</span><span class="sxs-lookup"><span data-stu-id="37393-104">Clear Cache</span></span>
 
<span data-ttu-id="37393-105">**摘要：** 了解清除缓存操作，它是用于呼叫的质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="37393-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="37393-106">呼叫质量仪表板是用于业务服务器 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="37393-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="37393-107">清除缓存操作是用于呼叫的质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="37393-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="37393-108">清除缓存</span><span class="sxs-lookup"><span data-stu-id="37393-108">Clear Cache</span></span>

<span data-ttu-id="37393-109">清除缓存操作删除查询和数据的服务器上的缓存。</span><span class="sxs-lookup"><span data-stu-id="37393-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="37393-110">这将重置缓存，我们将刷新数据从 QoE 多维数据集是用于新的请求。</span><span class="sxs-lookup"><span data-stu-id="37393-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="37393-111">**方法**</span><span class="sxs-lookup"><span data-stu-id="37393-111">**Method**</span></span>|<span data-ttu-id="37393-112">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="37393-112">**Request URI**</span></span>|<span data-ttu-id="37393-113">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="37393-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="37393-114">发布</span><span class="sxs-lookup"><span data-stu-id="37393-114">POST</span></span>  <br/> |<span data-ttu-id="37393-115">https://\<门户\>/QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="37393-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="37393-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="37393-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="37393-117">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="37393-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="37393-118">**请求标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="37393-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="37393-119">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="37393-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="37393-120">**响应**-响应包括 HTTP 状态代码和一响应标头。</span><span class="sxs-lookup"><span data-stu-id="37393-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="37393-121">**状态代码**-成功的操作返回状态代码 200 （确定)。</span><span class="sxs-lookup"><span data-stu-id="37393-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="37393-122">**响应标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="37393-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="37393-123">**响应正文**-无。</span><span class="sxs-lookup"><span data-stu-id="37393-123">**Response Body** - None.</span></span>
  

