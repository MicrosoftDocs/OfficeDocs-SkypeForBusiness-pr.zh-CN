---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal 包含分配至节点的作用域。
ms.openlocfilehash: efda792ab6f6c6cc7b188a9dffdaa7c324b24797
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831512"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="37b9c-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="37b9c-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="37b9c-104">tblScopePrincipal 包含分配至节点的作用域。</span><span class="sxs-lookup"><span data-stu-id="37b9c-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="37b9c-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="37b9c-105">**Columns**</span></span>

|<span data-ttu-id="37b9c-106">**列**</span><span class="sxs-lookup"><span data-stu-id="37b9c-106">**Column**</span></span>|<span data-ttu-id="37b9c-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="37b9c-107">**Type**</span></span>|<span data-ttu-id="37b9c-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="37b9c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="37b9c-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="37b9c-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="37b9c-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="37b9c-110">int, not null</span></span>  <br/> |<span data-ttu-id="37b9c-111">作用域适用的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="37b9c-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="37b9c-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="37b9c-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="37b9c-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="37b9c-113">int, not null</span></span>  <br/> |<span data-ttu-id="37b9c-114">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="37b9c-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="37b9c-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="37b9c-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="37b9c-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="37b9c-116">bit, not null</span></span>  <br/> |<span data-ttu-id="37b9c-117">如果作用域的类型为 Deny，则为 True；如果作用域的类型为 Allow，则为 False。</span><span class="sxs-lookup"><span data-stu-id="37b9c-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="37b9c-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="37b9c-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="37b9c-119">int, 不为 null</span><span class="sxs-lookup"><span data-stu-id="37b9c-119">int, not null</span></span>  <br/> |<span data-ttu-id="37b9c-120">上次更新此项的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="37b9c-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="37b9c-121">**Keys**</span><span class="sxs-lookup"><span data-stu-id="37b9c-121">**Keys**</span></span>

|<span data-ttu-id="37b9c-122">**列**</span><span class="sxs-lookup"><span data-stu-id="37b9c-122">**Column**</span></span>|<span data-ttu-id="37b9c-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="37b9c-123">**Description**</span></span>|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |<span data-ttu-id="37b9c-124">主键。</span><span class="sxs-lookup"><span data-stu-id="37b9c-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="37b9c-125">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="37b9c-125">scopeNodeID</span></span>  <br/> |<span data-ttu-id="37b9c-126">其查找包含在 tblNode.nodeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="37b9c-126">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="37b9c-127">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="37b9c-127">scopePrinID</span></span>  <br/> |<span data-ttu-id="37b9c-128">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="37b9c-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

