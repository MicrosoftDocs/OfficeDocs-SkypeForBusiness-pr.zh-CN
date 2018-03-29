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
description: tblLastChatId 包含已生成 （和 tblChat 表中） 的最后一个聊天 ID 为每个用户。
ms.openlocfilehash: 4a22dc9ba1c2dbe15ae0a24de6e4f347a62deaee
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastchatid"></a><span data-ttu-id="168e3-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="168e3-103">tblLastChatId</span></span>
 
<span data-ttu-id="168e3-104">tblLastChatId 包含已生成 （和 tblChat 表中） 的最后一个聊天 ID 为每个用户。</span><span class="sxs-lookup"><span data-stu-id="168e3-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="168e3-105">**列**</span><span class="sxs-lookup"><span data-stu-id="168e3-105">**Columns**</span></span>

|<span data-ttu-id="168e3-106">**列**</span><span class="sxs-lookup"><span data-stu-id="168e3-106">**Column**</span></span>|<span data-ttu-id="168e3-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="168e3-107">**Type**</span></span>|<span data-ttu-id="168e3-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="168e3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="168e3-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="168e3-109">nodeID</span></span>  <br/> |<span data-ttu-id="168e3-110">int，不为空</span><span class="sxs-lookup"><span data-stu-id="168e3-110">int, not null</span></span>  <br/> |<span data-ttu-id="168e3-111">节点 ID （仅聊天室类型）。</span><span class="sxs-lookup"><span data-stu-id="168e3-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="168e3-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="168e3-112">lastChatID</span></span>  <br/> |<span data-ttu-id="168e3-113">bigint，不为空</span><span class="sxs-lookup"><span data-stu-id="168e3-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="168e3-114">最后用的聊天 id。</span><span class="sxs-lookup"><span data-stu-id="168e3-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="168e3-115">**密钥**</span><span class="sxs-lookup"><span data-stu-id="168e3-115">**Keys**</span></span>

|<span data-ttu-id="168e3-116">**列**</span><span class="sxs-lookup"><span data-stu-id="168e3-116">**Column**</span></span>|<span data-ttu-id="168e3-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="168e3-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="168e3-118">\<nodeID lastChatID\></span><span class="sxs-lookup"><span data-stu-id="168e3-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="168e3-119">主关键字 （仅 nodeID 是足够进行处理）。</span><span class="sxs-lookup"><span data-stu-id="168e3-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="168e3-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="168e3-120">nodeID</span></span>  <br/> |<span data-ttu-id="168e3-121">TblNode.nodeID 表中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="168e3-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="168e3-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="168e3-122">See also</span></span>

#### 

[<span data-ttu-id="168e3-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="168e3-123">tblChat</span></span>](tblchat.md)

