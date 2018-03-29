---
title: tblPrincipalInvites
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites 包含邀请所有用户设置自动邀请的所有节点上。
ms.openlocfilehash: ae33d45e14340b6374299343f13c8352db1a5021
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="e1d4e-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="e1d4e-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="e1d4e-104">tblPrincipalInvites 包含邀请所有用户设置自动邀请的所有节点上。</span><span class="sxs-lookup"><span data-stu-id="e1d4e-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="e1d4e-105">**列**</span><span class="sxs-lookup"><span data-stu-id="e1d4e-105">**Columns**</span></span>

|<span data-ttu-id="e1d4e-106">**列**</span><span class="sxs-lookup"><span data-stu-id="e1d4e-106">**Column**</span></span>|<span data-ttu-id="e1d4e-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="e1d4e-107">**Type**</span></span>|<span data-ttu-id="e1d4e-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="e1d4e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e1d4e-109">prinID</span><span class="sxs-lookup"><span data-stu-id="e1d4e-109">prinID</span></span>  <br/> |<span data-ttu-id="e1d4e-110">int，不为空</span><span class="sxs-lookup"><span data-stu-id="e1d4e-110">int, not null</span></span>  <br/> |<span data-ttu-id="e1d4e-111">主体标识。</span><span class="sxs-lookup"><span data-stu-id="e1d4e-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="e1d4e-112">invID</span><span class="sxs-lookup"><span data-stu-id="e1d4e-112">invID</span></span>  <br/> |<span data-ttu-id="e1d4e-113">int，不为空</span><span class="sxs-lookup"><span data-stu-id="e1d4e-113">int, not null</span></span>  <br/> |<span data-ttu-id="e1d4e-114">唯一序列号 （每个主体 ID) 从 tblLastInviteId 表中生成。</span><span class="sxs-lookup"><span data-stu-id="e1d4e-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="e1d4e-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="e1d4e-115">nodeID</span></span>  <br/> |<span data-ttu-id="e1d4e-116">int，不为空</span><span class="sxs-lookup"><span data-stu-id="e1d4e-116">int, not null</span></span>  <br/> |<span data-ttu-id="e1d4e-117">节点 ID （仅适用于聊天室）。</span><span class="sxs-lookup"><span data-stu-id="e1d4e-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="e1d4e-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="e1d4e-118">createdOn</span></span>  <br/> |<span data-ttu-id="e1d4e-119">日期时间不为空</span><span class="sxs-lookup"><span data-stu-id="e1d4e-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="e1d4e-120">创建时间。</span><span class="sxs-lookup"><span data-stu-id="e1d4e-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="e1d4e-121">**密钥**</span><span class="sxs-lookup"><span data-stu-id="e1d4e-121">**Keys**</span></span>

|<span data-ttu-id="e1d4e-122">**列**</span><span class="sxs-lookup"><span data-stu-id="e1d4e-122">**Column**</span></span>|<span data-ttu-id="e1d4e-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="e1d4e-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e1d4e-124">\<prinID nodeID\></span><span class="sxs-lookup"><span data-stu-id="e1d4e-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="e1d4e-125">为主键。</span><span class="sxs-lookup"><span data-stu-id="e1d4e-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e1d4e-126">prinID</span><span class="sxs-lookup"><span data-stu-id="e1d4e-126">prinID</span></span>  <br/> |<span data-ttu-id="e1d4e-127">TblPrincipal.prinID 表中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="e1d4e-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="e1d4e-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="e1d4e-128">nodeID</span></span>  <br/> |<span data-ttu-id="e1d4e-129">TblNode.nodeID 表中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="e1d4e-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

