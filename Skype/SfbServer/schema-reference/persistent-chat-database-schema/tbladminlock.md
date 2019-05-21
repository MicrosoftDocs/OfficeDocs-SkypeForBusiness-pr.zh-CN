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
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock 包含运行某些管理员命令所需的管理员锁。
ms.openlocfilehash: ccdc2b2667dee4d1d82a583ef7e7698d3107651a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295522"
---
# <a name="tbladminlock"></a><span data-ttu-id="604f8-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="604f8-103">tblAdminLock</span></span>
 
<span data-ttu-id="604f8-104">tblAdminLock 包含运行某些管理员命令所需的管理员锁。</span><span class="sxs-lookup"><span data-stu-id="604f8-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="604f8-105">**多**</span><span class="sxs-lookup"><span data-stu-id="604f8-105">**Columns**</span></span>

|<span data-ttu-id="604f8-106">**列**</span><span class="sxs-lookup"><span data-stu-id="604f8-106">**Column**</span></span>|<span data-ttu-id="604f8-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="604f8-107">**Type**</span></span>|<span data-ttu-id="604f8-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="604f8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="604f8-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="604f8-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="604f8-110">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="604f8-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="604f8-111">锁定到期日期和时间。</span><span class="sxs-lookup"><span data-stu-id="604f8-111">Lock expiration date and time.</span></span> <span data-ttu-id="604f8-112">所有者可以定期延长此值。</span><span class="sxs-lookup"><span data-stu-id="604f8-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="604f8-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="604f8-113">lockServerID</span></span>  <br/> |<span data-ttu-id="604f8-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="604f8-114">int, not null</span></span>  <br/> |<span data-ttu-id="604f8-115">拥有锁定的服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="604f8-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="604f8-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="604f8-116">lockActorID</span></span>  <br/> |<span data-ttu-id="604f8-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="604f8-117">int, not null</span></span>  <br/> |<span data-ttu-id="604f8-118">拥有锁定的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="604f8-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

