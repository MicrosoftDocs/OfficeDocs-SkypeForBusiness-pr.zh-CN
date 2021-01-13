---
title: MonitoredUserSiteLink 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 表是一个支持表。 每条记录代表两个用户站点之间的一个链接。
ms.openlocfilehash: 88b4d385f3c96dc93a519274c584e1f99584982f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806352"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="ea04d-104">MonitoredUserSiteLink 表</span><span class="sxs-lookup"><span data-stu-id="ea04d-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="ea04d-p102">MonitoredUserSiteLink 表是一个支持表。每条记录代表两个用户站点之间的一个链接。</span><span class="sxs-lookup"><span data-stu-id="ea04d-p102">The MonitoredUserSiteLink table is a supporting table. Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="ea04d-107">**列**</span><span class="sxs-lookup"><span data-stu-id="ea04d-107">**Column**</span></span>|<span data-ttu-id="ea04d-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ea04d-108">**Data Type**</span></span>|<span data-ttu-id="ea04d-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="ea04d-109">**Key/Index**</span></span>|<span data-ttu-id="ea04d-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="ea04d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ea04d-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="ea04d-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="ea04d-112">int</span><span class="sxs-lookup"><span data-stu-id="ea04d-112">int</span></span>  <br/> |<span data-ttu-id="ea04d-113">主、外</span><span class="sxs-lookup"><span data-stu-id="ea04d-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ea04d-114">引用自 [UserSite 表](usersite.md)。</span><span class="sxs-lookup"><span data-stu-id="ea04d-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="ea04d-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="ea04d-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="ea04d-116">int</span><span class="sxs-lookup"><span data-stu-id="ea04d-116">int</span></span>  <br/> |<span data-ttu-id="ea04d-117">主、外</span><span class="sxs-lookup"><span data-stu-id="ea04d-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ea04d-118">[UserSite 表的引用](usersite.md)。</span><span class="sxs-lookup"><span data-stu-id="ea04d-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

