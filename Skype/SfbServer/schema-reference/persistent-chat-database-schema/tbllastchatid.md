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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId 包含为每位用户生成（并在 tblChat 表中使用）的最后一个聊天 ID。
ms.openlocfilehash: 95498f077948e1b400d0a370762c121def703e8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814580"
---
# <a name="tbllastchatid"></a><span data-ttu-id="bde42-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="bde42-103">tblLastChatId</span></span>
 
<span data-ttu-id="bde42-104">tblLastChatId 包含为每位用户生成（并在 tblChat 表中使用）的最后一个聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="bde42-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="bde42-105">**多**</span><span class="sxs-lookup"><span data-stu-id="bde42-105">**Columns**</span></span>

|<span data-ttu-id="bde42-106">**列**</span><span class="sxs-lookup"><span data-stu-id="bde42-106">**Column**</span></span>|<span data-ttu-id="bde42-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="bde42-107">**Type**</span></span>|<span data-ttu-id="bde42-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="bde42-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bde42-109">a</span><span class="sxs-lookup"><span data-stu-id="bde42-109">nodeID</span></span>  <br/> |<span data-ttu-id="bde42-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="bde42-110">int, not null</span></span>  <br/> |<span data-ttu-id="bde42-111">节点 ID （聊天室-仅类型）。</span><span class="sxs-lookup"><span data-stu-id="bde42-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="bde42-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="bde42-112">lastChatID</span></span>  <br/> |<span data-ttu-id="bde42-113">bigint，not null</span><span class="sxs-lookup"><span data-stu-id="bde42-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="bde42-114">上次使用的聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="bde42-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="bde42-115">**标示**</span><span class="sxs-lookup"><span data-stu-id="bde42-115">**Keys**</span></span>

|<span data-ttu-id="bde42-116">**列**</span><span class="sxs-lookup"><span data-stu-id="bde42-116">**Column**</span></span>|<span data-ttu-id="bde42-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="bde42-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bde42-118">\<lastChatID\></span><span class="sxs-lookup"><span data-stu-id="bde42-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="bde42-119">主关键字（仅一个参数 a 足以处理）。</span><span class="sxs-lookup"><span data-stu-id="bde42-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="bde42-120">a</span><span class="sxs-lookup"><span data-stu-id="bde42-120">nodeID</span></span>  <br/> |<span data-ttu-id="bde42-121">带有 tblNode 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="bde42-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bde42-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bde42-122">See also</span></span>

[<span data-ttu-id="bde42-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="bde42-123">tblChat</span></span>](tblchat.md)
