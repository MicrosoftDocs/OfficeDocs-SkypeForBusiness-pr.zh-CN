---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant 包含每个频道和每台服务器的当前参与者。
ms.openlocfilehash: bf6913d8bcc11db1589169c4479cec4a0238825d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295459"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="28cd2-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="28cd2-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="28cd2-104">tblComplianceParticipant 包含每个频道和每台服务器的当前参与者。</span><span class="sxs-lookup"><span data-stu-id="28cd2-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="28cd2-105">**多**</span><span class="sxs-lookup"><span data-stu-id="28cd2-105">**Columns**</span></span>

|<span data-ttu-id="28cd2-106">**列**</span><span class="sxs-lookup"><span data-stu-id="28cd2-106">**Column**</span></span>|<span data-ttu-id="28cd2-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="28cd2-107">**Type**</span></span>|<span data-ttu-id="28cd2-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="28cd2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="28cd2-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="28cd2-109">channelUri</span></span>  <br/> |<span data-ttu-id="28cd2-110">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="28cd2-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="28cd2-111">通道统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="28cd2-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="28cd2-112">userId</span><span class="sxs-lookup"><span data-stu-id="28cd2-112">userId</span></span>  <br/> |<span data-ttu-id="28cd2-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="28cd2-113">int, not null</span></span>  <br/> |<span data-ttu-id="28cd2-114">参与者的主体 ID (对应于 tblPrincipal 表)。</span><span class="sxs-lookup"><span data-stu-id="28cd2-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="28cd2-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="28cd2-115">joinedAt</span></span>  <br/> |<span data-ttu-id="28cd2-116">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="28cd2-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="28cd2-117">联接事件的时间戳。</span><span class="sxs-lookup"><span data-stu-id="28cd2-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="28cd2-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="28cd2-118">partedAt</span></span>  <br/> |<span data-ttu-id="28cd2-119">bigint</span><span class="sxs-lookup"><span data-stu-id="28cd2-119">bigint</span></span>  <br/> |<span data-ttu-id="28cd2-120">如果参与者仍处于加入, 则为 Null。</span><span class="sxs-lookup"><span data-stu-id="28cd2-120">Null if participant is still joined.</span></span> <span data-ttu-id="28cd2-121">如果 not null, 则通道的时间戳会留下事件。</span><span class="sxs-lookup"><span data-stu-id="28cd2-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="28cd2-122">这些条目最终会在所有翻译人员处理该事件时被删除。</span><span class="sxs-lookup"><span data-stu-id="28cd2-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="28cd2-123">userUri</span><span class="sxs-lookup"><span data-stu-id="28cd2-123">userUri</span></span>  <br/> |<span data-ttu-id="28cd2-124">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="28cd2-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="28cd2-125">用户 URI。</span><span class="sxs-lookup"><span data-stu-id="28cd2-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="28cd2-126">serverID</span><span class="sxs-lookup"><span data-stu-id="28cd2-126">serverID</span></span>  <br/> |<span data-ttu-id="28cd2-127">int</span><span class="sxs-lookup"><span data-stu-id="28cd2-127">int</span></span>  <br/> |<span data-ttu-id="28cd2-128">服务器标识 (如 tblServerIdentity 表中所示)。</span><span class="sxs-lookup"><span data-stu-id="28cd2-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="28cd2-129">标识符</span><span class="sxs-lookup"><span data-stu-id="28cd2-129">sessionId</span></span>  <br/> |<span data-ttu-id="28cd2-130">bigint</span><span class="sxs-lookup"><span data-stu-id="28cd2-130">bigint</span></span>  <br/> |<span data-ttu-id="28cd2-131">服务器会话。</span><span class="sxs-lookup"><span data-stu-id="28cd2-131">Server session.</span></span> <span data-ttu-id="28cd2-132">这是每次启动聊天服务时生成的随机数字。</span><span class="sxs-lookup"><span data-stu-id="28cd2-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="28cd2-133">它用于为识别孤立参与者的目的而区分会话。</span><span class="sxs-lookup"><span data-stu-id="28cd2-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="28cd2-134">**关键字**</span><span class="sxs-lookup"><span data-stu-id="28cd2-134">**Key**</span></span>

|<span data-ttu-id="28cd2-135">**列**</span><span class="sxs-lookup"><span data-stu-id="28cd2-135">**Column**</span></span>|<span data-ttu-id="28cd2-136">**说明**</span><span class="sxs-lookup"><span data-stu-id="28cd2-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="28cd2-137">\<channelUri、userId、joinedAt\></span><span class="sxs-lookup"><span data-stu-id="28cd2-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="28cd2-138">主键。</span><span class="sxs-lookup"><span data-stu-id="28cd2-138">Primary key.</span></span>  <br/> |
   

