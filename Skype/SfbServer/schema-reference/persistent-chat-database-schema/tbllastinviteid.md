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
description: tblLastInviteId 包含为每个用户生成 （并用于 tblPrincipalInvites 表） 的上一个邀请 ID。
ms.openlocfilehash: 5f94714bfe42d6777907f3ce3e467e4add7a00d8
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504850"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="13d6d-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="13d6d-103">tblLastInviteId</span></span>
 
<span data-ttu-id="13d6d-104">tblLastInviteId 包含为每个用户生成 （并用于 tblPrincipalInvites 表） 的上一个邀请 ID。</span><span class="sxs-lookup"><span data-stu-id="13d6d-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="13d6d-105">**列**</span><span class="sxs-lookup"><span data-stu-id="13d6d-105">**Columns**</span></span>

|<span data-ttu-id="13d6d-106">**列**</span><span class="sxs-lookup"><span data-stu-id="13d6d-106">**Column**</span></span>|<span data-ttu-id="13d6d-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="13d6d-107">**Type**</span></span>|<span data-ttu-id="13d6d-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="13d6d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="13d6d-109">prinID</span><span class="sxs-lookup"><span data-stu-id="13d6d-109">prinID</span></span>  <br/> |<span data-ttu-id="13d6d-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="13d6d-110">int, not null</span></span>  <br/> |<span data-ttu-id="13d6d-111">主体 id。</span><span class="sxs-lookup"><span data-stu-id="13d6d-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="13d6d-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="13d6d-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="13d6d-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="13d6d-113">int, not null</span></span>  <br/> |<span data-ttu-id="13d6d-114">上次使用的邀请 id。</span><span class="sxs-lookup"><span data-stu-id="13d6d-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="13d6d-115">**键**</span><span class="sxs-lookup"><span data-stu-id="13d6d-115">**Keys**</span></span>

|<span data-ttu-id="13d6d-116">**列**</span><span class="sxs-lookup"><span data-stu-id="13d6d-116">**Column**</span></span>|<span data-ttu-id="13d6d-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="13d6d-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="13d6d-118">prinID</span><span class="sxs-lookup"><span data-stu-id="13d6d-118">prinID</span></span>  <br/> |<span data-ttu-id="13d6d-119">主键。</span><span class="sxs-lookup"><span data-stu-id="13d6d-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="13d6d-120">prinID</span><span class="sxs-lookup"><span data-stu-id="13d6d-120">prinID</span></span>  <br/> |<span data-ttu-id="13d6d-121">在 tblPrincipal.prinID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="13d6d-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="13d6d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13d6d-122">See also</span></span>

[<span data-ttu-id="13d6d-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="13d6d-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)