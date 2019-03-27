---
title: tblLastInviteId
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId 包含为每个用户生成 （并用于 tblPrincipalInvites 表） 的上一个邀请 ID。
ms.openlocfilehash: 977911150992b2e90b7dc344af0550a25ad77221
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873935"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="af928-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="af928-103">tblLastInviteId</span></span>
 
<span data-ttu-id="af928-104">tblLastInviteId 包含为每个用户生成 （并用于 tblPrincipalInvites 表） 的上一个邀请 ID。</span><span class="sxs-lookup"><span data-stu-id="af928-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="af928-105">**列**</span><span class="sxs-lookup"><span data-stu-id="af928-105">**Columns**</span></span>

|<span data-ttu-id="af928-106">**列**</span><span class="sxs-lookup"><span data-stu-id="af928-106">**Column**</span></span>|<span data-ttu-id="af928-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="af928-107">**Type**</span></span>|<span data-ttu-id="af928-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="af928-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="af928-109">prinID</span><span class="sxs-lookup"><span data-stu-id="af928-109">prinID</span></span>  <br/> |<span data-ttu-id="af928-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="af928-110">int, not null</span></span>  <br/> |<span data-ttu-id="af928-111">主体 id。</span><span class="sxs-lookup"><span data-stu-id="af928-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="af928-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="af928-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="af928-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="af928-113">int, not null</span></span>  <br/> |<span data-ttu-id="af928-114">上次使用的邀请 id。</span><span class="sxs-lookup"><span data-stu-id="af928-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="af928-115">**键**</span><span class="sxs-lookup"><span data-stu-id="af928-115">**Keys**</span></span>

|<span data-ttu-id="af928-116">**列**</span><span class="sxs-lookup"><span data-stu-id="af928-116">**Column**</span></span>|<span data-ttu-id="af928-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="af928-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="af928-118">prinID</span><span class="sxs-lookup"><span data-stu-id="af928-118">prinID</span></span>  <br/> |<span data-ttu-id="af928-119">主键。</span><span class="sxs-lookup"><span data-stu-id="af928-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="af928-120">prinID</span><span class="sxs-lookup"><span data-stu-id="af928-120">prinID</span></span>  <br/> |<span data-ttu-id="af928-121">在 tblPrincipal.prinID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="af928-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="af928-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af928-122">See also</span></span>

[<span data-ttu-id="af928-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="af928-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
