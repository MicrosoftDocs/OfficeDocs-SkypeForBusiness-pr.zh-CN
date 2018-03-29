---
title: tblServerIdentity
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
ms.openlocfilehash: 445021bb486d418011ea21dd32c0339e11b4d17a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblserveridentity"></a><span data-ttu-id="10b63-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="10b63-103">tblServerIdentity</span></span>
 
<span data-ttu-id="10b63-104">tblServerIdentity 包含持久聊天服务器池中的活动聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="10b63-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="10b63-105">**列**</span><span class="sxs-lookup"><span data-stu-id="10b63-105">**Columns**</span></span>

|<span data-ttu-id="10b63-106">**列**</span><span class="sxs-lookup"><span data-stu-id="10b63-106">**Column**</span></span>|<span data-ttu-id="10b63-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="10b63-107">**Type**</span></span>|<span data-ttu-id="10b63-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="10b63-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="10b63-109">serverID</span><span class="sxs-lookup"><span data-stu-id="10b63-109">serverID</span></span>  <br/> |<span data-ttu-id="10b63-110">int，不为空</span><span class="sxs-lookup"><span data-stu-id="10b63-110">int, not null</span></span>  <br/> |<span data-ttu-id="10b63-111">服务器 id。</span><span class="sxs-lookup"><span data-stu-id="10b63-111">Server ID.</span></span> <span data-ttu-id="10b63-112">从中央管理存储对应的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="10b63-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="10b63-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="10b63-113">serverAddress</span></span>  <br/> |<span data-ttu-id="10b63-114">nvarchar (256) 不为空</span><span class="sxs-lookup"><span data-stu-id="10b63-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="10b63-115">使用窗口通信基础地址的服务器地址。</span><span class="sxs-lookup"><span data-stu-id="10b63-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="10b63-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="10b63-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="10b63-117">datetime</span><span class="sxs-lookup"><span data-stu-id="10b63-117">datetime</span></span>  <br/> |<span data-ttu-id="10b63-118">最晚的时间通道服务器更新该行，以便使它运行的证据。</span><span class="sxs-lookup"><span data-stu-id="10b63-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="10b63-119">**密钥**</span><span class="sxs-lookup"><span data-stu-id="10b63-119">**Key**</span></span>

|<span data-ttu-id="10b63-120">**列**</span><span class="sxs-lookup"><span data-stu-id="10b63-120">**Column**</span></span>|<span data-ttu-id="10b63-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="10b63-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="10b63-122">serverID</span><span class="sxs-lookup"><span data-stu-id="10b63-122">serverID</span></span>  <br/> |<span data-ttu-id="10b63-123">为主键。</span><span class="sxs-lookup"><span data-stu-id="10b63-123">Primary key.</span></span>  <br/> |
   

