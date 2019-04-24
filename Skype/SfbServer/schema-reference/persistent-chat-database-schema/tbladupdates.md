---
title: tblADUpdates
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates 包含尚未由后面的 Active Directory 同步步骤处理的 Active Directory 域服务更改。
ms.openlocfilehash: 0e7bde110ad3d0495cb7ddea55e405eac21d96b4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212640"
---
# <a name="tbladupdates"></a><span data-ttu-id="34f05-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="34f05-103">tblADUpdates</span></span>
 
<span data-ttu-id="34f05-104">tblADUpdates 包含尚未由后面的 Active Directory 同步步骤处理的 Active Directory 域服务更改。</span><span class="sxs-lookup"><span data-stu-id="34f05-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="34f05-105">**列**</span><span class="sxs-lookup"><span data-stu-id="34f05-105">**Columns**</span></span>

|<span data-ttu-id="34f05-106">**列**</span><span class="sxs-lookup"><span data-stu-id="34f05-106">**Column**</span></span>|<span data-ttu-id="34f05-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="34f05-107">**Type**</span></span>|<span data-ttu-id="34f05-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="34f05-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="34f05-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="34f05-109">prinGuid</span></span>  <br/> |<span data-ttu-id="34f05-110">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="34f05-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="34f05-111">更改的对象的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="34f05-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="34f05-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="34f05-112">prinADPath</span></span>  <br/> |<span data-ttu-id="34f05-113">nvarchar (384)，不为 null</span><span class="sxs-lookup"><span data-stu-id="34f05-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="34f05-114">对象的可分辨的名称。</span><span class="sxs-lookup"><span data-stu-id="34f05-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="34f05-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="34f05-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="34f05-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="34f05-116">bit, not null</span></span>  <br/> |<span data-ttu-id="34f05-117">如果对象至少一个属性更改为 true。</span><span class="sxs-lookup"><span data-stu-id="34f05-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="34f05-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="34f05-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="34f05-119">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="34f05-119">bit, not null</span></span>  <br/> |<span data-ttu-id="34f05-120">如果成员身份被更改，则为 true。</span><span class="sxs-lookup"><span data-stu-id="34f05-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="34f05-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="34f05-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="34f05-122">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="34f05-122">bit, not null</span></span>  <br/> |<span data-ttu-id="34f05-123">不使用。</span><span class="sxs-lookup"><span data-stu-id="34f05-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="34f05-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="34f05-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="34f05-125">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="34f05-125">bit, not null</span></span>  <br/> |<span data-ttu-id="34f05-126">如果对象已删除，则为 true。</span><span class="sxs-lookup"><span data-stu-id="34f05-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="34f05-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="34f05-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="34f05-128">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="34f05-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="34f05-129">插入行的时间戳。</span><span class="sxs-lookup"><span data-stu-id="34f05-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

