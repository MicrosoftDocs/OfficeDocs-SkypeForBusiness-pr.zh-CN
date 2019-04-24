---
title: MonitoredUserSiteLink 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 表是一个支持表。 每条记录代表一个两个用户站点之间的链接。
ms.openlocfilehash: 8022286289d4acd5fab8ea821c72897d9500597b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212521"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="41e82-104">MonitoredUserSiteLink 表</span><span class="sxs-lookup"><span data-stu-id="41e82-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="41e82-105">MonitoredUserSiteLink 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="41e82-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="41e82-106">每条记录代表一个两个用户站点之间的链接。</span><span class="sxs-lookup"><span data-stu-id="41e82-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="41e82-107">**列**</span><span class="sxs-lookup"><span data-stu-id="41e82-107">**Column**</span></span>|<span data-ttu-id="41e82-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="41e82-108">**Data Type**</span></span>|<span data-ttu-id="41e82-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="41e82-109">**Key/Index**</span></span>|<span data-ttu-id="41e82-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="41e82-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="41e82-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="41e82-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="41e82-112">int</span><span class="sxs-lookup"><span data-stu-id="41e82-112">int</span></span>  <br/> |<span data-ttu-id="41e82-113">主、 外</span><span class="sxs-lookup"><span data-stu-id="41e82-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="41e82-114">引用[自 UserSite table](usersite.md)。</span><span class="sxs-lookup"><span data-stu-id="41e82-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="41e82-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="41e82-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="41e82-116">int</span><span class="sxs-lookup"><span data-stu-id="41e82-116">int</span></span>  <br/> |<span data-ttu-id="41e82-117">主、 外</span><span class="sxs-lookup"><span data-stu-id="41e82-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="41e82-118">引用[自 UserSite table](usersite.md)。</span><span class="sxs-lookup"><span data-stu-id="41e82-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

