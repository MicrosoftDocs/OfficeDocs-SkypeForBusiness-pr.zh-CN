---
title: ConferenceMessageCount 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount 视图存储多少邮件用户发送到会议有关的信息。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: f0206145217f63e4530d2eac39c7c6533dcf154e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="0b8f6-104">ConferenceMessageCount 视图</span><span class="sxs-lookup"><span data-stu-id="0b8f6-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="0b8f6-105">ConferenceMessageCount 视图存储多少邮件用户发送到会议有关的信息。</span><span class="sxs-lookup"><span data-stu-id="0b8f6-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="0b8f6-106">在 Microsoft Lync Server 2013 引入了此视图。</span><span class="sxs-lookup"><span data-stu-id="0b8f6-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0b8f6-107">ConferenceMessageCount 视图它包含[ConferenceSessionDetails 视图](conferencesessiondetails.md)中的列的所有除了下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="0b8f6-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="0b8f6-108">**列**</span><span class="sxs-lookup"><span data-stu-id="0b8f6-108">**Column**</span></span>|<span data-ttu-id="0b8f6-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0b8f6-109">**Data Type**</span></span>|<span data-ttu-id="0b8f6-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="0b8f6-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0b8f6-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="0b8f6-111">**UserUri**</span></span> <br/> |<span data-ttu-id="0b8f6-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="0b8f6-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="0b8f6-113">发送消息的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="0b8f6-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="0b8f6-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="0b8f6-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="0b8f6-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0b8f6-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0b8f6-116">URI 的用户发送的消息的类型。</span><span class="sxs-lookup"><span data-stu-id="0b8f6-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="0b8f6-117">[UriTypes 表](uritypes.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="0b8f6-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0b8f6-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="0b8f6-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="0b8f6-119">唯一标识符</span><span class="sxs-lookup"><span data-stu-id="0b8f6-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="0b8f6-120">客户端的用户发送邮件的人。</span><span class="sxs-lookup"><span data-stu-id="0b8f6-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="0b8f6-121">[租户表](tenants.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="0b8f6-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0b8f6-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="0b8f6-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="0b8f6-123">smallint</span><span class="sxs-lookup"><span data-stu-id="0b8f6-123">smallint</span></span>  <br/> |<span data-ttu-id="0b8f6-124">会议会话过程中由用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="0b8f6-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

