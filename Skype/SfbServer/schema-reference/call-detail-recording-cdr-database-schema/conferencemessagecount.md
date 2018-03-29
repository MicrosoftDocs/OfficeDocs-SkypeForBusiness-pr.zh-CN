---
title: 在业务服务器 2015年的 Skype 的 ConferenceMessageCount 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: 此表中的每个记录表示一个用户在一个 IM 会议，包括由该用户发送的邮件数。 每个会议表示的多个记录表;每个用户的的一个记录。
ms.openlocfilehash: 6b9dfcf0743c03e69726bb501cc7a4a961bf5df8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d9cf7-104">在业务服务器 2015年的 Skype 的 ConferenceMessageCount 表</span><span class="sxs-lookup"><span data-stu-id="d9cf7-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d9cf7-105">此表中的每个记录表示一个用户在一个 IM 会议，包括由该用户发送的邮件数。</span><span class="sxs-lookup"><span data-stu-id="d9cf7-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="d9cf7-106">每个会议表示的多个记录表;每个用户的的一个记录。</span><span class="sxs-lookup"><span data-stu-id="d9cf7-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="d9cf7-107">**列**</span><span class="sxs-lookup"><span data-stu-id="d9cf7-107">**Column**</span></span>|<span data-ttu-id="d9cf7-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d9cf7-108">**Data Type**</span></span>|<span data-ttu-id="d9cf7-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="d9cf7-109">**Key/Index**</span></span>|<span data-ttu-id="d9cf7-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="d9cf7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d9cf7-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="d9cf7-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="d9cf7-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d9cf7-112">datetime</span></span>  <br/> |<span data-ttu-id="d9cf7-113">主键和外</span><span class="sxs-lookup"><span data-stu-id="d9cf7-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d9cf7-114">会议实例的时间。</span><span class="sxs-lookup"><span data-stu-id="d9cf7-114">Time of conference instance.</span></span> <span data-ttu-id="d9cf7-115">与**SessionIdSeq**配合使用，以唯一标识的会议实例。</span><span class="sxs-lookup"><span data-stu-id="d9cf7-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="d9cf7-116">[业务服务器 2015年的 Skype 在会议表格](conferences.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="d9cf7-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d9cf7-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="d9cf7-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="d9cf7-118">int</span><span class="sxs-lookup"><span data-stu-id="d9cf7-118">int</span></span>  <br/> |<span data-ttu-id="d9cf7-119">主键和外</span><span class="sxs-lookup"><span data-stu-id="d9cf7-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d9cf7-120">若要标识的会议实例的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="d9cf7-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="d9cf7-121">与**SessionIdTime**配合使用，以唯一标识的会议实例。</span><span class="sxs-lookup"><span data-stu-id="d9cf7-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="d9cf7-122">[业务服务器 2015年的 Skype 在会议表格](conferences.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="d9cf7-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d9cf7-123">**用户 Id**</span><span class="sxs-lookup"><span data-stu-id="d9cf7-123">**UserId**</span></span> <br/> |<span data-ttu-id="d9cf7-124">int</span><span class="sxs-lookup"><span data-stu-id="d9cf7-124">int</span></span>  <br/> |<span data-ttu-id="d9cf7-125">外</span><span class="sxs-lookup"><span data-stu-id="d9cf7-125">Foreign</span></span>  <br/> |<span data-ttu-id="d9cf7-126">标识该用户，从[用户表](users.md)中引用的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="d9cf7-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="d9cf7-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="d9cf7-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="d9cf7-128">smallint</span><span class="sxs-lookup"><span data-stu-id="d9cf7-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="d9cf7-129">这次会议过程中由该用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="d9cf7-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

