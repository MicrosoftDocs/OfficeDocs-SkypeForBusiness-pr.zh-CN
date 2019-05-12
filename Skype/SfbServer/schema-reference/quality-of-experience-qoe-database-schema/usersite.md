---
title: UserSite 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: 自 UserSite table 是一个支持表。 每条记录代表一个网络配置设置中定义用户的网站。
ms.openlocfilehash: 519cedc35c03fd9bcb5479ea3cecf75ec617917c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906951"
---
# <a name="usersite-table"></a><span data-ttu-id="23465-104">UserSite 表</span><span class="sxs-lookup"><span data-stu-id="23465-104">UserSite table</span></span>
 
<span data-ttu-id="23465-105">自 UserSite table 是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="23465-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="23465-106">每条记录代表一个网络配置设置中定义用户的网站。</span><span class="sxs-lookup"><span data-stu-id="23465-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="23465-107">**列**</span><span class="sxs-lookup"><span data-stu-id="23465-107">**Column**</span></span>|<span data-ttu-id="23465-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="23465-108">**Data Type**</span></span>|<span data-ttu-id="23465-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="23465-109">**Key/Index**</span></span>|<span data-ttu-id="23465-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="23465-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="23465-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="23465-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="23465-112">int</span><span class="sxs-lookup"><span data-stu-id="23465-112">int</span></span>  <br/> |<span data-ttu-id="23465-113">Primary</span><span class="sxs-lookup"><span data-stu-id="23465-113">Primary</span></span>  <br/> |<span data-ttu-id="23465-114">标识用户站点的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="23465-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="23465-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="23465-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="23465-116">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="23465-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="23465-117">唯一</span><span class="sxs-lookup"><span data-stu-id="23465-117">Unique</span></span>  <br/> |<span data-ttu-id="23465-118">用户站点的名称。</span><span class="sxs-lookup"><span data-stu-id="23465-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="23465-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="23465-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="23465-120">int</span><span class="sxs-lookup"><span data-stu-id="23465-120">int</span></span>  <br/> |<span data-ttu-id="23465-121">外</span><span class="sxs-lookup"><span data-stu-id="23465-121">Foreign</span></span>  <br/> |<span data-ttu-id="23465-122">引用自[Region table](region.md)。</span><span class="sxs-lookup"><span data-stu-id="23465-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

