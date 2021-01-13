---
title: 用户视图
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: 用户视图存储有关数据库中记录的呼叫或会话所涉及的用户的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 03af849f9185d90d1c7888c1946b47ee2ef38db4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831692"
---
# <a name="user-view"></a><span data-ttu-id="e6972-104">用户视图</span><span class="sxs-lookup"><span data-stu-id="e6972-104">User view</span></span>
 
<span data-ttu-id="e6972-105">用户视图存储有关数据库中记录的呼叫或会话所涉及的用户的信息。</span><span class="sxs-lookup"><span data-stu-id="e6972-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="e6972-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="e6972-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="e6972-107">**列**</span><span class="sxs-lookup"><span data-stu-id="e6972-107">**Column**</span></span>|<span data-ttu-id="e6972-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e6972-108">**Data Type**</span></span>|<span data-ttu-id="e6972-109">**Details**</span><span class="sxs-lookup"><span data-stu-id="e6972-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e6972-110">UserID</span><span class="sxs-lookup"><span data-stu-id="e6972-110">UserId</span></span>  <br/> |<span data-ttu-id="e6972-111">int</span><span class="sxs-lookup"><span data-stu-id="e6972-111">int</span></span>  <br/> |<span data-ttu-id="e6972-112">用于标识此用户的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="e6972-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="e6972-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="e6972-113">UserUri</span></span>  <br/> |<span data-ttu-id="e6972-114">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="e6972-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="e6972-115">用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="e6972-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="e6972-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="e6972-116">TenantKey</span></span>  <br/> |<span data-ttu-id="e6972-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="e6972-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="e6972-118">用户的租户。</span><span class="sxs-lookup"><span data-stu-id="e6972-118">Tenant of user.</span></span> <span data-ttu-id="e6972-119">有关详细信息 [，请参阅"租户](tenants.md) "表。</span><span class="sxs-lookup"><span data-stu-id="e6972-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e6972-120">UriType</span><span class="sxs-lookup"><span data-stu-id="e6972-120">UriType</span></span>  <br/> |<span data-ttu-id="e6972-121">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e6972-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e6972-122">用户 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="e6972-122">Type of user URI.</span></span> <span data-ttu-id="e6972-123">有关详细信息， [请参阅 UriTypes](uritypes.md) 表。</span><span class="sxs-lookup"><span data-stu-id="e6972-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

