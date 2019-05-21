---
title: UserAgent 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent 视图存储有关在数据库中具有记录的会话中涉及的用户代理的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 874a9c986ec77c3e19b557cd65dcf6dbeb045752
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294605"
---
# <a name="useragent-view"></a><span data-ttu-id="20356-104">UserAgent 视图</span><span class="sxs-lookup"><span data-stu-id="20356-104">UserAgent view</span></span>
 
<span data-ttu-id="20356-105">UserAgent 视图存储有关在数据库中具有记录的会话中涉及的用户代理的信息。</span><span class="sxs-lookup"><span data-stu-id="20356-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="20356-106">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="20356-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="20356-107">**列**</span><span class="sxs-lookup"><span data-stu-id="20356-107">**Column**</span></span>|<span data-ttu-id="20356-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="20356-108">**Data Type**</span></span>|<span data-ttu-id="20356-109">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="20356-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="20356-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="20356-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="20356-111">int</span><span class="sxs-lookup"><span data-stu-id="20356-111">int</span></span>  <br/> |<span data-ttu-id="20356-112">标识此用户代理的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="20356-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="20356-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="20356-113">UserAgent</span></span>  <br/> |<span data-ttu-id="20356-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="20356-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="20356-115">用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="20356-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="20356-116">UAType</span><span class="sxs-lookup"><span data-stu-id="20356-116">UAType</span></span>  <br/> |<span data-ttu-id="20356-117">smallint</span><span class="sxs-lookup"><span data-stu-id="20356-117">smallint</span></span>  <br/> |<span data-ttu-id="20356-118">用户代理的类型。</span><span class="sxs-lookup"><span data-stu-id="20356-118">Type of user agent.</span></span> <span data-ttu-id="20356-119">有关详细信息, 请参阅[UserAgent 表](useragent.md)。</span><span class="sxs-lookup"><span data-stu-id="20356-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="20356-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="20356-120">UACategory</span></span>  <br/> |<span data-ttu-id="20356-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="20356-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="20356-122">用户代理所属的类别。</span><span class="sxs-lookup"><span data-stu-id="20356-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="20356-123">例如, 用户代理 Conferencing_Attendant_ 1.0 属于 UACategory CAA。</span><span class="sxs-lookup"><span data-stu-id="20356-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

