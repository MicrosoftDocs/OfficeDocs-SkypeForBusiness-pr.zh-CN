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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite 表是支持表。 每条记录表示网络配置设置中定义的一个用户网站。
ms.openlocfilehash: e1d6c4ddc3a756f2e5df0713d6abe1cb7b61295f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805000"
---
# <a name="usersite-table"></a><span data-ttu-id="7b358-104">UserSite 表</span><span class="sxs-lookup"><span data-stu-id="7b358-104">UserSite table</span></span>
 
<span data-ttu-id="7b358-105">UserSite 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="7b358-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="7b358-106">每条记录表示网络配置设置中定义的一个用户网站。</span><span class="sxs-lookup"><span data-stu-id="7b358-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="7b358-107">**列**</span><span class="sxs-lookup"><span data-stu-id="7b358-107">**Column**</span></span>|<span data-ttu-id="7b358-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7b358-108">**Data Type**</span></span>|<span data-ttu-id="7b358-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="7b358-109">**Key/Index**</span></span>|<span data-ttu-id="7b358-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="7b358-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7b358-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="7b358-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="7b358-112">int</span><span class="sxs-lookup"><span data-stu-id="7b358-112">int</span></span>  <br/> |<span data-ttu-id="7b358-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7b358-113">Primary</span></span>  <br/> |<span data-ttu-id="7b358-114">标识用户网站的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="7b358-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="7b358-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="7b358-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="7b358-116">nvarchar</span><span class="sxs-lookup"><span data-stu-id="7b358-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="7b358-117">唯一</span><span class="sxs-lookup"><span data-stu-id="7b358-117">Unique</span></span>  <br/> |<span data-ttu-id="7b358-118">用户网站的名称。</span><span class="sxs-lookup"><span data-stu-id="7b358-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="7b358-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="7b358-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="7b358-120">int</span><span class="sxs-lookup"><span data-stu-id="7b358-120">int</span></span>  <br/> |<span data-ttu-id="7b358-121">外表</span><span class="sxs-lookup"><span data-stu-id="7b358-121">Foreign</span></span>  <br/> |<span data-ttu-id="7b358-122">从[Region 表](region.md)中引用。</span><span class="sxs-lookup"><span data-stu-id="7b358-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

