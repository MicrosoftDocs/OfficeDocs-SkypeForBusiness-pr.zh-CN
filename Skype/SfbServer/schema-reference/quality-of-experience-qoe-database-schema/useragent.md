---
title: UserAgent 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent 表是一个支持表, 用于存储参与数据库中记录的会话的各种用户代理的列表。 表中的每条记录表示一个用户代理
ms.openlocfilehash: f0c8a2f182611887db1324d17b6b7c28d6a9393d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294584"
---
# <a name="useragent-table"></a><span data-ttu-id="7a723-104">UserAgent 表</span><span class="sxs-lookup"><span data-stu-id="7a723-104">UserAgent table</span></span>
 
<span data-ttu-id="7a723-105">UserAgent 表是一个支持表, 用于存储参与数据库中记录的会话的各种用户代理的列表。</span><span class="sxs-lookup"><span data-stu-id="7a723-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="7a723-106">表中的每条记录表示一个用户代理</span><span class="sxs-lookup"><span data-stu-id="7a723-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="7a723-107">**列**</span><span class="sxs-lookup"><span data-stu-id="7a723-107">**Column**</span></span>|<span data-ttu-id="7a723-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7a723-108">**Data Type**</span></span>|<span data-ttu-id="7a723-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="7a723-109">**Key/Index**</span></span>|<span data-ttu-id="7a723-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="7a723-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7a723-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="7a723-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="7a723-112">int</span><span class="sxs-lookup"><span data-stu-id="7a723-112">int</span></span>  <br/> |<span data-ttu-id="7a723-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7a723-113">Primary</span></span>  <br/> |<span data-ttu-id="7a723-114">标识此用户代理的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="7a723-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="7a723-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="7a723-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="7a723-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7a723-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="7a723-117">唯一</span><span class="sxs-lookup"><span data-stu-id="7a723-117">Unique</span></span>  <br/> |<span data-ttu-id="7a723-118">用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="7a723-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="7a723-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="7a723-119">**UAType**</span></span> <br/> |<span data-ttu-id="7a723-120">smallint</span><span class="sxs-lookup"><span data-stu-id="7a723-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="7a723-121">1是中介服务器。</span><span class="sxs-lookup"><span data-stu-id="7a723-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="7a723-122">2是 A/V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="7a723-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="7a723-123">4是 Skype for business。</span><span class="sxs-lookup"><span data-stu-id="7a723-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="7a723-124">8是 IP 电话。</span><span class="sxs-lookup"><span data-stu-id="7a723-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="7a723-125">16是 Live Meeting 控制台。</span><span class="sxs-lookup"><span data-stu-id="7a723-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="7a723-126">32是部署验证工具 (DVT)。</span><span class="sxs-lookup"><span data-stu-id="7a723-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="7a723-127">64是 Macintosh 计算机上的 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="7a723-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="7a723-128">128是 Skype for business 服务器助理。</span><span class="sxs-lookup"><span data-stu-id="7a723-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="7a723-129">256是会议公告服务。</span><span class="sxs-lookup"><span data-stu-id="7a723-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="7a723-130">512是会议自动助理。</span><span class="sxs-lookup"><span data-stu-id="7a723-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="7a723-131">1024是响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="7a723-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="7a723-132">2048不在语音控制范围内。</span><span class="sxs-lookup"><span data-stu-id="7a723-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

