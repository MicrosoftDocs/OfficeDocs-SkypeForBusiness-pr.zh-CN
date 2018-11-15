---
title: 获取上次集成数据
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 摘要： 了解如何获取最后一个集成数据操作，它是用于呼叫的质量仪表板的数据 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: b2e759766987b6ee52795845ee55546920181807
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531785"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="0ed49-104">获取上次集成数据</span><span class="sxs-lookup"><span data-stu-id="0ed49-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="0ed49-105">**摘要：** 了解有关获取最后一个集成数据操作，它是用于呼叫的质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="0ed49-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="0ed49-106">呼叫质量仪表板是用于业务服务器 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="0ed49-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="0ed49-107">获取上次集成数据操作是用于呼叫的质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="0ed49-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="0ed49-108">获取上次集成数据</span><span class="sxs-lookup"><span data-stu-id="0ed49-108">Get Last Integration Data</span></span>

<span data-ttu-id="0ed49-109">获取上次集成数据操作返回上次 5 成功/的存档和多维数据集处理失败的列表。</span><span class="sxs-lookup"><span data-stu-id="0ed49-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="0ed49-110">默认情况下禁用此功能，并且它需要启用通过配置数据 API。</span><span class="sxs-lookup"><span data-stu-id="0ed49-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="0ed49-111">**方法**</span><span class="sxs-lookup"><span data-stu-id="0ed49-111">**Method**</span></span>|<span data-ttu-id="0ed49-112">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="0ed49-112">**Request URI**</span></span>|<span data-ttu-id="0ed49-113">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="0ed49-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0ed49-114">获取</span><span class="sxs-lookup"><span data-stu-id="0ed49-114">GET</span></span>  <br/> |<span data-ttu-id="0ed49-115">https://\<门户\>/QoEDataService/IntegrationLog/Status</span><span class="sxs-lookup"><span data-stu-id="0ed49-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="0ed49-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="0ed49-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="0ed49-117">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="0ed49-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="0ed49-118">**请求标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="0ed49-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0ed49-119">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="0ed49-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="0ed49-120">**响应**-响应包括 HTTP 状态代码和一响应标头。</span><span class="sxs-lookup"><span data-stu-id="0ed49-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="0ed49-121">**状态代码**-成功的操作返回状态代码 200 （确定)。</span><span class="sxs-lookup"><span data-stu-id="0ed49-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="0ed49-122">**响应标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="0ed49-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0ed49-123">**响应正文**-下面是示例日志状态。</span><span class="sxs-lookup"><span data-stu-id="0ed49-123">**Response Body** - Below is a sample log status.</span></span>
  
```
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