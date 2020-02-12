---
title: 获取最后一个集成数据
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 摘要：了解 "获取上次集成数据" 操作，它是 "呼叫质量" 仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: a4b455a543dd77f0edce223f43d64fe5c03e4bcb
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888791"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="758c7-104">获取最后一个集成数据</span><span class="sxs-lookup"><span data-stu-id="758c7-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="758c7-105">**摘要：** 了解 "获取上次集成数据" 操作，它是 "呼叫质量" 仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="758c7-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="758c7-106">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="758c7-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="758c7-107">"获取上次集成数据" 操作是 "调用质量" 仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="758c7-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="758c7-108">获取最后一个集成数据</span><span class="sxs-lookup"><span data-stu-id="758c7-108">Get Last Integration Data</span></span>

<span data-ttu-id="758c7-109">获取上次集成数据操作返回存档和多维数据集处理的最后5个成功/失败的列表。</span><span class="sxs-lookup"><span data-stu-id="758c7-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="758c7-110">默认情况下，此功能处于禁用状态，需要通过配置数据 API 启用它。</span><span class="sxs-lookup"><span data-stu-id="758c7-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="758c7-111">**种**</span><span class="sxs-lookup"><span data-stu-id="758c7-111">**Method**</span></span>|<span data-ttu-id="758c7-112">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="758c7-112">**Request URI**</span></span>|<span data-ttu-id="758c7-113">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="758c7-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="758c7-114">获取</span><span class="sxs-lookup"><span data-stu-id="758c7-114">GET</span></span>  <br/> |<span data-ttu-id="758c7-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span><span class="sxs-lookup"><span data-stu-id="758c7-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="758c7-116">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="758c7-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="758c7-117">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="758c7-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="758c7-118">**请求标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="758c7-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="758c7-119">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="758c7-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="758c7-120">**响应**-响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="758c7-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="758c7-121">**状态代码**-成功的操作返回状态代码200（OK）。</span><span class="sxs-lookup"><span data-stu-id="758c7-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="758c7-122">**响应标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="758c7-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="758c7-123">**响应正文**-下面是日志状态的示例。</span><span class="sxs-lookup"><span data-stu-id="758c7-123">**Response Body** - Below is a sample log status.</span></span>
  
```json
{
"LastSuccessIntegrations": ["01/18/2015 10:30:13",
"01/18/2015 10:28:29",
"01/17/2015 15:15:17",
"01/17/2015 15:00:17",
"01/17/2015 14:45:13"],
"LastSuccessCubeProcessings": ["01/17/2015 15:16:40",
"01/17/2015 15:01:41",
"01/17/2015 14:47:19",
"01/17/2015 14:31:40",
"01/17/2015 14:17:01"],
"LastFailedIntegrations":  ,
"LastFailedCubeProcessings": ["01/18/2015 10:30:58",
"01/18/2015 10:29:28",
"01/17/2015 10:02:20",
"01/15/2015 20:01:56",
"01/15/2015 19:45:50"],
"LastDataIntegrationStart": null,
"LastCubeProcessingStart": "01/18/2015 10:30:16"
}
```
