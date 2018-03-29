---
title: tblActivePeers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers 包含聊天服务之间的当前对等连接。
ms.openlocfilehash: 5dc585a8db67c1bbdcc1c3933018b1296fd75484
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblactivepeers"></a><span data-ttu-id="ff3a2-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="ff3a2-103">tblActivePeers</span></span>
 
<span data-ttu-id="ff3a2-104">tblActivePeers 包含聊天服务之间的当前对等连接。</span><span class="sxs-lookup"><span data-stu-id="ff3a2-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="ff3a2-105">**列**</span><span class="sxs-lookup"><span data-stu-id="ff3a2-105">**Columns**</span></span>

|<span data-ttu-id="ff3a2-106">**列**</span><span class="sxs-lookup"><span data-stu-id="ff3a2-106">**Column**</span></span>|<span data-ttu-id="ff3a2-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="ff3a2-107">**Type**</span></span>|<span data-ttu-id="ff3a2-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="ff3a2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ff3a2-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="ff3a2-109">aplServerID</span></span>  <br/> |<span data-ttu-id="ff3a2-110">int，不为空</span><span class="sxs-lookup"><span data-stu-id="ff3a2-110">int, not null</span></span>  <br/> |<span data-ttu-id="ff3a2-111">过帐此项的服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="ff3a2-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="ff3a2-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="ff3a2-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="ff3a2-113">int，不为空</span><span class="sxs-lookup"><span data-stu-id="ff3a2-113">int, not null</span></span>  <br/> |<span data-ttu-id="ff3a2-114">连接到发布服务器的对等方的 ID。</span><span class="sxs-lookup"><span data-stu-id="ff3a2-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="ff3a2-115">**密钥**</span><span class="sxs-lookup"><span data-stu-id="ff3a2-115">**Keys**</span></span>

|<span data-ttu-id="ff3a2-116">**列**</span><span class="sxs-lookup"><span data-stu-id="ff3a2-116">**Column**</span></span>|<span data-ttu-id="ff3a2-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="ff3a2-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ff3a2-118">\<aplServerID aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="ff3a2-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="ff3a2-119">为主键。</span><span class="sxs-lookup"><span data-stu-id="ff3a2-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="ff3a2-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="ff3a2-120">aplServerID</span></span>  <br/> |<span data-ttu-id="ff3a2-121">TblServerIdentity.serverID 表中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="ff3a2-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="ff3a2-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="ff3a2-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="ff3a2-123">TblServerIdentity.serverID 表中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="ff3a2-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

