---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole 包含分配至节点的显式角色。
ms.openlocfilehash: 69cfb0cb2b821064801a07510758514bb5d33128
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212451"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="aac2a-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="aac2a-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="aac2a-104">tblPrincipalRole 包含分配至节点的显式角色。</span><span class="sxs-lookup"><span data-stu-id="aac2a-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="aac2a-105">**列**</span><span class="sxs-lookup"><span data-stu-id="aac2a-105">**Columns**</span></span>

|<span data-ttu-id="aac2a-106">**列**</span><span class="sxs-lookup"><span data-stu-id="aac2a-106">**Column**</span></span>|<span data-ttu-id="aac2a-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="aac2a-107">**Type**</span></span>|<span data-ttu-id="aac2a-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="aac2a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aac2a-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="aac2a-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="aac2a-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="aac2a-110">int, not null</span></span>  <br/> |<span data-ttu-id="aac2a-111">角色适用的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="aac2a-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="aac2a-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="aac2a-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="aac2a-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="aac2a-113">int, not null</span></span>  <br/> |<span data-ttu-id="aac2a-114">主体 id。</span><span class="sxs-lookup"><span data-stu-id="aac2a-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="aac2a-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="aac2a-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="aac2a-116">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="aac2a-116">int, not null</span></span>  <br/> |<span data-ttu-id="aac2a-117">角色类型 ID （来自 tblRoleType)。</span><span class="sxs-lookup"><span data-stu-id="aac2a-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="aac2a-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="aac2a-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="aac2a-119">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="aac2a-119">int, not null</span></span>  <br/> |<span data-ttu-id="aac2a-120">上次更新此项的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="aac2a-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="aac2a-121">**键**</span><span class="sxs-lookup"><span data-stu-id="aac2a-121">**Keys**</span></span>

|<span data-ttu-id="aac2a-122">**列**</span><span class="sxs-lookup"><span data-stu-id="aac2a-122">**Column**</span></span>|<span data-ttu-id="aac2a-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="aac2a-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aac2a-124">\<prinRoleNodeID，prinRolePrinID prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="aac2a-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="aac2a-125">主键。</span><span class="sxs-lookup"><span data-stu-id="aac2a-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="aac2a-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="aac2a-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="aac2a-127">在 tblNode.nodeID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="aac2a-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="aac2a-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="aac2a-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="aac2a-129">在 tblPrincipal.prinID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="aac2a-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="aac2a-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="aac2a-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="aac2a-131">在 tblRoleType.rtypeID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="aac2a-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

