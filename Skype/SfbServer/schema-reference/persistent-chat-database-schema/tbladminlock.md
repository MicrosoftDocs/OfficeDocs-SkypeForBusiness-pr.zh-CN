---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock 包含运行一些管理员命令所需的管理员锁。
ms.openlocfilehash: aed7720a9b74483a34704c0009958ea91a786fc1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809882"
---
# <a name="tbladminlock"></a><span data-ttu-id="de15c-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="de15c-103">tblAdminLock</span></span>
 
<span data-ttu-id="de15c-104">tblAdminLock 包含运行一些管理员命令所需的管理员锁。</span><span class="sxs-lookup"><span data-stu-id="de15c-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="de15c-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="de15c-105">**Columns**</span></span>

|<span data-ttu-id="de15c-106">**列**</span><span class="sxs-lookup"><span data-stu-id="de15c-106">**Column**</span></span>|<span data-ttu-id="de15c-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="de15c-107">**Type**</span></span>|<span data-ttu-id="de15c-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="de15c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="de15c-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="de15c-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="de15c-110">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="de15c-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="de15c-p101">锁到期日期和时间。所有者可以定期延长该值。</span><span class="sxs-lookup"><span data-stu-id="de15c-p101">Lock expiration date and time. The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="de15c-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="de15c-113">lockServerID</span></span>  <br/> |<span data-ttu-id="de15c-114">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="de15c-114">int, not null</span></span>  <br/> |<span data-ttu-id="de15c-115">拥有锁的服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="de15c-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="de15c-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="de15c-116">lockActorID</span></span>  <br/> |<span data-ttu-id="de15c-117">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="de15c-117">int, not null</span></span>  <br/> |<span data-ttu-id="de15c-118">拥有锁的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="de15c-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

