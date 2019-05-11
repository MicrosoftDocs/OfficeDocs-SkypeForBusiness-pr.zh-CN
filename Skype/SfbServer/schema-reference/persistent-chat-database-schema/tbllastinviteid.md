---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId 包含为每个用户生成 （并用于 tblPrincipalInvites 表） 的上一个邀请 ID。
ms.openlocfilehash: f57ca67a91b71b9245644a53eb3e5c5771ca6fb0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929901"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="29ffb-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="29ffb-103">tblLastInviteId</span></span>
 
<span data-ttu-id="29ffb-104">tblLastInviteId 包含为每个用户生成 （并用于 tblPrincipalInvites 表） 的上一个邀请 ID。</span><span class="sxs-lookup"><span data-stu-id="29ffb-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="29ffb-105">**列**</span><span class="sxs-lookup"><span data-stu-id="29ffb-105">**Columns**</span></span>

|<span data-ttu-id="29ffb-106">**列**</span><span class="sxs-lookup"><span data-stu-id="29ffb-106">**Column**</span></span>|<span data-ttu-id="29ffb-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="29ffb-107">**Type**</span></span>|<span data-ttu-id="29ffb-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="29ffb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="29ffb-109">prinID</span><span class="sxs-lookup"><span data-stu-id="29ffb-109">prinID</span></span>  <br/> |<span data-ttu-id="29ffb-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="29ffb-110">int, not null</span></span>  <br/> |<span data-ttu-id="29ffb-111">主体 id。</span><span class="sxs-lookup"><span data-stu-id="29ffb-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="29ffb-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="29ffb-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="29ffb-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="29ffb-113">int, not null</span></span>  <br/> |<span data-ttu-id="29ffb-114">上次使用的邀请 id。</span><span class="sxs-lookup"><span data-stu-id="29ffb-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="29ffb-115">**键**</span><span class="sxs-lookup"><span data-stu-id="29ffb-115">**Keys**</span></span>

|<span data-ttu-id="29ffb-116">**列**</span><span class="sxs-lookup"><span data-stu-id="29ffb-116">**Column**</span></span>|<span data-ttu-id="29ffb-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="29ffb-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="29ffb-118">prinID</span><span class="sxs-lookup"><span data-stu-id="29ffb-118">prinID</span></span>  <br/> |<span data-ttu-id="29ffb-119">主键。</span><span class="sxs-lookup"><span data-stu-id="29ffb-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="29ffb-120">prinID</span><span class="sxs-lookup"><span data-stu-id="29ffb-120">prinID</span></span>  <br/> |<span data-ttu-id="29ffb-121">在 tblPrincipal.prinID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="29ffb-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="29ffb-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29ffb-122">See also</span></span>

[<span data-ttu-id="29ffb-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="29ffb-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
