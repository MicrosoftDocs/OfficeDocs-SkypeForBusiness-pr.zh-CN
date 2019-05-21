---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal 包含分配给节点的作用域。
ms.openlocfilehash: 2fd8e434710c7bcd266c427fa492e23adacedb22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295193"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="4250a-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="4250a-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="4250a-104">tblScopePrincipal 包含分配给节点的作用域。</span><span class="sxs-lookup"><span data-stu-id="4250a-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="4250a-105">**多**</span><span class="sxs-lookup"><span data-stu-id="4250a-105">**Columns**</span></span>

|<span data-ttu-id="4250a-106">**列**</span><span class="sxs-lookup"><span data-stu-id="4250a-106">**Column**</span></span>|<span data-ttu-id="4250a-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="4250a-107">**Type**</span></span>|<span data-ttu-id="4250a-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="4250a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4250a-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="4250a-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="4250a-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="4250a-110">int, not null</span></span>  <br/> |<span data-ttu-id="4250a-111">作用域所适用的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="4250a-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="4250a-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="4250a-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="4250a-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="4250a-113">int, not null</span></span>  <br/> |<span data-ttu-id="4250a-114">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="4250a-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="4250a-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="4250a-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="4250a-116">位, not null</span><span class="sxs-lookup"><span data-stu-id="4250a-116">bit, not null</span></span>  <br/> |<span data-ttu-id="4250a-117">如果范围的类型为 "拒绝", 则为 True;如果允许, 则为 False。</span><span class="sxs-lookup"><span data-stu-id="4250a-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="4250a-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="4250a-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="4250a-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="4250a-119">int, not null</span></span>  <br/> |<span data-ttu-id="4250a-120">上次更新此条目的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="4250a-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="4250a-121">**标示**</span><span class="sxs-lookup"><span data-stu-id="4250a-121">**Keys**</span></span>

|<span data-ttu-id="4250a-122">**列**</span><span class="sxs-lookup"><span data-stu-id="4250a-122">**Column**</span></span>|<span data-ttu-id="4250a-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="4250a-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4250a-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="4250a-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="4250a-125">主键。</span><span class="sxs-lookup"><span data-stu-id="4250a-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="4250a-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="4250a-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="4250a-127">带有 tblNode 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="4250a-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="4250a-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="4250a-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="4250a-129">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="4250a-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

