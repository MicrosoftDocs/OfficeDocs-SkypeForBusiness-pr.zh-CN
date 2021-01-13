---
title: UserAgent 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent 表是一个支持表，用于存储已参与数据库中记录的会话的各种用户代理的列表。 表中的每条记录表示一个用户代理
ms.openlocfilehash: a1d0e647ff78d409555988a27592228fac2643be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799928"
---
# <a name="useragent-table"></a><span data-ttu-id="0cad4-104">UserAgent 表</span><span class="sxs-lookup"><span data-stu-id="0cad4-104">UserAgent table</span></span>
 
<span data-ttu-id="0cad4-105">UserAgent 表是一个支持表，用于存储已参与数据库中记录的会话的各种用户代理的列表。</span><span class="sxs-lookup"><span data-stu-id="0cad4-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="0cad4-106">表中的每条记录表示一个用户代理</span><span class="sxs-lookup"><span data-stu-id="0cad4-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="0cad4-107">**列**</span><span class="sxs-lookup"><span data-stu-id="0cad4-107">**Column**</span></span>|<span data-ttu-id="0cad4-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0cad4-108">**Data Type**</span></span>|<span data-ttu-id="0cad4-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="0cad4-109">**Key/Index**</span></span>|<span data-ttu-id="0cad4-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="0cad4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0cad4-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="0cad4-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="0cad4-112">int</span><span class="sxs-lookup"><span data-stu-id="0cad4-112">int</span></span>  <br/> |<span data-ttu-id="0cad4-113">主</span><span class="sxs-lookup"><span data-stu-id="0cad4-113">Primary</span></span>  <br/> |<span data-ttu-id="0cad4-114">标识此用户代理的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="0cad4-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="0cad4-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="0cad4-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="0cad4-116">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="0cad4-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0cad4-117">独特</span><span class="sxs-lookup"><span data-stu-id="0cad4-117">Unique</span></span>  <br/> |<span data-ttu-id="0cad4-118">用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="0cad4-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="0cad4-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="0cad4-119">**UAType**</span></span> <br/> |<span data-ttu-id="0cad4-120">smallint</span><span class="sxs-lookup"><span data-stu-id="0cad4-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="0cad4-121">1 是中介服务器。</span><span class="sxs-lookup"><span data-stu-id="0cad4-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="0cad4-122">2 是 A/V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="0cad4-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="0cad4-123">4 是 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="0cad4-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="0cad4-124">8 是 IP 电话。</span><span class="sxs-lookup"><span data-stu-id="0cad4-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="0cad4-125">16 是 Live Meeting 控制台。</span><span class="sxs-lookup"><span data-stu-id="0cad4-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="0cad4-126">32 是部署验证工具 (DVDT) 。</span><span class="sxs-lookup"><span data-stu-id="0cad4-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="0cad4-127">64 是 Macintosh 计算机上的 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="0cad4-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="0cad4-128">128 是 Skype for Business Server Attendant。</span><span class="sxs-lookup"><span data-stu-id="0cad4-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="0cad4-129">256 是会议通知服务。</span><span class="sxs-lookup"><span data-stu-id="0cad4-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="0cad4-130">512 是会议自动助理。</span><span class="sxs-lookup"><span data-stu-id="0cad4-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="0cad4-131">1024 是响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="0cad4-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="0cad4-132">2048 是外部语音控制。</span><span class="sxs-lookup"><span data-stu-id="0cad4-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

