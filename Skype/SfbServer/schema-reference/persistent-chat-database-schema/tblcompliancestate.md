---
title: tblComplianceState
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState 包含池范围的合规性状态信息。
ms.openlocfilehash: 4e9f103ef019e743b5dfcb4ef554ff6a28c340b8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212633"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="6aa97-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="6aa97-103">tblComplianceState</span></span>
 
<span data-ttu-id="6aa97-104">tblComplianceState 包含池范围的合规性状态信息。</span><span class="sxs-lookup"><span data-stu-id="6aa97-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="6aa97-105">**列**</span><span class="sxs-lookup"><span data-stu-id="6aa97-105">**Columns**</span></span>

|<span data-ttu-id="6aa97-106">**列**</span><span class="sxs-lookup"><span data-stu-id="6aa97-106">**Column**</span></span>|<span data-ttu-id="6aa97-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="6aa97-107">**Type**</span></span>|<span data-ttu-id="6aa97-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="6aa97-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6aa97-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="6aa97-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="6aa97-110">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="6aa97-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="6aa97-111">最新处理的合规性事件的 ID。</span><span class="sxs-lookup"><span data-stu-id="6aa97-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="6aa97-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="6aa97-112">activeServerID</span></span>  <br/> |<span data-ttu-id="6aa97-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="6aa97-113">int, not null</span></span>  <br/> |<span data-ttu-id="6aa97-114">如果无则保留排除锁数据库，则为-1 上的合规性服务器 ID。</span><span class="sxs-lookup"><span data-stu-id="6aa97-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="6aa97-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="6aa97-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="6aa97-116">datetime2，不为 null</span><span class="sxs-lookup"><span data-stu-id="6aa97-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="6aa97-117">锁定到期时间，（如果 activeServerID 不为-1）。</span><span class="sxs-lookup"><span data-stu-id="6aa97-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

