---
title: UserSite 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: 自 UserSite table 是一个支持表。 每条记录代表一个网络配置设置中定义用户的网站。
ms.openlocfilehash: a52f5cd9aa7059e2b545dec3bcc7ccb86191347a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212044"
---
# <a name="usersite-table"></a><span data-ttu-id="76ad7-104">UserSite 表</span><span class="sxs-lookup"><span data-stu-id="76ad7-104">UserSite table</span></span>
 
<span data-ttu-id="76ad7-105">自 UserSite table 是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="76ad7-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="76ad7-106">每条记录代表一个网络配置设置中定义用户的网站。</span><span class="sxs-lookup"><span data-stu-id="76ad7-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="76ad7-107">**列**</span><span class="sxs-lookup"><span data-stu-id="76ad7-107">**Column**</span></span>|<span data-ttu-id="76ad7-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="76ad7-108">**Data Type**</span></span>|<span data-ttu-id="76ad7-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="76ad7-109">**Key/Index**</span></span>|<span data-ttu-id="76ad7-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="76ad7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="76ad7-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="76ad7-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="76ad7-112">int</span><span class="sxs-lookup"><span data-stu-id="76ad7-112">int</span></span>  <br/> |<span data-ttu-id="76ad7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="76ad7-113">Primary</span></span>  <br/> |<span data-ttu-id="76ad7-114">标识用户站点的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="76ad7-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="76ad7-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="76ad7-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="76ad7-116">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="76ad7-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="76ad7-117">唯一</span><span class="sxs-lookup"><span data-stu-id="76ad7-117">Unique</span></span>  <br/> |<span data-ttu-id="76ad7-118">用户站点的名称。</span><span class="sxs-lookup"><span data-stu-id="76ad7-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="76ad7-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="76ad7-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="76ad7-120">int</span><span class="sxs-lookup"><span data-stu-id="76ad7-120">int</span></span>  <br/> |<span data-ttu-id="76ad7-121">外</span><span class="sxs-lookup"><span data-stu-id="76ad7-121">Foreign</span></span>  <br/> |<span data-ttu-id="76ad7-122">引用自[Region table](region.md)。</span><span class="sxs-lookup"><span data-stu-id="76ad7-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

