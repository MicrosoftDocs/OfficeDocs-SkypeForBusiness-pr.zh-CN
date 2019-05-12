---
title: ConferenceMessageCount 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: 此表中的每条记录代表一个 IM 会议中的一个用户，并包含该用户发送的消息数。 此表; 中的多个记录由表示每个会议每个用户的的一个记录。
ms.openlocfilehash: f45de53333b23368351c8c5330b474cd3260192b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901427"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d4f7f-104">ConferenceMessageCount 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="d4f7f-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d4f7f-105">此表中的每条记录代表一个 IM 会议中的一个用户，并包含该用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="d4f7f-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="d4f7f-106">此表; 中的多个记录由表示每个会议每个用户的的一个记录。</span><span class="sxs-lookup"><span data-stu-id="d4f7f-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="d4f7f-107">**列**</span><span class="sxs-lookup"><span data-stu-id="d4f7f-107">**Column**</span></span>|<span data-ttu-id="d4f7f-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d4f7f-108">**Data Type**</span></span>|<span data-ttu-id="d4f7f-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="d4f7f-109">**Key/Index**</span></span>|<span data-ttu-id="d4f7f-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="d4f7f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d4f7f-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="d4f7f-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="d4f7f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d4f7f-112">datetime</span></span>  <br/> |<span data-ttu-id="d4f7f-113">主、 外</span><span class="sxs-lookup"><span data-stu-id="d4f7f-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d4f7f-114">会议实例的时间。</span><span class="sxs-lookup"><span data-stu-id="d4f7f-114">Time of conference instance.</span></span> <span data-ttu-id="d4f7f-115">与**SessionIdSeq**结合使用，来唯一地标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="d4f7f-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="d4f7f-116">请参阅[Conferences 表中的业务服务器 2015 Skype](conferences.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d4f7f-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d4f7f-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="d4f7f-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="d4f7f-118">int</span><span class="sxs-lookup"><span data-stu-id="d4f7f-118">int</span></span>  <br/> |<span data-ttu-id="d4f7f-119">主、 外</span><span class="sxs-lookup"><span data-stu-id="d4f7f-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d4f7f-120">若要确定会议实例的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="d4f7f-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="d4f7f-121">与**SessionIdTime**结合使用，来唯一地标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="d4f7f-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="d4f7f-122">请参阅[Conferences 表中的业务服务器 2015 Skype](conferences.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d4f7f-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d4f7f-123">**用户 Id**</span><span class="sxs-lookup"><span data-stu-id="d4f7f-123">**UserId**</span></span> <br/> |<span data-ttu-id="d4f7f-124">int</span><span class="sxs-lookup"><span data-stu-id="d4f7f-124">int</span></span>  <br/> |<span data-ttu-id="d4f7f-125">外</span><span class="sxs-lookup"><span data-stu-id="d4f7f-125">Foreign</span></span>  <br/> |<span data-ttu-id="d4f7f-126">标识此用户从[Users table](users.md)引用的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="d4f7f-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="d4f7f-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="d4f7f-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="d4f7f-128">smallint</span><span class="sxs-lookup"><span data-stu-id="d4f7f-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="d4f7f-129">在此会议期间发送的此用户的消息数。</span><span class="sxs-lookup"><span data-stu-id="d4f7f-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

