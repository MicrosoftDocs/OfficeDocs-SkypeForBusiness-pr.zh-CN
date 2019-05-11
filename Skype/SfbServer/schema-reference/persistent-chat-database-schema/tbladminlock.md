---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock 包含运行一些管理员命令所需的管理员锁。
ms.openlocfilehash: ea1cff137e58ef65eda172a9c09e5dd38e66d8a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929810"
---
# <a name="tbladminlock"></a><span data-ttu-id="d8c34-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="d8c34-103">tblAdminLock</span></span>
 
<span data-ttu-id="d8c34-104">tblAdminLock 包含运行一些管理员命令所需的管理员锁。</span><span class="sxs-lookup"><span data-stu-id="d8c34-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="d8c34-105">**列**</span><span class="sxs-lookup"><span data-stu-id="d8c34-105">**Columns**</span></span>

|<span data-ttu-id="d8c34-106">**列**</span><span class="sxs-lookup"><span data-stu-id="d8c34-106">**Column**</span></span>|<span data-ttu-id="d8c34-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="d8c34-107">**Type**</span></span>|<span data-ttu-id="d8c34-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="d8c34-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d8c34-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="d8c34-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="d8c34-110">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="d8c34-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="d8c34-111">锁定到期日期和时间。</span><span class="sxs-lookup"><span data-stu-id="d8c34-111">Lock expiration date and time.</span></span> <span data-ttu-id="d8c34-112">所有者可以定期扩展此值。</span><span class="sxs-lookup"><span data-stu-id="d8c34-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="d8c34-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="d8c34-113">lockServerID</span></span>  <br/> |<span data-ttu-id="d8c34-114">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="d8c34-114">int, not null</span></span>  <br/> |<span data-ttu-id="d8c34-115">拥有锁的服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="d8c34-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="d8c34-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="d8c34-116">lockActorID</span></span>  <br/> |<span data-ttu-id="d8c34-117">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="d8c34-117">int, not null</span></span>  <br/> |<span data-ttu-id="d8c34-118">拥有锁的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="d8c34-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

