---
title: UserAgent 视图
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent 视图存储有关数据库中包含记录的会话中涉及的用户代理的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: c63873f219f5d741925339f52f949be55fc64411
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875002"
---
# <a name="useragent-view"></a><span data-ttu-id="63fed-104">UserAgent 视图</span><span class="sxs-lookup"><span data-stu-id="63fed-104">UserAgent view</span></span>
 
<span data-ttu-id="63fed-105">UserAgent 视图存储有关数据库中包含记录的会话中涉及的用户代理的信息。</span><span class="sxs-lookup"><span data-stu-id="63fed-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="63fed-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="63fed-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="63fed-107">**列**</span><span class="sxs-lookup"><span data-stu-id="63fed-107">**Column**</span></span>|<span data-ttu-id="63fed-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="63fed-108">**Data Type**</span></span>|<span data-ttu-id="63fed-109">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="63fed-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="63fed-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="63fed-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="63fed-111">int</span><span class="sxs-lookup"><span data-stu-id="63fed-111">int</span></span>  <br/> |<span data-ttu-id="63fed-112">标识此用户代理的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="63fed-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="63fed-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="63fed-113">UserAgent</span></span>  <br/> |<span data-ttu-id="63fed-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63fed-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="63fed-115">用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="63fed-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="63fed-116">UAType</span><span class="sxs-lookup"><span data-stu-id="63fed-116">UAType</span></span>  <br/> |<span data-ttu-id="63fed-117">smallint</span><span class="sxs-lookup"><span data-stu-id="63fed-117">smallint</span></span>  <br/> |<span data-ttu-id="63fed-118">用户代理的类型。</span><span class="sxs-lookup"><span data-stu-id="63fed-118">Type of user agent.</span></span> <span data-ttu-id="63fed-119">请参阅[UserAgent 表](useragent.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="63fed-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="63fed-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="63fed-120">UACategory</span></span>  <br/> |<span data-ttu-id="63fed-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="63fed-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="63fed-122">用户代理所属的类别。</span><span class="sxs-lookup"><span data-stu-id="63fed-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="63fed-123">例如，用户代理 Conferencing_Attendant_1.0 所属 UACategory CAA。</span><span class="sxs-lookup"><span data-stu-id="63fed-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

