---
title: UriTypes 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes 表包含的业务服务器 2015 Skype 中监控的不同 URI （统一资源标识符） 类型。
ms.openlocfilehash: 72704715ff5e5fd3a354b75b0aa6baff45ecea54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930267"
---
# <a name="uritypes-table"></a><span data-ttu-id="c0f3f-103">UriTypes 表</span><span class="sxs-lookup"><span data-stu-id="c0f3f-103">UriTypes table</span></span>
 
<span data-ttu-id="c0f3f-104">UriTypes 表包含的业务服务器 2015 Skype 中监控的不同 URI （统一资源标识符） 类型。</span><span class="sxs-lookup"><span data-stu-id="c0f3f-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="c0f3f-105">创建 CDR 数据库后，创建两个记录表示 PhoneUri 和 UserUri，并在的动态分配 UriTypeId 后创建的记录。</span><span class="sxs-lookup"><span data-stu-id="c0f3f-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="c0f3f-106">**列**</span><span class="sxs-lookup"><span data-stu-id="c0f3f-106">**Column**</span></span>|<span data-ttu-id="c0f3f-107">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c0f3f-107">**Data Type**</span></span>|<span data-ttu-id="c0f3f-108">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="c0f3f-108">**Key/Index**</span></span>|<span data-ttu-id="c0f3f-109">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="c0f3f-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c0f3f-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="c0f3f-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="c0f3f-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="c0f3f-111">tinyint</span></span>  <br/> |<span data-ttu-id="c0f3f-112">Primary</span><span class="sxs-lookup"><span data-stu-id="c0f3f-112">Primary</span></span>  <br/> |<span data-ttu-id="c0f3f-113">分配给 URI 类型的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="c0f3f-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="c0f3f-114">可能值-0 到 255</span><span class="sxs-lookup"><span data-stu-id="c0f3f-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="c0f3f-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="c0f3f-115">**UriType**</span></span> <br/> |<span data-ttu-id="c0f3f-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c0f3f-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="c0f3f-117">不同的 URI 类型的说明。</span><span class="sxs-lookup"><span data-stu-id="c0f3f-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="c0f3f-118">预先分配是以下值：</span><span class="sxs-lookup"><span data-stu-id="c0f3f-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="c0f3f-119">1-电话 Uri</span><span class="sxs-lookup"><span data-stu-id="c0f3f-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="c0f3f-120">0-用户 Uri</span><span class="sxs-lookup"><span data-stu-id="c0f3f-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="c0f3f-121">其他可能的类型包括：</span><span class="sxs-lookup"><span data-stu-id="c0f3f-121">Other possible types include:</span></span> <br/><span data-ttu-id="c0f3f-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="c0f3f-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="c0f3f-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="c0f3f-123">conf:audio-video</span></span><br/> <span data-ttu-id="c0f3f-124">conf:chat</span><span class="sxs-lookup"><span data-stu-id="c0f3f-124">conf:chat</span></span><br/>    <span data-ttu-id="c0f3f-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="c0f3f-125">conf:focus</span></span><br/>   <span data-ttu-id="c0f3f-126">mras</span><span class="sxs-lookup"><span data-stu-id="c0f3f-126">mras</span></span><br/>
