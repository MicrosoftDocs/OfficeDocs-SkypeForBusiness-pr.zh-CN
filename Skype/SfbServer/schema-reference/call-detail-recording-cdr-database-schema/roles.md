---
title: Roles 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: 角色表是一个静态表，用于存储可能的会议角色，如与会者和演示者列表。
ms.openlocfilehash: e0088d059d6e4ed536e5f52e1290211377438889
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930302"
---
# <a name="roles-table"></a><span data-ttu-id="cbfd9-103">Roles 表</span><span class="sxs-lookup"><span data-stu-id="cbfd9-103">Roles table</span></span>
 
<span data-ttu-id="cbfd9-104">角色表是一个静态表，用于存储可能的会议角色，如与会者和演示者列表。</span><span class="sxs-lookup"><span data-stu-id="cbfd9-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="cbfd9-105">**列**</span><span class="sxs-lookup"><span data-stu-id="cbfd9-105">**Column**</span></span>|<span data-ttu-id="cbfd9-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="cbfd9-106">**Data Type**</span></span>|<span data-ttu-id="cbfd9-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="cbfd9-107">**Key/Index**</span></span>|<span data-ttu-id="cbfd9-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="cbfd9-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cbfd9-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="cbfd9-109">**RoleId**</span></span> <br/> |<span data-ttu-id="cbfd9-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="cbfd9-110">tinyint</span></span>  <br/> |<span data-ttu-id="cbfd9-111">Primary</span><span class="sxs-lookup"><span data-stu-id="cbfd9-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="cbfd9-112">**角色**</span><span class="sxs-lookup"><span data-stu-id="cbfd9-112">**Role**</span></span> <br/> |<span data-ttu-id="cbfd9-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cbfd9-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="cbfd9-114">允许的值：</span><span class="sxs-lookup"><span data-stu-id="cbfd9-114">Allowed values:</span></span> <br/>  <span data-ttu-id="cbfd9-115">0-未知</span><span class="sxs-lookup"><span data-stu-id="cbfd9-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="cbfd9-116">1-演示者</span><span class="sxs-lookup"><span data-stu-id="cbfd9-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="cbfd9-117">2-与会者</span><span class="sxs-lookup"><span data-stu-id="cbfd9-117">2 - Attendee</span></span> <br/> |
   

