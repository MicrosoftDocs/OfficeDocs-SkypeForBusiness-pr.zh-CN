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
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole 包含分配给节点的显式角色。
ms.openlocfilehash: 9675713afba5753378f4d01b70489d0eee93b8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295235"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="20376-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="20376-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="20376-104">tblPrincipalRole 包含分配给节点的显式角色。</span><span class="sxs-lookup"><span data-stu-id="20376-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="20376-105">**多**</span><span class="sxs-lookup"><span data-stu-id="20376-105">**Columns**</span></span>

|<span data-ttu-id="20376-106">**列**</span><span class="sxs-lookup"><span data-stu-id="20376-106">**Column**</span></span>|<span data-ttu-id="20376-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="20376-107">**Type**</span></span>|<span data-ttu-id="20376-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="20376-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="20376-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="20376-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="20376-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="20376-110">int, not null</span></span>  <br/> |<span data-ttu-id="20376-111">角色所应用的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="20376-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="20376-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="20376-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="20376-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="20376-113">int, not null</span></span>  <br/> |<span data-ttu-id="20376-114">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="20376-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="20376-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="20376-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="20376-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="20376-116">int, not null</span></span>  <br/> |<span data-ttu-id="20376-117">角色类型 ID (来自 tblRoleType)。</span><span class="sxs-lookup"><span data-stu-id="20376-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="20376-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="20376-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="20376-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="20376-119">int, not null</span></span>  <br/> |<span data-ttu-id="20376-120">上次更新此条目的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="20376-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="20376-121">**标示**</span><span class="sxs-lookup"><span data-stu-id="20376-121">**Keys**</span></span>

|<span data-ttu-id="20376-122">**列**</span><span class="sxs-lookup"><span data-stu-id="20376-122">**Column**</span></span>|<span data-ttu-id="20376-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="20376-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="20376-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="20376-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="20376-125">主键。</span><span class="sxs-lookup"><span data-stu-id="20376-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="20376-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="20376-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="20376-127">带有 tblNode 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="20376-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="20376-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="20376-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="20376-129">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="20376-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="20376-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="20376-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="20376-131">TblRoleType 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="20376-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

