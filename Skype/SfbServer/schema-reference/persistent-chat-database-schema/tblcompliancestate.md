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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState 包含池范围的合规性状态信息。
ms.openlocfilehash: 6f3a7b1b7744260d0630a5328021b1752137a797
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814630"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="c8627-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="c8627-103">tblComplianceState</span></span>
 
<span data-ttu-id="c8627-104">tblComplianceState 包含池范围的合规性状态信息。</span><span class="sxs-lookup"><span data-stu-id="c8627-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="c8627-105">**多**</span><span class="sxs-lookup"><span data-stu-id="c8627-105">**Columns**</span></span>

|<span data-ttu-id="c8627-106">**列**</span><span class="sxs-lookup"><span data-stu-id="c8627-106">**Column**</span></span>|<span data-ttu-id="c8627-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="c8627-107">**Type**</span></span>|<span data-ttu-id="c8627-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="c8627-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c8627-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="c8627-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="c8627-110">bigint，not null</span><span class="sxs-lookup"><span data-stu-id="c8627-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="c8627-111">最新的已处理合规性事件的 ID。</span><span class="sxs-lookup"><span data-stu-id="c8627-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="c8627-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="c8627-112">activeServerID</span></span>  <br/> |<span data-ttu-id="c8627-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="c8627-113">int, not null</span></span>  <br/> |<span data-ttu-id="c8627-114">在数据库上持有独占锁的合规性服务器 ID，或者，如果没有，则为-1。</span><span class="sxs-lookup"><span data-stu-id="c8627-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="c8627-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="c8627-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="c8627-116">datetime2，not null</span><span class="sxs-lookup"><span data-stu-id="c8627-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="c8627-117">锁过期时间（如果 activeServerID 不是-1）。</span><span class="sxs-lookup"><span data-stu-id="c8627-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

