---
title: Roles 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: 角色表是一个静态表，用于存储可能的会议角色，如与会者和演示者列表。
ms.openlocfilehash: 2b7759cc600471a8bf1b989ce429f6b2a4149ee0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212829"
---
# <a name="roles-table"></a><span data-ttu-id="ee823-103">Roles 表</span><span class="sxs-lookup"><span data-stu-id="ee823-103">Roles table</span></span>
 
<span data-ttu-id="ee823-104">角色表是一个静态表，用于存储可能的会议角色，如与会者和演示者列表。</span><span class="sxs-lookup"><span data-stu-id="ee823-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="ee823-105">**列**</span><span class="sxs-lookup"><span data-stu-id="ee823-105">**Column**</span></span>|<span data-ttu-id="ee823-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ee823-106">**Data Type**</span></span>|<span data-ttu-id="ee823-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="ee823-107">**Key/Index**</span></span>|<span data-ttu-id="ee823-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="ee823-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ee823-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="ee823-109">**RoleId**</span></span> <br/> |<span data-ttu-id="ee823-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="ee823-110">tinyint</span></span>  <br/> |<span data-ttu-id="ee823-111">Primary</span><span class="sxs-lookup"><span data-stu-id="ee823-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="ee823-112">**角色**</span><span class="sxs-lookup"><span data-stu-id="ee823-112">**Role**</span></span> <br/> |<span data-ttu-id="ee823-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ee823-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="ee823-114">允许的值：</span><span class="sxs-lookup"><span data-stu-id="ee823-114">Allowed values:</span></span> <br/>  <span data-ttu-id="ee823-115">0-未知</span><span class="sxs-lookup"><span data-stu-id="ee823-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="ee823-116">1-演示者</span><span class="sxs-lookup"><span data-stu-id="ee823-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="ee823-117">2-与会者</span><span class="sxs-lookup"><span data-stu-id="ee823-117">2 - Attendee</span></span> <br/> |
   

