---
title: Locations 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: 每条记录代表一个位置引用中将紧急呼叫，如 E9-1-1 呼叫。
ms.openlocfilehash: 389aa56dfaf6d8b732692909ff3375a992b504b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930239"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="17b20-103">Locations 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="17b20-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="17b20-104">每条记录代表一个位置引用中将紧急呼叫，如 E9-1-1 呼叫。</span><span class="sxs-lookup"><span data-stu-id="17b20-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="17b20-105">**列**</span><span class="sxs-lookup"><span data-stu-id="17b20-105">**Column**</span></span>|<span data-ttu-id="17b20-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="17b20-106">**Data Type**</span></span>|<span data-ttu-id="17b20-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="17b20-107">**Key/Index**</span></span>|<span data-ttu-id="17b20-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="17b20-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="17b20-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="17b20-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="17b20-110">datetime</span><span class="sxs-lookup"><span data-stu-id="17b20-110">datetime</span></span>  <br/> |<span data-ttu-id="17b20-111">主、 外</span><span class="sxs-lookup"><span data-stu-id="17b20-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="17b20-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="17b20-112">Time of session request.</span></span> <span data-ttu-id="17b20-113">与**SessionIdSeq**结合使用，来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="17b20-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="17b20-114">[Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="17b20-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="17b20-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="17b20-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="17b20-116">int</span><span class="sxs-lookup"><span data-stu-id="17b20-116">int</span></span>  <br/> |<span data-ttu-id="17b20-117">主、 外</span><span class="sxs-lookup"><span data-stu-id="17b20-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="17b20-118">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="17b20-118">ID number to identify the session.</span></span> <span data-ttu-id="17b20-119">与**SessionIdTime**结合使用，来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="17b20-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="17b20-120">[Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="17b20-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="17b20-121">**位置**</span><span class="sxs-lookup"><span data-stu-id="17b20-121">**Location**</span></span> <br/> |<span data-ttu-id="17b20-122">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="17b20-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="17b20-123">紧急呼叫的位置。</span><span class="sxs-lookup"><span data-stu-id="17b20-123">Location of emergency call.</span></span>  <br/> |
   

