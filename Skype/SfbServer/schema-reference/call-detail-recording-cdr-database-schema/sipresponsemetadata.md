---
title: SIPResponseMetaData 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable 包含 SIP 响应代码列表以及每个代码的分类和定义。 系统会生成这些代码, 以响应影响 SIP 设备和 SIP 通信会话的事件;例如, 在 SIP 设备发出请求时, 将生成响应代码 403, 但服务器拒绝接受该请求。
ms.openlocfilehash: eecd8397315b93ebce9e5fad973f1274a6eb763a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295788"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="1605b-104">SIPResponseMetaData 表</span><span class="sxs-lookup"><span data-stu-id="1605b-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="1605b-105">SIPResponseMetaDataTable 包含 SIP 响应代码列表以及每个代码的分类和定义。</span><span class="sxs-lookup"><span data-stu-id="1605b-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="1605b-106">系统会生成这些代码, 以响应影响 SIP 设备和 SIP 通信会话的事件;例如, 在 SIP 设备发出请求时, 将生成响应代码 403, 但服务器拒绝接受该请求。</span><span class="sxs-lookup"><span data-stu-id="1605b-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="1605b-107">此表是在 Skype for Business Server 2015 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1605b-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="1605b-108">**列**</span><span class="sxs-lookup"><span data-stu-id="1605b-108">**Column**</span></span>|<span data-ttu-id="1605b-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1605b-109">**Data Type**</span></span>|<span data-ttu-id="1605b-110">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="1605b-110">**Key/Index**</span></span>|<span data-ttu-id="1605b-111">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="1605b-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1605b-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="1605b-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="1605b-113">int</span><span class="sxs-lookup"><span data-stu-id="1605b-113">int</span></span>  <br/> |<span data-ttu-id="1605b-114">Primary</span><span class="sxs-lookup"><span data-stu-id="1605b-114">Primary</span></span>  <br/> |<span data-ttu-id="1605b-115">表示 SIP 响应代码的数值。</span><span class="sxs-lookup"><span data-stu-id="1605b-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="1605b-116">**种类**</span><span class="sxs-lookup"><span data-stu-id="1605b-116">**Class**</span></span> <br/> |<span data-ttu-id="1605b-117">int</span><span class="sxs-lookup"><span data-stu-id="1605b-117">int</span></span>  <br/> || <span data-ttu-id="1605b-118">响应代码的常规分类。</span><span class="sxs-lookup"><span data-stu-id="1605b-118">General classification for the response code.</span></span> <span data-ttu-id="1605b-119">分类包括:</span><span class="sxs-lookup"><span data-stu-id="1605b-119">Classifications include:</span></span> <br/>  <span data-ttu-id="1605b-120">1-信息答复</span><span class="sxs-lookup"><span data-stu-id="1605b-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="1605b-121">2-成功的答复</span><span class="sxs-lookup"><span data-stu-id="1605b-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="1605b-122">3-重定向答复</span><span class="sxs-lookup"><span data-stu-id="1605b-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="1605b-123">4-客户端故障响应</span><span class="sxs-lookup"><span data-stu-id="1605b-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="1605b-124">5--服务器故障响应</span><span class="sxs-lookup"><span data-stu-id="1605b-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="1605b-125">6-全球故障响应</span><span class="sxs-lookup"><span data-stu-id="1605b-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="1605b-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="1605b-126">**Description**</span></span> <br/> |<span data-ttu-id="1605b-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1605b-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="1605b-128">SIP 响应代码的说明。</span><span class="sxs-lookup"><span data-stu-id="1605b-128">Description of the SIP response code.</span></span> <span data-ttu-id="1605b-129">例如, 响应代码181具有以下说明:</span><span class="sxs-lookup"><span data-stu-id="1605b-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="1605b-130">正在转发呼叫</span><span class="sxs-lookup"><span data-stu-id="1605b-130">Call Is Being Forwarded</span></span>  <br/> |
   

