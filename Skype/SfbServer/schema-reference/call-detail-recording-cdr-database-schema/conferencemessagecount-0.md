---
title: ConferenceMessageCount 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount 视图存储有关用户向会议发送的邮件数的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 890a5912c6f828f614fbff89627c94c4e12ba7e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296488"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="3caf9-104">ConferenceMessageCount 视图</span><span class="sxs-lookup"><span data-stu-id="3caf9-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="3caf9-105">ConferenceMessageCount 视图存储有关用户向会议发送的邮件数的信息。</span><span class="sxs-lookup"><span data-stu-id="3caf9-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="3caf9-106">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="3caf9-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3caf9-107">ConferenceMessageCount 视图包含[ConferenceSessionDetails 视图](conferencesessiondetails.md)中的所有列以及下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="3caf9-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="3caf9-108">**列**</span><span class="sxs-lookup"><span data-stu-id="3caf9-108">**Column**</span></span>|<span data-ttu-id="3caf9-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3caf9-109">**Data Type**</span></span>|<span data-ttu-id="3caf9-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="3caf9-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3caf9-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="3caf9-111">**UserUri**</span></span> <br/> |<span data-ttu-id="3caf9-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3caf9-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="3caf9-113">发送邮件的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="3caf9-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="3caf9-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="3caf9-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="3caf9-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3caf9-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3caf9-116">发送邮件的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="3caf9-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="3caf9-117">有关详细信息, 请参阅[UriTypes 表](uritypes.md)。</span><span class="sxs-lookup"><span data-stu-id="3caf9-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3caf9-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="3caf9-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="3caf9-119">标识符</span><span class="sxs-lookup"><span data-stu-id="3caf9-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="3caf9-120">发送消息的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="3caf9-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="3caf9-121">有关详细信息, 请参阅[租户表](tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="3caf9-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3caf9-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="3caf9-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="3caf9-123">smallint</span><span class="sxs-lookup"><span data-stu-id="3caf9-123">smallint</span></span>  <br/> |<span data-ttu-id="3caf9-124">在会议会话期间用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="3caf9-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

