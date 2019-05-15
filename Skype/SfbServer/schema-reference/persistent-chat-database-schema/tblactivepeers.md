---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers 包含聊天服务之间当前对等连接。
ms.openlocfilehash: 7d7f995b878d6e47878636bee6f9c16ac142352e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929873"
---
# <a name="tblactivepeers"></a><span data-ttu-id="5181c-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="5181c-103">tblActivePeers</span></span>
 
<span data-ttu-id="5181c-104">tblActivePeers 包含聊天服务之间当前对等连接。</span><span class="sxs-lookup"><span data-stu-id="5181c-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="5181c-105">**列**</span><span class="sxs-lookup"><span data-stu-id="5181c-105">**Columns**</span></span>

|<span data-ttu-id="5181c-106">**列**</span><span class="sxs-lookup"><span data-stu-id="5181c-106">**Column**</span></span>|<span data-ttu-id="5181c-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="5181c-107">**Type**</span></span>|<span data-ttu-id="5181c-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="5181c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5181c-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="5181c-109">aplServerID</span></span>  <br/> |<span data-ttu-id="5181c-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="5181c-110">int, not null</span></span>  <br/> |<span data-ttu-id="5181c-111">发布条目的服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="5181c-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="5181c-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="5181c-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="5181c-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="5181c-113">int, not null</span></span>  <br/> |<span data-ttu-id="5181c-114">发布服务器连接到的对等方的 ID。</span><span class="sxs-lookup"><span data-stu-id="5181c-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="5181c-115">**键**</span><span class="sxs-lookup"><span data-stu-id="5181c-115">**Keys**</span></span>

|<span data-ttu-id="5181c-116">**列**</span><span class="sxs-lookup"><span data-stu-id="5181c-116">**Column**</span></span>|<span data-ttu-id="5181c-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="5181c-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5181c-118">\<aplServerID aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="5181c-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="5181c-119">主键。</span><span class="sxs-lookup"><span data-stu-id="5181c-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5181c-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="5181c-120">aplServerID</span></span>  <br/> |<span data-ttu-id="5181c-121">包含在 tblServerIdentity.serverID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="5181c-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="5181c-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="5181c-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="5181c-123">包含在 tblServerIdentity.serverID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="5181c-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

