---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState 包含池范围的合规性状态信息。
ms.openlocfilehash: 1c5571d7150c3859978f8d217f0264f67ee993d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295473"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="de56e-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="de56e-103">tblComplianceState</span></span>
 
<span data-ttu-id="de56e-104">tblComplianceState 包含池范围的合规性状态信息。</span><span class="sxs-lookup"><span data-stu-id="de56e-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="de56e-105">**多**</span><span class="sxs-lookup"><span data-stu-id="de56e-105">**Columns**</span></span>

|<span data-ttu-id="de56e-106">**列**</span><span class="sxs-lookup"><span data-stu-id="de56e-106">**Column**</span></span>|<span data-ttu-id="de56e-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="de56e-107">**Type**</span></span>|<span data-ttu-id="de56e-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="de56e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="de56e-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="de56e-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="de56e-110">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="de56e-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="de56e-111">最新的已处理合规性事件的 ID。</span><span class="sxs-lookup"><span data-stu-id="de56e-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="de56e-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="de56e-112">activeServerID</span></span>  <br/> |<span data-ttu-id="de56e-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="de56e-113">int, not null</span></span>  <br/> |<span data-ttu-id="de56e-114">在数据库上持有独占锁的合规性服务器 ID, 或者, 如果没有, 则为-1。</span><span class="sxs-lookup"><span data-stu-id="de56e-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="de56e-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="de56e-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="de56e-116">datetime2, not null</span><span class="sxs-lookup"><span data-stu-id="de56e-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="de56e-117">锁过期时间 (如果 activeServerID 不是-1)。</span><span class="sxs-lookup"><span data-stu-id="de56e-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

