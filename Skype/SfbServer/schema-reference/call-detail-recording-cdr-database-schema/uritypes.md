---
title: UriTypes 表
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
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes 表包含 Skype for Business Server 2015 中 (受监视) 统一资源标识符的不同 URI。
ms.openlocfilehash: 622384086dbd1031633b70758cdcea600ad31d43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831682"
---
# <a name="uritypes-table"></a><span data-ttu-id="442aa-103">UriTypes 表</span><span class="sxs-lookup"><span data-stu-id="442aa-103">UriTypes table</span></span>
 
<span data-ttu-id="442aa-104">UriTypes 表包含 Skype for Business Server 2015 中 (受监视) 统一资源标识符的不同 URI。</span><span class="sxs-lookup"><span data-stu-id="442aa-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="442aa-105">创建 CDR DB 后，将创建两条代表 PhoneUri 和 UserUri 的记录，然后动态分配 UriTypeId。</span><span class="sxs-lookup"><span data-stu-id="442aa-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="442aa-106">**列**</span><span class="sxs-lookup"><span data-stu-id="442aa-106">**Column**</span></span>|<span data-ttu-id="442aa-107">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="442aa-107">**Data Type**</span></span>|<span data-ttu-id="442aa-108">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="442aa-108">**Key/Index**</span></span>|<span data-ttu-id="442aa-109">**Details**</span><span class="sxs-lookup"><span data-stu-id="442aa-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="442aa-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="442aa-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="442aa-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="442aa-111">tinyint</span></span>  <br/> |<span data-ttu-id="442aa-112">主</span><span class="sxs-lookup"><span data-stu-id="442aa-112">Primary</span></span>  <br/> |<span data-ttu-id="442aa-113">分配给 URI 类型的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="442aa-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="442aa-114">可能的值 - 0 到 255</span><span class="sxs-lookup"><span data-stu-id="442aa-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="442aa-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="442aa-115">**UriType**</span></span> <br/> |<span data-ttu-id="442aa-116">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="442aa-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="442aa-117">不同的 URI 类型的描述。</span><span class="sxs-lookup"><span data-stu-id="442aa-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="442aa-118">预分配以下值：</span><span class="sxs-lookup"><span data-stu-id="442aa-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="442aa-119">1 - 电话 Uri</span><span class="sxs-lookup"><span data-stu-id="442aa-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="442aa-120">0 - 用户 Uri</span><span class="sxs-lookup"><span data-stu-id="442aa-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="442aa-121">其他可能的类型包括：</span><span class="sxs-lookup"><span data-stu-id="442aa-121">Other possible types include:</span></span> <br/><span data-ttu-id="442aa-122">conf：applicationsharing</span><span class="sxs-lookup"><span data-stu-id="442aa-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="442aa-123">conf：audio-video</span><span class="sxs-lookup"><span data-stu-id="442aa-123">conf:audio-video</span></span><br/> <span data-ttu-id="442aa-124">conf：chat</span><span class="sxs-lookup"><span data-stu-id="442aa-124">conf:chat</span></span><br/>    <span data-ttu-id="442aa-125">conf：focus</span><span class="sxs-lookup"><span data-stu-id="442aa-125">conf:focus</span></span><br/>   <span data-ttu-id="442aa-126">mras</span><span class="sxs-lookup"><span data-stu-id="442aa-126">mras</span></span><br/>
