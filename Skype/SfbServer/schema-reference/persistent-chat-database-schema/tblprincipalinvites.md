---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites 包含打开自动邀请的所有节点的所有已设置用户的邀请。
ms.openlocfilehash: 5008158dcb1c62c766162595d9bffe1875d56514
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924421"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="d7aa3-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="d7aa3-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="d7aa3-104">tblPrincipalInvites 包含打开自动邀请的所有节点的所有已设置用户的邀请。</span><span class="sxs-lookup"><span data-stu-id="d7aa3-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="d7aa3-105">**列**</span><span class="sxs-lookup"><span data-stu-id="d7aa3-105">**Columns**</span></span>

|<span data-ttu-id="d7aa3-106">**列**</span><span class="sxs-lookup"><span data-stu-id="d7aa3-106">**Column**</span></span>|<span data-ttu-id="d7aa3-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="d7aa3-107">**Type**</span></span>|<span data-ttu-id="d7aa3-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="d7aa3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d7aa3-109">prinID</span><span class="sxs-lookup"><span data-stu-id="d7aa3-109">prinID</span></span>  <br/> |<span data-ttu-id="d7aa3-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="d7aa3-110">int, not null</span></span>  <br/> |<span data-ttu-id="d7aa3-111">主体 id。</span><span class="sxs-lookup"><span data-stu-id="d7aa3-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="d7aa3-112">invID</span><span class="sxs-lookup"><span data-stu-id="d7aa3-112">invID</span></span>  <br/> |<span data-ttu-id="d7aa3-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="d7aa3-113">int, not null</span></span>  <br/> |<span data-ttu-id="d7aa3-114">生成的唯一连续数字 （每个主体 ID) 从 tblLastInviteId 表。</span><span class="sxs-lookup"><span data-stu-id="d7aa3-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="d7aa3-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="d7aa3-115">nodeID</span></span>  <br/> |<span data-ttu-id="d7aa3-116">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="d7aa3-116">int, not null</span></span>  <br/> |<span data-ttu-id="d7aa3-117">节点 ID （仅聊天室）。</span><span class="sxs-lookup"><span data-stu-id="d7aa3-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="d7aa3-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="d7aa3-118">createdOn</span></span>  <br/> |<span data-ttu-id="d7aa3-119">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="d7aa3-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="d7aa3-120">创建的时间。</span><span class="sxs-lookup"><span data-stu-id="d7aa3-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="d7aa3-121">**键**</span><span class="sxs-lookup"><span data-stu-id="d7aa3-121">**Keys**</span></span>

|<span data-ttu-id="d7aa3-122">**列**</span><span class="sxs-lookup"><span data-stu-id="d7aa3-122">**Column**</span></span>|<span data-ttu-id="d7aa3-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="d7aa3-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d7aa3-124">\<prinID nodeID\></span><span class="sxs-lookup"><span data-stu-id="d7aa3-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="d7aa3-125">主键。</span><span class="sxs-lookup"><span data-stu-id="d7aa3-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d7aa3-126">prinID</span><span class="sxs-lookup"><span data-stu-id="d7aa3-126">prinID</span></span>  <br/> |<span data-ttu-id="d7aa3-127">在 tblPrincipal.prinID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="d7aa3-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="d7aa3-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="d7aa3-128">nodeID</span></span>  <br/> |<span data-ttu-id="d7aa3-129">在 tblNode.nodeID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="d7aa3-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

