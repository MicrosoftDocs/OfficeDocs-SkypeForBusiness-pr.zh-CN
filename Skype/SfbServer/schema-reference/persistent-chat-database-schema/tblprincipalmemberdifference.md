---
title: tblPrincipalMemberDifference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference 包含组成员身份的更改 （添加和删除成员） 尚未处理的后续活动目录域服务同步步骤。
ms.openlocfilehash: 603c8345f2adc2ba7d5eb04835218fd3e83d8ed4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="95fbb-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="95fbb-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="95fbb-104">tblPrincipalMemberDifference 包含组成员身份的更改 （添加和删除成员） 尚未处理的后续活动目录域服务同步步骤。</span><span class="sxs-lookup"><span data-stu-id="95fbb-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="95fbb-105">**列**</span><span class="sxs-lookup"><span data-stu-id="95fbb-105">**Columns**</span></span>

|<span data-ttu-id="95fbb-106">**列**</span><span class="sxs-lookup"><span data-stu-id="95fbb-106">**Column**</span></span>|<span data-ttu-id="95fbb-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="95fbb-107">**Type**</span></span>|<span data-ttu-id="95fbb-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="95fbb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="95fbb-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="95fbb-109">prinGuid</span></span>  <br/> |<span data-ttu-id="95fbb-110">GUID，不为空</span><span class="sxs-lookup"><span data-stu-id="95fbb-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="95fbb-111">更改组的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="95fbb-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="95fbb-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="95fbb-112">memberADPath</span></span>  <br/> |<span data-ttu-id="95fbb-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="95fbb-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="95fbb-114">成员的可分辨的名称。</span><span class="sxs-lookup"><span data-stu-id="95fbb-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="95fbb-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="95fbb-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="95fbb-116">位，不为空</span><span class="sxs-lookup"><span data-stu-id="95fbb-116">bit, not null</span></span>  <br/> |<span data-ttu-id="95fbb-117">如果添加的成员，则为 false。</span><span class="sxs-lookup"><span data-stu-id="95fbb-117">False if the member was added.</span></span> <span data-ttu-id="95fbb-118">如果成员已删除，则为 true。</span><span class="sxs-lookup"><span data-stu-id="95fbb-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="95fbb-119">**密钥**</span><span class="sxs-lookup"><span data-stu-id="95fbb-119">**Key**</span></span>

|<span data-ttu-id="95fbb-120">**列**</span><span class="sxs-lookup"><span data-stu-id="95fbb-120">**Column**</span></span>|<span data-ttu-id="95fbb-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="95fbb-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="95fbb-122">\<prinGuid memberADPath\></span><span class="sxs-lookup"><span data-stu-id="95fbb-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="95fbb-123">为主键。</span><span class="sxs-lookup"><span data-stu-id="95fbb-123">Primary key.</span></span>  <br/> |
   

