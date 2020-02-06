---
title: Skype for Business Server 2015 中的 EdgeServers 表
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
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: EdgeServers 表是支持表。 每个记录存储有关在数据库中具有记录的通话中涉及的一个边缘服务器的信息。
ms.openlocfilehash: 7a1621e3416b6cff48c430e7bc2e45057ecb3e14
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815260"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="cdaca-104">Skype for Business Server 2015 中的 EdgeServers 表</span><span class="sxs-lookup"><span data-stu-id="cdaca-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cdaca-105">EdgeServers 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="cdaca-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="cdaca-106">每个记录存储有关在数据库中具有记录的通话中涉及的一个边缘服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="cdaca-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="cdaca-107">**列**</span><span class="sxs-lookup"><span data-stu-id="cdaca-107">**Column**</span></span>|<span data-ttu-id="cdaca-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="cdaca-108">**Data Type**</span></span>|<span data-ttu-id="cdaca-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="cdaca-109">**Key/Index**</span></span>|<span data-ttu-id="cdaca-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="cdaca-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cdaca-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="cdaca-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="cdaca-112">int</span><span class="sxs-lookup"><span data-stu-id="cdaca-112">int</span></span>  <br/> |<span data-ttu-id="cdaca-113">Primary</span><span class="sxs-lookup"><span data-stu-id="cdaca-113">Primary</span></span>  <br/> |<span data-ttu-id="cdaca-114">标识此边缘服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="cdaca-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="cdaca-115">**EdgeServer**</span><span class="sxs-lookup"><span data-stu-id="cdaca-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="cdaca-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cdaca-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="cdaca-117">边缘服务器名称。</span><span class="sxs-lookup"><span data-stu-id="cdaca-117">Edge Server name.</span></span>  <br/> |
   

