---
title: SIPResponseMetaData 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable 包含 SIP 响应代码的分类和定义的每个代码的列表。 这些代码以响应事件影响 SIP 设备生成和 SIP 通信会话;例如，SIP 设备发出请求，但服务器拒绝接受该请求时，将生成 403 的响应代码。
ms.openlocfilehash: edd1f4e60376b367f701864ff15d334c4d971e47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930283"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="2a5e1-104">SIPResponseMetaData 表</span><span class="sxs-lookup"><span data-stu-id="2a5e1-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="2a5e1-105">SIPResponseMetaDataTable 包含 SIP 响应代码的分类和定义的每个代码的列表。</span><span class="sxs-lookup"><span data-stu-id="2a5e1-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="2a5e1-106">这些代码以响应事件影响 SIP 设备生成和 SIP 通信会话;例如，SIP 设备发出请求，但服务器拒绝接受该请求时，将生成 403 的响应代码。</span><span class="sxs-lookup"><span data-stu-id="2a5e1-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="2a5e1-107">此表中引入 Skype 的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="2a5e1-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="2a5e1-108">**列**</span><span class="sxs-lookup"><span data-stu-id="2a5e1-108">**Column**</span></span>|<span data-ttu-id="2a5e1-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="2a5e1-109">**Data Type**</span></span>|<span data-ttu-id="2a5e1-110">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="2a5e1-110">**Key/Index**</span></span>|<span data-ttu-id="2a5e1-111">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="2a5e1-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a5e1-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="2a5e1-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="2a5e1-113">int</span><span class="sxs-lookup"><span data-stu-id="2a5e1-113">int</span></span>  <br/> |<span data-ttu-id="2a5e1-114">Primary</span><span class="sxs-lookup"><span data-stu-id="2a5e1-114">Primary</span></span>  <br/> |<span data-ttu-id="2a5e1-115">表示 SIP 响应代码的数值。</span><span class="sxs-lookup"><span data-stu-id="2a5e1-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="2a5e1-116">**类**</span><span class="sxs-lookup"><span data-stu-id="2a5e1-116">**Class**</span></span> <br/> |<span data-ttu-id="2a5e1-117">int</span><span class="sxs-lookup"><span data-stu-id="2a5e1-117">int</span></span>  <br/> || <span data-ttu-id="2a5e1-118">常规分类的响应代码。</span><span class="sxs-lookup"><span data-stu-id="2a5e1-118">General classification for the response code.</span></span> <span data-ttu-id="2a5e1-119">分类包括：</span><span class="sxs-lookup"><span data-stu-id="2a5e1-119">Classifications include:</span></span> <br/>  <span data-ttu-id="2a5e1-120">1-信息响应</span><span class="sxs-lookup"><span data-stu-id="2a5e1-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="2a5e1-121">2-成功响应</span><span class="sxs-lookup"><span data-stu-id="2a5e1-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="2a5e1-122">3-重定向响应</span><span class="sxs-lookup"><span data-stu-id="2a5e1-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="2a5e1-123">4-客户端失败响应</span><span class="sxs-lookup"><span data-stu-id="2a5e1-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="2a5e1-124">5 – 服务器失败响应</span><span class="sxs-lookup"><span data-stu-id="2a5e1-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="2a5e1-125">6-全局失败响应</span><span class="sxs-lookup"><span data-stu-id="2a5e1-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="2a5e1-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="2a5e1-126">**Description**</span></span> <br/> |<span data-ttu-id="2a5e1-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2a5e1-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="2a5e1-128">SIP 响应代码的描述。</span><span class="sxs-lookup"><span data-stu-id="2a5e1-128">Description of the SIP response code.</span></span> <span data-ttu-id="2a5e1-129">例如，响应代码 181 具有以下描述：</span><span class="sxs-lookup"><span data-stu-id="2a5e1-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="2a5e1-130">呼叫转接</span><span class="sxs-lookup"><span data-stu-id="2a5e1-130">Call Is Being Forwarded</span></span>  <br/> |
   

