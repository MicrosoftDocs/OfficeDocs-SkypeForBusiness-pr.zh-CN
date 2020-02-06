---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference 包含后续 Active Directory 域服务同步步骤尚未处理的组成员身份更改（添加和删除的成员）。
ms.openlocfilehash: c7e965658c9e351a7a2d079921b7abe8166b48ad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814070"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="78bba-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="78bba-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="78bba-104">tblPrincipalMemberDifference 包含后续 Active Directory 域服务同步步骤尚未处理的组成员身份更改（添加和删除的成员）。</span><span class="sxs-lookup"><span data-stu-id="78bba-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="78bba-105">**多**</span><span class="sxs-lookup"><span data-stu-id="78bba-105">**Columns**</span></span>

|<span data-ttu-id="78bba-106">**列**</span><span class="sxs-lookup"><span data-stu-id="78bba-106">**Column**</span></span>|<span data-ttu-id="78bba-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="78bba-107">**Type**</span></span>|<span data-ttu-id="78bba-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="78bba-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="78bba-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="78bba-109">prinGuid</span></span>  <br/> |<span data-ttu-id="78bba-110">GUID，not null</span><span class="sxs-lookup"><span data-stu-id="78bba-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="78bba-111">已更改的组的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="78bba-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="78bba-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="78bba-112">memberADPath</span></span>  <br/> |<span data-ttu-id="78bba-113">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="78bba-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="78bba-114">成员的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="78bba-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="78bba-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="78bba-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="78bba-116">位，not null</span><span class="sxs-lookup"><span data-stu-id="78bba-116">bit, not null</span></span>  <br/> |<span data-ttu-id="78bba-117">如果添加了成员，则为 False。</span><span class="sxs-lookup"><span data-stu-id="78bba-117">False if the member was added.</span></span> <span data-ttu-id="78bba-118">如果删除了该成员，则为 True。</span><span class="sxs-lookup"><span data-stu-id="78bba-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="78bba-119">**Key**</span><span class="sxs-lookup"><span data-stu-id="78bba-119">**Key**</span></span>

|<span data-ttu-id="78bba-120">**列**</span><span class="sxs-lookup"><span data-stu-id="78bba-120">**Column**</span></span>|<span data-ttu-id="78bba-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="78bba-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="78bba-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="78bba-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="78bba-123">主键。</span><span class="sxs-lookup"><span data-stu-id="78bba-123">Primary key.</span></span>  <br/> |
   

