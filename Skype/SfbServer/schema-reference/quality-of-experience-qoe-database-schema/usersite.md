---
title: UserSite 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite 表是支持表。 每条记录表示网络配置设置中定义的一个用户网站。
ms.openlocfilehash: 21f60afdb1690024f85dc74e11f856642413e6a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294570"
---
# <a name="usersite-table"></a><span data-ttu-id="f6064-104">UserSite 表</span><span class="sxs-lookup"><span data-stu-id="f6064-104">UserSite table</span></span>
 
<span data-ttu-id="f6064-105">UserSite 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="f6064-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="f6064-106">每条记录表示网络配置设置中定义的一个用户网站。</span><span class="sxs-lookup"><span data-stu-id="f6064-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="f6064-107">**列**</span><span class="sxs-lookup"><span data-stu-id="f6064-107">**Column**</span></span>|<span data-ttu-id="f6064-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f6064-108">**Data Type**</span></span>|<span data-ttu-id="f6064-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="f6064-109">**Key/Index**</span></span>|<span data-ttu-id="f6064-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="f6064-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f6064-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="f6064-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="f6064-112">int</span><span class="sxs-lookup"><span data-stu-id="f6064-112">int</span></span>  <br/> |<span data-ttu-id="f6064-113">Primary</span><span class="sxs-lookup"><span data-stu-id="f6064-113">Primary</span></span>  <br/> |<span data-ttu-id="f6064-114">标识用户网站的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="f6064-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="f6064-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="f6064-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="f6064-116">nvarchar</span><span class="sxs-lookup"><span data-stu-id="f6064-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="f6064-117">唯一</span><span class="sxs-lookup"><span data-stu-id="f6064-117">Unique</span></span>  <br/> |<span data-ttu-id="f6064-118">用户网站的名称。</span><span class="sxs-lookup"><span data-stu-id="f6064-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="f6064-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="f6064-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="f6064-120">int</span><span class="sxs-lookup"><span data-stu-id="f6064-120">int</span></span>  <br/> |<span data-ttu-id="f6064-121">外表</span><span class="sxs-lookup"><span data-stu-id="f6064-121">Foreign</span></span>  <br/> |<span data-ttu-id="f6064-122">从[Region 表](region.md)中引用。</span><span class="sxs-lookup"><span data-stu-id="f6064-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

