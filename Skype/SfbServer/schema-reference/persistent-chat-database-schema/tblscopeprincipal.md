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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212395"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="a7218-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="a7218-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="a7218-104">tblScopePrincipal 包含分配至节点。</span><span class="sxs-lookup"><span data-stu-id="a7218-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="a7218-105">**列**</span><span class="sxs-lookup"><span data-stu-id="a7218-105">**Columns**</span></span>

|<span data-ttu-id="a7218-106">**列**</span><span class="sxs-lookup"><span data-stu-id="a7218-106">**Column**</span></span>|<span data-ttu-id="a7218-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="a7218-107">**Type**</span></span>|<span data-ttu-id="a7218-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="a7218-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a7218-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="a7218-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="a7218-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="a7218-110">int, not null</span></span>  <br/> |<span data-ttu-id="a7218-111">作用域适用的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="a7218-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="a7218-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="a7218-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="a7218-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="a7218-113">int, not null</span></span>  <br/> |<span data-ttu-id="a7218-114">主体 id。</span><span class="sxs-lookup"><span data-stu-id="a7218-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="a7218-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="a7218-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="a7218-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="a7218-116">bit, not null</span></span>  <br/> |<span data-ttu-id="a7218-117">作用域的类型为 Deny; 时为 true允许则为 false。</span><span class="sxs-lookup"><span data-stu-id="a7218-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="a7218-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="a7218-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="a7218-119">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="a7218-119">int, not null</span></span>  <br/> |<span data-ttu-id="a7218-120">上次更新此项的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="a7218-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="a7218-121">**键**</span><span class="sxs-lookup"><span data-stu-id="a7218-121">**Keys**</span></span>

|<span data-ttu-id="a7218-122">**列**</span><span class="sxs-lookup"><span data-stu-id="a7218-122">**Column**</span></span>|<span data-ttu-id="a7218-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="a7218-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a7218-124">\<scopeNodeID scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="a7218-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="a7218-125">主键。</span><span class="sxs-lookup"><span data-stu-id="a7218-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a7218-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="a7218-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="a7218-127">在 tblNode.nodeID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="a7218-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="a7218-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="a7218-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="a7218-129">在 tblPrincipal.prinID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="a7218-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

