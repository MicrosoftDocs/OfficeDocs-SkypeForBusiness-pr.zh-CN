---
title: 维度成员
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 摘要： 了解如何获取维度成员操作。 获取维度成员操作是呼叫质量仪表板的数据 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 6da1b8f6d93dc197df320f1fb5875a6269a9b45a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-dimension-members"></a><span data-ttu-id="efeee-105">维度成员</span><span class="sxs-lookup"><span data-stu-id="efeee-105">Get Dimension Members</span></span>
 
<span data-ttu-id="efeee-106">**摘要：**了解有关获取维度成员操作。</span><span class="sxs-lookup"><span data-stu-id="efeee-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="efeee-107">获取维度成员操作是呼叫质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="efeee-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="efeee-108">通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="efeee-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="efeee-109">获取维度成员操作是呼叫质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="efeee-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="efeee-110">维度成员</span><span class="sxs-lookup"><span data-stu-id="efeee-110">Get Dimension Members</span></span>

<span data-ttu-id="efeee-111">获取维度成员操作返回的特定维度中的成员的列表。</span><span class="sxs-lookup"><span data-stu-id="efeee-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="efeee-112">它还提供筛选成员名单和获取子集，以减少网络传输成本的能力。</span><span class="sxs-lookup"><span data-stu-id="efeee-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="efeee-113">**方法**</span><span class="sxs-lookup"><span data-stu-id="efeee-113">**Method**</span></span>|<span data-ttu-id="efeee-114">**请求的 URI**</span><span class="sxs-lookup"><span data-stu-id="efeee-114">**Request URI**</span></span>|<span data-ttu-id="efeee-115">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="efeee-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="efeee-116">发布</span><span class="sxs-lookup"><span data-stu-id="efeee-116">POST</span></span>  <br/> |<span data-ttu-id="efeee-117">https://\<门户网站\>/QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="efeee-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="efeee-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="efeee-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="efeee-119">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="efeee-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="efeee-120">**请求标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="efeee-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="efeee-121">**请求正文**-它包含了我们想要的成员的维度的名称。</span><span class="sxs-lookup"><span data-stu-id="efeee-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="efeee-122">此外返回成员的最大数目，旁边还可以指定某些筛选，用于限制返回的成员。</span><span class="sxs-lookup"><span data-stu-id="efeee-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
```
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}

```

 <span data-ttu-id="efeee-123">**响应**-响应包括 HTTP 状态代码和一套响应标头。</span><span class="sxs-lookup"><span data-stu-id="efeee-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="efeee-124">**状态代码**-操作成功返回状态码 200 (OK)。</span><span class="sxs-lookup"><span data-stu-id="efeee-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="efeee-125">**响应标头**的任何其他标头。</span><span class="sxs-lookup"><span data-stu-id="efeee-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="efeee-126">**响应正文**-下面是示例的响应负载在 JSON 响应请求的"[开始日期]。[月]"维度。</span><span class="sxs-lookup"><span data-stu-id="efeee-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="efeee-127">列表仅显示列表中的一小部分。</span><span class="sxs-lookup"><span data-stu-id="efeee-127">The list is only showing a small portion of the list.</span></span> 
  
```
{
"MembersCount": 493,
"Members": [["[1990-01-01T00:00:00]",
"January 1990"],
["[1990-02-01T00:00:00]",
"February 1990"],
["[1990-03-01T00:00:00]",
"March 1990"],
 
    ...
    
["[2030-10-01T00:00:00]",
"October 2030"],
["[2030-11-01T00:00:00]",
"November 2030"],
["[2030-12-01T00:00:00]",
"December 2030"],
["[2031-01-01T00:00:00]",
"January 2031"]]
}

```


