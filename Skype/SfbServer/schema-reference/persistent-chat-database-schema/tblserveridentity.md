---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity 包含持久聊天服务器池中的活动聊天服务器。
ms.openlocfilehash: 4f6389f21c35da914b4943a279d8d485b6ec1eae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812270"
---
# <a name="tblserveridentity"></a><span data-ttu-id="b5201-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="b5201-103">tblServerIdentity</span></span>
 
<span data-ttu-id="b5201-104">tblServerIdentity 包含持久聊天服务器池中的活动聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="b5201-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="b5201-105">**多**</span><span class="sxs-lookup"><span data-stu-id="b5201-105">**Columns**</span></span>

|<span data-ttu-id="b5201-106">**列**</span><span class="sxs-lookup"><span data-stu-id="b5201-106">**Column**</span></span>|<span data-ttu-id="b5201-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="b5201-107">**Type**</span></span>|<span data-ttu-id="b5201-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="b5201-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b5201-109">serverID</span><span class="sxs-lookup"><span data-stu-id="b5201-109">serverID</span></span>  <br/> |<span data-ttu-id="b5201-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="b5201-110">int, not null</span></span>  <br/> |<span data-ttu-id="b5201-111">服务器 ID。</span><span class="sxs-lookup"><span data-stu-id="b5201-111">Server ID.</span></span> <span data-ttu-id="b5201-112">对应于中央管理存储中的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="b5201-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="b5201-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="b5201-113">serverAddress</span></span>  <br/> |<span data-ttu-id="b5201-114">nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="b5201-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="b5201-115">使用 Windows Communication Foundation 地址的服务器地址。</span><span class="sxs-lookup"><span data-stu-id="b5201-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="b5201-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="b5201-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="b5201-117">datetime</span><span class="sxs-lookup"><span data-stu-id="b5201-117">datetime</span></span>  <br/> |<span data-ttu-id="b5201-118">频道服务器更新此行以提供它正在运行的证据的最新时间。</span><span class="sxs-lookup"><span data-stu-id="b5201-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="b5201-119">**Key**</span><span class="sxs-lookup"><span data-stu-id="b5201-119">**Key**</span></span>

|<span data-ttu-id="b5201-120">**列**</span><span class="sxs-lookup"><span data-stu-id="b5201-120">**Column**</span></span>|<span data-ttu-id="b5201-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="b5201-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b5201-122">serverID</span><span class="sxs-lookup"><span data-stu-id="b5201-122">serverID</span></span>  <br/> |<span data-ttu-id="b5201-123">主键。</span><span class="sxs-lookup"><span data-stu-id="b5201-123">Primary key.</span></span>  <br/> |
   

