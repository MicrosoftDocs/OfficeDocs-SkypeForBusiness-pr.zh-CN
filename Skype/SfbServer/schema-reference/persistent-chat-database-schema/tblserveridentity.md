---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity 包含持久聊天服务器池中的活动聊天服务器。
ms.openlocfilehash: 7fa8c1b804432b3a9368785682f45e9ce8d7898e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831492"
---
# <a name="tblserveridentity"></a><span data-ttu-id="d0037-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="d0037-103">tblServerIdentity</span></span>
 
<span data-ttu-id="d0037-104">tblServerIdentity 包含持久聊天服务器池中的活动聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="d0037-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="d0037-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="d0037-105">**Columns**</span></span>

|<span data-ttu-id="d0037-106">**列**</span><span class="sxs-lookup"><span data-stu-id="d0037-106">**Column**</span></span>|<span data-ttu-id="d0037-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="d0037-107">**Type**</span></span>|<span data-ttu-id="d0037-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="d0037-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d0037-109">serverID</span><span class="sxs-lookup"><span data-stu-id="d0037-109">serverID</span></span>  <br/> |<span data-ttu-id="d0037-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="d0037-110">int, not null</span></span>  <br/> |<span data-ttu-id="d0037-111">服务器 ID。</span><span class="sxs-lookup"><span data-stu-id="d0037-111">Server ID.</span></span> <span data-ttu-id="d0037-112">对应于中央管理存储中的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="d0037-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="d0037-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="d0037-113">serverAddress</span></span>  <br/> |<span data-ttu-id="d0037-114">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="d0037-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="d0037-115">使用 Windows Communication Foundation 地址的服务器地址。</span><span class="sxs-lookup"><span data-stu-id="d0037-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="d0037-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="d0037-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="d0037-117">datetime</span><span class="sxs-lookup"><span data-stu-id="d0037-117">datetime</span></span>  <br/> |<span data-ttu-id="d0037-118">通道服务器更新此行以表明服务器正在运行的最新时间。</span><span class="sxs-lookup"><span data-stu-id="d0037-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="d0037-119">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="d0037-119">**Key**</span></span>

|<span data-ttu-id="d0037-120">**列**</span><span class="sxs-lookup"><span data-stu-id="d0037-120">**Column**</span></span>|<span data-ttu-id="d0037-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="d0037-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d0037-122">serverID</span><span class="sxs-lookup"><span data-stu-id="d0037-122">serverID</span></span>  <br/> |<span data-ttu-id="d0037-123">主键。</span><span class="sxs-lookup"><span data-stu-id="d0037-123">Primary key.</span></span>  <br/> |
   

