---
title: SIPResponseMetaData 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable 包含 SIP 响应代码的分类和定义的每个这些代码的列表。 这些代码以响应事件影响 SIP 设备生成和 SIP 通信会话;例如，对 SIP 设备发出请求，而服务器拒绝接受请求时生成响应代码 403。
ms.openlocfilehash: a90a248837dd705746fe3b342874aad10480e8a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="4540f-104">SIPResponseMetaData 表</span><span class="sxs-lookup"><span data-stu-id="4540f-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="4540f-105">SIPResponseMetaDataTable 包含 SIP 响应代码的分类和定义的每个这些代码的列表。</span><span class="sxs-lookup"><span data-stu-id="4540f-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="4540f-106">这些代码以响应事件影响 SIP 设备生成和 SIP 通信会话;例如，对 SIP 设备发出请求，而服务器拒绝接受请求时生成响应代码 403。</span><span class="sxs-lookup"><span data-stu-id="4540f-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="4540f-107">为业务服务器 2015年在 Skype 引入了此表。</span><span class="sxs-lookup"><span data-stu-id="4540f-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="4540f-108">**列**</span><span class="sxs-lookup"><span data-stu-id="4540f-108">**Column**</span></span>|<span data-ttu-id="4540f-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4540f-109">**Data Type**</span></span>|<span data-ttu-id="4540f-110">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="4540f-110">**Key/Index**</span></span>|<span data-ttu-id="4540f-111">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="4540f-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4540f-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="4540f-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="4540f-113">int</span><span class="sxs-lookup"><span data-stu-id="4540f-113">int</span></span>  <br/> |<span data-ttu-id="4540f-114">Primary</span><span class="sxs-lookup"><span data-stu-id="4540f-114">Primary</span></span>  <br/> |<span data-ttu-id="4540f-115">数字值，表示 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="4540f-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="4540f-116">**类**</span><span class="sxs-lookup"><span data-stu-id="4540f-116">**Class**</span></span> <br/> |<span data-ttu-id="4540f-117">int</span><span class="sxs-lookup"><span data-stu-id="4540f-117">int</span></span>  <br/> || <span data-ttu-id="4540f-118">响应代码的的一般分类。</span><span class="sxs-lookup"><span data-stu-id="4540f-118">General classification for the response code.</span></span> <span data-ttu-id="4540f-119">类别包括：</span><span class="sxs-lookup"><span data-stu-id="4540f-119">Classifications include:</span></span> <br/>  <span data-ttu-id="4540f-120">1-信息的响应</span><span class="sxs-lookup"><span data-stu-id="4540f-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="4540f-121">2-成功的响应</span><span class="sxs-lookup"><span data-stu-id="4540f-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="4540f-122">3-重定向响应</span><span class="sxs-lookup"><span data-stu-id="4540f-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="4540f-123">4-客户端故障响应</span><span class="sxs-lookup"><span data-stu-id="4540f-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="4540f-124">5-服务器故障响应</span><span class="sxs-lookup"><span data-stu-id="4540f-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="4540f-125">6-全局失败响应</span><span class="sxs-lookup"><span data-stu-id="4540f-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="4540f-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="4540f-126">**Description**</span></span> <br/> |<span data-ttu-id="4540f-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4540f-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="4540f-128">SIP 响应代码的描述。</span><span class="sxs-lookup"><span data-stu-id="4540f-128">Description of the SIP response code.</span></span> <span data-ttu-id="4540f-129">例如，响应代码 181 有以下说明：</span><span class="sxs-lookup"><span data-stu-id="4540f-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="4540f-130">呼叫已转发</span><span class="sxs-lookup"><span data-stu-id="4540f-130">Call Is Being Forwarded</span></span>  <br/> |
   

