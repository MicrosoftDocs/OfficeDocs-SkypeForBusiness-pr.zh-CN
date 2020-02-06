---
title: Servers 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1535e676-a647-4606-bc56-e8bfde5ca823
description: 服务器表是存储有关各种服务器的信息的支持表。 表中的每条记录表示一台服务器。
ms.openlocfilehash: e2e2c86e96f7f929a218a5efa86100d3c383e339
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814920"
---
# <a name="servers-table"></a><span data-ttu-id="db72e-104">Servers 表</span><span class="sxs-lookup"><span data-stu-id="db72e-104">Servers table</span></span>
 
<span data-ttu-id="db72e-105">服务器表是存储有关各种服务器的信息的支持表。</span><span class="sxs-lookup"><span data-stu-id="db72e-105">The Servers table is a supporting table that stores information about the various servers.</span></span> <span data-ttu-id="db72e-106">表中的每条记录表示一台服务器。</span><span class="sxs-lookup"><span data-stu-id="db72e-106">Each record in the table represents one server.</span></span>
  
|<span data-ttu-id="db72e-107">**列**</span><span class="sxs-lookup"><span data-stu-id="db72e-107">**Column**</span></span>|<span data-ttu-id="db72e-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="db72e-108">**Data Type**</span></span>|<span data-ttu-id="db72e-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="db72e-109">**Key/Index**</span></span>|<span data-ttu-id="db72e-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="db72e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="db72e-111">**ServerId**</span><span class="sxs-lookup"><span data-stu-id="db72e-111">**ServerId**</span></span> <br/> |<span data-ttu-id="db72e-112">int</span><span class="sxs-lookup"><span data-stu-id="db72e-112">int</span></span>  <br/> |<span data-ttu-id="db72e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="db72e-113">Primary</span></span>  <br/> |<span data-ttu-id="db72e-114">标识此服务器的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="db72e-114">Unique number identifying this server.</span></span>  <br/> |
|<span data-ttu-id="db72e-115">**ServerFQDN**</span><span class="sxs-lookup"><span data-stu-id="db72e-115">**ServerFQDN**</span></span> <br/> |<span data-ttu-id="db72e-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="db72e-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="db72e-117">服务器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="db72e-117">Server FQDN.</span></span>  <br/> |
   

