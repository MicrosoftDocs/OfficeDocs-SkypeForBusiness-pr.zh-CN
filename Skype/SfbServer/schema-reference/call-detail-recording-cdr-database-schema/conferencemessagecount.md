---
title: Skype for Business Server 2015 中的 ConferenceMessageCount 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: 此表中的每条记录表示一个 IM 会议中的一个用户, 包括该用户发送的消息数。 每个会议都由该表中的多条记录表示;每个用户一条记录。
ms.openlocfilehash: ef343536c34b3bd27d71ee37813e4b4e65156094
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296453"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="fb893-104">Skype for Business Server 2015 中的 ConferenceMessageCount 表</span><span class="sxs-lookup"><span data-stu-id="fb893-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fb893-105">此表中的每条记录表示一个 IM 会议中的一个用户, 包括该用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="fb893-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="fb893-106">每个会议都由该表中的多条记录表示;每个用户一条记录。</span><span class="sxs-lookup"><span data-stu-id="fb893-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="fb893-107">**列**</span><span class="sxs-lookup"><span data-stu-id="fb893-107">**Column**</span></span>|<span data-ttu-id="fb893-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="fb893-108">**Data Type**</span></span>|<span data-ttu-id="fb893-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="fb893-109">**Key/Index**</span></span>|<span data-ttu-id="fb893-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="fb893-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fb893-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="fb893-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="fb893-112">datetime</span><span class="sxs-lookup"><span data-stu-id="fb893-112">datetime</span></span>  <br/> |<span data-ttu-id="fb893-113">主、外部</span><span class="sxs-lookup"><span data-stu-id="fb893-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="fb893-114">会议实例的时间。</span><span class="sxs-lookup"><span data-stu-id="fb893-114">Time of conference instance.</span></span> <span data-ttu-id="fb893-115">与**SessionIdSeq**结合使用以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="fb893-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="fb893-116">有关详细信息, 请参阅[Skype For Business Server 2015 中](conferences.md)的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="fb893-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="fb893-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="fb893-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="fb893-118">int</span><span class="sxs-lookup"><span data-stu-id="fb893-118">int</span></span>  <br/> |<span data-ttu-id="fb893-119">主、外部</span><span class="sxs-lookup"><span data-stu-id="fb893-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="fb893-120">标识会议实例的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="fb893-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="fb893-121">与**SessionIdTime**结合使用以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="fb893-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="fb893-122">有关详细信息, 请参阅[Skype For Business Server 2015 中](conferences.md)的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="fb893-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="fb893-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="fb893-123">**UserId**</span></span> <br/> |<span data-ttu-id="fb893-124">int</span><span class="sxs-lookup"><span data-stu-id="fb893-124">int</span></span>  <br/> |<span data-ttu-id="fb893-125">外表</span><span class="sxs-lookup"><span data-stu-id="fb893-125">Foreign</span></span>  <br/> |<span data-ttu-id="fb893-126">标识此用户的唯一号码, 从 "[用户" 表](users.md)中引用。</span><span class="sxs-lookup"><span data-stu-id="fb893-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="fb893-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="fb893-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="fb893-128">smallint</span><span class="sxs-lookup"><span data-stu-id="fb893-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="fb893-129">此用户在此会议期间发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="fb893-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

