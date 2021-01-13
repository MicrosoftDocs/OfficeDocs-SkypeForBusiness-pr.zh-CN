---
title: 获取维度成员
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
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 摘要：了解"获取维度成员"操作。 "获取维度成员"操作是通话质量仪表板的数据 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: ffec3b02a3c876a003adb679a28b0e8f2edb91c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832632"
---
# <a name="get-dimension-members"></a><span data-ttu-id="a23e0-105">获取维度成员</span><span class="sxs-lookup"><span data-stu-id="a23e0-105">Get Dimension Members</span></span>
 
<span data-ttu-id="a23e0-106">**摘要：** 了解"获取维度成员"操作。</span><span class="sxs-lookup"><span data-stu-id="a23e0-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="a23e0-107">"获取维度成员"操作是通话质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="a23e0-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="a23e0-108">通话质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="a23e0-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a23e0-109">"获取维度成员"操作是通话质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="a23e0-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="a23e0-110">获取维度成员</span><span class="sxs-lookup"><span data-stu-id="a23e0-110">Get Dimension Members</span></span>

<span data-ttu-id="a23e0-111">"获取维度成员"操作返回特定维度的成员列表。</span><span class="sxs-lookup"><span data-stu-id="a23e0-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="a23e0-112">它还提供筛选成员列表和获取子集的能力，以减少线路传输成本。</span><span class="sxs-lookup"><span data-stu-id="a23e0-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="a23e0-113">**方法**</span><span class="sxs-lookup"><span data-stu-id="a23e0-113">**Method**</span></span>|<span data-ttu-id="a23e0-114">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="a23e0-114">**Request URI**</span></span>|<span data-ttu-id="a23e0-115">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="a23e0-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a23e0-116">POST</span><span class="sxs-lookup"><span data-stu-id="a23e0-116">POST</span></span>  <br/> |<span data-ttu-id="a23e0-117">https:// \<portal\> /QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="a23e0-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="a23e0-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="a23e0-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="a23e0-119">**URI 参数** - 无。</span><span class="sxs-lookup"><span data-stu-id="a23e0-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="a23e0-120">**请求标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="a23e0-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a23e0-121">**请求正文** - 这包含我们希望成员使用的尺寸的名称。</span><span class="sxs-lookup"><span data-stu-id="a23e0-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="a23e0-122">此外，返回的最大成员数，旁边可以指定一些筛选以限制返回的成员。</span><span class="sxs-lookup"><span data-stu-id="a23e0-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
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

 <span data-ttu-id="a23e0-123">**响应** - 响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="a23e0-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="a23e0-124">**状态代码** - 成功操作返回状态代码 200 (确定) 。</span><span class="sxs-lookup"><span data-stu-id="a23e0-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="a23e0-125">**响应标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="a23e0-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a23e0-126">**响应正文** - 下面是 JSON 中响应"[StartDate]请求的示例响应有效负载。[Month]" 维度。</span><span class="sxs-lookup"><span data-stu-id="a23e0-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a23e0-127">列表只显示列表的一小部分。</span><span class="sxs-lookup"><span data-stu-id="a23e0-127">The list is only showing a small portion of the list.</span></span> 
  
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
