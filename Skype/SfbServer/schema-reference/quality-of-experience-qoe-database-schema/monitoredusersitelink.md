---
title: MonitoredUserSiteLink 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 表是支持表。 每条记录表示两个用户网站之间的一个链接。
ms.openlocfilehash: 789c1a721e1a8c204ff6e214f419de77d1b7f7bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294850"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="d7f6c-104">MonitoredUserSiteLink 表</span><span class="sxs-lookup"><span data-stu-id="d7f6c-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="d7f6c-105">MonitoredUserSiteLink 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="d7f6c-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="d7f6c-106">每条记录表示两个用户网站之间的一个链接。</span><span class="sxs-lookup"><span data-stu-id="d7f6c-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="d7f6c-107">**列**</span><span class="sxs-lookup"><span data-stu-id="d7f6c-107">**Column**</span></span>|<span data-ttu-id="d7f6c-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d7f6c-108">**Data Type**</span></span>|<span data-ttu-id="d7f6c-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="d7f6c-109">**Key/Index**</span></span>|<span data-ttu-id="d7f6c-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="d7f6c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d7f6c-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="d7f6c-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="d7f6c-112">int</span><span class="sxs-lookup"><span data-stu-id="d7f6c-112">int</span></span>  <br/> |<span data-ttu-id="d7f6c-113">主、外部</span><span class="sxs-lookup"><span data-stu-id="d7f6c-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d7f6c-114">从[UserSite 表](usersite.md)中引用。</span><span class="sxs-lookup"><span data-stu-id="d7f6c-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="d7f6c-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="d7f6c-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="d7f6c-116">int</span><span class="sxs-lookup"><span data-stu-id="d7f6c-116">int</span></span>  <br/> |<span data-ttu-id="d7f6c-117">主、外部</span><span class="sxs-lookup"><span data-stu-id="d7f6c-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d7f6c-118">从[UserSite 表](usersite.md)引用。</span><span class="sxs-lookup"><span data-stu-id="d7f6c-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

