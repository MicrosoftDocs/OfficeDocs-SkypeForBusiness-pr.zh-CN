---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId 包含为每位用户生成 (并在 tblChat 表中使用) 的最后一个聊天 ID。
ms.openlocfilehash: f14d8090fd3252d88ef747de93a987f51870a63b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295396"
---
# <a name="tbllastchatid"></a><span data-ttu-id="06a6b-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="06a6b-103">tblLastChatId</span></span>
 
<span data-ttu-id="06a6b-104">tblLastChatId 包含为每位用户生成 (并在 tblChat 表中使用) 的最后一个聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="06a6b-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="06a6b-105">**多**</span><span class="sxs-lookup"><span data-stu-id="06a6b-105">**Columns**</span></span>

|<span data-ttu-id="06a6b-106">**列**</span><span class="sxs-lookup"><span data-stu-id="06a6b-106">**Column**</span></span>|<span data-ttu-id="06a6b-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="06a6b-107">**Type**</span></span>|<span data-ttu-id="06a6b-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="06a6b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="06a6b-109">a</span><span class="sxs-lookup"><span data-stu-id="06a6b-109">nodeID</span></span>  <br/> |<span data-ttu-id="06a6b-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="06a6b-110">int, not null</span></span>  <br/> |<span data-ttu-id="06a6b-111">节点 ID (聊天室-仅类型)。</span><span class="sxs-lookup"><span data-stu-id="06a6b-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="06a6b-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="06a6b-112">lastChatID</span></span>  <br/> |<span data-ttu-id="06a6b-113">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="06a6b-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="06a6b-114">上次使用的聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="06a6b-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="06a6b-115">**标示**</span><span class="sxs-lookup"><span data-stu-id="06a6b-115">**Keys**</span></span>

|<span data-ttu-id="06a6b-116">**列**</span><span class="sxs-lookup"><span data-stu-id="06a6b-116">**Column**</span></span>|<span data-ttu-id="06a6b-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="06a6b-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="06a6b-118">\<lastChatID\></span><span class="sxs-lookup"><span data-stu-id="06a6b-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="06a6b-119">主关键字 (仅一个参数 a 足以处理)。</span><span class="sxs-lookup"><span data-stu-id="06a6b-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="06a6b-120">a</span><span class="sxs-lookup"><span data-stu-id="06a6b-120">nodeID</span></span>  <br/> |<span data-ttu-id="06a6b-121">带有 tblNode 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="06a6b-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="06a6b-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06a6b-122">See also</span></span>

[<span data-ttu-id="06a6b-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="06a6b-123">tblChat</span></span>](tblchat.md)
