---
title: 获取维度成员
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
description: 摘要： 了解如何获取维度成员操作。 获取维度成员操作是用于呼叫的质量仪表板的数据 API 的一部分。 呼叫质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 6d3f5f30ccb3b79aabe9faa37f7c960b846ef0cd
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295960"
---
# <a name="get-dimension-members"></a><span data-ttu-id="9b3f9-105">获取维度成员</span><span class="sxs-lookup"><span data-stu-id="9b3f9-105">Get Dimension Members</span></span>
 
<span data-ttu-id="9b3f9-106">**摘要：** 了解有关获取维度成员操作。</span><span class="sxs-lookup"><span data-stu-id="9b3f9-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="9b3f9-107">获取维度成员操作是用于呼叫的质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="9b3f9-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="9b3f9-108">呼叫质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="9b3f9-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9b3f9-109">获取维度成员操作是用于呼叫的质量仪表板的数据 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="9b3f9-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="9b3f9-110">获取维度成员</span><span class="sxs-lookup"><span data-stu-id="9b3f9-110">Get Dimension Members</span></span>

<span data-ttu-id="9b3f9-111">获取维度成员操作返回的特定维度成员的列表。</span><span class="sxs-lookup"><span data-stu-id="9b3f9-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="9b3f9-112">它还提供的功能来筛选成员列表和获取子集，以减少线路传输成本。</span><span class="sxs-lookup"><span data-stu-id="9b3f9-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="9b3f9-113">**方法**</span><span class="sxs-lookup"><span data-stu-id="9b3f9-113">**Method**</span></span>|<span data-ttu-id="9b3f9-114">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="9b3f9-114">**Request URI**</span></span>|<span data-ttu-id="9b3f9-115">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="9b3f9-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9b3f9-116">发布</span><span class="sxs-lookup"><span data-stu-id="9b3f9-116">POST</span></span>  <br/> |<span data-ttu-id="9b3f9-117">https://\<门户\>/QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="9b3f9-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="9b3f9-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="9b3f9-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9b3f9-119">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="9b3f9-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="9b3f9-120">**请求标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="9b3f9-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9b3f9-121">**请求正文**-此部件包含我们希望成员的维度的名称。</span><span class="sxs-lookup"><span data-stu-id="9b3f9-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="9b3f9-122">此外返回成员的最大数目，旁边可以指定某些筛选，以限制返回的成员。</span><span class="sxs-lookup"><span data-stu-id="9b3f9-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
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

 <span data-ttu-id="9b3f9-123">**响应**-响应包括 HTTP 状态代码和一响应标头。</span><span class="sxs-lookup"><span data-stu-id="9b3f9-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="9b3f9-124">**状态代码**-成功的操作返回状态代码 200 （确定)。</span><span class="sxs-lookup"><span data-stu-id="9b3f9-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="9b3f9-125">**响应标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="9b3f9-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9b3f9-126">**响应正文**-下面是示例的响应负载以 json 格式以响应的请求"[StartDate]。[月份]"维度。</span><span class="sxs-lookup"><span data-stu-id="9b3f9-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9b3f9-127">列表列表的一小部分仅显示。</span><span class="sxs-lookup"><span data-stu-id="9b3f9-127">The list is only showing a small portion of the list.</span></span> 
  
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