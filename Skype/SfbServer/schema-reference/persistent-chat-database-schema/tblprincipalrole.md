---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole 包含分配至节点的显式角色。
ms.openlocfilehash: 7c144f2f531af58c7c5693b28b224a2ee4456783
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904179"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="67b70-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="67b70-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="67b70-104">tblPrincipalRole 包含分配至节点的显式角色。</span><span class="sxs-lookup"><span data-stu-id="67b70-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="67b70-105">**列**</span><span class="sxs-lookup"><span data-stu-id="67b70-105">**Columns**</span></span>

|<span data-ttu-id="67b70-106">**列**</span><span class="sxs-lookup"><span data-stu-id="67b70-106">**Column**</span></span>|<span data-ttu-id="67b70-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="67b70-107">**Type**</span></span>|<span data-ttu-id="67b70-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="67b70-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="67b70-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="67b70-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="67b70-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="67b70-110">int, not null</span></span>  <br/> |<span data-ttu-id="67b70-111">角色适用的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="67b70-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="67b70-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="67b70-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="67b70-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="67b70-113">int, not null</span></span>  <br/> |<span data-ttu-id="67b70-114">主体 id。</span><span class="sxs-lookup"><span data-stu-id="67b70-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="67b70-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="67b70-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="67b70-116">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="67b70-116">int, not null</span></span>  <br/> |<span data-ttu-id="67b70-117">角色类型 ID （来自 tblRoleType)。</span><span class="sxs-lookup"><span data-stu-id="67b70-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="67b70-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="67b70-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="67b70-119">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="67b70-119">int, not null</span></span>  <br/> |<span data-ttu-id="67b70-120">上次更新此项的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="67b70-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="67b70-121">**键**</span><span class="sxs-lookup"><span data-stu-id="67b70-121">**Keys**</span></span>

|<span data-ttu-id="67b70-122">**列**</span><span class="sxs-lookup"><span data-stu-id="67b70-122">**Column**</span></span>|<span data-ttu-id="67b70-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="67b70-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="67b70-124">\<prinRoleNodeID，prinRolePrinID prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="67b70-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="67b70-125">主键。</span><span class="sxs-lookup"><span data-stu-id="67b70-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="67b70-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="67b70-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="67b70-127">在 tblNode.nodeID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="67b70-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="67b70-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="67b70-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="67b70-129">在 tblPrincipal.prinID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="67b70-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="67b70-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="67b70-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="67b70-131">在 tblRoleType.rtypeID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="67b70-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

