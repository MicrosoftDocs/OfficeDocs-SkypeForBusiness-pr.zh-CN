---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity 包含持久聊天服务器池中的活动聊天服务器。
ms.openlocfilehash: d780c2153b2e7f9f1ed5aad20217228e44f29504
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924806"
---
# <a name="tblserveridentity"></a><span data-ttu-id="355e1-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="355e1-103">tblServerIdentity</span></span>
 
<span data-ttu-id="355e1-104">tblServerIdentity 包含持久聊天服务器池中的活动聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="355e1-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="355e1-105">**列**</span><span class="sxs-lookup"><span data-stu-id="355e1-105">**Columns**</span></span>

|<span data-ttu-id="355e1-106">**列**</span><span class="sxs-lookup"><span data-stu-id="355e1-106">**Column**</span></span>|<span data-ttu-id="355e1-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="355e1-107">**Type**</span></span>|<span data-ttu-id="355e1-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="355e1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="355e1-109">serverID</span><span class="sxs-lookup"><span data-stu-id="355e1-109">serverID</span></span>  <br/> |<span data-ttu-id="355e1-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="355e1-110">int, not null</span></span>  <br/> |<span data-ttu-id="355e1-111">服务器 id。</span><span class="sxs-lookup"><span data-stu-id="355e1-111">Server ID.</span></span> <span data-ttu-id="355e1-112">从中央管理存储对应的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="355e1-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="355e1-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="355e1-113">serverAddress</span></span>  <br/> |<span data-ttu-id="355e1-114">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="355e1-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="355e1-115">使用 Windows Communication Foundation 地址的服务器地址。</span><span class="sxs-lookup"><span data-stu-id="355e1-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="355e1-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="355e1-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="355e1-117">datetime</span><span class="sxs-lookup"><span data-stu-id="355e1-117">datetime</span></span>  <br/> |<span data-ttu-id="355e1-118">频道服务器更新此行以表明它运行最新时间。</span><span class="sxs-lookup"><span data-stu-id="355e1-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="355e1-119">**关键字**</span><span class="sxs-lookup"><span data-stu-id="355e1-119">**Key**</span></span>

|<span data-ttu-id="355e1-120">**列**</span><span class="sxs-lookup"><span data-stu-id="355e1-120">**Column**</span></span>|<span data-ttu-id="355e1-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="355e1-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="355e1-122">serverID</span><span class="sxs-lookup"><span data-stu-id="355e1-122">serverID</span></span>  <br/> |<span data-ttu-id="355e1-123">主键。</span><span class="sxs-lookup"><span data-stu-id="355e1-123">Primary key.</span></span>  <br/> |
   

