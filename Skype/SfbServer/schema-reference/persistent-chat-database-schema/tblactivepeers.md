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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers 包含聊天服务之间的当前点对点连接。
ms.openlocfilehash: 4604c13dbff9565748dd59e5917a5c133bd71947
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814710"
---
# <a name="tblactivepeers"></a><span data-ttu-id="9c493-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="9c493-103">tblActivePeers</span></span>
 
<span data-ttu-id="9c493-104">tblActivePeers 包含聊天服务之间的当前点对点连接。</span><span class="sxs-lookup"><span data-stu-id="9c493-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="9c493-105">**多**</span><span class="sxs-lookup"><span data-stu-id="9c493-105">**Columns**</span></span>

|<span data-ttu-id="9c493-106">**列**</span><span class="sxs-lookup"><span data-stu-id="9c493-106">**Column**</span></span>|<span data-ttu-id="9c493-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="9c493-107">**Type**</span></span>|<span data-ttu-id="9c493-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="9c493-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9c493-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="9c493-109">aplServerID</span></span>  <br/> |<span data-ttu-id="9c493-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="9c493-110">int, not null</span></span>  <br/> |<span data-ttu-id="9c493-111">已发布条目的服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="9c493-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="9c493-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="9c493-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="9c493-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="9c493-113">int, not null</span></span>  <br/> |<span data-ttu-id="9c493-114">过帐服务器连接到的对等的 ID。</span><span class="sxs-lookup"><span data-stu-id="9c493-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="9c493-115">**标示**</span><span class="sxs-lookup"><span data-stu-id="9c493-115">**Keys**</span></span>

|<span data-ttu-id="9c493-116">**列**</span><span class="sxs-lookup"><span data-stu-id="9c493-116">**Column**</span></span>|<span data-ttu-id="9c493-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="9c493-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9c493-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="9c493-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="9c493-119">主键。</span><span class="sxs-lookup"><span data-stu-id="9c493-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="9c493-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="9c493-120">aplServerID</span></span>  <br/> |<span data-ttu-id="9c493-121">TblServerIdentity 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="9c493-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="9c493-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="9c493-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="9c493-123">TblServerIdentity 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="9c493-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

