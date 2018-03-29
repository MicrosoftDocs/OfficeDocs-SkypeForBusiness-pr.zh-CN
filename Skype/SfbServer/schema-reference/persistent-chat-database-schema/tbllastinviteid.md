---
title: tblLastInviteId
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId 包含已生成 （和 tblPrincipalInvites 表中） 的最后一次邀请 ID 为每个用户。
ms.openlocfilehash: 55eb9d9f5edbb3cc0e8c786b650e51cdc1e3d141
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastinviteid"></a><span data-ttu-id="12fa2-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="12fa2-103">tblLastInviteId</span></span>
 
<span data-ttu-id="12fa2-104">tblLastInviteId 包含已生成 （和 tblPrincipalInvites 表中） 的最后一次邀请 ID 为每个用户。</span><span class="sxs-lookup"><span data-stu-id="12fa2-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="12fa2-105">**列**</span><span class="sxs-lookup"><span data-stu-id="12fa2-105">**Columns**</span></span>

|<span data-ttu-id="12fa2-106">**列**</span><span class="sxs-lookup"><span data-stu-id="12fa2-106">**Column**</span></span>|<span data-ttu-id="12fa2-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="12fa2-107">**Type**</span></span>|<span data-ttu-id="12fa2-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="12fa2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="12fa2-109">prinID</span><span class="sxs-lookup"><span data-stu-id="12fa2-109">prinID</span></span>  <br/> |<span data-ttu-id="12fa2-110">int，不为空</span><span class="sxs-lookup"><span data-stu-id="12fa2-110">int, not null</span></span>  <br/> |<span data-ttu-id="12fa2-111">主体标识。</span><span class="sxs-lookup"><span data-stu-id="12fa2-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="12fa2-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="12fa2-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="12fa2-113">int，不为空</span><span class="sxs-lookup"><span data-stu-id="12fa2-113">int, not null</span></span>  <br/> |<span data-ttu-id="12fa2-114">最后用的邀请 id。</span><span class="sxs-lookup"><span data-stu-id="12fa2-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="12fa2-115">**密钥**</span><span class="sxs-lookup"><span data-stu-id="12fa2-115">**Keys**</span></span>

|<span data-ttu-id="12fa2-116">**列**</span><span class="sxs-lookup"><span data-stu-id="12fa2-116">**Column**</span></span>|<span data-ttu-id="12fa2-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="12fa2-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="12fa2-118">prinID</span><span class="sxs-lookup"><span data-stu-id="12fa2-118">prinID</span></span>  <br/> |<span data-ttu-id="12fa2-119">为主键。</span><span class="sxs-lookup"><span data-stu-id="12fa2-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="12fa2-120">prinID</span><span class="sxs-lookup"><span data-stu-id="12fa2-120">prinID</span></span>  <br/> |<span data-ttu-id="12fa2-121">TblPrincipal.prinID 表中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="12fa2-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="12fa2-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12fa2-122">See also</span></span>

#### 

[<span data-ttu-id="12fa2-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="12fa2-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)

