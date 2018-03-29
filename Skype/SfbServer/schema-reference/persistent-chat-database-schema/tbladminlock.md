---
title: tblAdminLock
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock 包含运行某些管理员命令所需的管理员锁定。
ms.openlocfilehash: 919ead84ed9baab859e1e85eb2f30f5ff6902531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tbladminlock"></a><span data-ttu-id="b14c6-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="b14c6-103">tblAdminLock</span></span>
 
<span data-ttu-id="b14c6-104">tblAdminLock 包含运行某些管理员命令所需的管理员锁定。</span><span class="sxs-lookup"><span data-stu-id="b14c6-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="b14c6-105">**列**</span><span class="sxs-lookup"><span data-stu-id="b14c6-105">**Columns**</span></span>

|<span data-ttu-id="b14c6-106">**列**</span><span class="sxs-lookup"><span data-stu-id="b14c6-106">**Column**</span></span>|<span data-ttu-id="b14c6-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="b14c6-107">**Type**</span></span>|<span data-ttu-id="b14c6-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="b14c6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b14c6-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="b14c6-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="b14c6-110">日期时间不为空</span><span class="sxs-lookup"><span data-stu-id="b14c6-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="b14c6-111">锁定到期日期和时间。</span><span class="sxs-lookup"><span data-stu-id="b14c6-111">Lock expiration date and time.</span></span> <span data-ttu-id="b14c6-112">所有者可以定期扩展此值。</span><span class="sxs-lookup"><span data-stu-id="b14c6-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="b14c6-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="b14c6-113">lockServerID</span></span>  <br/> |<span data-ttu-id="b14c6-114">int，不为空</span><span class="sxs-lookup"><span data-stu-id="b14c6-114">int, not null</span></span>  <br/> |<span data-ttu-id="b14c6-115">拥有的锁的服务器 ID。</span><span class="sxs-lookup"><span data-stu-id="b14c6-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="b14c6-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="b14c6-116">lockActorID</span></span>  <br/> |<span data-ttu-id="b14c6-117">int，不为空</span><span class="sxs-lookup"><span data-stu-id="b14c6-117">int, not null</span></span>  <br/> |<span data-ttu-id="b14c6-118">拥有的锁的主要用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="b14c6-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

