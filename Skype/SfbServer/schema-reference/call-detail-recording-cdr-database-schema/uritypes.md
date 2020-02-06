---
title: UriTypes 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes 表包含 Skype for Business Server 2015 中监视的不同 URI （统一资源标识符）类型。
ms.openlocfilehash: 81cd00503f88eac03f952b63ef7a3bd9464c1f51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814840"
---
# <a name="uritypes-table"></a><span data-ttu-id="07f4f-103">UriTypes 表</span><span class="sxs-lookup"><span data-stu-id="07f4f-103">UriTypes table</span></span>
 
<span data-ttu-id="07f4f-104">UriTypes 表包含 Skype for Business Server 2015 中监视的不同 URI （统一资源标识符）类型。</span><span class="sxs-lookup"><span data-stu-id="07f4f-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="07f4f-105">在创建 CDR 数据库时，将创建两个记录来表示 PhoneUri 和 UserUri，并在此之后创建的记录会被动态分配 UriTypeId。</span><span class="sxs-lookup"><span data-stu-id="07f4f-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="07f4f-106">**列**</span><span class="sxs-lookup"><span data-stu-id="07f4f-106">**Column**</span></span>|<span data-ttu-id="07f4f-107">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="07f4f-107">**Data Type**</span></span>|<span data-ttu-id="07f4f-108">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="07f4f-108">**Key/Index**</span></span>|<span data-ttu-id="07f4f-109">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="07f4f-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07f4f-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="07f4f-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="07f4f-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="07f4f-111">tinyint</span></span>  <br/> |<span data-ttu-id="07f4f-112">Primary</span><span class="sxs-lookup"><span data-stu-id="07f4f-112">Primary</span></span>  <br/> |<span data-ttu-id="07f4f-113">分配给 URI 类型的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="07f4f-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="07f4f-114">可能的值-0 到255</span><span class="sxs-lookup"><span data-stu-id="07f4f-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="07f4f-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="07f4f-115">**UriType**</span></span> <br/> |<span data-ttu-id="07f4f-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="07f4f-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="07f4f-117">不同 URI 类型的说明。</span><span class="sxs-lookup"><span data-stu-id="07f4f-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="07f4f-118">以下值是预分配的：</span><span class="sxs-lookup"><span data-stu-id="07f4f-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="07f4f-119">1-电话 Uri</span><span class="sxs-lookup"><span data-stu-id="07f4f-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="07f4f-120">0-用户 Uri</span><span class="sxs-lookup"><span data-stu-id="07f4f-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="07f4f-121">其他可能的类型包括：</span><span class="sxs-lookup"><span data-stu-id="07f4f-121">Other possible types include:</span></span> <br/><span data-ttu-id="07f4f-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="07f4f-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="07f4f-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="07f4f-123">conf:audio-video</span></span><br/> <span data-ttu-id="07f4f-124">会议：聊天</span><span class="sxs-lookup"><span data-stu-id="07f4f-124">conf:chat</span></span><br/>    <span data-ttu-id="07f4f-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="07f4f-125">conf:focus</span></span><br/>   <span data-ttu-id="07f4f-126">mras</span><span class="sxs-lookup"><span data-stu-id="07f4f-126">mras</span></span><br/>
