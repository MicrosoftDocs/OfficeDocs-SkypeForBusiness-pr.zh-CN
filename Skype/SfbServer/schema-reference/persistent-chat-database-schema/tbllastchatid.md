---
title: tblLastChatId
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
ms.openlocfilehash: dc25eb68ee1b4069ba54133548f743ca45b73e16
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505086"
---
# <a name="tbllastchatid"></a><span data-ttu-id="fb2a9-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="fb2a9-103">tblLastChatId</span></span>
 
<span data-ttu-id="fb2a9-104">Lastchatid 包含为每个用户生成并且在 tblChat 表中使用） 的上一个聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="fb2a9-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="fb2a9-105">**列**</span><span class="sxs-lookup"><span data-stu-id="fb2a9-105">**Columns**</span></span>

|<span data-ttu-id="fb2a9-106">**列**</span><span class="sxs-lookup"><span data-stu-id="fb2a9-106">**Column**</span></span>|<span data-ttu-id="fb2a9-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="fb2a9-107">**Type**</span></span>|<span data-ttu-id="fb2a9-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="fb2a9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fb2a9-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="fb2a9-109">nodeID</span></span>  <br/> |<span data-ttu-id="fb2a9-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="fb2a9-110">int, not null</span></span>  <br/> |<span data-ttu-id="fb2a9-111">节点 ID （仅限聊天室类型）。</span><span class="sxs-lookup"><span data-stu-id="fb2a9-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="fb2a9-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="fb2a9-112">lastChatID</span></span>  <br/> |<span data-ttu-id="fb2a9-113">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="fb2a9-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="fb2a9-114">上次使用的聊天 id。</span><span class="sxs-lookup"><span data-stu-id="fb2a9-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="fb2a9-115">**键**</span><span class="sxs-lookup"><span data-stu-id="fb2a9-115">**Keys**</span></span>

|<span data-ttu-id="fb2a9-116">**列**</span><span class="sxs-lookup"><span data-stu-id="fb2a9-116">**Column**</span></span>|<span data-ttu-id="fb2a9-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="fb2a9-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fb2a9-118">\<nodeID lastChatID\></span><span class="sxs-lookup"><span data-stu-id="fb2a9-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="fb2a9-119">主键 (只有 nodeid 足以进行处理)。</span><span class="sxs-lookup"><span data-stu-id="fb2a9-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="fb2a9-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="fb2a9-120">nodeID</span></span>  <br/> |<span data-ttu-id="fb2a9-121">在 tblNode.nodeID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="fb2a9-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="fb2a9-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb2a9-122">See also</span></span>

[<span data-ttu-id="fb2a9-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="fb2a9-123">tblChat</span></span>](tblchat.md)