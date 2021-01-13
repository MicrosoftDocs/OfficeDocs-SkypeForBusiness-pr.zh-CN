---
title: Roles 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: 角色表是一个静态表，用于存储可能的会议角色（如与者会和演示者）的列表。
ms.openlocfilehash: 6c5e28ccd2d186b0122d70f91621a3365e6d2b07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809972"
---
# <a name="roles-table"></a><span data-ttu-id="3dfcf-103">Roles 表</span><span class="sxs-lookup"><span data-stu-id="3dfcf-103">Roles table</span></span>
 
<span data-ttu-id="3dfcf-104">角色表是一个静态表，用于存储可能的会议角色（如与者会和演示者）的列表。</span><span class="sxs-lookup"><span data-stu-id="3dfcf-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="3dfcf-105">**列**</span><span class="sxs-lookup"><span data-stu-id="3dfcf-105">**Column**</span></span>|<span data-ttu-id="3dfcf-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3dfcf-106">**Data Type**</span></span>|<span data-ttu-id="3dfcf-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="3dfcf-107">**Key/Index**</span></span>|<span data-ttu-id="3dfcf-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="3dfcf-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3dfcf-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="3dfcf-109">**RoleId**</span></span> <br/> |<span data-ttu-id="3dfcf-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="3dfcf-110">tinyint</span></span>  <br/> |<span data-ttu-id="3dfcf-111">主</span><span class="sxs-lookup"><span data-stu-id="3dfcf-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="3dfcf-112">**角色**</span><span class="sxs-lookup"><span data-stu-id="3dfcf-112">**Role**</span></span> <br/> |<span data-ttu-id="3dfcf-113">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="3dfcf-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="3dfcf-114">允许的值：</span><span class="sxs-lookup"><span data-stu-id="3dfcf-114">Allowed values:</span></span> <br/>  <span data-ttu-id="3dfcf-115">0 -- 未知</span><span class="sxs-lookup"><span data-stu-id="3dfcf-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="3dfcf-116">1 -- 演示者</span><span class="sxs-lookup"><span data-stu-id="3dfcf-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="3dfcf-117">2 -- 与会者</span><span class="sxs-lookup"><span data-stu-id="3dfcf-117">2 - Attendee</span></span> <br/> |
   

