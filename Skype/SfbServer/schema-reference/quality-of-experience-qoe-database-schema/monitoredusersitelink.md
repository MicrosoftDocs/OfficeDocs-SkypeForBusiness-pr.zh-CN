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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 表是支持表。 每条记录表示两个用户网站之间的一个链接。
ms.openlocfilehash: 2cf229947da143fb01b3009020cfa432a4b558a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807790"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="7b791-104">MonitoredUserSiteLink 表</span><span class="sxs-lookup"><span data-stu-id="7b791-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="7b791-105">MonitoredUserSiteLink 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="7b791-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="7b791-106">每条记录表示两个用户网站之间的一个链接。</span><span class="sxs-lookup"><span data-stu-id="7b791-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="7b791-107">**列**</span><span class="sxs-lookup"><span data-stu-id="7b791-107">**Column**</span></span>|<span data-ttu-id="7b791-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7b791-108">**Data Type**</span></span>|<span data-ttu-id="7b791-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="7b791-109">**Key/Index**</span></span>|<span data-ttu-id="7b791-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="7b791-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7b791-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="7b791-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="7b791-112">int</span><span class="sxs-lookup"><span data-stu-id="7b791-112">int</span></span>  <br/> |<span data-ttu-id="7b791-113">主、外部</span><span class="sxs-lookup"><span data-stu-id="7b791-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="7b791-114">从[UserSite 表](usersite.md)中引用。</span><span class="sxs-lookup"><span data-stu-id="7b791-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="7b791-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="7b791-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="7b791-116">int</span><span class="sxs-lookup"><span data-stu-id="7b791-116">int</span></span>  <br/> |<span data-ttu-id="7b791-117">主、外部</span><span class="sxs-lookup"><span data-stu-id="7b791-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="7b791-118">从[UserSite 表](usersite.md)引用。</span><span class="sxs-lookup"><span data-stu-id="7b791-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

