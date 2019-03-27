---
title: tblADCookie
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie 包含当前轻型目录访问协议 (LDAP) 同步 cookie。
ms.openlocfilehash: 3e7eeeeae6623bbbb308f4e05c4ab8a4b9a7be50
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890978"
---
# <a name="tbladcookie"></a><span data-ttu-id="e3fd4-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="e3fd4-103">tblADCookie</span></span>
 
<span data-ttu-id="e3fd4-104">tblADCookie 包含当前轻型目录访问协议 (LDAP) 同步 cookie。</span><span class="sxs-lookup"><span data-stu-id="e3fd4-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="e3fd4-105">**列**</span><span class="sxs-lookup"><span data-stu-id="e3fd4-105">**Columns**</span></span>

|<span data-ttu-id="e3fd4-106">**列**</span><span class="sxs-lookup"><span data-stu-id="e3fd4-106">**Column**</span></span>|<span data-ttu-id="e3fd4-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="e3fd4-107">**Type**</span></span>|<span data-ttu-id="e3fd4-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="e3fd4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e3fd4-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e3fd4-109">prinGuid</span></span>  <br/> |<span data-ttu-id="e3fd4-110">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="e3fd4-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="e3fd4-111">要监控的域的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="e3fd4-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="e3fd4-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="e3fd4-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="e3fd4-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="e3fd4-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="e3fd4-114">完全限定的域名 (FQDN) 的当前用于 Active Directory 域服务同步的域控制器。具有信息的价值。</span><span class="sxs-lookup"><span data-stu-id="e3fd4-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="e3fd4-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="e3fd4-115">adcContent</span></span>  <br/> |<span data-ttu-id="e3fd4-116">图像 （二进制）</span><span class="sxs-lookup"><span data-stu-id="e3fd4-116">image (binary)</span></span>  <br/> |<span data-ttu-id="e3fd4-117">Active Directory 同步 cookie。</span><span class="sxs-lookup"><span data-stu-id="e3fd4-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="e3fd4-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="e3fd4-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="e3fd4-119">datetime</span><span class="sxs-lookup"><span data-stu-id="e3fd4-119">datetime</span></span>  <br/> |<span data-ttu-id="e3fd4-120">具有行更新时间的时间戳。</span><span class="sxs-lookup"><span data-stu-id="e3fd4-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="e3fd4-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="e3fd4-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="e3fd4-122">datetime</span><span class="sxs-lookup"><span data-stu-id="e3fd4-122">datetime</span></span>  <br/> |<span data-ttu-id="e3fd4-123">行锁定更改时间。</span><span class="sxs-lookup"><span data-stu-id="e3fd4-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="e3fd4-124">这是软件互锁机制，以确保只有一个聊天服务的每次执行 Active Directory 同步的一部分。</span><span class="sxs-lookup"><span data-stu-id="e3fd4-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="e3fd4-125">**键**</span><span class="sxs-lookup"><span data-stu-id="e3fd4-125">**Keys**</span></span>

|<span data-ttu-id="e3fd4-126">**列**</span><span class="sxs-lookup"><span data-stu-id="e3fd4-126">**Column(s)**</span></span>|<span data-ttu-id="e3fd4-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="e3fd4-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e3fd4-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e3fd4-128">prinGuid</span></span>  <br/> |<span data-ttu-id="e3fd4-129">主键。</span><span class="sxs-lookup"><span data-stu-id="e3fd4-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e3fd4-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e3fd4-130">prinGuid</span></span>  <br/> |<span data-ttu-id="e3fd4-131">在 Principal.prinGuid 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="e3fd4-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

