---
title: QoE 视图列表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: 视图介绍用于从 QoE SQL 数据库返回数据的最常见方案。 建议用于构建而不是直接访问数据库表; 的自定义报告视图这是因为视图是更容易保持向后兼容性将来版本。
ms.openlocfilehash: f384f75ecc0c8a0dfdb2cdaedacdcef81bdba9b4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212142"
---
# <a name="qoe-view-details"></a><span data-ttu-id="01f70-104">QoE 视图列表</span><span class="sxs-lookup"><span data-stu-id="01f70-104">QoE view details</span></span>
 
<span data-ttu-id="01f70-105">视图介绍用于从 QoE SQL 数据库返回数据的最常见方案。</span><span class="sxs-lookup"><span data-stu-id="01f70-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="01f70-106">建议用于构建而不是直接访问数据库表; 的自定义报告视图这是因为视图是更容易保持向后兼容性将来版本。</span><span class="sxs-lookup"><span data-stu-id="01f70-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="01f70-107">**视图名称**</span><span class="sxs-lookup"><span data-stu-id="01f70-107">**View Name**</span></span>|<span data-ttu-id="01f70-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="01f70-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="01f70-109">AudioStreamDetail 视图</span><span class="sxs-lookup"><span data-stu-id="01f70-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="01f70-110">在数据库中存储有关每个音频流的信息。</span><span class="sxs-lookup"><span data-stu-id="01f70-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="01f70-111">MediaLine 视图</span><span class="sxs-lookup"><span data-stu-id="01f70-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="01f70-112">在数据库中存储有关每个媒体行的信息。</span><span class="sxs-lookup"><span data-stu-id="01f70-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="01f70-113">一个音频会话通常包含一个音频媒体行。</span><span class="sxs-lookup"><span data-stu-id="01f70-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="01f70-114">一个音频和视频 (A / V) 会话通常包含一个音频媒体行和视频媒体一行;但是，会话可能包含两个视频媒体行，如果使用一种会议设备，或使用库视图。</span><span class="sxs-lookup"><span data-stu-id="01f70-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="01f70-115">NetworkConfigurationSettings 视图</span><span class="sxs-lookup"><span data-stu-id="01f70-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="01f70-116">存储有关网络配置信息。</span><span class="sxs-lookup"><span data-stu-id="01f70-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="01f70-117">会话视图</span><span class="sxs-lookup"><span data-stu-id="01f70-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="01f70-118">存储有关数据库中包含记录的会话的信息。</span><span class="sxs-lookup"><span data-stu-id="01f70-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="01f70-119">UserAgent 视图</span><span class="sxs-lookup"><span data-stu-id="01f70-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="01f70-120">存储有关数据库中包含记录的会话中涉及的用户代理的信息。</span><span class="sxs-lookup"><span data-stu-id="01f70-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="01f70-121">VideoStreamDetail 视图</span><span class="sxs-lookup"><span data-stu-id="01f70-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="01f70-122">在数据库中存储有关每个视频流的信息。</span><span class="sxs-lookup"><span data-stu-id="01f70-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

