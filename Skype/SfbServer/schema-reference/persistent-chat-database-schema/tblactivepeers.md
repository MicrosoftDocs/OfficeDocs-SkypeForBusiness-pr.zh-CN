---
title: tblActivePeers
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers 包含聊天服务之间当前对等连接。
ms.openlocfilehash: befba4086a78281fbfbec1e270b7c8e3f8174752
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812932"
---
# <a name="tblactivepeers"></a><span data-ttu-id="67784-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="67784-103">tblActivePeers</span></span>
 
<span data-ttu-id="67784-104">tblActivePeers 包含聊天服务之间当前对等连接。</span><span class="sxs-lookup"><span data-stu-id="67784-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="67784-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="67784-105">**Columns**</span></span>

|<span data-ttu-id="67784-106">**列**</span><span class="sxs-lookup"><span data-stu-id="67784-106">**Column**</span></span>|<span data-ttu-id="67784-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="67784-107">**Type**</span></span>|<span data-ttu-id="67784-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="67784-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="67784-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="67784-109">aplServerID</span></span>  <br/> |<span data-ttu-id="67784-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="67784-110">int, not null</span></span>  <br/> |<span data-ttu-id="67784-111">发布条目的服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="67784-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="67784-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="67784-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="67784-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="67784-113">int, not null</span></span>  <br/> |<span data-ttu-id="67784-114">发布服务器连接到的对等方的 ID。</span><span class="sxs-lookup"><span data-stu-id="67784-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="67784-115">**Keys**</span><span class="sxs-lookup"><span data-stu-id="67784-115">**Keys**</span></span>

|<span data-ttu-id="67784-116">**列**</span><span class="sxs-lookup"><span data-stu-id="67784-116">**Column**</span></span>|<span data-ttu-id="67784-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="67784-117">**Description**</span></span>|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |<span data-ttu-id="67784-118">主键。</span><span class="sxs-lookup"><span data-stu-id="67784-118">Primary key.</span></span>  <br/> |
|<span data-ttu-id="67784-119">aplServerID</span><span class="sxs-lookup"><span data-stu-id="67784-119">aplServerID</span></span>  <br/> |<span data-ttu-id="67784-120">其查找包含在 tblServerIdentity.serverID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="67784-120">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="67784-121">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="67784-121">aplPeerID</span></span>  <br/> |<span data-ttu-id="67784-122">其查找包含在 tblServerIdentity.serverID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="67784-122">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

