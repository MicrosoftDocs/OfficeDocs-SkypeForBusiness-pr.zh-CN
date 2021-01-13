---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId 包含上次为每个用户生成的并且在 tblPrincipalInvites 表中使用的邀请 ID。
ms.openlocfilehash: 9d5ec67a4f5c3db8558c58834582d489fde00ab6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815962"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="984db-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="984db-103">tblLastInviteId</span></span>
 
<span data-ttu-id="984db-104">tblLastInviteId 包含上次为每个用户生成的并且在 tblPrincipalInvites 表中使用的邀请 ID。</span><span class="sxs-lookup"><span data-stu-id="984db-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="984db-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="984db-105">**Columns**</span></span>

|<span data-ttu-id="984db-106">**列**</span><span class="sxs-lookup"><span data-stu-id="984db-106">**Column**</span></span>|<span data-ttu-id="984db-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="984db-107">**Type**</span></span>|<span data-ttu-id="984db-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="984db-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="984db-109">prinID</span><span class="sxs-lookup"><span data-stu-id="984db-109">prinID</span></span>  <br/> |<span data-ttu-id="984db-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="984db-110">int, not null</span></span>  <br/> |<span data-ttu-id="984db-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="984db-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="984db-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="984db-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="984db-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="984db-113">int, not null</span></span>  <br/> |<span data-ttu-id="984db-114">上次使用的邀请 ID。</span><span class="sxs-lookup"><span data-stu-id="984db-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="984db-115">**Keys**</span><span class="sxs-lookup"><span data-stu-id="984db-115">**Keys**</span></span>

|<span data-ttu-id="984db-116">**列**</span><span class="sxs-lookup"><span data-stu-id="984db-116">**Column**</span></span>|<span data-ttu-id="984db-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="984db-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="984db-118">prinID</span><span class="sxs-lookup"><span data-stu-id="984db-118">prinID</span></span>  <br/> |<span data-ttu-id="984db-119">主键。</span><span class="sxs-lookup"><span data-stu-id="984db-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="984db-120">prinID</span><span class="sxs-lookup"><span data-stu-id="984db-120">prinID</span></span>  <br/> |<span data-ttu-id="984db-121">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="984db-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="984db-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="984db-122">See also</span></span>

[<span data-ttu-id="984db-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="984db-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
