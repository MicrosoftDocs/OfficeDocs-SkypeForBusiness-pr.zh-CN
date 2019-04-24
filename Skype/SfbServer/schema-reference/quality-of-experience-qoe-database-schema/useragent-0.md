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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212065"
---
# <a name="useragent-view"></a><span data-ttu-id="8e953-104">UserAgent 视图</span><span class="sxs-lookup"><span data-stu-id="8e953-104">UserAgent view</span></span>
 
<span data-ttu-id="8e953-105">UserAgent 视图存储有关数据库中包含记录的会话中涉及的用户代理的信息。</span><span class="sxs-lookup"><span data-stu-id="8e953-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="8e953-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="8e953-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="8e953-107">**列**</span><span class="sxs-lookup"><span data-stu-id="8e953-107">**Column**</span></span>|<span data-ttu-id="8e953-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8e953-108">**Data Type**</span></span>|<span data-ttu-id="8e953-109">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="8e953-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8e953-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="8e953-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="8e953-111">int</span><span class="sxs-lookup"><span data-stu-id="8e953-111">int</span></span>  <br/> |<span data-ttu-id="8e953-112">标识此用户代理的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="8e953-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="8e953-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="8e953-113">UserAgent</span></span>  <br/> |<span data-ttu-id="8e953-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8e953-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8e953-115">用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="8e953-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="8e953-116">UAType</span><span class="sxs-lookup"><span data-stu-id="8e953-116">UAType</span></span>  <br/> |<span data-ttu-id="8e953-117">smallint</span><span class="sxs-lookup"><span data-stu-id="8e953-117">smallint</span></span>  <br/> |<span data-ttu-id="8e953-118">用户代理的类型。</span><span class="sxs-lookup"><span data-stu-id="8e953-118">Type of user agent.</span></span> <span data-ttu-id="8e953-119">请参阅[UserAgent 表](useragent.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8e953-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="8e953-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="8e953-120">UACategory</span></span>  <br/> |<span data-ttu-id="8e953-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="8e953-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="8e953-122">用户代理所属的类别。</span><span class="sxs-lookup"><span data-stu-id="8e953-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="8e953-123">例如，用户代理 Conferencing_Attendant_1.0 所属 UACategory CAA。</span><span class="sxs-lookup"><span data-stu-id="8e953-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

