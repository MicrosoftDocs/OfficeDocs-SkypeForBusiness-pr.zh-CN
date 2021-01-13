---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference 包含组成员身份更改 (添加和删除) 尚未由稍后的 Active Directory 域服务同步步骤处理的成员。
ms.openlocfilehash: 8fac76f1abfbd55d13d89c96bb23a6953d38edf9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809702"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="6a3f4-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="6a3f4-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="6a3f4-104">tblPrincipalMemberDifference 包含组成员身份更改 (添加和删除) 尚未由稍后的 Active Directory 域服务同步步骤处理的成员。</span><span class="sxs-lookup"><span data-stu-id="6a3f4-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="6a3f4-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="6a3f4-105">**Columns**</span></span>

|<span data-ttu-id="6a3f4-106">**列**</span><span class="sxs-lookup"><span data-stu-id="6a3f4-106">**Column**</span></span>|<span data-ttu-id="6a3f4-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="6a3f4-107">**Type**</span></span>|<span data-ttu-id="6a3f4-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="6a3f4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6a3f4-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="6a3f4-109">prinGuid</span></span>  <br/> |<span data-ttu-id="6a3f4-110">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="6a3f4-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="6a3f4-111">更改的组的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="6a3f4-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="6a3f4-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="6a3f4-112">memberADPath</span></span>  <br/> |<span data-ttu-id="6a3f4-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6a3f4-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="6a3f4-114">成员的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="6a3f4-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="6a3f4-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="6a3f4-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="6a3f4-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="6a3f4-116">bit, not null</span></span>  <br/> |<span data-ttu-id="6a3f4-p101">在添加成员时，设置为 False。在删除成员时，设置为 True。</span><span class="sxs-lookup"><span data-stu-id="6a3f4-p101">False if the member was added. True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="6a3f4-119">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="6a3f4-119">**Key**</span></span>

|<span data-ttu-id="6a3f4-120">**列**</span><span class="sxs-lookup"><span data-stu-id="6a3f4-120">**Column**</span></span>|<span data-ttu-id="6a3f4-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="6a3f4-121">**Description**</span></span>|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |<span data-ttu-id="6a3f4-122">主键。</span><span class="sxs-lookup"><span data-stu-id="6a3f4-122">Primary key.</span></span>  <br/> |
   

