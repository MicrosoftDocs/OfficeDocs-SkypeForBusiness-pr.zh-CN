---
title: Skype for Business Server 2015 中的 ConferenceMessageCount 表
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
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: 此表中的每条记录表示一个 IM 会议中的一个用户，并包括该用户发送的消息数。 每个会议都由此表中的多个记录表示;每个用户一条记录。
ms.openlocfilehash: b931b45915fc12fb01ea36f81bee62f36914e903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813272"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="6b82f-104">Skype for Business Server 2015 中的 ConferenceMessageCount 表</span><span class="sxs-lookup"><span data-stu-id="6b82f-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6b82f-105">此表中的每条记录表示一个 IM 会议中的一个用户，并包括该用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="6b82f-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="6b82f-106">每个会议都由此表中的多个记录表示;每个用户一条记录。</span><span class="sxs-lookup"><span data-stu-id="6b82f-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="6b82f-107">**列**</span><span class="sxs-lookup"><span data-stu-id="6b82f-107">**Column**</span></span>|<span data-ttu-id="6b82f-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="6b82f-108">**Data Type**</span></span>|<span data-ttu-id="6b82f-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="6b82f-109">**Key/Index**</span></span>|<span data-ttu-id="6b82f-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="6b82f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6b82f-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="6b82f-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="6b82f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="6b82f-112">datetime</span></span>  <br/> |<span data-ttu-id="6b82f-113">主、外</span><span class="sxs-lookup"><span data-stu-id="6b82f-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="6b82f-114">会议实例的时间。</span><span class="sxs-lookup"><span data-stu-id="6b82f-114">Time of conference instance.</span></span> <span data-ttu-id="6b82f-115">与 **SessionIdSeq 结合使用** 来唯一地标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="6b82f-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="6b82f-116">有关详细信息 [，请参阅 Skype for Business Server 2015](conferences.md) 中的 Conferences 表。</span><span class="sxs-lookup"><span data-stu-id="6b82f-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6b82f-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="6b82f-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="6b82f-118">int</span><span class="sxs-lookup"><span data-stu-id="6b82f-118">int</span></span>  <br/> |<span data-ttu-id="6b82f-119">主、外</span><span class="sxs-lookup"><span data-stu-id="6b82f-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="6b82f-120">用于标识会议实例的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="6b82f-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="6b82f-121">与 **SessionIdTime** 结合使用来唯一地标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="6b82f-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="6b82f-122">有关详细信息 [，请参阅 Skype for Business Server 2015](conferences.md) 中的 Conferences 表。</span><span class="sxs-lookup"><span data-stu-id="6b82f-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6b82f-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="6b82f-123">**UserId**</span></span> <br/> |<span data-ttu-id="6b82f-124">int</span><span class="sxs-lookup"><span data-stu-id="6b82f-124">int</span></span>  <br/> |<span data-ttu-id="6b82f-125">Foreign</span><span class="sxs-lookup"><span data-stu-id="6b82f-125">Foreign</span></span>  <br/> |<span data-ttu-id="6b82f-126">标识此用户的唯一编号，从 Users 表中 [引用](users.md)。</span><span class="sxs-lookup"><span data-stu-id="6b82f-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="6b82f-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="6b82f-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="6b82f-128">smallint</span><span class="sxs-lookup"><span data-stu-id="6b82f-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="6b82f-129">此用户在此会议期间发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="6b82f-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

