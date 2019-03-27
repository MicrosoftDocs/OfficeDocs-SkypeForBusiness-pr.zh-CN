---
title: tblActivePeers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers 包含聊天服务之间当前对等连接。
ms.openlocfilehash: e921d6faa4f7bcf3e3c6f6dc9859f4bd0db16bc5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884165"
---
# <a name="tblactivepeers"></a><span data-ttu-id="23c8e-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="23c8e-103">tblActivePeers</span></span>
 
<span data-ttu-id="23c8e-104">tblActivePeers 包含聊天服务之间当前对等连接。</span><span class="sxs-lookup"><span data-stu-id="23c8e-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="23c8e-105">**列**</span><span class="sxs-lookup"><span data-stu-id="23c8e-105">**Columns**</span></span>

|<span data-ttu-id="23c8e-106">**列**</span><span class="sxs-lookup"><span data-stu-id="23c8e-106">**Column**</span></span>|<span data-ttu-id="23c8e-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="23c8e-107">**Type**</span></span>|<span data-ttu-id="23c8e-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="23c8e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="23c8e-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="23c8e-109">aplServerID</span></span>  <br/> |<span data-ttu-id="23c8e-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="23c8e-110">int, not null</span></span>  <br/> |<span data-ttu-id="23c8e-111">发布条目的服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="23c8e-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="23c8e-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="23c8e-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="23c8e-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="23c8e-113">int, not null</span></span>  <br/> |<span data-ttu-id="23c8e-114">发布服务器连接到的对等方的 ID。</span><span class="sxs-lookup"><span data-stu-id="23c8e-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="23c8e-115">**键**</span><span class="sxs-lookup"><span data-stu-id="23c8e-115">**Keys**</span></span>

|<span data-ttu-id="23c8e-116">**列**</span><span class="sxs-lookup"><span data-stu-id="23c8e-116">**Column**</span></span>|<span data-ttu-id="23c8e-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="23c8e-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="23c8e-118">\<aplServerID aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="23c8e-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="23c8e-119">主键。</span><span class="sxs-lookup"><span data-stu-id="23c8e-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="23c8e-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="23c8e-120">aplServerID</span></span>  <br/> |<span data-ttu-id="23c8e-121">包含在 tblServerIdentity.serverID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="23c8e-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="23c8e-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="23c8e-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="23c8e-123">包含在 tblServerIdentity.serverID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="23c8e-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

