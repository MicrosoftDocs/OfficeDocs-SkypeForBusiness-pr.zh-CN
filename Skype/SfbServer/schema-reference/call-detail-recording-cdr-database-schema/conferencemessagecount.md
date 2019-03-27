---
title: ConferenceMessageCount 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: 此表中的每条记录代表一个 IM 会议中的一个用户，并包含该用户发送的消息数。 此表; 中的多个记录由表示每个会议每个用户的的一个记录。
ms.openlocfilehash: 60fa79de17c2db14116bd0ffe211e25a61ec9136
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874355"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="f915d-104">ConferenceMessageCount 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="f915d-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f915d-105">此表中的每条记录代表一个 IM 会议中的一个用户，并包含该用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="f915d-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="f915d-106">此表; 中的多个记录由表示每个会议每个用户的的一个记录。</span><span class="sxs-lookup"><span data-stu-id="f915d-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="f915d-107">**列**</span><span class="sxs-lookup"><span data-stu-id="f915d-107">**Column**</span></span>|<span data-ttu-id="f915d-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f915d-108">**Data Type**</span></span>|<span data-ttu-id="f915d-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="f915d-109">**Key/Index**</span></span>|<span data-ttu-id="f915d-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="f915d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f915d-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="f915d-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="f915d-112">datetime</span><span class="sxs-lookup"><span data-stu-id="f915d-112">datetime</span></span>  <br/> |<span data-ttu-id="f915d-113">主、 外</span><span class="sxs-lookup"><span data-stu-id="f915d-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f915d-114">会议实例的时间。</span><span class="sxs-lookup"><span data-stu-id="f915d-114">Time of conference instance.</span></span> <span data-ttu-id="f915d-115">与**SessionIdSeq**结合使用，来唯一地标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="f915d-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="f915d-116">请参阅[Conferences 表中的业务服务器 2015 Skype](conferences.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f915d-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="f915d-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="f915d-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="f915d-118">int</span><span class="sxs-lookup"><span data-stu-id="f915d-118">int</span></span>  <br/> |<span data-ttu-id="f915d-119">主、 外</span><span class="sxs-lookup"><span data-stu-id="f915d-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f915d-120">若要确定会议实例的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="f915d-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="f915d-121">与**SessionIdTime**结合使用，来唯一地标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="f915d-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="f915d-122">请参阅[Conferences 表中的业务服务器 2015 Skype](conferences.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f915d-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="f915d-123">**用户 Id**</span><span class="sxs-lookup"><span data-stu-id="f915d-123">**UserId**</span></span> <br/> |<span data-ttu-id="f915d-124">int</span><span class="sxs-lookup"><span data-stu-id="f915d-124">int</span></span>  <br/> |<span data-ttu-id="f915d-125">外</span><span class="sxs-lookup"><span data-stu-id="f915d-125">Foreign</span></span>  <br/> |<span data-ttu-id="f915d-126">标识此用户从[Users table](users.md)引用的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="f915d-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="f915d-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="f915d-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="f915d-128">smallint</span><span class="sxs-lookup"><span data-stu-id="f915d-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="f915d-129">在此会议期间发送的此用户的消息数。</span><span class="sxs-lookup"><span data-stu-id="f915d-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

