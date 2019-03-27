---
title: tblServerIdentity
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity 包含持久聊天服务器池中的活动聊天服务器。
ms.openlocfilehash: 1f9455e4c35a3bc6061c1d44ad10cbd4778c6c1f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899524"
---
# <a name="tblserveridentity"></a><span data-ttu-id="89bce-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="89bce-103">tblServerIdentity</span></span>
 
<span data-ttu-id="89bce-104">tblServerIdentity 包含持久聊天服务器池中的活动聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="89bce-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="89bce-105">**列**</span><span class="sxs-lookup"><span data-stu-id="89bce-105">**Columns**</span></span>

|<span data-ttu-id="89bce-106">**列**</span><span class="sxs-lookup"><span data-stu-id="89bce-106">**Column**</span></span>|<span data-ttu-id="89bce-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="89bce-107">**Type**</span></span>|<span data-ttu-id="89bce-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="89bce-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="89bce-109">serverID</span><span class="sxs-lookup"><span data-stu-id="89bce-109">serverID</span></span>  <br/> |<span data-ttu-id="89bce-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="89bce-110">int, not null</span></span>  <br/> |<span data-ttu-id="89bce-111">服务器 id。</span><span class="sxs-lookup"><span data-stu-id="89bce-111">Server ID.</span></span> <span data-ttu-id="89bce-112">从中央管理存储对应的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="89bce-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="89bce-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="89bce-113">serverAddress</span></span>  <br/> |<span data-ttu-id="89bce-114">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="89bce-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="89bce-115">使用 Windows Communication Foundation 地址的服务器地址。</span><span class="sxs-lookup"><span data-stu-id="89bce-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="89bce-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="89bce-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="89bce-117">datetime</span><span class="sxs-lookup"><span data-stu-id="89bce-117">datetime</span></span>  <br/> |<span data-ttu-id="89bce-118">频道服务器更新此行以表明它运行最新时间。</span><span class="sxs-lookup"><span data-stu-id="89bce-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="89bce-119">**关键字**</span><span class="sxs-lookup"><span data-stu-id="89bce-119">**Key**</span></span>

|<span data-ttu-id="89bce-120">**列**</span><span class="sxs-lookup"><span data-stu-id="89bce-120">**Column**</span></span>|<span data-ttu-id="89bce-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="89bce-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="89bce-122">serverID</span><span class="sxs-lookup"><span data-stu-id="89bce-122">serverID</span></span>  <br/> |<span data-ttu-id="89bce-123">主键。</span><span class="sxs-lookup"><span data-stu-id="89bce-123">Primary key.</span></span>  <br/> |
   

