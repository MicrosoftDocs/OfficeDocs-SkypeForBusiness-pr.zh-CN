---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant 包含每个通道和每台服务器的当前参与者。
ms.openlocfilehash: c6aae3c1e7b13456708034512c6b68d67d6d1f92
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809742"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="e5b16-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="e5b16-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="e5b16-104">tblComplianceParticipant 包含每个通道和每台服务器的当前参与者。</span><span class="sxs-lookup"><span data-stu-id="e5b16-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="e5b16-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="e5b16-105">**Columns**</span></span>

|<span data-ttu-id="e5b16-106">**列**</span><span class="sxs-lookup"><span data-stu-id="e5b16-106">**Column**</span></span>|<span data-ttu-id="e5b16-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="e5b16-107">**Type**</span></span>|<span data-ttu-id="e5b16-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="e5b16-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e5b16-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="e5b16-109">channelUri</span></span>  <br/> |<span data-ttu-id="e5b16-110">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="e5b16-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="e5b16-111">通道统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="e5b16-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="e5b16-112">userId</span><span class="sxs-lookup"><span data-stu-id="e5b16-112">userId</span></span>  <br/> |<span data-ttu-id="e5b16-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="e5b16-113">int, not null</span></span>  <br/> |<span data-ttu-id="e5b16-114">参与者的主体 ID（与 tblPrincipal.prinID 表对应）。</span><span class="sxs-lookup"><span data-stu-id="e5b16-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="e5b16-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="e5b16-115">joinedAt</span></span>  <br/> |<span data-ttu-id="e5b16-116">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="e5b16-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="e5b16-117">加入事件的时间戳。</span><span class="sxs-lookup"><span data-stu-id="e5b16-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="e5b16-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="e5b16-118">partedAt</span></span>  <br/> |<span data-ttu-id="e5b16-119">bigint</span><span class="sxs-lookup"><span data-stu-id="e5b16-119">bigint</span></span>  <br/> |<span data-ttu-id="e5b16-p101">如果仍加入参与者，则为 null。如果不为 null，则为通道离开事件的时间戳。</span><span class="sxs-lookup"><span data-stu-id="e5b16-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="e5b16-122">当所有转换器处理该事件时，将最终删除这些项。</span><span class="sxs-lookup"><span data-stu-id="e5b16-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="e5b16-123">userUri</span><span class="sxs-lookup"><span data-stu-id="e5b16-123">userUri</span></span>  <br/> |<span data-ttu-id="e5b16-124">nvarchar(255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="e5b16-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="e5b16-125">用户 URI。</span><span class="sxs-lookup"><span data-stu-id="e5b16-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="e5b16-126">serverID</span><span class="sxs-lookup"><span data-stu-id="e5b16-126">serverID</span></span>  <br/> |<span data-ttu-id="e5b16-127">int</span><span class="sxs-lookup"><span data-stu-id="e5b16-127">int</span></span>  <br/> |<span data-ttu-id="e5b16-128">服务器标识（如 tblServerIdentity.serverID 表中所示）。</span><span class="sxs-lookup"><span data-stu-id="e5b16-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="e5b16-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="e5b16-129">sessionId</span></span>  <br/> |<span data-ttu-id="e5b16-130">bigint</span><span class="sxs-lookup"><span data-stu-id="e5b16-130">bigint</span></span>  <br/> |<span data-ttu-id="e5b16-p102">服务器会话。它是每次聊天服务启动时生成的随机数字。它用于区分会话以便标识孤立参与者。</span><span class="sxs-lookup"><span data-stu-id="e5b16-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="e5b16-134">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="e5b16-134">**Key**</span></span>

|<span data-ttu-id="e5b16-135">**列**</span><span class="sxs-lookup"><span data-stu-id="e5b16-135">**Column**</span></span>|<span data-ttu-id="e5b16-136">**说明**</span><span class="sxs-lookup"><span data-stu-id="e5b16-136">**Description**</span></span>|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |<span data-ttu-id="e5b16-137">主键。</span><span class="sxs-lookup"><span data-stu-id="e5b16-137">Primary key.</span></span>  <br/> |
   

