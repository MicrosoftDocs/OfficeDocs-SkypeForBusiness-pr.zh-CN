---
title: 在业务服务器 2015年的 Skype 的 Mcu 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcu 表是支持表。 每个记录都存储着一个会议服务有关的信息。 这些可以包括 IM 会议服务和电话服务会议服务 （它作为进程运行在前端服务器上），和 Web 会议服务和 A / V 会议服务。
ms.openlocfilehash: 2a85d46e733d230dc7c8096c8804146b19766bcf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3208e-105">在业务服务器 2015年的 Skype 的 Mcu 表</span><span class="sxs-lookup"><span data-stu-id="3208e-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3208e-106">Mcu 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="3208e-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="3208e-107">每个记录都存储着一个会议服务有关的信息。</span><span class="sxs-lookup"><span data-stu-id="3208e-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="3208e-108">这些可以包括 IM 会议服务和电话服务会议服务 （它作为进程运行在前端服务器上），和 Web 会议服务和 A / V 会议服务。</span><span class="sxs-lookup"><span data-stu-id="3208e-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="3208e-109">**列**</span><span class="sxs-lookup"><span data-stu-id="3208e-109">**Column**</span></span>|<span data-ttu-id="3208e-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3208e-110">**Data Type**</span></span>|<span data-ttu-id="3208e-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="3208e-111">**Key/Index**</span></span>|<span data-ttu-id="3208e-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="3208e-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3208e-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="3208e-113">**McuId**</span></span> <br/> |<span data-ttu-id="3208e-114">int</span><span class="sxs-lookup"><span data-stu-id="3208e-114">int</span></span>  <br/> |<span data-ttu-id="3208e-115">Primary</span><span class="sxs-lookup"><span data-stu-id="3208e-115">Primary</span></span>  <br/> |<span data-ttu-id="3208e-116">标识此会议服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="3208e-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="3208e-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="3208e-117">**McuUri**</span></span> <br/> |<span data-ttu-id="3208e-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="3208e-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="3208e-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="3208e-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="3208e-120">inyint</span><span class="sxs-lookup"><span data-stu-id="3208e-120">inyint</span></span>  <br/> | <span data-ttu-id="3208e-121">外</span><span class="sxs-lookup"><span data-stu-id="3208e-121">Foreign</span></span> <br/> |<span data-ttu-id="3208e-122">会议服务器类型，（用于 IMs) conf:chat 和 conf:audio 的视频。</span><span class="sxs-lookup"><span data-stu-id="3208e-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="3208e-123">[UriTypes 表](uritypes.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="3208e-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

