---
title: 清除缓存
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 摘要：了解"清除缓存"操作，这是通话质量仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: c9b966bb1e35a5a6255cd75ea6c685daaf220a09
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806412"
---
# <a name="clear-cache"></a><span data-ttu-id="eda09-104">清除缓存</span><span class="sxs-lookup"><span data-stu-id="eda09-104">Clear Cache</span></span>
 
<span data-ttu-id="eda09-105">**摘要：** 了解"清除缓存"操作，这是通话质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="eda09-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="eda09-106">通话质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="eda09-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="eda09-107">清除缓存操作是通话质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="eda09-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="eda09-108">清除缓存</span><span class="sxs-lookup"><span data-stu-id="eda09-108">Clear Cache</span></span>

<span data-ttu-id="eda09-109">清除缓存操作会删除服务器上用于查询和数据的缓存。</span><span class="sxs-lookup"><span data-stu-id="eda09-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="eda09-110">这将重置缓存，我们将在以后获取新请求的 QoE 多维数据集中的新数据。</span><span class="sxs-lookup"><span data-stu-id="eda09-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="eda09-111">**方法**</span><span class="sxs-lookup"><span data-stu-id="eda09-111">**Method**</span></span>|<span data-ttu-id="eda09-112">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="eda09-112">**Request URI**</span></span>|<span data-ttu-id="eda09-113">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="eda09-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="eda09-114">POST</span><span class="sxs-lookup"><span data-stu-id="eda09-114">POST</span></span>  <br/> |<span data-ttu-id="eda09-115">https:// \<portal\> /QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="eda09-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="eda09-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="eda09-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="eda09-117">**URI 参数** - 无。</span><span class="sxs-lookup"><span data-stu-id="eda09-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="eda09-118">**请求标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="eda09-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="eda09-119">**请求正文** - 无。</span><span class="sxs-lookup"><span data-stu-id="eda09-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="eda09-120">**响应** - 响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="eda09-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="eda09-121">**状态代码** - 成功操作返回状态代码 200 (确定) 。</span><span class="sxs-lookup"><span data-stu-id="eda09-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="eda09-122">**响应标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="eda09-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="eda09-123">**响应正文** - 无。</span><span class="sxs-lookup"><span data-stu-id="eda09-123">**Response Body** - None.</span></span>
  

