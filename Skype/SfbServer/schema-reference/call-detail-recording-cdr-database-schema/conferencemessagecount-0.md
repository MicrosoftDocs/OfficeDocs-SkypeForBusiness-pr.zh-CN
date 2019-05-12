---
title: ConferenceMessageCount 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount 视图存储有关多少邮件由用户发送会议信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: ce94cd13637b70b87a92fd688ca8ce8aefd2c69e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901413"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="f0b0c-104">ConferenceMessageCount 视图</span><span class="sxs-lookup"><span data-stu-id="f0b0c-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="f0b0c-105">ConferenceMessageCount 视图存储有关多少邮件由用户发送会议信息。</span><span class="sxs-lookup"><span data-stu-id="f0b0c-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="f0b0c-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="f0b0c-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f0b0c-107">ConferenceMessageCount 视图包含[ConferenceSessionDetails 视图](conferencesessiondetails.md)中的列中所有下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="f0b0c-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="f0b0c-108">**列**</span><span class="sxs-lookup"><span data-stu-id="f0b0c-108">**Column**</span></span>|<span data-ttu-id="f0b0c-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f0b0c-109">**Data Type**</span></span>|<span data-ttu-id="f0b0c-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="f0b0c-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f0b0c-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="f0b0c-111">**UserUri**</span></span> <br/> |<span data-ttu-id="f0b0c-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="f0b0c-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="f0b0c-113">发送邮件的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="f0b0c-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="f0b0c-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="f0b0c-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="f0b0c-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f0b0c-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f0b0c-116">发送邮件的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="f0b0c-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="f0b0c-117">请参阅[UriTypes 表](uritypes.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f0b0c-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="f0b0c-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="f0b0c-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="f0b0c-119">唯一标识符</span><span class="sxs-lookup"><span data-stu-id="f0b0c-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="f0b0c-120">用户的租户，发送邮件。</span><span class="sxs-lookup"><span data-stu-id="f0b0c-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="f0b0c-121">请参阅[Tenants 表](tenants.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f0b0c-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="f0b0c-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="f0b0c-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="f0b0c-123">smallint</span><span class="sxs-lookup"><span data-stu-id="f0b0c-123">smallint</span></span>  <br/> |<span data-ttu-id="f0b0c-124">在会议会话期间发送的用户的消息数。</span><span class="sxs-lookup"><span data-stu-id="f0b0c-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

