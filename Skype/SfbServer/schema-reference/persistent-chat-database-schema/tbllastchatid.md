---
title: tblLastChatId
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: Lastchatid 包含为每个用户生成并且在 tblChat 表中使用） 的上一个聊天 ID。
ms.openlocfilehash: 3208ada77643957295f9894cb58187c2b4bc7493
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884927"
---
# <a name="tbllastchatid"></a><span data-ttu-id="91527-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="91527-103">tblLastChatId</span></span>
 
<span data-ttu-id="91527-104">Lastchatid 包含为每个用户生成并且在 tblChat 表中使用） 的上一个聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="91527-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="91527-105">**列**</span><span class="sxs-lookup"><span data-stu-id="91527-105">**Columns**</span></span>

|<span data-ttu-id="91527-106">**列**</span><span class="sxs-lookup"><span data-stu-id="91527-106">**Column**</span></span>|<span data-ttu-id="91527-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="91527-107">**Type**</span></span>|<span data-ttu-id="91527-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="91527-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="91527-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="91527-109">nodeID</span></span>  <br/> |<span data-ttu-id="91527-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="91527-110">int, not null</span></span>  <br/> |<span data-ttu-id="91527-111">节点 ID （仅限聊天室类型）。</span><span class="sxs-lookup"><span data-stu-id="91527-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="91527-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="91527-112">lastChatID</span></span>  <br/> |<span data-ttu-id="91527-113">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="91527-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="91527-114">上次使用的聊天 id。</span><span class="sxs-lookup"><span data-stu-id="91527-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="91527-115">**键**</span><span class="sxs-lookup"><span data-stu-id="91527-115">**Keys**</span></span>

|<span data-ttu-id="91527-116">**列**</span><span class="sxs-lookup"><span data-stu-id="91527-116">**Column**</span></span>|<span data-ttu-id="91527-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="91527-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="91527-118">\<nodeID lastChatID\></span><span class="sxs-lookup"><span data-stu-id="91527-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="91527-119">主键 (只有 nodeid 足以进行处理)。</span><span class="sxs-lookup"><span data-stu-id="91527-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="91527-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="91527-120">nodeID</span></span>  <br/> |<span data-ttu-id="91527-121">在 tblNode.nodeID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="91527-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="91527-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91527-122">See also</span></span>

[<span data-ttu-id="91527-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="91527-123">tblChat</span></span>](tblchat.md)
