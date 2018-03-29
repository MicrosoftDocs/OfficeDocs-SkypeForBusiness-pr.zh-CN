---
title: tblADUpdates
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates 包含尚未处理后续活动目录同步步骤通过 Active Directory 域服务更改。
ms.openlocfilehash: 33d2ae6d2113d3f55b0fdf54439e2383ca142589
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tbladupdates"></a><span data-ttu-id="5e4a8-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="5e4a8-103">tblADUpdates</span></span>
 
<span data-ttu-id="5e4a8-104">tblADUpdates 包含尚未处理后续活动目录同步步骤通过 Active Directory 域服务更改。</span><span class="sxs-lookup"><span data-stu-id="5e4a8-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="5e4a8-105">**列**</span><span class="sxs-lookup"><span data-stu-id="5e4a8-105">**Columns**</span></span>

|<span data-ttu-id="5e4a8-106">**列**</span><span class="sxs-lookup"><span data-stu-id="5e4a8-106">**Column**</span></span>|<span data-ttu-id="5e4a8-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="5e4a8-107">**Type**</span></span>|<span data-ttu-id="5e4a8-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="5e4a8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5e4a8-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="5e4a8-109">prinGuid</span></span>  <br/> |<span data-ttu-id="5e4a8-110">GUID，不为空</span><span class="sxs-lookup"><span data-stu-id="5e4a8-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="5e4a8-111">主体的更改的对象的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5e4a8-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="5e4a8-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="5e4a8-112">prinADPath</span></span>  <br/> |<span data-ttu-id="5e4a8-113">nvarchar (384) 不为空</span><span class="sxs-lookup"><span data-stu-id="5e4a8-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="5e4a8-114">对象的可分辨的名称。</span><span class="sxs-lookup"><span data-stu-id="5e4a8-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="5e4a8-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="5e4a8-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="5e4a8-116">位，不为空</span><span class="sxs-lookup"><span data-stu-id="5e4a8-116">bit, not null</span></span>  <br/> |<span data-ttu-id="5e4a8-117">如果至少一个对象的属性更改，则为 true。</span><span class="sxs-lookup"><span data-stu-id="5e4a8-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="5e4a8-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="5e4a8-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="5e4a8-119">位，不为空</span><span class="sxs-lookup"><span data-stu-id="5e4a8-119">bit, not null</span></span>  <br/> |<span data-ttu-id="5e4a8-120">如果更改的成员资格，则为 true。</span><span class="sxs-lookup"><span data-stu-id="5e4a8-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="5e4a8-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="5e4a8-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="5e4a8-122">位，不为空</span><span class="sxs-lookup"><span data-stu-id="5e4a8-122">bit, not null</span></span>  <br/> |<span data-ttu-id="5e4a8-123">不使用。</span><span class="sxs-lookup"><span data-stu-id="5e4a8-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="5e4a8-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="5e4a8-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="5e4a8-125">位，不为空</span><span class="sxs-lookup"><span data-stu-id="5e4a8-125">bit, not null</span></span>  <br/> |<span data-ttu-id="5e4a8-126">如果对象已被删除，则为 true。</span><span class="sxs-lookup"><span data-stu-id="5e4a8-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="5e4a8-127">上次更新</span><span class="sxs-lookup"><span data-stu-id="5e4a8-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="5e4a8-128">日期时间不为空</span><span class="sxs-lookup"><span data-stu-id="5e4a8-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="5e4a8-129">插入行的时间戳。</span><span class="sxs-lookup"><span data-stu-id="5e4a8-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

