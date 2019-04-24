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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213156"
---
# <a name="tbladcookie"></a><span data-ttu-id="adc0c-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="adc0c-103">tblADCookie</span></span>
 
<span data-ttu-id="adc0c-104">tblADCookie 包含当前轻型目录访问协议 (LDAP) 同步 cookie。</span><span class="sxs-lookup"><span data-stu-id="adc0c-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="adc0c-105">**列**</span><span class="sxs-lookup"><span data-stu-id="adc0c-105">**Columns**</span></span>

|<span data-ttu-id="adc0c-106">**列**</span><span class="sxs-lookup"><span data-stu-id="adc0c-106">**Column**</span></span>|<span data-ttu-id="adc0c-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="adc0c-107">**Type**</span></span>|<span data-ttu-id="adc0c-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="adc0c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="adc0c-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="adc0c-109">prinGuid</span></span>  <br/> |<span data-ttu-id="adc0c-110">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="adc0c-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="adc0c-111">要监控的域的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="adc0c-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="adc0c-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="adc0c-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="adc0c-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="adc0c-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="adc0c-114">完全限定的域名 (FQDN) 的当前用于 Active Directory 域服务同步的域控制器。具有信息的价值。</span><span class="sxs-lookup"><span data-stu-id="adc0c-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="adc0c-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="adc0c-115">adcContent</span></span>  <br/> |<span data-ttu-id="adc0c-116">图像 （二进制）</span><span class="sxs-lookup"><span data-stu-id="adc0c-116">image (binary)</span></span>  <br/> |<span data-ttu-id="adc0c-117">Active Directory 同步 cookie。</span><span class="sxs-lookup"><span data-stu-id="adc0c-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="adc0c-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="adc0c-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="adc0c-119">datetime</span><span class="sxs-lookup"><span data-stu-id="adc0c-119">datetime</span></span>  <br/> |<span data-ttu-id="adc0c-120">具有行更新时间的时间戳。</span><span class="sxs-lookup"><span data-stu-id="adc0c-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="adc0c-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="adc0c-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="adc0c-122">datetime</span><span class="sxs-lookup"><span data-stu-id="adc0c-122">datetime</span></span>  <br/> |<span data-ttu-id="adc0c-123">行锁定更改时间。</span><span class="sxs-lookup"><span data-stu-id="adc0c-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="adc0c-124">这是软件互锁机制，以确保只有一个聊天服务的每次执行 Active Directory 同步的一部分。</span><span class="sxs-lookup"><span data-stu-id="adc0c-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="adc0c-125">**键**</span><span class="sxs-lookup"><span data-stu-id="adc0c-125">**Keys**</span></span>

|<span data-ttu-id="adc0c-126">**列**</span><span class="sxs-lookup"><span data-stu-id="adc0c-126">**Column(s)**</span></span>|<span data-ttu-id="adc0c-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="adc0c-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="adc0c-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="adc0c-128">prinGuid</span></span>  <br/> |<span data-ttu-id="adc0c-129">主键。</span><span class="sxs-lookup"><span data-stu-id="adc0c-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="adc0c-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="adc0c-130">prinGuid</span></span>  <br/> |<span data-ttu-id="adc0c-131">在 Principal.prinGuid 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="adc0c-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

