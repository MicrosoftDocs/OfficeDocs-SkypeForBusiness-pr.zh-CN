---
title: tblADCookie
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie 包含当前的轻型目录访问协议 (LDAP) 同步 cookie。
ms.openlocfilehash: bc2c0657caa66a0420bc493bf4b688a2a081db36
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tbladcookie"></a><span data-ttu-id="bbd65-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="bbd65-103">tblADCookie</span></span>
 
<span data-ttu-id="bbd65-104">tblADCookie 包含当前的轻型目录访问协议 (LDAP) 同步 cookie。</span><span class="sxs-lookup"><span data-stu-id="bbd65-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="bbd65-105">**列**</span><span class="sxs-lookup"><span data-stu-id="bbd65-105">**Columns**</span></span>

|<span data-ttu-id="bbd65-106">**列**</span><span class="sxs-lookup"><span data-stu-id="bbd65-106">**Column**</span></span>|<span data-ttu-id="bbd65-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="bbd65-107">**Type**</span></span>|<span data-ttu-id="bbd65-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="bbd65-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bbd65-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="bbd65-109">prinGuid</span></span>  <br/> |<span data-ttu-id="bbd65-110">GUID，不为空</span><span class="sxs-lookup"><span data-stu-id="bbd65-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="bbd65-111">被监视的域主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="bbd65-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="bbd65-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="bbd65-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="bbd65-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="bbd65-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="bbd65-114">活动目录域服务同步所用的当前域控制器的完全限定的域名称 (FQDN)。有信息的价值。</span><span class="sxs-lookup"><span data-stu-id="bbd65-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="bbd65-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="bbd65-115">adcContent</span></span>  <br/> |<span data-ttu-id="bbd65-116">图像 （二进制）</span><span class="sxs-lookup"><span data-stu-id="bbd65-116">image (binary)</span></span>  <br/> |<span data-ttu-id="bbd65-117">活动目录同步 cookie。</span><span class="sxs-lookup"><span data-stu-id="bbd65-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="bbd65-118">上次更新</span><span class="sxs-lookup"><span data-stu-id="bbd65-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="bbd65-119">datetime</span><span class="sxs-lookup"><span data-stu-id="bbd65-119">datetime</span></span>  <br/> |<span data-ttu-id="bbd65-120">行更新时间的时间戳。</span><span class="sxs-lookup"><span data-stu-id="bbd65-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="bbd65-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="bbd65-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="bbd65-122">datetime</span><span class="sxs-lookup"><span data-stu-id="bbd65-122">datetime</span></span>  <br/> |<span data-ttu-id="bbd65-123">行被锁定的更改时间。</span><span class="sxs-lookup"><span data-stu-id="bbd65-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="bbd65-124">这是确保，只有一个聊天服务，看看活动目录同步时间的软件互锁机制的一部分。</span><span class="sxs-lookup"><span data-stu-id="bbd65-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="bbd65-125">**密钥**</span><span class="sxs-lookup"><span data-stu-id="bbd65-125">**Keys**</span></span>

|<span data-ttu-id="bbd65-126">**列**</span><span class="sxs-lookup"><span data-stu-id="bbd65-126">**Column(s)**</span></span>|<span data-ttu-id="bbd65-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="bbd65-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bbd65-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="bbd65-128">prinGuid</span></span>  <br/> |<span data-ttu-id="bbd65-129">为主键。</span><span class="sxs-lookup"><span data-stu-id="bbd65-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="bbd65-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="bbd65-130">prinGuid</span></span>  <br/> |<span data-ttu-id="bbd65-131">Principal.prinGuid 表中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="bbd65-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

