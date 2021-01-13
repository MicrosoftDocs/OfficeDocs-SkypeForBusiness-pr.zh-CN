---
title: Skype for Business Server 2015 中的位置表
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
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: 每条记录均表示紧急呼叫（例如 E9-1-1 呼叫）中的一个位置引用。
ms.openlocfilehash: b177e79217f8586d7655b2a4645a603bd8e2f97f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821512"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a7f6d-103">Skype for Business Server 2015 中的位置表</span><span class="sxs-lookup"><span data-stu-id="a7f6d-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a7f6d-104">每条记录均表示紧急呼叫（例如 E9-1-1 呼叫）中的一个位置引用。</span><span class="sxs-lookup"><span data-stu-id="a7f6d-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="a7f6d-105">**列**</span><span class="sxs-lookup"><span data-stu-id="a7f6d-105">**Column**</span></span>|<span data-ttu-id="a7f6d-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a7f6d-106">**Data Type**</span></span>|<span data-ttu-id="a7f6d-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="a7f6d-107">**Key/Index**</span></span>|<span data-ttu-id="a7f6d-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="a7f6d-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7f6d-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="a7f6d-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="a7f6d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="a7f6d-110">datetime</span></span>  <br/> |<span data-ttu-id="a7f6d-111">主、外</span><span class="sxs-lookup"><span data-stu-id="a7f6d-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="a7f6d-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="a7f6d-112">Time of session request.</span></span> <span data-ttu-id="a7f6d-113">与 **SessionIdSeq** 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="a7f6d-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="a7f6d-114">有关详细信息，请参阅 [Skype for Business Server 2015 中的 Dialogs](dialogs.md) 表。</span><span class="sxs-lookup"><span data-stu-id="a7f6d-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a7f6d-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="a7f6d-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="a7f6d-116">int</span><span class="sxs-lookup"><span data-stu-id="a7f6d-116">int</span></span>  <br/> |<span data-ttu-id="a7f6d-117">主、外</span><span class="sxs-lookup"><span data-stu-id="a7f6d-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="a7f6d-118">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="a7f6d-118">ID number to identify the session.</span></span> <span data-ttu-id="a7f6d-119">与 **SessionIdTime** 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="a7f6d-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="a7f6d-120">有关详细信息，请参阅 [Skype for Business Server 2015 中的 Dialogs](dialogs.md) 表。</span><span class="sxs-lookup"><span data-stu-id="a7f6d-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a7f6d-121">**位置**</span><span class="sxs-lookup"><span data-stu-id="a7f6d-121">**Location**</span></span> <br/> |<span data-ttu-id="a7f6d-122">nvarchar (max) </span><span class="sxs-lookup"><span data-stu-id="a7f6d-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="a7f6d-123">紧急呼叫的位置。</span><span class="sxs-lookup"><span data-stu-id="a7f6d-123">Location of emergency call.</span></span>  <br/> |
   

