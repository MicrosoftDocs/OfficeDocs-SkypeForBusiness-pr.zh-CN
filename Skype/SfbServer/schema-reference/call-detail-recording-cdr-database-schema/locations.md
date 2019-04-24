---
title: Locations 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: 每条记录代表一个位置引用中将紧急呼叫，如 E9-1-1 呼叫。
ms.openlocfilehash: 180a094ef10cc54b4fd65a30adb0909789afa3d6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212999"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="55de2-103">Locations 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="55de2-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="55de2-104">每条记录代表一个位置引用中将紧急呼叫，如 E9-1-1 呼叫。</span><span class="sxs-lookup"><span data-stu-id="55de2-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="55de2-105">**列**</span><span class="sxs-lookup"><span data-stu-id="55de2-105">**Column**</span></span>|<span data-ttu-id="55de2-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="55de2-106">**Data Type**</span></span>|<span data-ttu-id="55de2-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="55de2-107">**Key/Index**</span></span>|<span data-ttu-id="55de2-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="55de2-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="55de2-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="55de2-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="55de2-110">datetime</span><span class="sxs-lookup"><span data-stu-id="55de2-110">datetime</span></span>  <br/> |<span data-ttu-id="55de2-111">主、 外</span><span class="sxs-lookup"><span data-stu-id="55de2-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="55de2-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="55de2-112">Time of session request.</span></span> <span data-ttu-id="55de2-113">与**SessionIdSeq**结合使用，来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="55de2-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="55de2-114">[Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="55de2-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="55de2-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="55de2-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="55de2-116">int</span><span class="sxs-lookup"><span data-stu-id="55de2-116">int</span></span>  <br/> |<span data-ttu-id="55de2-117">主、 外</span><span class="sxs-lookup"><span data-stu-id="55de2-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="55de2-118">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="55de2-118">ID number to identify the session.</span></span> <span data-ttu-id="55de2-119">与**SessionIdTime**结合使用，来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="55de2-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="55de2-120">[Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="55de2-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="55de2-121">**位置**</span><span class="sxs-lookup"><span data-stu-id="55de2-121">**Location**</span></span> <br/> |<span data-ttu-id="55de2-122">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="55de2-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="55de2-123">紧急呼叫的位置。</span><span class="sxs-lookup"><span data-stu-id="55de2-123">Location of emergency call.</span></span>  <br/> |
   

