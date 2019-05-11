---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates 包含尚未由后面的 Active Directory 同步步骤处理的 Active Directory 域服务更改。
ms.openlocfilehash: 4ed1abe2d5926c8b34ddccb28133ecc34ddaa03a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929859"
---
# <a name="tbladupdates"></a><span data-ttu-id="a4891-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="a4891-103">tblADUpdates</span></span>
 
<span data-ttu-id="a4891-104">tblADUpdates 包含尚未由后面的 Active Directory 同步步骤处理的 Active Directory 域服务更改。</span><span class="sxs-lookup"><span data-stu-id="a4891-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="a4891-105">**列**</span><span class="sxs-lookup"><span data-stu-id="a4891-105">**Columns**</span></span>

|<span data-ttu-id="a4891-106">**列**</span><span class="sxs-lookup"><span data-stu-id="a4891-106">**Column**</span></span>|<span data-ttu-id="a4891-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="a4891-107">**Type**</span></span>|<span data-ttu-id="a4891-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="a4891-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a4891-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="a4891-109">prinGuid</span></span>  <br/> |<span data-ttu-id="a4891-110">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="a4891-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="a4891-111">更改的对象的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="a4891-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="a4891-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="a4891-112">prinADPath</span></span>  <br/> |<span data-ttu-id="a4891-113">nvarchar (384)，不为 null</span><span class="sxs-lookup"><span data-stu-id="a4891-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="a4891-114">对象的可分辨的名称。</span><span class="sxs-lookup"><span data-stu-id="a4891-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="a4891-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="a4891-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="a4891-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="a4891-116">bit, not null</span></span>  <br/> |<span data-ttu-id="a4891-117">如果对象至少一个属性更改为 true。</span><span class="sxs-lookup"><span data-stu-id="a4891-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="a4891-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="a4891-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="a4891-119">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="a4891-119">bit, not null</span></span>  <br/> |<span data-ttu-id="a4891-120">如果成员身份被更改，则为 true。</span><span class="sxs-lookup"><span data-stu-id="a4891-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="a4891-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="a4891-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="a4891-122">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="a4891-122">bit, not null</span></span>  <br/> |<span data-ttu-id="a4891-123">不使用。</span><span class="sxs-lookup"><span data-stu-id="a4891-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="a4891-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="a4891-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="a4891-125">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="a4891-125">bit, not null</span></span>  <br/> |<span data-ttu-id="a4891-126">如果对象已删除，则为 true。</span><span class="sxs-lookup"><span data-stu-id="a4891-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="a4891-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="a4891-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="a4891-128">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="a4891-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="a4891-129">插入行的时间戳。</span><span class="sxs-lookup"><span data-stu-id="a4891-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

