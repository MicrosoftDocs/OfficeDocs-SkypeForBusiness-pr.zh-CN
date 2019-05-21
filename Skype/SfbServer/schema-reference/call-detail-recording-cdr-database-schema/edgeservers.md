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
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: EdgeServers 表是支持表。 每个记录存储有关在数据库中具有记录的通话中涉及的一个边缘服务器的信息。
ms.openlocfilehash: a78acd3b6297bbef3348ef87047c8cb7f0893231
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296341"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="fb115-104">Skype for Business Server 2015 中的 EdgeServers 表</span><span class="sxs-lookup"><span data-stu-id="fb115-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fb115-105">EdgeServers 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="fb115-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="fb115-106">每个记录存储有关在数据库中具有记录的通话中涉及的一个边缘服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="fb115-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="fb115-107">**列**</span><span class="sxs-lookup"><span data-stu-id="fb115-107">**Column**</span></span>|<span data-ttu-id="fb115-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="fb115-108">**Data Type**</span></span>|<span data-ttu-id="fb115-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="fb115-109">**Key/Index**</span></span>|<span data-ttu-id="fb115-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="fb115-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fb115-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="fb115-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="fb115-112">int</span><span class="sxs-lookup"><span data-stu-id="fb115-112">int</span></span>  <br/> |<span data-ttu-id="fb115-113">Primary</span><span class="sxs-lookup"><span data-stu-id="fb115-113">Primary</span></span>  <br/> |<span data-ttu-id="fb115-114">标识此边缘服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="fb115-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="fb115-115">**EdgeServer**</span><span class="sxs-lookup"><span data-stu-id="fb115-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="fb115-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fb115-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="fb115-117">边缘服务器名称。</span><span class="sxs-lookup"><span data-stu-id="fb115-117">Edge Server name.</span></span>  <br/> |
   

