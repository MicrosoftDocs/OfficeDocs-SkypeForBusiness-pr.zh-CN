---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie 包含当前轻型目录访问协议 (LDAP) 同步 Cookie。
ms.openlocfilehash: 78a477399da811e674bb5a4493e61100acdd4782
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814752"
---
# <a name="tbladcookie"></a><span data-ttu-id="51c4d-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="51c4d-103">tblADCookie</span></span>
 
<span data-ttu-id="51c4d-104">tblADCookie 包含当前轻型目录访问协议 (LDAP) 同步 Cookie。</span><span class="sxs-lookup"><span data-stu-id="51c4d-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="51c4d-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="51c4d-105">**Columns**</span></span>

|<span data-ttu-id="51c4d-106">**列**</span><span class="sxs-lookup"><span data-stu-id="51c4d-106">**Column**</span></span>|<span data-ttu-id="51c4d-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="51c4d-107">**Type**</span></span>|<span data-ttu-id="51c4d-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="51c4d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="51c4d-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="51c4d-109">prinGuid</span></span>  <br/> |<span data-ttu-id="51c4d-110">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="51c4d-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="51c4d-111">要监控的域的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="51c4d-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="51c4d-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="51c4d-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="51c4d-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="51c4d-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="51c4d-114">用于 Active Directory 域 () 当前域控制器的 FQDN 的完全限定域名。具有信息性值。</span><span class="sxs-lookup"><span data-stu-id="51c4d-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="51c4d-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="51c4d-115">adcContent</span></span>  <br/> |<span data-ttu-id="51c4d-116">image (binary)</span><span class="sxs-lookup"><span data-stu-id="51c4d-116">image (binary)</span></span>  <br/> |<span data-ttu-id="51c4d-117">Active Directory 同步 Cookie。</span><span class="sxs-lookup"><span data-stu-id="51c4d-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="51c4d-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="51c4d-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="51c4d-119">datetime</span><span class="sxs-lookup"><span data-stu-id="51c4d-119">datetime</span></span>  <br/> |<span data-ttu-id="51c4d-120">具有行更新时间的时间戳。</span><span class="sxs-lookup"><span data-stu-id="51c4d-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="51c4d-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="51c4d-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="51c4d-122">datetime</span><span class="sxs-lookup"><span data-stu-id="51c4d-122">datetime</span></span>  <br/> |<span data-ttu-id="51c4d-p101">为更改锁定行的截止时间。此时间是软件联锁机制的一部分，可确保一次仅使其中一个聊天服务执行 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="51c4d-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="51c4d-125">**Keys**</span><span class="sxs-lookup"><span data-stu-id="51c4d-125">**Keys**</span></span>

|<span data-ttu-id="51c4d-126">**列 ()**</span><span class="sxs-lookup"><span data-stu-id="51c4d-126">**Column(s)**</span></span>|<span data-ttu-id="51c4d-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="51c4d-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="51c4d-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="51c4d-128">prinGuid</span></span>  <br/> |<span data-ttu-id="51c4d-129">主键。</span><span class="sxs-lookup"><span data-stu-id="51c4d-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="51c4d-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="51c4d-130">prinGuid</span></span>  <br/> |<span data-ttu-id="51c4d-131">其查找包含在 Principal.prinGuid 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="51c4d-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

