---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole 包含分配给节点的显式角色。
ms.openlocfilehash: 1cc606ec3825bb664d4123154e97fabb15678cfd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813360"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="a9315-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="a9315-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="a9315-104">tblPrincipalRole 包含分配给节点的显式角色。</span><span class="sxs-lookup"><span data-stu-id="a9315-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="a9315-105">**多**</span><span class="sxs-lookup"><span data-stu-id="a9315-105">**Columns**</span></span>

|<span data-ttu-id="a9315-106">**列**</span><span class="sxs-lookup"><span data-stu-id="a9315-106">**Column**</span></span>|<span data-ttu-id="a9315-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="a9315-107">**Type**</span></span>|<span data-ttu-id="a9315-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="a9315-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a9315-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="a9315-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="a9315-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="a9315-110">int, not null</span></span>  <br/> |<span data-ttu-id="a9315-111">角色所应用的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="a9315-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="a9315-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="a9315-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="a9315-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="a9315-113">int, not null</span></span>  <br/> |<span data-ttu-id="a9315-114">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="a9315-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="a9315-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="a9315-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="a9315-116">int，not null</span><span class="sxs-lookup"><span data-stu-id="a9315-116">int, not null</span></span>  <br/> |<span data-ttu-id="a9315-117">角色类型 ID （来自 tblRoleType）。</span><span class="sxs-lookup"><span data-stu-id="a9315-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="a9315-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="a9315-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="a9315-119">int，not null</span><span class="sxs-lookup"><span data-stu-id="a9315-119">int, not null</span></span>  <br/> |<span data-ttu-id="a9315-120">上次更新此条目的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="a9315-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="a9315-121">**标示**</span><span class="sxs-lookup"><span data-stu-id="a9315-121">**Keys**</span></span>

|<span data-ttu-id="a9315-122">**列**</span><span class="sxs-lookup"><span data-stu-id="a9315-122">**Column**</span></span>|<span data-ttu-id="a9315-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="a9315-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a9315-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="a9315-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="a9315-125">主键。</span><span class="sxs-lookup"><span data-stu-id="a9315-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a9315-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="a9315-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="a9315-127">带有 tblNode 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="a9315-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="a9315-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="a9315-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="a9315-129">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="a9315-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="a9315-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="a9315-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="a9315-131">TblRoleType 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="a9315-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

