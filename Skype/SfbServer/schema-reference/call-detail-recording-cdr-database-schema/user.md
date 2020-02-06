---
title: 用户视图
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: "\"用户\" 视图存储与在数据库中具有记录的通话或会话中参与的用户的相关信息。 此视图已在 Microsoft Lync Server 2013 中引入。"
ms.openlocfilehash: 1d170b558dbf77cd8ebeff09a914826830d5621d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814830"
---
# <a name="user-view"></a><span data-ttu-id="e1c55-104">用户视图</span><span class="sxs-lookup"><span data-stu-id="e1c55-104">User view</span></span>
 
<span data-ttu-id="e1c55-105">"用户" 视图存储与在数据库中具有记录的通话或会话中参与的用户的相关信息。</span><span class="sxs-lookup"><span data-stu-id="e1c55-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="e1c55-106">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="e1c55-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="e1c55-107">**列**</span><span class="sxs-lookup"><span data-stu-id="e1c55-107">**Column**</span></span>|<span data-ttu-id="e1c55-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e1c55-108">**Data Type**</span></span>|<span data-ttu-id="e1c55-109">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="e1c55-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e1c55-110">UserId</span><span class="sxs-lookup"><span data-stu-id="e1c55-110">UserId</span></span>  <br/> |<span data-ttu-id="e1c55-111">int</span><span class="sxs-lookup"><span data-stu-id="e1c55-111">int</span></span>  <br/> |<span data-ttu-id="e1c55-112">标识此用户的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="e1c55-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="e1c55-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="e1c55-113">UserUri</span></span>  <br/> |<span data-ttu-id="e1c55-114">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e1c55-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="e1c55-115">用户的 Uri。</span><span class="sxs-lookup"><span data-stu-id="e1c55-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="e1c55-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="e1c55-116">TenantKey</span></span>  <br/> |<span data-ttu-id="e1c55-117">标识符</span><span class="sxs-lookup"><span data-stu-id="e1c55-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="e1c55-118">用户的租户。</span><span class="sxs-lookup"><span data-stu-id="e1c55-118">Tenant of user.</span></span> <span data-ttu-id="e1c55-119">有关详细信息，请参阅[租户表](tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="e1c55-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e1c55-120">UriType</span><span class="sxs-lookup"><span data-stu-id="e1c55-120">UriType</span></span>  <br/> |<span data-ttu-id="e1c55-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e1c55-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e1c55-122">用户 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="e1c55-122">Type of user URI.</span></span> <span data-ttu-id="e1c55-123">有关详细信息，请参阅[UriTypes 表](uritypes.md)。</span><span class="sxs-lookup"><span data-stu-id="e1c55-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

