---
title: tblScopePrincipal
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal 包含分配给节点的作用。
ms.openlocfilehash: ba2927598cdff07368cb017866ec41bfa7540f48
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="12178-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="12178-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="12178-104">tblScopePrincipal 包含分配给节点的作用。</span><span class="sxs-lookup"><span data-stu-id="12178-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="12178-105">**列**</span><span class="sxs-lookup"><span data-stu-id="12178-105">**Columns**</span></span>

|<span data-ttu-id="12178-106">**列**</span><span class="sxs-lookup"><span data-stu-id="12178-106">**Column**</span></span>|<span data-ttu-id="12178-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="12178-107">**Type**</span></span>|<span data-ttu-id="12178-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="12178-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="12178-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="12178-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="12178-110">int，不为空</span><span class="sxs-lookup"><span data-stu-id="12178-110">int, not null</span></span>  <br/> |<span data-ttu-id="12178-111">作用域应用到的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="12178-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="12178-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="12178-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="12178-113">int，不为空</span><span class="sxs-lookup"><span data-stu-id="12178-113">int, not null</span></span>  <br/> |<span data-ttu-id="12178-114">主体标识。</span><span class="sxs-lookup"><span data-stu-id="12178-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="12178-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="12178-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="12178-116">位，不为空</span><span class="sxs-lookup"><span data-stu-id="12178-116">bit, not null</span></span>  <br/> |<span data-ttu-id="12178-117">如果类型的作用域是拒绝;假如果允许。</span><span class="sxs-lookup"><span data-stu-id="12178-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="12178-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="12178-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="12178-119">int，不为空</span><span class="sxs-lookup"><span data-stu-id="12178-119">int, not null</span></span>  <br/> |<span data-ttu-id="12178-120">上次更新此项的主要用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="12178-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="12178-121">**密钥**</span><span class="sxs-lookup"><span data-stu-id="12178-121">**Keys**</span></span>

|<span data-ttu-id="12178-122">**列**</span><span class="sxs-lookup"><span data-stu-id="12178-122">**Column**</span></span>|<span data-ttu-id="12178-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="12178-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="12178-124">\<scopeNodeID scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="12178-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="12178-125">为主键。</span><span class="sxs-lookup"><span data-stu-id="12178-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="12178-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="12178-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="12178-127">TblNode.nodeID 表中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="12178-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="12178-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="12178-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="12178-129">TblPrincipal.prinID 表中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="12178-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

