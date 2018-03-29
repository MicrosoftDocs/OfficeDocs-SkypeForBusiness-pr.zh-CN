---
title: QoE 查看详细信息
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: 视图包括从 QoE SQL 数据库返回数据的最常见方案。 建议视图用于生成自定义报告，而不是直接访问数据库表中。这是因为视图会更容易保持向后兼容与将来的发行版。
ms.openlocfilehash: 72fe0a1cd4bd3319bbb6907a23bda0932b3ef619
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="qoe-view-details"></a><span data-ttu-id="31680-104">QoE 查看详细信息</span><span class="sxs-lookup"><span data-stu-id="31680-104">QoE view details</span></span>
 
<span data-ttu-id="31680-105">视图包括从 QoE SQL 数据库返回数据的最常见方案。</span><span class="sxs-lookup"><span data-stu-id="31680-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="31680-106">建议视图用于生成自定义报告，而不是直接访问数据库表中。这是因为视图会更容易保持向后兼容与将来的发行版。</span><span class="sxs-lookup"><span data-stu-id="31680-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="31680-107">**视图名称**</span><span class="sxs-lookup"><span data-stu-id="31680-107">**View Name**</span></span>|<span data-ttu-id="31680-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="31680-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="31680-109">AudioStreamDetail 视图</span><span class="sxs-lookup"><span data-stu-id="31680-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="31680-110">在数据库中存储有关每个音频流信息。</span><span class="sxs-lookup"><span data-stu-id="31680-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="31680-111">MediaLine 视图</span><span class="sxs-lookup"><span data-stu-id="31680-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="31680-112">在数据库中存储有关每个媒体行的信息。</span><span class="sxs-lookup"><span data-stu-id="31680-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="31680-113">一个音频会话通常包含音频媒体一行。</span><span class="sxs-lookup"><span data-stu-id="31680-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="31680-114">一个音频和视频 (A / V) 会话通常包含音频媒体一行和视频媒体一行;但是，会话可能包含两个视频媒体行如果使用电话会议设备，或使用图片库视图。</span><span class="sxs-lookup"><span data-stu-id="31680-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="31680-115">NetworkConfigurationSettings 视图</span><span class="sxs-lookup"><span data-stu-id="31680-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="31680-116">存储有关网络配置的信息。</span><span class="sxs-lookup"><span data-stu-id="31680-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="31680-117">会话视图</span><span class="sxs-lookup"><span data-stu-id="31680-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="31680-118">存储在数据库中具有记录的会话信息。</span><span class="sxs-lookup"><span data-stu-id="31680-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="31680-119">用户代理视图</span><span class="sxs-lookup"><span data-stu-id="31680-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="31680-120">存储在数据库中具有记录的会话中涉及的用户代理信息。</span><span class="sxs-lookup"><span data-stu-id="31680-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="31680-121">VideoStreamDetail 视图</span><span class="sxs-lookup"><span data-stu-id="31680-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="31680-122">在数据库中存储有关每个视频流的信息。</span><span class="sxs-lookup"><span data-stu-id="31680-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

