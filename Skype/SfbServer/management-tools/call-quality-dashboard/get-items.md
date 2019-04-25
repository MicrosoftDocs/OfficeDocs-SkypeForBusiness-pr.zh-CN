---
title: 获取项目
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 摘要： 了解如何获取项操作，即项服务的一部分。 项服务是呼叫质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: ad4be2c09de9d71499cd7592989334ccf4cf17c9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235728"
---
# <a name="get-items"></a><span data-ttu-id="f4856-105">获取项目</span><span class="sxs-lookup"><span data-stu-id="f4856-105">Get Items</span></span>
 
<span data-ttu-id="f4856-106">**摘要：** 了解有关获取项操作，即项服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="f4856-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="f4856-107">项服务是呼叫质量仪表板的存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="f4856-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="f4856-108">呼叫质量仪表板是用于业务服务器 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="f4856-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="f4856-109">获取项操作是用于呼叫的质量仪表板的存储库 API 中的项服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="f4856-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="f4856-110">获取项目</span><span class="sxs-lookup"><span data-stu-id="f4856-110">Get Items</span></span>

<span data-ttu-id="f4856-111">在存储库中获取项目返回的所有项目。</span><span class="sxs-lookup"><span data-stu-id="f4856-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="f4856-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="f4856-112">**Method**</span></span>|<span data-ttu-id="f4856-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="f4856-113">**Request URI**</span></span>|<span data-ttu-id="f4856-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="f4856-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f4856-115">获取</span><span class="sxs-lookup"><span data-stu-id="f4856-115">GET</span></span>  <br/> |<span data-ttu-id="f4856-116">https://\<门户\>/QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="f4856-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="f4856-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="f4856-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="f4856-118">**URI 参数**-无。</span><span class="sxs-lookup"><span data-stu-id="f4856-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="f4856-119">**请求标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="f4856-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f4856-120">**请求正文**-无。</span><span class="sxs-lookup"><span data-stu-id="f4856-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="f4856-121">**响应**-响应包括 HTTP 状态代码和一响应标头。</span><span class="sxs-lookup"><span data-stu-id="f4856-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="f4856-122">**状态代码**-成功的操作返回状态代码 200 （确定)。</span><span class="sxs-lookup"><span data-stu-id="f4856-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="f4856-123">**响应标头**的任何其他的标头。</span><span class="sxs-lookup"><span data-stu-id="f4856-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f4856-124">**响应正文**-下面是以 json 格式的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="f4856-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f4856-125">返回项目对象的数组。</span><span class="sxs-lookup"><span data-stu-id="f4856-125">An array of Item objects is returned.</span></span> <span data-ttu-id="f4856-126">有关项目对象的详细信息，请参阅获取项。</span><span class="sxs-lookup"><span data-stu-id="f4856-126">For details about Item object, see Get Item.</span></span> 
  
```
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]
```
