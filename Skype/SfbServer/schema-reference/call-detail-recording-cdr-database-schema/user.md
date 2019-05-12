---
title: 用户视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: 用户视图存储已参与呼叫或在数据库中包含记录的会话的用户的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: f4e255f2de8dd087308ee46c64ef301cc0e9d390
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930076"
---
# <a name="user-view"></a><span data-ttu-id="5b519-104">用户视图</span><span class="sxs-lookup"><span data-stu-id="5b519-104">User view</span></span>
 
<span data-ttu-id="5b519-105">用户视图存储已参与呼叫或在数据库中包含记录的会话的用户的信息。</span><span class="sxs-lookup"><span data-stu-id="5b519-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="5b519-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="5b519-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="5b519-107">**列**</span><span class="sxs-lookup"><span data-stu-id="5b519-107">**Column**</span></span>|<span data-ttu-id="5b519-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5b519-108">**Data Type**</span></span>|<span data-ttu-id="5b519-109">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="5b519-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5b519-110">用户 Id</span><span class="sxs-lookup"><span data-stu-id="5b519-110">UserId</span></span>  <br/> |<span data-ttu-id="5b519-111">int</span><span class="sxs-lookup"><span data-stu-id="5b519-111">int</span></span>  <br/> |<span data-ttu-id="5b519-112">标识此用户的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="5b519-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="5b519-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="5b519-113">UserUri</span></span>  <br/> |<span data-ttu-id="5b519-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="5b519-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="5b519-115">用户的 Uri。</span><span class="sxs-lookup"><span data-stu-id="5b519-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="5b519-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="5b519-116">TenantKey</span></span>  <br/> |<span data-ttu-id="5b519-117">唯一标识符</span><span class="sxs-lookup"><span data-stu-id="5b519-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="5b519-118">用户的租户。</span><span class="sxs-lookup"><span data-stu-id="5b519-118">Tenant of user.</span></span> <span data-ttu-id="5b519-119">请参阅[Tenants 表](tenants.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5b519-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="5b519-120">UriType</span><span class="sxs-lookup"><span data-stu-id="5b519-120">UriType</span></span>  <br/> |<span data-ttu-id="5b519-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5b519-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="5b519-122">用户 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="5b519-122">Type of user URI.</span></span> <span data-ttu-id="5b519-123">请参阅[UriTypes 表](uritypes.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5b519-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

