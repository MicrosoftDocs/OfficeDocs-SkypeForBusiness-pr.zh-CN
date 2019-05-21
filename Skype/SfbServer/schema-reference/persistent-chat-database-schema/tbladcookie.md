---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie 包含当前的轻型目录访问协议 (LDAP) 同步 cookie。
ms.openlocfilehash: d75b1dc90d36aa0535fdac62b9e1a7061694cc76
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295529"
---
# <a name="tbladcookie"></a><span data-ttu-id="ae7b1-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="ae7b1-103">tblADCookie</span></span>
 
<span data-ttu-id="ae7b1-104">tblADCookie 包含当前的轻型目录访问协议 (LDAP) 同步 cookie。</span><span class="sxs-lookup"><span data-stu-id="ae7b1-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="ae7b1-105">**多**</span><span class="sxs-lookup"><span data-stu-id="ae7b1-105">**Columns**</span></span>

|<span data-ttu-id="ae7b1-106">**列**</span><span class="sxs-lookup"><span data-stu-id="ae7b1-106">**Column**</span></span>|<span data-ttu-id="ae7b1-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="ae7b1-107">**Type**</span></span>|<span data-ttu-id="ae7b1-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="ae7b1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ae7b1-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="ae7b1-109">prinGuid</span></span>  <br/> |<span data-ttu-id="ae7b1-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="ae7b1-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="ae7b1-111">正在监视的域的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="ae7b1-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="ae7b1-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="ae7b1-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="ae7b1-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="ae7b1-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="ae7b1-114">用于 Active Directory 域服务同步的当前域控制器的完全限定的域名 (FQDN)。有信息值。</span><span class="sxs-lookup"><span data-stu-id="ae7b1-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="ae7b1-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="ae7b1-115">adcContent</span></span>  <br/> |<span data-ttu-id="ae7b1-116">图像 (二进制)</span><span class="sxs-lookup"><span data-stu-id="ae7b1-116">image (binary)</span></span>  <br/> |<span data-ttu-id="ae7b1-117">Active Directory 同步 cookie。</span><span class="sxs-lookup"><span data-stu-id="ae7b1-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="ae7b1-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="ae7b1-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="ae7b1-119">datetime</span><span class="sxs-lookup"><span data-stu-id="ae7b1-119">datetime</span></span>  <br/> |<span data-ttu-id="ae7b1-120">带有行更新时间的时间戳。</span><span class="sxs-lookup"><span data-stu-id="ae7b1-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="ae7b1-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="ae7b1-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="ae7b1-122">datetime</span><span class="sxs-lookup"><span data-stu-id="ae7b1-122">datetime</span></span>  <br/> |<span data-ttu-id="ae7b1-123">对行进行更改锁定的时间。</span><span class="sxs-lookup"><span data-stu-id="ae7b1-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="ae7b1-124">这是一种软件互操作机制的一部分, 可确保每次只有一个聊天服务执行 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="ae7b1-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="ae7b1-125">**标示**</span><span class="sxs-lookup"><span data-stu-id="ae7b1-125">**Keys**</span></span>

|<span data-ttu-id="ae7b1-126">**列**</span><span class="sxs-lookup"><span data-stu-id="ae7b1-126">**Column(s)**</span></span>|<span data-ttu-id="ae7b1-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="ae7b1-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ae7b1-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="ae7b1-128">prinGuid</span></span>  <br/> |<span data-ttu-id="ae7b1-129">主键。</span><span class="sxs-lookup"><span data-stu-id="ae7b1-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="ae7b1-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="ae7b1-130">prinGuid</span></span>  <br/> |<span data-ttu-id="ae7b1-131">PrinGuid 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="ae7b1-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

