---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole 包含分配给节点的显式角色。
ms.openlocfilehash: 13c9c25db9ba1dbe281947468bbd834e80417899
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831552"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="8834c-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="8834c-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="8834c-104">tblPrincipalRole 包含分配给节点的显式角色。</span><span class="sxs-lookup"><span data-stu-id="8834c-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="8834c-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="8834c-105">**Columns**</span></span>

|<span data-ttu-id="8834c-106">**列**</span><span class="sxs-lookup"><span data-stu-id="8834c-106">**Column**</span></span>|<span data-ttu-id="8834c-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="8834c-107">**Type**</span></span>|<span data-ttu-id="8834c-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="8834c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8834c-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="8834c-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="8834c-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="8834c-110">int, not null</span></span>  <br/> |<span data-ttu-id="8834c-111">角色应用于的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="8834c-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="8834c-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="8834c-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="8834c-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="8834c-113">int, not null</span></span>  <br/> |<span data-ttu-id="8834c-114">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="8834c-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="8834c-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="8834c-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="8834c-116">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="8834c-116">int, not null</span></span>  <br/> |<span data-ttu-id="8834c-117">角色类型 ID (tblRoleType) 。</span><span class="sxs-lookup"><span data-stu-id="8834c-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="8834c-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="8834c-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="8834c-119">int, 不为 null</span><span class="sxs-lookup"><span data-stu-id="8834c-119">int, not null</span></span>  <br/> |<span data-ttu-id="8834c-120">上次更新此项的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="8834c-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="8834c-121">**Keys**</span><span class="sxs-lookup"><span data-stu-id="8834c-121">**Keys**</span></span>

|<span data-ttu-id="8834c-122">**列**</span><span class="sxs-lookup"><span data-stu-id="8834c-122">**Column**</span></span>|<span data-ttu-id="8834c-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="8834c-123">**Description**</span></span>|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |<span data-ttu-id="8834c-124">主键。</span><span class="sxs-lookup"><span data-stu-id="8834c-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="8834c-125">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="8834c-125">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="8834c-126">其查找包含在 tblNode.nodeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="8834c-126">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="8834c-127">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="8834c-127">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="8834c-128">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="8834c-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="8834c-129">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="8834c-129">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="8834c-130">在 tblRoleType.rtypeID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="8834c-130">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

