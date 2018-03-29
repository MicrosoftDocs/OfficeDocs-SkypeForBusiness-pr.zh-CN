---
title: tblComplianceState
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState 包含池范围的法规遵从性状态的信息。
ms.openlocfilehash: e46db9c73f4489ade9bbed90f0061567fd14af1d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancestate"></a><span data-ttu-id="61fea-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="61fea-103">tblComplianceState</span></span>
 
<span data-ttu-id="61fea-104">tblComplianceState 包含池范围的法规遵从性状态的信息。</span><span class="sxs-lookup"><span data-stu-id="61fea-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="61fea-105">**列**</span><span class="sxs-lookup"><span data-stu-id="61fea-105">**Columns**</span></span>

|<span data-ttu-id="61fea-106">**列**</span><span class="sxs-lookup"><span data-stu-id="61fea-106">**Column**</span></span>|<span data-ttu-id="61fea-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="61fea-107">**Type**</span></span>|<span data-ttu-id="61fea-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="61fea-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="61fea-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="61fea-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="61fea-110">bigint，不为空</span><span class="sxs-lookup"><span data-stu-id="61fea-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="61fea-111">最新的处理法规遵从性事件 ID。</span><span class="sxs-lookup"><span data-stu-id="61fea-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="61fea-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="61fea-112">activeServerID</span></span>  <br/> |<span data-ttu-id="61fea-113">int，不为空</span><span class="sxs-lookup"><span data-stu-id="61fea-113">int, not null</span></span>  <br/> |<span data-ttu-id="61fea-114">如果没有保存在数据库中，则为-1 的排它锁的法规遵从性服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="61fea-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="61fea-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="61fea-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="61fea-116">datetime2，不为空</span><span class="sxs-lookup"><span data-stu-id="61fea-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="61fea-117">锁定到期时间 （如果 activeServerID 不是-1）。</span><span class="sxs-lookup"><span data-stu-id="61fea-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

