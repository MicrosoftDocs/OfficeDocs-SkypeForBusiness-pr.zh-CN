---
title: Skype for Business Server 2015 中的 Mcus 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcus 表是支持表。 每条记录存储有关一个会议服务的信息。 这些服务可以包括 IM 会议服务和电话会议服务 (该服务作为前端服务器上的进程运行)、Web 会议服务和 A/V 会议服务。
ms.openlocfilehash: fcd12bcc8da7aa6513d78e1a9c4a6f11930065aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296040"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="72911-105">Skype for Business Server 2015 中的 Mcus 表</span><span class="sxs-lookup"><span data-stu-id="72911-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="72911-106">Mcus 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="72911-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="72911-107">每条记录存储有关一个会议服务的信息。</span><span class="sxs-lookup"><span data-stu-id="72911-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="72911-108">这些服务可以包括 IM 会议服务和电话会议服务 (该服务作为前端服务器上的进程运行)、Web 会议服务和 A/V 会议服务。</span><span class="sxs-lookup"><span data-stu-id="72911-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="72911-109">**列**</span><span class="sxs-lookup"><span data-stu-id="72911-109">**Column**</span></span>|<span data-ttu-id="72911-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="72911-110">**Data Type**</span></span>|<span data-ttu-id="72911-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="72911-111">**Key/Index**</span></span>|<span data-ttu-id="72911-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="72911-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="72911-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="72911-113">**McuId**</span></span> <br/> |<span data-ttu-id="72911-114">int</span><span class="sxs-lookup"><span data-stu-id="72911-114">int</span></span>  <br/> |<span data-ttu-id="72911-115">Primary</span><span class="sxs-lookup"><span data-stu-id="72911-115">Primary</span></span>  <br/> |<span data-ttu-id="72911-116">标识此会议服务器的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="72911-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="72911-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="72911-117">**McuUri**</span></span> <br/> |<span data-ttu-id="72911-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="72911-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="72911-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="72911-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="72911-120">inyint</span><span class="sxs-lookup"><span data-stu-id="72911-120">inyint</span></span>  <br/> | <span data-ttu-id="72911-121">外表</span><span class="sxs-lookup"><span data-stu-id="72911-121">Foreign</span></span> <br/> |<span data-ttu-id="72911-122">会议服务器类型, 例如会议: 聊天 (适用于 Im) 或会议: 音频视频。</span><span class="sxs-lookup"><span data-stu-id="72911-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="72911-123">有关详细信息, 请参阅[UriTypes 表](uritypes.md)。</span><span class="sxs-lookup"><span data-stu-id="72911-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

