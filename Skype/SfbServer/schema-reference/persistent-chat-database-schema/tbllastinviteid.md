---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId 包含为每位用户生成（并在 tblPrincipalInvites 表中使用）的最后一个邀请 ID。
ms.openlocfilehash: 17d1b725da034f79f8efc9ff9071c36430efde7d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814570"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="79d4c-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="79d4c-103">tblLastInviteId</span></span>
 
<span data-ttu-id="79d4c-104">tblLastInviteId 包含为每位用户生成（并在 tblPrincipalInvites 表中使用）的最后一个邀请 ID。</span><span class="sxs-lookup"><span data-stu-id="79d4c-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="79d4c-105">**多**</span><span class="sxs-lookup"><span data-stu-id="79d4c-105">**Columns**</span></span>

|<span data-ttu-id="79d4c-106">**列**</span><span class="sxs-lookup"><span data-stu-id="79d4c-106">**Column**</span></span>|<span data-ttu-id="79d4c-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="79d4c-107">**Type**</span></span>|<span data-ttu-id="79d4c-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="79d4c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="79d4c-109">prinID</span><span class="sxs-lookup"><span data-stu-id="79d4c-109">prinID</span></span>  <br/> |<span data-ttu-id="79d4c-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="79d4c-110">int, not null</span></span>  <br/> |<span data-ttu-id="79d4c-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="79d4c-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="79d4c-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="79d4c-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="79d4c-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="79d4c-113">int, not null</span></span>  <br/> |<span data-ttu-id="79d4c-114">上次使用的邀请 ID。</span><span class="sxs-lookup"><span data-stu-id="79d4c-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="79d4c-115">**标示**</span><span class="sxs-lookup"><span data-stu-id="79d4c-115">**Keys**</span></span>

|<span data-ttu-id="79d4c-116">**列**</span><span class="sxs-lookup"><span data-stu-id="79d4c-116">**Column**</span></span>|<span data-ttu-id="79d4c-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="79d4c-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="79d4c-118">prinID</span><span class="sxs-lookup"><span data-stu-id="79d4c-118">prinID</span></span>  <br/> |<span data-ttu-id="79d4c-119">主键。</span><span class="sxs-lookup"><span data-stu-id="79d4c-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="79d4c-120">prinID</span><span class="sxs-lookup"><span data-stu-id="79d4c-120">prinID</span></span>  <br/> |<span data-ttu-id="79d4c-121">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="79d4c-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="79d4c-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79d4c-122">See also</span></span>

[<span data-ttu-id="79d4c-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="79d4c-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
