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
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates 包含后续 Active Directory 同步步骤尚未处理的 Active Directory 域服务更改。
ms.openlocfilehash: 3e7788db170539f888923a4600392e19022bbb0e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295557"
---
# <a name="tbladupdates"></a><span data-ttu-id="aaff0-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="aaff0-103">tblADUpdates</span></span>
 
<span data-ttu-id="aaff0-104">tblADUpdates 包含后续 Active Directory 同步步骤尚未处理的 Active Directory 域服务更改。</span><span class="sxs-lookup"><span data-stu-id="aaff0-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="aaff0-105">**多**</span><span class="sxs-lookup"><span data-stu-id="aaff0-105">**Columns**</span></span>

|<span data-ttu-id="aaff0-106">**列**</span><span class="sxs-lookup"><span data-stu-id="aaff0-106">**Column**</span></span>|<span data-ttu-id="aaff0-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="aaff0-107">**Type**</span></span>|<span data-ttu-id="aaff0-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="aaff0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aaff0-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="aaff0-109">prinGuid</span></span>  <br/> |<span data-ttu-id="aaff0-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="aaff0-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="aaff0-111">已更改对象的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="aaff0-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="aaff0-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="aaff0-112">prinADPath</span></span>  <br/> |<span data-ttu-id="aaff0-113">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="aaff0-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="aaff0-114">对象的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="aaff0-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="aaff0-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="aaff0-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="aaff0-116">位, not null</span><span class="sxs-lookup"><span data-stu-id="aaff0-116">bit, not null</span></span>  <br/> |<span data-ttu-id="aaff0-117">如果对象的至少一个属性发生更改, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="aaff0-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="aaff0-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="aaff0-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="aaff0-119">位, not null</span><span class="sxs-lookup"><span data-stu-id="aaff0-119">bit, not null</span></span>  <br/> |<span data-ttu-id="aaff0-120">如果成员身份已更改, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="aaff0-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="aaff0-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="aaff0-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="aaff0-122">位, not null</span><span class="sxs-lookup"><span data-stu-id="aaff0-122">bit, not null</span></span>  <br/> |<span data-ttu-id="aaff0-123">未使用。</span><span class="sxs-lookup"><span data-stu-id="aaff0-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="aaff0-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="aaff0-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="aaff0-125">位, not null</span><span class="sxs-lookup"><span data-stu-id="aaff0-125">bit, not null</span></span>  <br/> |<span data-ttu-id="aaff0-126">如果对象已删除, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="aaff0-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="aaff0-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="aaff0-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="aaff0-128">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="aaff0-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="aaff0-129">插入行的时间戳。</span><span class="sxs-lookup"><span data-stu-id="aaff0-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

