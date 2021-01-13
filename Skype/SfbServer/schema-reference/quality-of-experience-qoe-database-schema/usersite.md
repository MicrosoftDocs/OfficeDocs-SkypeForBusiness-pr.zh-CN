---
title: UserSite 表
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite 表是一个支持表。 每条记录代表一个在网络配置设置中定义的用户站点。
ms.openlocfilehash: 88df08875ea3254ee355a96aa3b12d3ee7f5ccaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799912"
---
# <a name="usersite-table"></a><span data-ttu-id="e5c5d-104">UserSite 表</span><span class="sxs-lookup"><span data-stu-id="e5c5d-104">UserSite table</span></span>
 
<span data-ttu-id="e5c5d-p102">UserSite 表是一个支持表。每条记录代表一个在网络配置设置中定义的用户站点。</span><span class="sxs-lookup"><span data-stu-id="e5c5d-p102">The UserSite table is a supporting table. Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="e5c5d-107">**列**</span><span class="sxs-lookup"><span data-stu-id="e5c5d-107">**Column**</span></span>|<span data-ttu-id="e5c5d-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e5c5d-108">**Data Type**</span></span>|<span data-ttu-id="e5c5d-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="e5c5d-109">**Key/Index**</span></span>|<span data-ttu-id="e5c5d-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="e5c5d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e5c5d-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="e5c5d-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="e5c5d-112">int</span><span class="sxs-lookup"><span data-stu-id="e5c5d-112">int</span></span>  <br/> |<span data-ttu-id="e5c5d-113">主</span><span class="sxs-lookup"><span data-stu-id="e5c5d-113">Primary</span></span>  <br/> |<span data-ttu-id="e5c5d-114">标识用户站点的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="e5c5d-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="e5c5d-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="e5c5d-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="e5c5d-116">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="e5c5d-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="e5c5d-117">独特</span><span class="sxs-lookup"><span data-stu-id="e5c5d-117">Unique</span></span>  <br/> |<span data-ttu-id="e5c5d-118">用户网站的名称。</span><span class="sxs-lookup"><span data-stu-id="e5c5d-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="e5c5d-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="e5c5d-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="e5c5d-120">int</span><span class="sxs-lookup"><span data-stu-id="e5c5d-120">int</span></span>  <br/> |<span data-ttu-id="e5c5d-121">Foreign</span><span class="sxs-lookup"><span data-stu-id="e5c5d-121">Foreign</span></span>  <br/> |<span data-ttu-id="e5c5d-122">引用自 [Region 表](region.md)。</span><span class="sxs-lookup"><span data-stu-id="e5c5d-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

