---
title: UserAgent 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: 用户代理表是一个支持的表来存储会话记录在数据库中都可以参加的各种用户代理的列表。 每个表中的记录表示一个用户代理
ms.openlocfilehash: 5b9bcc35fbad3d20a006410aeb3538b6f5daa77e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="useragent-table"></a><span data-ttu-id="1569e-104">UserAgent 表</span><span class="sxs-lookup"><span data-stu-id="1569e-104">UserAgent table</span></span>
 
<span data-ttu-id="1569e-105">用户代理表是一个支持的表来存储会话记录在数据库中都可以参加的各种用户代理的列表。</span><span class="sxs-lookup"><span data-stu-id="1569e-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="1569e-106">每个表中的记录表示一个用户代理</span><span class="sxs-lookup"><span data-stu-id="1569e-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="1569e-107">**列**</span><span class="sxs-lookup"><span data-stu-id="1569e-107">**Column**</span></span>|<span data-ttu-id="1569e-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1569e-108">**Data Type**</span></span>|<span data-ttu-id="1569e-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="1569e-109">**Key/Index**</span></span>|<span data-ttu-id="1569e-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="1569e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1569e-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="1569e-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="1569e-112">int</span><span class="sxs-lookup"><span data-stu-id="1569e-112">int</span></span>  <br/> |<span data-ttu-id="1569e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="1569e-113">Primary</span></span>  <br/> |<span data-ttu-id="1569e-114">标识此用户代理的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="1569e-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="1569e-115">**用户代理**</span><span class="sxs-lookup"><span data-stu-id="1569e-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="1569e-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1569e-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1569e-117">唯一</span><span class="sxs-lookup"><span data-stu-id="1569e-117">Unique</span></span>  <br/> |<span data-ttu-id="1569e-118">用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="1569e-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="1569e-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="1569e-119">**UAType**</span></span> <br/> |<span data-ttu-id="1569e-120">smallint</span><span class="sxs-lookup"><span data-stu-id="1569e-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="1569e-121">1 是中介服务器。</span><span class="sxs-lookup"><span data-stu-id="1569e-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="1569e-122">2 是 A / V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="1569e-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="1569e-123">4 是 Skype 的业务。</span><span class="sxs-lookup"><span data-stu-id="1569e-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="1569e-124">IP 电话是 8。</span><span class="sxs-lookup"><span data-stu-id="1569e-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="1569e-125">16 是 Live Meeting 控制台。</span><span class="sxs-lookup"><span data-stu-id="1569e-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="1569e-126">32 是部署验证工具 (DVT)。</span><span class="sxs-lookup"><span data-stu-id="1569e-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="1569e-127">64 是在 Macintosh 计算机上的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="1569e-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="1569e-128">128 是 Skype 业务服务器助理。</span><span class="sxs-lookup"><span data-stu-id="1569e-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="1569e-129">256 是会议发布服务。</span><span class="sxs-lookup"><span data-stu-id="1569e-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="1569e-130">512 是会议自动助理。</span><span class="sxs-lookup"><span data-stu-id="1569e-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="1569e-131">1024 是响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="1569e-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="1569e-132">2048 是外部声音控制。</span><span class="sxs-lookup"><span data-stu-id="1569e-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

