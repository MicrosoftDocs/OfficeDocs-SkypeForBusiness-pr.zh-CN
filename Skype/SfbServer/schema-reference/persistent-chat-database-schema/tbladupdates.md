---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates 包含尚未由稍后的 Active Directory 同步步骤处理的 Active Directory 域服务更改。
ms.openlocfilehash: 16bb393eb57e7aaf8d3fea7001157eaabbe70c52
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821382"
---
# <a name="tbladupdates"></a><span data-ttu-id="a1201-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="a1201-103">tblADUpdates</span></span>
 
<span data-ttu-id="a1201-104">tblADUpdates 包含尚未由稍后的 Active Directory 同步步骤处理的 Active Directory 域服务更改。</span><span class="sxs-lookup"><span data-stu-id="a1201-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="a1201-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="a1201-105">**Columns**</span></span>

|<span data-ttu-id="a1201-106">**列**</span><span class="sxs-lookup"><span data-stu-id="a1201-106">**Column**</span></span>|<span data-ttu-id="a1201-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="a1201-107">**Type**</span></span>|<span data-ttu-id="a1201-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="a1201-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a1201-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="a1201-109">prinGuid</span></span>  <br/> |<span data-ttu-id="a1201-110">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="a1201-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="a1201-111">被更改对象的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="a1201-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="a1201-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="a1201-112">prinADPath</span></span>  <br/> |<span data-ttu-id="a1201-113">nvarchar (384)，不为 null</span><span class="sxs-lookup"><span data-stu-id="a1201-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="a1201-114">对象的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="a1201-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="a1201-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="a1201-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="a1201-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="a1201-116">bit, not null</span></span>  <br/> |<span data-ttu-id="a1201-117">如果对象至少有一个属性被更改，则为 True。</span><span class="sxs-lookup"><span data-stu-id="a1201-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="a1201-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="a1201-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="a1201-119">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="a1201-119">bit, not null</span></span>  <br/> |<span data-ttu-id="a1201-120">如果成员身份被更改，则为 True。</span><span class="sxs-lookup"><span data-stu-id="a1201-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="a1201-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="a1201-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="a1201-122">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="a1201-122">bit, not null</span></span>  <br/> |<span data-ttu-id="a1201-123">未使用。</span><span class="sxs-lookup"><span data-stu-id="a1201-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="a1201-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="a1201-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="a1201-125">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="a1201-125">bit, not null</span></span>  <br/> |<span data-ttu-id="a1201-126">如果对象已删除，则为 True。</span><span class="sxs-lookup"><span data-stu-id="a1201-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="a1201-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="a1201-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="a1201-128">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="a1201-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="a1201-129">插入行时的时间戳。</span><span class="sxs-lookup"><span data-stu-id="a1201-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

