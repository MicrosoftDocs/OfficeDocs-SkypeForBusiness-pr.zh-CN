---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: Principalmemberdifference 包含组的成员身份更改 （添加和删除的成员） 尚未由后面的 Active Directory 域服务同步步骤处理。
ms.openlocfilehash: 4445bc6a4b83053d7d9244fc20d0a7a8cbd01b26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902234"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="d44ed-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="d44ed-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="d44ed-104">Principalmemberdifference 包含组的成员身份更改 （添加和删除的成员） 尚未由后面的 Active Directory 域服务同步步骤处理。</span><span class="sxs-lookup"><span data-stu-id="d44ed-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="d44ed-105">**列**</span><span class="sxs-lookup"><span data-stu-id="d44ed-105">**Columns**</span></span>

|<span data-ttu-id="d44ed-106">**列**</span><span class="sxs-lookup"><span data-stu-id="d44ed-106">**Column**</span></span>|<span data-ttu-id="d44ed-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="d44ed-107">**Type**</span></span>|<span data-ttu-id="d44ed-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="d44ed-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d44ed-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="d44ed-109">prinGuid</span></span>  <br/> |<span data-ttu-id="d44ed-110">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="d44ed-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="d44ed-111">更改的组的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="d44ed-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="d44ed-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="d44ed-112">memberADPath</span></span>  <br/> |<span data-ttu-id="d44ed-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d44ed-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="d44ed-114">成员的可分辨的名称。</span><span class="sxs-lookup"><span data-stu-id="d44ed-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="d44ed-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="d44ed-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="d44ed-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="d44ed-116">bit, not null</span></span>  <br/> |<span data-ttu-id="d44ed-117">如果已添加成员，则为 false。</span><span class="sxs-lookup"><span data-stu-id="d44ed-117">False if the member was added.</span></span> <span data-ttu-id="d44ed-118">如果已删除成员，则为 true。</span><span class="sxs-lookup"><span data-stu-id="d44ed-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="d44ed-119">**关键字**</span><span class="sxs-lookup"><span data-stu-id="d44ed-119">**Key**</span></span>

|<span data-ttu-id="d44ed-120">**列**</span><span class="sxs-lookup"><span data-stu-id="d44ed-120">**Column**</span></span>|<span data-ttu-id="d44ed-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="d44ed-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d44ed-122">\<prinGuid memberADPath\></span><span class="sxs-lookup"><span data-stu-id="d44ed-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="d44ed-123">主键。</span><span class="sxs-lookup"><span data-stu-id="d44ed-123">Primary key.</span></span>  <br/> |
   

