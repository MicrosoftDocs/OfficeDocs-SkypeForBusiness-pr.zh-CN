---
title: Roles 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Roles 表是一个静态表, 它存储了可能的会议角色 (如与会者和演示者) 的列表。
ms.openlocfilehash: 2cf1fb22230d92951df0b3b8e18a5bd666c73519
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295893"
---
# <a name="roles-table"></a><span data-ttu-id="8bf1d-103">Roles 表</span><span class="sxs-lookup"><span data-stu-id="8bf1d-103">Roles table</span></span>
 
<span data-ttu-id="8bf1d-104">Roles 表是一个静态表, 它存储了可能的会议角色 (如与会者和演示者) 的列表。</span><span class="sxs-lookup"><span data-stu-id="8bf1d-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="8bf1d-105">**列**</span><span class="sxs-lookup"><span data-stu-id="8bf1d-105">**Column**</span></span>|<span data-ttu-id="8bf1d-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8bf1d-106">**Data Type**</span></span>|<span data-ttu-id="8bf1d-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="8bf1d-107">**Key/Index**</span></span>|<span data-ttu-id="8bf1d-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="8bf1d-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8bf1d-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="8bf1d-109">**RoleId**</span></span> <br/> |<span data-ttu-id="8bf1d-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="8bf1d-110">tinyint</span></span>  <br/> |<span data-ttu-id="8bf1d-111">Primary</span><span class="sxs-lookup"><span data-stu-id="8bf1d-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="8bf1d-112">**角色**</span><span class="sxs-lookup"><span data-stu-id="8bf1d-112">**Role**</span></span> <br/> |<span data-ttu-id="8bf1d-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8bf1d-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="8bf1d-114">允许的值:</span><span class="sxs-lookup"><span data-stu-id="8bf1d-114">Allowed values:</span></span> <br/>  <span data-ttu-id="8bf1d-115">0-未知</span><span class="sxs-lookup"><span data-stu-id="8bf1d-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="8bf1d-116">1-演示者</span><span class="sxs-lookup"><span data-stu-id="8bf1d-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="8bf1d-117">2-与会者</span><span class="sxs-lookup"><span data-stu-id="8bf1d-117">2 - Attendee</span></span> <br/> |
   

