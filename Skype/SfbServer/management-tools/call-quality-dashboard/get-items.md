---
title: 获取项目
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
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 摘要：了解作为项目服务的一部分的 Get Items 操作。 项目服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: 7da3ba77e782abe44896a7c1eb51a458d9a7e0b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832532"
---
# <a name="get-items"></a><span data-ttu-id="1c599-105">获取项目</span><span class="sxs-lookup"><span data-stu-id="1c599-105">Get Items</span></span>
 
<span data-ttu-id="1c599-106">**摘要：** 了解"获取项目"操作，该操作是项服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="1c599-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="1c599-107">项目服务是通话质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="1c599-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="1c599-108">通话质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="1c599-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="1c599-109">Get Items 操作是呼叫质量仪表板的存储库 API 中的项目服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="1c599-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="1c599-110">获取项目</span><span class="sxs-lookup"><span data-stu-id="1c599-110">Get Items</span></span>

<span data-ttu-id="1c599-111">获取项目将返回存储库中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="1c599-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="1c599-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="1c599-112">**Method**</span></span>|<span data-ttu-id="1c599-113">**请求 URI**</span><span class="sxs-lookup"><span data-stu-id="1c599-113">**Request URI**</span></span>|<span data-ttu-id="1c599-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="1c599-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1c599-115">GET</span><span class="sxs-lookup"><span data-stu-id="1c599-115">GET</span></span>  <br/> |<span data-ttu-id="1c599-116">https:// \<portal\> /QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="1c599-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="1c599-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="1c599-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="1c599-118">**URI 参数** - 无。</span><span class="sxs-lookup"><span data-stu-id="1c599-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="1c599-119">**请求标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="1c599-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1c599-120">**请求正文** - 无。</span><span class="sxs-lookup"><span data-stu-id="1c599-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="1c599-121">**响应** - 响应包括 HTTP 状态代码和一组响应标头。</span><span class="sxs-lookup"><span data-stu-id="1c599-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="1c599-122">**状态代码** - 成功操作返回状态代码 200 (确定) 。</span><span class="sxs-lookup"><span data-stu-id="1c599-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="1c599-123">**响应标头** - 无其他标头。</span><span class="sxs-lookup"><span data-stu-id="1c599-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1c599-124">**响应正文** - 下面是 JSON 中的示例响应负载。</span><span class="sxs-lookup"><span data-stu-id="1c599-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1c599-125">返回 Item 对象的数组。</span><span class="sxs-lookup"><span data-stu-id="1c599-125">An array of Item objects is returned.</span></span> <span data-ttu-id="1c599-126">有关 Item 对象的详细信息，请参阅"获取项目"。</span><span class="sxs-lookup"><span data-stu-id="1c599-126">For details about Item object, see Get Item.</span></span> 
  
```json
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
