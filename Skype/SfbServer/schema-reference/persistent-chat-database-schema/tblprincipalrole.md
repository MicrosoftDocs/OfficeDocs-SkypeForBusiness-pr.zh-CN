---
title: tblPrincipalRole
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole 包含显式角色分配给节点。
ms.openlocfilehash: 0e6c7f60f372bc14542567ccaa1b1b1a837c6c6d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalrole"></a><span data-ttu-id="65215-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="65215-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="65215-104">tblPrincipalRole 包含显式角色分配给节点。</span><span class="sxs-lookup"><span data-stu-id="65215-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="65215-105">**列**</span><span class="sxs-lookup"><span data-stu-id="65215-105">**Columns**</span></span>

|<span data-ttu-id="65215-106">**列**</span><span class="sxs-lookup"><span data-stu-id="65215-106">**Column**</span></span>|<span data-ttu-id="65215-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="65215-107">**Type**</span></span>|<span data-ttu-id="65215-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="65215-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="65215-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="65215-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="65215-110">int，不为空</span><span class="sxs-lookup"><span data-stu-id="65215-110">int, not null</span></span>  <br/> |<span data-ttu-id="65215-111">该角色适用于的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="65215-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="65215-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="65215-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="65215-113">int，不为空</span><span class="sxs-lookup"><span data-stu-id="65215-113">int, not null</span></span>  <br/> |<span data-ttu-id="65215-114">主体标识。</span><span class="sxs-lookup"><span data-stu-id="65215-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="65215-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="65215-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="65215-116">int，不为空</span><span class="sxs-lookup"><span data-stu-id="65215-116">int, not null</span></span>  <br/> |<span data-ttu-id="65215-117">角色类型 ID （从 tblRoleType)。</span><span class="sxs-lookup"><span data-stu-id="65215-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="65215-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="65215-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="65215-119">int，不为空</span><span class="sxs-lookup"><span data-stu-id="65215-119">int, not null</span></span>  <br/> |<span data-ttu-id="65215-120">上次更新此项的主要用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="65215-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="65215-121">**密钥**</span><span class="sxs-lookup"><span data-stu-id="65215-121">**Keys**</span></span>

|<span data-ttu-id="65215-122">**列**</span><span class="sxs-lookup"><span data-stu-id="65215-122">**Column**</span></span>|<span data-ttu-id="65215-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="65215-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="65215-124">\<prinRoleNodeID，prinRolePrinID prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="65215-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="65215-125">为主键。</span><span class="sxs-lookup"><span data-stu-id="65215-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="65215-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="65215-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="65215-127">TblNode.nodeID 表中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="65215-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="65215-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="65215-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="65215-129">TblPrincipal.prinID 表中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="65215-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="65215-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="65215-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="65215-131">TblRoleType.rtypeID 表中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="65215-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

