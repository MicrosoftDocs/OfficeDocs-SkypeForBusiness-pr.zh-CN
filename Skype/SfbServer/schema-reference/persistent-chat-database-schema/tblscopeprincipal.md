---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal 包含分配至节点。
ms.openlocfilehash: e93b92280605dfe01f288435c7cb42b724c22064
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885622"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="5ead8-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="5ead8-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="5ead8-104">tblScopePrincipal 包含分配至节点。</span><span class="sxs-lookup"><span data-stu-id="5ead8-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="5ead8-105">**列**</span><span class="sxs-lookup"><span data-stu-id="5ead8-105">**Columns**</span></span>

|<span data-ttu-id="5ead8-106">**列**</span><span class="sxs-lookup"><span data-stu-id="5ead8-106">**Column**</span></span>|<span data-ttu-id="5ead8-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="5ead8-107">**Type**</span></span>|<span data-ttu-id="5ead8-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="5ead8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5ead8-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="5ead8-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="5ead8-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="5ead8-110">int, not null</span></span>  <br/> |<span data-ttu-id="5ead8-111">作用域适用的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="5ead8-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="5ead8-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="5ead8-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="5ead8-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="5ead8-113">int, not null</span></span>  <br/> |<span data-ttu-id="5ead8-114">主体 id。</span><span class="sxs-lookup"><span data-stu-id="5ead8-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="5ead8-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="5ead8-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="5ead8-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="5ead8-116">bit, not null</span></span>  <br/> |<span data-ttu-id="5ead8-117">作用域的类型为 Deny; 时为 true允许则为 false。</span><span class="sxs-lookup"><span data-stu-id="5ead8-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="5ead8-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="5ead8-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="5ead8-119">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="5ead8-119">int, not null</span></span>  <br/> |<span data-ttu-id="5ead8-120">上次更新此项的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="5ead8-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="5ead8-121">**键**</span><span class="sxs-lookup"><span data-stu-id="5ead8-121">**Keys**</span></span>

|<span data-ttu-id="5ead8-122">**列**</span><span class="sxs-lookup"><span data-stu-id="5ead8-122">**Column**</span></span>|<span data-ttu-id="5ead8-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="5ead8-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5ead8-124">\<scopeNodeID scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="5ead8-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="5ead8-125">主键。</span><span class="sxs-lookup"><span data-stu-id="5ead8-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5ead8-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="5ead8-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="5ead8-127">在 tblNode.nodeID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="5ead8-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="5ead8-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="5ead8-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="5ead8-129">在 tblPrincipal.prinID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="5ead8-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

