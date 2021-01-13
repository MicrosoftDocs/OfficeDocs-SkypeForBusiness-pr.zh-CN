---
title: ConferenceMessageCount 视图
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount 视图存储有关用户已向会议中发送的消息数的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 8394ed37d4b85e8ec5fcda4234b4c28f4276fb17
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813292"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="66442-104">ConferenceMessageCount 视图</span><span class="sxs-lookup"><span data-stu-id="66442-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="66442-105">ConferenceMessageCount 视图存储有关用户已向会议中发送的消息数的信息。</span><span class="sxs-lookup"><span data-stu-id="66442-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="66442-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="66442-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="66442-107">ConferenceMessageCount 视图包含 [ConferenceSessionDetails](conferencesessiondetails.md) 视图中的所有列以及下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="66442-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="66442-108">**列**</span><span class="sxs-lookup"><span data-stu-id="66442-108">**Column**</span></span>|<span data-ttu-id="66442-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="66442-109">**Data Type**</span></span>|<span data-ttu-id="66442-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="66442-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="66442-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="66442-111">**UserUri**</span></span> <br/> |<span data-ttu-id="66442-112">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="66442-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="66442-113">发送消息的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="66442-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="66442-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="66442-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="66442-115">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="66442-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="66442-116">发送消息的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="66442-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="66442-117">有关详细信息， [请参阅 UriTypes](uritypes.md) 表。</span><span class="sxs-lookup"><span data-stu-id="66442-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="66442-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="66442-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="66442-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="66442-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="66442-120">发送消息的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="66442-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="66442-121">有关详细信息 [，请参阅"租户](tenants.md) "表。</span><span class="sxs-lookup"><span data-stu-id="66442-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="66442-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="66442-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="66442-123">smallint</span><span class="sxs-lookup"><span data-stu-id="66442-123">smallint</span></span>  <br/> |<span data-ttu-id="66442-124">用户在会议会话期间发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="66442-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

