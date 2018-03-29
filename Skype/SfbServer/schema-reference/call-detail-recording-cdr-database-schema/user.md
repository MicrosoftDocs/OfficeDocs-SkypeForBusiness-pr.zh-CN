---
title: 用户视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: 用户视图存储有关已调用或数据库中具有记录的会话中涉及的用户信息。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 014b773a60cc053c0ec258c7dd853e31a590319c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="user-view"></a><span data-ttu-id="3a3a0-104">用户视图</span><span class="sxs-lookup"><span data-stu-id="3a3a0-104">User view</span></span>
 
<span data-ttu-id="3a3a0-105">用户视图存储有关已调用或数据库中具有记录的会话中涉及的用户信息。</span><span class="sxs-lookup"><span data-stu-id="3a3a0-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="3a3a0-106">在 Microsoft Lync Server 2013 引入了此视图。</span><span class="sxs-lookup"><span data-stu-id="3a3a0-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="3a3a0-107">**列**</span><span class="sxs-lookup"><span data-stu-id="3a3a0-107">**Column**</span></span>|<span data-ttu-id="3a3a0-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3a3a0-108">**Data Type**</span></span>|<span data-ttu-id="3a3a0-109">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="3a3a0-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3a3a0-110">用户 Id</span><span class="sxs-lookup"><span data-stu-id="3a3a0-110">UserId</span></span>  <br/> |<span data-ttu-id="3a3a0-111">int</span><span class="sxs-lookup"><span data-stu-id="3a3a0-111">int</span></span>  <br/> |<span data-ttu-id="3a3a0-112">识别该用户的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="3a3a0-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="3a3a0-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="3a3a0-113">UserUri</span></span>  <br/> |<span data-ttu-id="3a3a0-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="3a3a0-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="3a3a0-115">用户的 Uri。</span><span class="sxs-lookup"><span data-stu-id="3a3a0-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="3a3a0-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="3a3a0-116">TenantKey</span></span>  <br/> |<span data-ttu-id="3a3a0-117">唯一标识符</span><span class="sxs-lookup"><span data-stu-id="3a3a0-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="3a3a0-118">用户的客户端。</span><span class="sxs-lookup"><span data-stu-id="3a3a0-118">Tenant of user.</span></span> <span data-ttu-id="3a3a0-119">[租户表](tenants.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="3a3a0-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3a3a0-120">UriType</span><span class="sxs-lookup"><span data-stu-id="3a3a0-120">UriType</span></span>  <br/> |<span data-ttu-id="3a3a0-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3a3a0-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3a3a0-122">用户 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="3a3a0-122">Type of user URI.</span></span> <span data-ttu-id="3a3a0-123">[UriTypes 表](uritypes.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="3a3a0-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

