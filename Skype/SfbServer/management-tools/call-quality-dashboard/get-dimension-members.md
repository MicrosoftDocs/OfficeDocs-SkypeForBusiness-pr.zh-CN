---
title: 获取维度成员
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
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 摘要：了解 "获取维度成员" 操作。 "获取维度成员" 操作是 "调用质量" 仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: 40e5ac8b95c24c3a8cb759da99f7d7aeaa391576
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888811"
---
# <a name="get-dimension-members"></a><span data-ttu-id="c9e18-105">获取维度成员</span><span class="sxs-lookup"><span data-stu-id="c9e18-105">Get Dimension Members</span></span>
 
<span data-ttu-id="c9e18-106">**摘要：** 了解 "获取维度成员" 操作。</span><span class="sxs-lookup"><span data-stu-id="c9e18-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="c9e18-107">"获取维度成员" 操作是 "调用质量" 仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="c9e18-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="c9e18-108">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="c9e18-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="c9e18-109">"获取维度成员" 操作是 "调用质量" 仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="c9e18-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="c9e18-110">获取维度成员</span><span class="sxs-lookup"><span data-stu-id="c9e18-110">Get Dimension Members</span></span>

<span data-ttu-id="c9e18-111">获取维度成员操作返回特定维度的成员列表。</span><span class="sxs-lookup"><span data-stu-id="c9e18-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="c9e18-112">它还提供了筛选成员列表和获取子集的功能，以降低线路传输成本。</span><span class="sxs-lookup"><span data-stu-id="c9e18-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="c9e18-113">**种**</span><span class="sxs-lookup"><span data-stu-id="c9e18-113">**Method**</span></span>|<span data-ttu-id="c9e18-114">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="c9e18-114">**Request URI**</span></span>|<span data-ttu-id="c9e18-115">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="c9e18-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c9e18-116">发布</span><span class="sxs-lookup"><span data-stu-id="c9e18-116">POST</span></span>  <br/> |<span data-ttu-id="c9e18-117">https://\<portal\>/QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="c9e18-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="c9e18-118">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="c9e18-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="c9e18-119">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="c9e18-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="c9e18-120">**请求标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="c9e18-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c9e18-121">**请求正文**-此项包含我们想要成员的维度的名称。</span><span class="sxs-lookup"><span data-stu-id="c9e18-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="c9e18-122">同样，返回的最大成员数，您可以指定一些筛选来限制返回的成员。</span><span class="sxs-lookup"><span data-stu-id="c9e18-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
```json
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 <span data-ttu-id="c9e18-123">**响应**-响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="c9e18-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="c9e18-124">**状态代码**-成功的操作返回状态代码200（OK）。</span><span class="sxs-lookup"><span data-stu-id="c9e18-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="c9e18-125">**响应标题**-无其他标题。</span><span class="sxs-lookup"><span data-stu-id="c9e18-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c9e18-126">**响应正文**-下面是 JSON 中的一个示例响应负载，用于响应 "[开始日期]" 请求。[Month] "维度。</span><span class="sxs-lookup"><span data-stu-id="c9e18-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9e18-127">列表仅显示列表的一小部分。</span><span class="sxs-lookup"><span data-stu-id="c9e18-127">The list is only showing a small portion of the list.</span></span> 
  
```json
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
