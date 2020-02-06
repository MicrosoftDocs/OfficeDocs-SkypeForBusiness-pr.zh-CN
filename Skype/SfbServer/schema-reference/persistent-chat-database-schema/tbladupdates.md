---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates 包含后续 Active Directory 同步步骤尚未处理的 Active Directory 域服务更改。
ms.openlocfilehash: 6d50e065bd10e11383f606b2a4dfed0d5584cd1e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814680"
---
# <a name="tbladupdates"></a><span data-ttu-id="2f5d2-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="2f5d2-103">tblADUpdates</span></span>
 
<span data-ttu-id="2f5d2-104">tblADUpdates 包含后续 Active Directory 同步步骤尚未处理的 Active Directory 域服务更改。</span><span class="sxs-lookup"><span data-stu-id="2f5d2-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="2f5d2-105">**多**</span><span class="sxs-lookup"><span data-stu-id="2f5d2-105">**Columns**</span></span>

|<span data-ttu-id="2f5d2-106">**列**</span><span class="sxs-lookup"><span data-stu-id="2f5d2-106">**Column**</span></span>|<span data-ttu-id="2f5d2-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="2f5d2-107">**Type**</span></span>|<span data-ttu-id="2f5d2-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="2f5d2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2f5d2-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2f5d2-109">prinGuid</span></span>  <br/> |<span data-ttu-id="2f5d2-110">GUID，not null</span><span class="sxs-lookup"><span data-stu-id="2f5d2-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="2f5d2-111">已更改对象的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="2f5d2-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="2f5d2-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="2f5d2-112">prinADPath</span></span>  <br/> |<span data-ttu-id="2f5d2-113">nvarchar （384），not null</span><span class="sxs-lookup"><span data-stu-id="2f5d2-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="2f5d2-114">对象的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="2f5d2-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="2f5d2-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="2f5d2-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="2f5d2-116">位，not null</span><span class="sxs-lookup"><span data-stu-id="2f5d2-116">bit, not null</span></span>  <br/> |<span data-ttu-id="2f5d2-117">如果对象的至少一个属性发生更改，则为 True。</span><span class="sxs-lookup"><span data-stu-id="2f5d2-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="2f5d2-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="2f5d2-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="2f5d2-119">位，not null</span><span class="sxs-lookup"><span data-stu-id="2f5d2-119">bit, not null</span></span>  <br/> |<span data-ttu-id="2f5d2-120">如果成员身份已更改，则为 True。</span><span class="sxs-lookup"><span data-stu-id="2f5d2-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="2f5d2-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="2f5d2-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="2f5d2-122">位，not null</span><span class="sxs-lookup"><span data-stu-id="2f5d2-122">bit, not null</span></span>  <br/> |<span data-ttu-id="2f5d2-123">未使用。</span><span class="sxs-lookup"><span data-stu-id="2f5d2-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="2f5d2-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="2f5d2-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="2f5d2-125">位，not null</span><span class="sxs-lookup"><span data-stu-id="2f5d2-125">bit, not null</span></span>  <br/> |<span data-ttu-id="2f5d2-126">如果对象已删除，则为 True。</span><span class="sxs-lookup"><span data-stu-id="2f5d2-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="2f5d2-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="2f5d2-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="2f5d2-128">datetime，not null</span><span class="sxs-lookup"><span data-stu-id="2f5d2-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="2f5d2-129">插入行的时间戳。</span><span class="sxs-lookup"><span data-stu-id="2f5d2-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

