---
title: Mcus 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcus 表是一个支持表。 每个记录存储有关一个会议服务的信息。 其中可以包括 IM 会议服务和电话会议服务 （它作为进程运行前端服务器），以及 Web 会议服务和 A / V 会议服务。
ms.openlocfilehash: e051af3a77d4f9b8231c122c596a3b6915f6f3e1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893010"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="07a1c-105">Mcus 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="07a1c-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="07a1c-106">Mcus 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="07a1c-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="07a1c-107">每个记录存储有关一个会议服务的信息。</span><span class="sxs-lookup"><span data-stu-id="07a1c-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="07a1c-108">其中可以包括 IM 会议服务和电话会议服务 （它作为进程运行前端服务器），以及 Web 会议服务和 A / V 会议服务。</span><span class="sxs-lookup"><span data-stu-id="07a1c-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="07a1c-109">**列**</span><span class="sxs-lookup"><span data-stu-id="07a1c-109">**Column**</span></span>|<span data-ttu-id="07a1c-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="07a1c-110">**Data Type**</span></span>|<span data-ttu-id="07a1c-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="07a1c-111">**Key/Index**</span></span>|<span data-ttu-id="07a1c-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="07a1c-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07a1c-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="07a1c-113">**McuId**</span></span> <br/> |<span data-ttu-id="07a1c-114">int</span><span class="sxs-lookup"><span data-stu-id="07a1c-114">int</span></span>  <br/> |<span data-ttu-id="07a1c-115">Primary</span><span class="sxs-lookup"><span data-stu-id="07a1c-115">Primary</span></span>  <br/> |<span data-ttu-id="07a1c-116">标识此会议服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="07a1c-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="07a1c-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="07a1c-117">**McuUri**</span></span> <br/> |<span data-ttu-id="07a1c-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="07a1c-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="07a1c-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="07a1c-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="07a1c-120">inyint</span><span class="sxs-lookup"><span data-stu-id="07a1c-120">inyint</span></span>  <br/> | <span data-ttu-id="07a1c-121">外</span><span class="sxs-lookup"><span data-stu-id="07a1c-121">Foreign</span></span> <br/> |<span data-ttu-id="07a1c-122">会议服务器类型，如 conf:chat （对于 Im) 或 conf:audio-视频。</span><span class="sxs-lookup"><span data-stu-id="07a1c-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="07a1c-123">请参阅[UriTypes 表](uritypes.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="07a1c-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

