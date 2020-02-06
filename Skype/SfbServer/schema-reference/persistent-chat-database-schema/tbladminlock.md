---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock 包含运行某些管理员命令所需的管理员锁。
ms.openlocfilehash: cb3a03fa7404004df37da2adf07eff1e37ff334f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814690"
---
# <a name="tbladminlock"></a><span data-ttu-id="3fbf8-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="3fbf8-103">tblAdminLock</span></span>
 
<span data-ttu-id="3fbf8-104">tblAdminLock 包含运行某些管理员命令所需的管理员锁。</span><span class="sxs-lookup"><span data-stu-id="3fbf8-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="3fbf8-105">**多**</span><span class="sxs-lookup"><span data-stu-id="3fbf8-105">**Columns**</span></span>

|<span data-ttu-id="3fbf8-106">**列**</span><span class="sxs-lookup"><span data-stu-id="3fbf8-106">**Column**</span></span>|<span data-ttu-id="3fbf8-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="3fbf8-107">**Type**</span></span>|<span data-ttu-id="3fbf8-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="3fbf8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3fbf8-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="3fbf8-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="3fbf8-110">datetime，not null</span><span class="sxs-lookup"><span data-stu-id="3fbf8-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="3fbf8-111">锁定到期日期和时间。</span><span class="sxs-lookup"><span data-stu-id="3fbf8-111">Lock expiration date and time.</span></span> <span data-ttu-id="3fbf8-112">所有者可以定期延长此值。</span><span class="sxs-lookup"><span data-stu-id="3fbf8-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="3fbf8-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="3fbf8-113">lockServerID</span></span>  <br/> |<span data-ttu-id="3fbf8-114">int，not null</span><span class="sxs-lookup"><span data-stu-id="3fbf8-114">int, not null</span></span>  <br/> |<span data-ttu-id="3fbf8-115">拥有锁定的服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="3fbf8-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="3fbf8-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="3fbf8-116">lockActorID</span></span>  <br/> |<span data-ttu-id="3fbf8-117">int，not null</span><span class="sxs-lookup"><span data-stu-id="3fbf8-117">int, not null</span></span>  <br/> |<span data-ttu-id="3fbf8-118">拥有锁定的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="3fbf8-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

