---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: Principalmemberdifference 包含组的成员身份更改 （添加和删除的成员） 尚未由后面的 Active Directory 域服务同步步骤处理。
ms.openlocfilehash: 77b246e96dbd13464b5655fe87d5a10861db30c7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212444"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="65667-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="65667-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="65667-104">Principalmemberdifference 包含组的成员身份更改 （添加和删除的成员） 尚未由后面的 Active Directory 域服务同步步骤处理。</span><span class="sxs-lookup"><span data-stu-id="65667-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="65667-105">**列**</span><span class="sxs-lookup"><span data-stu-id="65667-105">**Columns**</span></span>

|<span data-ttu-id="65667-106">**列**</span><span class="sxs-lookup"><span data-stu-id="65667-106">**Column**</span></span>|<span data-ttu-id="65667-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="65667-107">**Type**</span></span>|<span data-ttu-id="65667-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="65667-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="65667-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="65667-109">prinGuid</span></span>  <br/> |<span data-ttu-id="65667-110">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="65667-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="65667-111">更改的组的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="65667-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="65667-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="65667-112">memberADPath</span></span>  <br/> |<span data-ttu-id="65667-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="65667-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="65667-114">成员的可分辨的名称。</span><span class="sxs-lookup"><span data-stu-id="65667-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="65667-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="65667-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="65667-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="65667-116">bit, not null</span></span>  <br/> |<span data-ttu-id="65667-117">如果已添加成员，则为 false。</span><span class="sxs-lookup"><span data-stu-id="65667-117">False if the member was added.</span></span> <span data-ttu-id="65667-118">如果已删除成员，则为 true。</span><span class="sxs-lookup"><span data-stu-id="65667-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="65667-119">**关键字**</span><span class="sxs-lookup"><span data-stu-id="65667-119">**Key**</span></span>

|<span data-ttu-id="65667-120">**列**</span><span class="sxs-lookup"><span data-stu-id="65667-120">**Column**</span></span>|<span data-ttu-id="65667-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="65667-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="65667-122">\<prinGuid memberADPath\></span><span class="sxs-lookup"><span data-stu-id="65667-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="65667-123">主键。</span><span class="sxs-lookup"><span data-stu-id="65667-123">Primary key.</span></span>  <br/> |
   

