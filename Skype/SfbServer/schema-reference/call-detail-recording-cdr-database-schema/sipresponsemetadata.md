---
title: SIPResponseMetaData 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable 包含 SIP 响应代码的列表以及每种代码的分类和定义。在响应影响 SIP 设备和 SIP 通信会话的事件时生成这些代码；例如，当某个 SIP 设备发出请求，但服务器拒绝服从该请求时，将生成响应代码 403。
ms.openlocfilehash: 3d6714e9c5b5c154d19381fad33821b02ec8a73e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809922"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="9647e-104">SIPResponseMetaData 表</span><span class="sxs-lookup"><span data-stu-id="9647e-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="9647e-p102">SIPResponseMetaDataTable 包含 SIP 响应代码的列表以及每种代码的分类和定义。在响应影响 SIP 设备和 SIP 通信会话的事件时生成这些代码；例如，当某个 SIP 设备发出请求，但服务器拒绝服从该请求时，将生成响应代码 403。</span><span class="sxs-lookup"><span data-stu-id="9647e-p102">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes. These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="9647e-107">此表在 Skype for Business Server 2015 中引入。</span><span class="sxs-lookup"><span data-stu-id="9647e-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="9647e-108">**列**</span><span class="sxs-lookup"><span data-stu-id="9647e-108">**Column**</span></span>|<span data-ttu-id="9647e-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9647e-109">**Data Type**</span></span>|<span data-ttu-id="9647e-110">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="9647e-110">**Key/Index**</span></span>|<span data-ttu-id="9647e-111">**Details**</span><span class="sxs-lookup"><span data-stu-id="9647e-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9647e-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="9647e-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="9647e-113">int</span><span class="sxs-lookup"><span data-stu-id="9647e-113">int</span></span>  <br/> |<span data-ttu-id="9647e-114">主</span><span class="sxs-lookup"><span data-stu-id="9647e-114">Primary</span></span>  <br/> |<span data-ttu-id="9647e-115">表示 SIP 响应代码的数字值。</span><span class="sxs-lookup"><span data-stu-id="9647e-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="9647e-116">**Class**</span><span class="sxs-lookup"><span data-stu-id="9647e-116">**Class**</span></span> <br/> |<span data-ttu-id="9647e-117">int</span><span class="sxs-lookup"><span data-stu-id="9647e-117">int</span></span>  <br/> || <span data-ttu-id="9647e-p103">响应代码的常规分类。分类包括：</span><span class="sxs-lookup"><span data-stu-id="9647e-p103">General classification for the response code. Classifications include:</span></span> <br/>  <span data-ttu-id="9647e-120">1 - 信息响应</span><span class="sxs-lookup"><span data-stu-id="9647e-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="9647e-121">2 - 成功响应</span><span class="sxs-lookup"><span data-stu-id="9647e-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="9647e-122">3 - 重定向响应</span><span class="sxs-lookup"><span data-stu-id="9647e-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="9647e-123">4 - 客户端故障响应</span><span class="sxs-lookup"><span data-stu-id="9647e-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="9647e-124">5 -- 服务器故障响应</span><span class="sxs-lookup"><span data-stu-id="9647e-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="9647e-125">6 - 全局故障响应</span><span class="sxs-lookup"><span data-stu-id="9647e-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="9647e-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="9647e-126">**Description**</span></span> <br/> |<span data-ttu-id="9647e-127">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="9647e-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="9647e-p104">SIP 响应代码的说明。例如，响应代码 181 的说明如下：</span><span class="sxs-lookup"><span data-stu-id="9647e-p104">Description of the SIP response code. For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="9647e-130">Call Is Being Forwarded</span><span class="sxs-lookup"><span data-stu-id="9647e-130">Call Is Being Forwarded</span></span>  <br/> |
   

