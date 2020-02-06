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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie 包含当前的轻型目录访问协议（LDAP）同步 cookie。
ms.openlocfilehash: c9a4c666a5fe4a76ecb3685f60f1208ec3ea88ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814700"
---
# <a name="tbladcookie"></a><span data-ttu-id="2cfa3-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="2cfa3-103">tblADCookie</span></span>
 
<span data-ttu-id="2cfa3-104">tblADCookie 包含当前的轻型目录访问协议（LDAP）同步 cookie。</span><span class="sxs-lookup"><span data-stu-id="2cfa3-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="2cfa3-105">**多**</span><span class="sxs-lookup"><span data-stu-id="2cfa3-105">**Columns**</span></span>

|<span data-ttu-id="2cfa3-106">**列**</span><span class="sxs-lookup"><span data-stu-id="2cfa3-106">**Column**</span></span>|<span data-ttu-id="2cfa3-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="2cfa3-107">**Type**</span></span>|<span data-ttu-id="2cfa3-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="2cfa3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2cfa3-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2cfa3-109">prinGuid</span></span>  <br/> |<span data-ttu-id="2cfa3-110">GUID，not null</span><span class="sxs-lookup"><span data-stu-id="2cfa3-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="2cfa3-111">正在监视的域的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="2cfa3-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="2cfa3-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="2cfa3-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="2cfa3-113">nvarchar （255）</span><span class="sxs-lookup"><span data-stu-id="2cfa3-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="2cfa3-114">用于 Active Directory 域服务同步的当前域控制器的完全限定的域名（FQDN）。有信息值。</span><span class="sxs-lookup"><span data-stu-id="2cfa3-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="2cfa3-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="2cfa3-115">adcContent</span></span>  <br/> |<span data-ttu-id="2cfa3-116">图像（二进制）</span><span class="sxs-lookup"><span data-stu-id="2cfa3-116">image (binary)</span></span>  <br/> |<span data-ttu-id="2cfa3-117">Active Directory 同步 cookie。</span><span class="sxs-lookup"><span data-stu-id="2cfa3-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="2cfa3-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="2cfa3-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="2cfa3-119">datetime</span><span class="sxs-lookup"><span data-stu-id="2cfa3-119">datetime</span></span>  <br/> |<span data-ttu-id="2cfa3-120">带有行更新时间的时间戳。</span><span class="sxs-lookup"><span data-stu-id="2cfa3-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="2cfa3-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="2cfa3-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="2cfa3-122">datetime</span><span class="sxs-lookup"><span data-stu-id="2cfa3-122">datetime</span></span>  <br/> |<span data-ttu-id="2cfa3-123">对行进行更改锁定的时间。</span><span class="sxs-lookup"><span data-stu-id="2cfa3-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="2cfa3-124">这是一种软件互操作机制的一部分，可确保每次只有一个聊天服务执行 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="2cfa3-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="2cfa3-125">**标示**</span><span class="sxs-lookup"><span data-stu-id="2cfa3-125">**Keys**</span></span>

|<span data-ttu-id="2cfa3-126">**列**</span><span class="sxs-lookup"><span data-stu-id="2cfa3-126">**Column(s)**</span></span>|<span data-ttu-id="2cfa3-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="2cfa3-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2cfa3-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2cfa3-128">prinGuid</span></span>  <br/> |<span data-ttu-id="2cfa3-129">主键。</span><span class="sxs-lookup"><span data-stu-id="2cfa3-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="2cfa3-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2cfa3-130">prinGuid</span></span>  <br/> |<span data-ttu-id="2cfa3-131">PrinGuid 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="2cfa3-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

