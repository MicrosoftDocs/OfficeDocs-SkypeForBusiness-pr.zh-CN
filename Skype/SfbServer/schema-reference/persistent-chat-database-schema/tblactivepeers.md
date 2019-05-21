---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers 包含聊天服务之间的当前点对点连接。
ms.openlocfilehash: f45a04019cafc2304baf825b5000e96ca7a6cead
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295543"
---
# <a name="tblactivepeers"></a><span data-ttu-id="5d931-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="5d931-103">tblActivePeers</span></span>
 
<span data-ttu-id="5d931-104">tblActivePeers 包含聊天服务之间的当前点对点连接。</span><span class="sxs-lookup"><span data-stu-id="5d931-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="5d931-105">**多**</span><span class="sxs-lookup"><span data-stu-id="5d931-105">**Columns**</span></span>

|<span data-ttu-id="5d931-106">**列**</span><span class="sxs-lookup"><span data-stu-id="5d931-106">**Column**</span></span>|<span data-ttu-id="5d931-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="5d931-107">**Type**</span></span>|<span data-ttu-id="5d931-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="5d931-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5d931-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="5d931-109">aplServerID</span></span>  <br/> |<span data-ttu-id="5d931-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="5d931-110">int, not null</span></span>  <br/> |<span data-ttu-id="5d931-111">已发布条目的服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="5d931-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="5d931-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="5d931-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="5d931-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="5d931-113">int, not null</span></span>  <br/> |<span data-ttu-id="5d931-114">过帐服务器连接到的对等的 ID。</span><span class="sxs-lookup"><span data-stu-id="5d931-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="5d931-115">**标示**</span><span class="sxs-lookup"><span data-stu-id="5d931-115">**Keys**</span></span>

|<span data-ttu-id="5d931-116">**列**</span><span class="sxs-lookup"><span data-stu-id="5d931-116">**Column**</span></span>|<span data-ttu-id="5d931-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="5d931-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5d931-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="5d931-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="5d931-119">主键。</span><span class="sxs-lookup"><span data-stu-id="5d931-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5d931-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="5d931-120">aplServerID</span></span>  <br/> |<span data-ttu-id="5d931-121">TblServerIdentity 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="5d931-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="5d931-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="5d931-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="5d931-123">TblServerIdentity 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="5d931-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

