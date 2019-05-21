---
title: Skype for Business Server 2015 中的 "位置" 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: 每条记录代表紧急呼叫中的一个位置引用, 如 E9-1-1 通话。
ms.openlocfilehash: 28054419187b8f23348396f52ec147b06eee2136
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296117"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="f799b-103">Skype for Business Server 2015 中的 "位置" 表</span><span class="sxs-lookup"><span data-stu-id="f799b-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f799b-104">每条记录代表紧急呼叫中的一个位置引用, 如 E9-1-1 通话。</span><span class="sxs-lookup"><span data-stu-id="f799b-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="f799b-105">**列**</span><span class="sxs-lookup"><span data-stu-id="f799b-105">**Column**</span></span>|<span data-ttu-id="f799b-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f799b-106">**Data Type**</span></span>|<span data-ttu-id="f799b-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="f799b-107">**Key/Index**</span></span>|<span data-ttu-id="f799b-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="f799b-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f799b-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="f799b-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="f799b-110">datetime</span><span class="sxs-lookup"><span data-stu-id="f799b-110">datetime</span></span>  <br/> |<span data-ttu-id="f799b-111">主、外部</span><span class="sxs-lookup"><span data-stu-id="f799b-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f799b-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="f799b-112">Time of session request.</span></span> <span data-ttu-id="f799b-113">与**SessionIdSeq**结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="f799b-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="f799b-114">有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。</span><span class="sxs-lookup"><span data-stu-id="f799b-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="f799b-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="f799b-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="f799b-116">int</span><span class="sxs-lookup"><span data-stu-id="f799b-116">int</span></span>  <br/> |<span data-ttu-id="f799b-117">主、外部</span><span class="sxs-lookup"><span data-stu-id="f799b-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f799b-118">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="f799b-118">ID number to identify the session.</span></span> <span data-ttu-id="f799b-119">与**SessionIdTime**结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="f799b-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="f799b-120">有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。</span><span class="sxs-lookup"><span data-stu-id="f799b-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="f799b-121">**位置**</span><span class="sxs-lookup"><span data-stu-id="f799b-121">**Location**</span></span> <br/> |<span data-ttu-id="f799b-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="f799b-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="f799b-123">紧急电话的位置。</span><span class="sxs-lookup"><span data-stu-id="f799b-123">Location of emergency call.</span></span>  <br/> |
   

