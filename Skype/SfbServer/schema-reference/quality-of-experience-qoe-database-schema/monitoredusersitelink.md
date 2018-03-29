---
title: MonitoredUserSiteLink 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 表是支持表。 每个记录表示两个用户站点之间的一个链接。
ms.openlocfilehash: 7b9b2ddab3bff48105a24f586816666b15c0b9b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="39bed-104">MonitoredUserSiteLink 表</span><span class="sxs-lookup"><span data-stu-id="39bed-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="39bed-105">MonitoredUserSiteLink 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="39bed-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="39bed-106">每个记录表示两个用户站点之间的一个链接。</span><span class="sxs-lookup"><span data-stu-id="39bed-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="39bed-107">**列**</span><span class="sxs-lookup"><span data-stu-id="39bed-107">**Column**</span></span>|<span data-ttu-id="39bed-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="39bed-108">**Data Type**</span></span>|<span data-ttu-id="39bed-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="39bed-109">**Key/Index**</span></span>|<span data-ttu-id="39bed-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="39bed-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="39bed-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="39bed-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="39bed-112">int</span><span class="sxs-lookup"><span data-stu-id="39bed-112">int</span></span>  <br/> |<span data-ttu-id="39bed-113">主键和外</span><span class="sxs-lookup"><span data-stu-id="39bed-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="39bed-114">从[UserSite 表](usersite.md)引用。</span><span class="sxs-lookup"><span data-stu-id="39bed-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="39bed-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="39bed-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="39bed-116">int</span><span class="sxs-lookup"><span data-stu-id="39bed-116">int</span></span>  <br/> |<span data-ttu-id="39bed-117">主键和外</span><span class="sxs-lookup"><span data-stu-id="39bed-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="39bed-118">从[UserSite 表](usersite.md)的引用。</span><span class="sxs-lookup"><span data-stu-id="39bed-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

