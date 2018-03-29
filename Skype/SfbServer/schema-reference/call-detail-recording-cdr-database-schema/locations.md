---
title: 在业务服务器 2015年的 Skype 的位置表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: 每个记录表示紧急呼叫，类似 E9-1-1 调用中的一个位置引用。
ms.openlocfilehash: b15e7f0b7930871b97dc3341a47153965529810e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="69939-103">在业务服务器 2015年的 Skype 的位置表</span><span class="sxs-lookup"><span data-stu-id="69939-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="69939-104">每个记录表示紧急呼叫，类似 E9-1-1 调用中的一个位置引用。</span><span class="sxs-lookup"><span data-stu-id="69939-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="69939-105">**列**</span><span class="sxs-lookup"><span data-stu-id="69939-105">**Column**</span></span>|<span data-ttu-id="69939-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="69939-106">**Data Type**</span></span>|<span data-ttu-id="69939-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="69939-107">**Key/Index**</span></span>|<span data-ttu-id="69939-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="69939-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="69939-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="69939-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="69939-110">datetime</span><span class="sxs-lookup"><span data-stu-id="69939-110">datetime</span></span>  <br/> |<span data-ttu-id="69939-111">主键和外</span><span class="sxs-lookup"><span data-stu-id="69939-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="69939-112">会议请求的时间。</span><span class="sxs-lookup"><span data-stu-id="69939-112">Time of session request.</span></span> <span data-ttu-id="69939-113">与**SessionIdSeq**配合使用，以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="69939-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="69939-114">[对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="69939-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="69939-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="69939-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="69939-116">int</span><span class="sxs-lookup"><span data-stu-id="69939-116">int</span></span>  <br/> |<span data-ttu-id="69939-117">主键和外</span><span class="sxs-lookup"><span data-stu-id="69939-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="69939-118">以标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="69939-118">ID number to identify the session.</span></span> <span data-ttu-id="69939-119">与**SessionIdTime**配合使用，以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="69939-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="69939-120">[对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="69939-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="69939-121">**位置**</span><span class="sxs-lookup"><span data-stu-id="69939-121">**Location**</span></span> <br/> |<span data-ttu-id="69939-122">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="69939-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="69939-123">紧急呼叫的位置。</span><span class="sxs-lookup"><span data-stu-id="69939-123">Location of emergency call.</span></span>  <br/> |
   

