---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant 包含每个通道和每台服务器的当前参与者。
ms.openlocfilehash: a3d18c4a78af2892a837e1105a435a3ce46ea14b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881414"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="87346-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="87346-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="87346-104">tblComplianceParticipant 包含每个通道和每台服务器的当前参与者。</span><span class="sxs-lookup"><span data-stu-id="87346-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="87346-105">**列**</span><span class="sxs-lookup"><span data-stu-id="87346-105">**Columns**</span></span>

|<span data-ttu-id="87346-106">**列**</span><span class="sxs-lookup"><span data-stu-id="87346-106">**Column**</span></span>|<span data-ttu-id="87346-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="87346-107">**Type**</span></span>|<span data-ttu-id="87346-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="87346-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="87346-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="87346-109">channelUri</span></span>  <br/> |<span data-ttu-id="87346-110">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="87346-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="87346-111">通道统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="87346-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="87346-112">用户 Id</span><span class="sxs-lookup"><span data-stu-id="87346-112">userId</span></span>  <br/> |<span data-ttu-id="87346-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="87346-113">int, not null</span></span>  <br/> |<span data-ttu-id="87346-114">（与 tblPrincipal.prinID 表对应） 的参与者的主体 ID。</span><span class="sxs-lookup"><span data-stu-id="87346-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="87346-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="87346-115">joinedAt</span></span>  <br/> |<span data-ttu-id="87346-116">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="87346-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="87346-117">加入事件的时间戳。</span><span class="sxs-lookup"><span data-stu-id="87346-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="87346-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="87346-118">partedAt</span></span>  <br/> |<span data-ttu-id="87346-119">bigint</span><span class="sxs-lookup"><span data-stu-id="87346-119">bigint</span></span>  <br/> |<span data-ttu-id="87346-120">如果参与者仍加入，则为 null。</span><span class="sxs-lookup"><span data-stu-id="87346-120">Null if participant is still joined.</span></span> <span data-ttu-id="87346-121">如果不为 null 离开事件该频道的时间戳。</span><span class="sxs-lookup"><span data-stu-id="87346-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="87346-122">当所有转换器都处理该事件时，将最终删除这些条目。</span><span class="sxs-lookup"><span data-stu-id="87346-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="87346-123">userUri</span><span class="sxs-lookup"><span data-stu-id="87346-123">userUri</span></span>  <br/> |<span data-ttu-id="87346-124">nvarchar （255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="87346-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="87346-125">用户 URI。</span><span class="sxs-lookup"><span data-stu-id="87346-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="87346-126">serverID</span><span class="sxs-lookup"><span data-stu-id="87346-126">serverID</span></span>  <br/> |<span data-ttu-id="87346-127">int</span><span class="sxs-lookup"><span data-stu-id="87346-127">int</span></span>  <br/> |<span data-ttu-id="87346-128">服务器标识 （与 tblServerIdentity.serverID 表）。</span><span class="sxs-lookup"><span data-stu-id="87346-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="87346-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="87346-129">sessionId</span></span>  <br/> |<span data-ttu-id="87346-130">bigint</span><span class="sxs-lookup"><span data-stu-id="87346-130">bigint</span></span>  <br/> |<span data-ttu-id="87346-131">服务器会话。</span><span class="sxs-lookup"><span data-stu-id="87346-131">Server session.</span></span> <span data-ttu-id="87346-132">这是生成每次聊天服务启动一个随机数字。</span><span class="sxs-lookup"><span data-stu-id="87346-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="87346-133">它用于区分以便标识孤立的参与者的会话。</span><span class="sxs-lookup"><span data-stu-id="87346-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="87346-134">**关键字**</span><span class="sxs-lookup"><span data-stu-id="87346-134">**Key**</span></span>

|<span data-ttu-id="87346-135">**列**</span><span class="sxs-lookup"><span data-stu-id="87346-135">**Column**</span></span>|<span data-ttu-id="87346-136">**说明**</span><span class="sxs-lookup"><span data-stu-id="87346-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="87346-137">\<channelUri，用户 Id joinedAt\></span><span class="sxs-lookup"><span data-stu-id="87346-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="87346-138">主键。</span><span class="sxs-lookup"><span data-stu-id="87346-138">Primary key.</span></span>  <br/> |
   

