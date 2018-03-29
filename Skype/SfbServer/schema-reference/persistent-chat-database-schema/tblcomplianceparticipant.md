---
title: tblComplianceParticipant
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant 包含当前参与者每个通道，每个服务器。
ms.openlocfilehash: ba488f377592b48845880acaeed61074bc31ccd2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="6b6e4-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="6b6e4-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="6b6e4-104">tblComplianceParticipant 包含当前参与者每个通道，每个服务器。</span><span class="sxs-lookup"><span data-stu-id="6b6e4-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="6b6e4-105">**列**</span><span class="sxs-lookup"><span data-stu-id="6b6e4-105">**Columns**</span></span>

|<span data-ttu-id="6b6e4-106">**列**</span><span class="sxs-lookup"><span data-stu-id="6b6e4-106">**Column**</span></span>|<span data-ttu-id="6b6e4-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="6b6e4-107">**Type**</span></span>|<span data-ttu-id="6b6e4-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="6b6e4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6b6e4-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="6b6e4-109">channelUri</span></span>  <br/> |<span data-ttu-id="6b6e4-110">nvarchar (255) 不为空</span><span class="sxs-lookup"><span data-stu-id="6b6e4-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="6b6e4-111">统一资源标识符 (URI) 的通道。</span><span class="sxs-lookup"><span data-stu-id="6b6e4-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="6b6e4-112">用户 Id</span><span class="sxs-lookup"><span data-stu-id="6b6e4-112">userId</span></span>  <br/> |<span data-ttu-id="6b6e4-113">int，不为空</span><span class="sxs-lookup"><span data-stu-id="6b6e4-113">int, not null</span></span>  <br/> |<span data-ttu-id="6b6e4-114">（对应于 tblPrincipal.prinID 表） 的参与者的主体 ID。</span><span class="sxs-lookup"><span data-stu-id="6b6e4-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="6b6e4-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="6b6e4-115">joinedAt</span></span>  <br/> |<span data-ttu-id="6b6e4-116">bigint，不为空</span><span class="sxs-lookup"><span data-stu-id="6b6e4-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="6b6e4-117">连接事件的时间戳。</span><span class="sxs-lookup"><span data-stu-id="6b6e4-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="6b6e4-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="6b6e4-118">partedAt</span></span>  <br/> |<span data-ttu-id="6b6e4-119">bigint</span><span class="sxs-lookup"><span data-stu-id="6b6e4-119">bigint</span></span>  <br/> |<span data-ttu-id="6b6e4-120">如果参与者仍加入，则为 null。</span><span class="sxs-lookup"><span data-stu-id="6b6e4-120">Null if participant is still joined.</span></span> <span data-ttu-id="6b6e4-121">如果不为 null，则将事件通道的时间戳。</span><span class="sxs-lookup"><span data-stu-id="6b6e4-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="6b6e4-122">在所有翻译人员处理事件最终删除这些条目。</span><span class="sxs-lookup"><span data-stu-id="6b6e4-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="6b6e4-123">userUri</span><span class="sxs-lookup"><span data-stu-id="6b6e4-123">userUri</span></span>  <br/> |<span data-ttu-id="6b6e4-124">nvarchar(255)，不为空</span><span class="sxs-lookup"><span data-stu-id="6b6e4-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="6b6e4-125">用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="6b6e4-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="6b6e4-126">serverID</span><span class="sxs-lookup"><span data-stu-id="6b6e4-126">serverID</span></span>  <br/> |<span data-ttu-id="6b6e4-127">int</span><span class="sxs-lookup"><span data-stu-id="6b6e4-127">int</span></span>  <br/> |<span data-ttu-id="6b6e4-128">服务器标识 （例如，tblServerIdentity.serverID 表）。</span><span class="sxs-lookup"><span data-stu-id="6b6e4-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="6b6e4-129">会话标识符</span><span class="sxs-lookup"><span data-stu-id="6b6e4-129">sessionId</span></span>  <br/> |<span data-ttu-id="6b6e4-130">bigint</span><span class="sxs-lookup"><span data-stu-id="6b6e4-130">bigint</span></span>  <br/> |<span data-ttu-id="6b6e4-131">服务器会话。</span><span class="sxs-lookup"><span data-stu-id="6b6e4-131">Server session.</span></span> <span data-ttu-id="6b6e4-132">这是一个随机数生成每次聊天服务启动。</span><span class="sxs-lookup"><span data-stu-id="6b6e4-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="6b6e4-133">它用来区分会话以便可以标识孤立的参与者。</span><span class="sxs-lookup"><span data-stu-id="6b6e4-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="6b6e4-134">**密钥**</span><span class="sxs-lookup"><span data-stu-id="6b6e4-134">**Key**</span></span>

|<span data-ttu-id="6b6e4-135">**列**</span><span class="sxs-lookup"><span data-stu-id="6b6e4-135">**Column**</span></span>|<span data-ttu-id="6b6e4-136">**说明**</span><span class="sxs-lookup"><span data-stu-id="6b6e4-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6b6e4-137">\<channelUri，用户 Id joinedAt\></span><span class="sxs-lookup"><span data-stu-id="6b6e4-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="6b6e4-138">为主键。</span><span class="sxs-lookup"><span data-stu-id="6b6e4-138">Primary key.</span></span>  <br/> |
   

