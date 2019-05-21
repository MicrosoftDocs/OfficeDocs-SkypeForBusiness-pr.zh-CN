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
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId 包含为每位用户生成 (并在 tblPrincipalInvites 表中使用) 的最后一个邀请 ID。
ms.openlocfilehash: f36b0824bb8e9dbf2cb0aa14575cc1649bde708a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295354"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="3371e-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="3371e-103">tblLastInviteId</span></span>
 
<span data-ttu-id="3371e-104">tblLastInviteId 包含为每位用户生成 (并在 tblPrincipalInvites 表中使用) 的最后一个邀请 ID。</span><span class="sxs-lookup"><span data-stu-id="3371e-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="3371e-105">**多**</span><span class="sxs-lookup"><span data-stu-id="3371e-105">**Columns**</span></span>

|<span data-ttu-id="3371e-106">**列**</span><span class="sxs-lookup"><span data-stu-id="3371e-106">**Column**</span></span>|<span data-ttu-id="3371e-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="3371e-107">**Type**</span></span>|<span data-ttu-id="3371e-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="3371e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3371e-109">prinID</span><span class="sxs-lookup"><span data-stu-id="3371e-109">prinID</span></span>  <br/> |<span data-ttu-id="3371e-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="3371e-110">int, not null</span></span>  <br/> |<span data-ttu-id="3371e-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="3371e-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="3371e-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="3371e-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="3371e-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="3371e-113">int, not null</span></span>  <br/> |<span data-ttu-id="3371e-114">上次使用的邀请 ID。</span><span class="sxs-lookup"><span data-stu-id="3371e-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="3371e-115">**标示**</span><span class="sxs-lookup"><span data-stu-id="3371e-115">**Keys**</span></span>

|<span data-ttu-id="3371e-116">**列**</span><span class="sxs-lookup"><span data-stu-id="3371e-116">**Column**</span></span>|<span data-ttu-id="3371e-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="3371e-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3371e-118">prinID</span><span class="sxs-lookup"><span data-stu-id="3371e-118">prinID</span></span>  <br/> |<span data-ttu-id="3371e-119">主键。</span><span class="sxs-lookup"><span data-stu-id="3371e-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="3371e-120">prinID</span><span class="sxs-lookup"><span data-stu-id="3371e-120">prinID</span></span>  <br/> |<span data-ttu-id="3371e-121">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="3371e-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3371e-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3371e-122">See also</span></span>

[<span data-ttu-id="3371e-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="3371e-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
