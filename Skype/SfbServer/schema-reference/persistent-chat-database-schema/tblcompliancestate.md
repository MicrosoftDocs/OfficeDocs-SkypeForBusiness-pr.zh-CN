---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState 包含池范围的合规性状态信息。
ms.openlocfilehash: 82c775b315976b0e5b112c476a41a8f5adc6a24c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809722"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="4a876-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="4a876-103">tblComplianceState</span></span>
 
<span data-ttu-id="4a876-104">tblComplianceState 包含池范围的合规性状态信息。</span><span class="sxs-lookup"><span data-stu-id="4a876-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="4a876-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="4a876-105">**Columns**</span></span>

|<span data-ttu-id="4a876-106">**列**</span><span class="sxs-lookup"><span data-stu-id="4a876-106">**Column**</span></span>|<span data-ttu-id="4a876-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="4a876-107">**Type**</span></span>|<span data-ttu-id="4a876-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="4a876-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4a876-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="4a876-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="4a876-110">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="4a876-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="4a876-111">最新处理的合规性事件的 ID。</span><span class="sxs-lookup"><span data-stu-id="4a876-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="4a876-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="4a876-112">activeServerID</span></span>  <br/> |<span data-ttu-id="4a876-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="4a876-113">int, not null</span></span>  <br/> |<span data-ttu-id="4a876-114">数据库上保留排除锁的合规性服务器 ID，或者，如果无则为 -1。</span><span class="sxs-lookup"><span data-stu-id="4a876-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="4a876-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="4a876-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="4a876-116">datetime2，不为 null</span><span class="sxs-lookup"><span data-stu-id="4a876-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="4a876-117">锁定到期时间（如果 activeServerID 不为 -1）。</span><span class="sxs-lookup"><span data-stu-id="4a876-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

