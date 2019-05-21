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
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: "\"用户\" 视图存储与在数据库中具有记录的通话或会话中参与的用户的相关信息。 此视图已在 Microsoft Lync Server 2013 中引入。"
ms.openlocfilehash: 2fe0ba4748a776a8f17065a3c5db21d34bd6340d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295739"
---
# <a name="user-view"></a><span data-ttu-id="436fe-104">用户视图</span><span class="sxs-lookup"><span data-stu-id="436fe-104">User view</span></span>
 
<span data-ttu-id="436fe-105">"用户" 视图存储与在数据库中具有记录的通话或会话中参与的用户的相关信息。</span><span class="sxs-lookup"><span data-stu-id="436fe-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="436fe-106">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="436fe-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="436fe-107">**列**</span><span class="sxs-lookup"><span data-stu-id="436fe-107">**Column**</span></span>|<span data-ttu-id="436fe-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="436fe-108">**Data Type**</span></span>|<span data-ttu-id="436fe-109">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="436fe-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="436fe-110">UserId</span><span class="sxs-lookup"><span data-stu-id="436fe-110">UserId</span></span>  <br/> |<span data-ttu-id="436fe-111">int</span><span class="sxs-lookup"><span data-stu-id="436fe-111">int</span></span>  <br/> |<span data-ttu-id="436fe-112">标识此用户的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="436fe-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="436fe-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="436fe-113">UserUri</span></span>  <br/> |<span data-ttu-id="436fe-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="436fe-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="436fe-115">用户的 Uri。</span><span class="sxs-lookup"><span data-stu-id="436fe-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="436fe-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="436fe-116">TenantKey</span></span>  <br/> |<span data-ttu-id="436fe-117">标识符</span><span class="sxs-lookup"><span data-stu-id="436fe-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="436fe-118">用户的租户。</span><span class="sxs-lookup"><span data-stu-id="436fe-118">Tenant of user.</span></span> <span data-ttu-id="436fe-119">有关详细信息, 请参阅[租户表](tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="436fe-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="436fe-120">UriType</span><span class="sxs-lookup"><span data-stu-id="436fe-120">UriType</span></span>  <br/> |<span data-ttu-id="436fe-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="436fe-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="436fe-122">用户 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="436fe-122">Type of user URI.</span></span> <span data-ttu-id="436fe-123">有关详细信息, 请参阅[UriTypes 表](uritypes.md)。</span><span class="sxs-lookup"><span data-stu-id="436fe-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

