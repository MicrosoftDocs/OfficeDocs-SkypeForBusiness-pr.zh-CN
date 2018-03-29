---
title: UriTypes 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes 表中包含不同的 URI （统一资源标识符） 类型业务服务器 2015年的 Skype 进行监控。
ms.openlocfilehash: 00c70c166716ad879257e7b18db80dd760ce4ec4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="uritypes-table"></a><span data-ttu-id="18691-103">UriTypes 表</span><span class="sxs-lookup"><span data-stu-id="18691-103">UriTypes table</span></span>
 
<span data-ttu-id="18691-104">UriTypes 表中包含不同的 URI （统一资源标识符） 类型业务服务器 2015年的 Skype 进行监控。</span><span class="sxs-lookup"><span data-stu-id="18691-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="18691-105">**列**</span><span class="sxs-lookup"><span data-stu-id="18691-105">**Column**</span></span>|<span data-ttu-id="18691-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="18691-106">**Data Type**</span></span>|<span data-ttu-id="18691-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="18691-107">**Key/Index**</span></span>|<span data-ttu-id="18691-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="18691-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="18691-109">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="18691-109">**UriTypeId**</span></span> <br/> |<span data-ttu-id="18691-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="18691-110">tinyint</span></span>  <br/> |<span data-ttu-id="18691-111">Primary</span><span class="sxs-lookup"><span data-stu-id="18691-111">Primary</span></span>  <br/> |<span data-ttu-id="18691-112">分配给一个 URI 类型的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="18691-112">Unique identifier assigned to a URI type.</span></span>  <br/> |
|<span data-ttu-id="18691-113">**UriType**</span><span class="sxs-lookup"><span data-stu-id="18691-113">**UriType**</span></span> <br/> |<span data-ttu-id="18691-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="18691-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="18691-115">不同的 URI 类型的说明。</span><span class="sxs-lookup"><span data-stu-id="18691-115">Descriptions of the different URI types.</span></span> <span data-ttu-id="18691-116">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="18691-116">Allowed values are:</span></span> <br/>  <span data-ttu-id="18691-117">0-电话 Uri</span><span class="sxs-lookup"><span data-stu-id="18691-117">0 - Phone Uri</span></span> <br/>  <span data-ttu-id="18691-118">1-用户 Uri</span><span class="sxs-lookup"><span data-stu-id="18691-118">1 - User Uri</span></span> <br/> |
   

