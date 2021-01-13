---
title: Skype for Business Server 2015 中的 Mcus 表
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcus 表是一个支持表。 每条记录都存储有关一个会议服务的信息。 其中包括 IM 会议服务和电话会议服务 (它们作为进程在前端服务器) 以及 Web 会议服务和 A/V 会议服务中运行。
ms.openlocfilehash: fe43bfc747cd08febe00a68925ad520b6add5846
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821422"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a36a0-105">Skype for Business Server 2015 中的 Mcus 表</span><span class="sxs-lookup"><span data-stu-id="a36a0-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a36a0-106">Mcus 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="a36a0-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="a36a0-107">每条记录都存储有关一个会议服务的信息。</span><span class="sxs-lookup"><span data-stu-id="a36a0-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="a36a0-108">其中包括 IM 会议服务和电话会议服务 (它们作为进程在前端服务器) 以及 Web 会议服务和 A/V 会议服务中运行。</span><span class="sxs-lookup"><span data-stu-id="a36a0-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="a36a0-109">**列**</span><span class="sxs-lookup"><span data-stu-id="a36a0-109">**Column**</span></span>|<span data-ttu-id="a36a0-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a36a0-110">**Data Type**</span></span>|<span data-ttu-id="a36a0-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="a36a0-111">**Key/Index**</span></span>|<span data-ttu-id="a36a0-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="a36a0-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a36a0-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="a36a0-113">**McuId**</span></span> <br/> |<span data-ttu-id="a36a0-114">int</span><span class="sxs-lookup"><span data-stu-id="a36a0-114">int</span></span>  <br/> |<span data-ttu-id="a36a0-115">主</span><span class="sxs-lookup"><span data-stu-id="a36a0-115">Primary</span></span>  <br/> |<span data-ttu-id="a36a0-116">标识此会议服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="a36a0-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="a36a0-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="a36a0-117">**McuUri**</span></span> <br/> |<span data-ttu-id="a36a0-118">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="a36a0-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="a36a0-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="a36a0-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="a36a0-120">inyint</span><span class="sxs-lookup"><span data-stu-id="a36a0-120">inyint</span></span>  <br/> | <span data-ttu-id="a36a0-121">Foreign</span><span class="sxs-lookup"><span data-stu-id="a36a0-121">Foreign</span></span> <br/> |<span data-ttu-id="a36a0-122">会议服务器类型，例如 conf：chat (用于) conf：audio-video。</span><span class="sxs-lookup"><span data-stu-id="a36a0-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="a36a0-123">有关详细信息， [请参阅 UriTypes](uritypes.md) 表。</span><span class="sxs-lookup"><span data-stu-id="a36a0-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

