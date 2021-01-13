---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: LastChatId 包含上次为每个用户生成的并且在 tblChat 表中使用的聊天 ID。
ms.openlocfilehash: 80664d6b296fce9b4909674f9d21b1aa13285826
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816002"
---
# <a name="tbllastchatid"></a><span data-ttu-id="5837f-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="5837f-103">tblLastChatId</span></span>
 
<span data-ttu-id="5837f-104">LastChatId 包含上次为每个用户生成的并且在 tblChat 表中使用的聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="5837f-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="5837f-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="5837f-105">**Columns**</span></span>

|<span data-ttu-id="5837f-106">**列**</span><span class="sxs-lookup"><span data-stu-id="5837f-106">**Column**</span></span>|<span data-ttu-id="5837f-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="5837f-107">**Type**</span></span>|<span data-ttu-id="5837f-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="5837f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5837f-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="5837f-109">nodeID</span></span>  <br/> |<span data-ttu-id="5837f-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="5837f-110">int, not null</span></span>  <br/> |<span data-ttu-id="5837f-111">节点 ID（仅限聊天室类型）。</span><span class="sxs-lookup"><span data-stu-id="5837f-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="5837f-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="5837f-112">lastChatID</span></span>  <br/> |<span data-ttu-id="5837f-113">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="5837f-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="5837f-114">上次使用的聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="5837f-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="5837f-115">**Keys**</span><span class="sxs-lookup"><span data-stu-id="5837f-115">**Keys**</span></span>

|<span data-ttu-id="5837f-116">**列**</span><span class="sxs-lookup"><span data-stu-id="5837f-116">**Column**</span></span>|<span data-ttu-id="5837f-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="5837f-117">**Description**</span></span>|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |<span data-ttu-id="5837f-118">主键（只有 nodeID 足以进行处理）。</span><span class="sxs-lookup"><span data-stu-id="5837f-118">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="5837f-119">nodeID</span><span class="sxs-lookup"><span data-stu-id="5837f-119">nodeID</span></span>  <br/> |<span data-ttu-id="5837f-120">其查找包含在 tblNode.nodeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="5837f-120">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5837f-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5837f-121">See also</span></span>

[<span data-ttu-id="5837f-122">tblChat</span><span class="sxs-lookup"><span data-stu-id="5837f-122">tblChat</span></span>](tblchat.md)
