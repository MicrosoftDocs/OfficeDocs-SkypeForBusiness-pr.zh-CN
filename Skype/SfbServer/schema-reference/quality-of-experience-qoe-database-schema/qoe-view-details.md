---
title: QoE 视图列表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: 视图涵盖从 QoE SQL 数据库返回数据的最常见方案。 推荐用于构建自定义报表的视图, 而不是直接访问数据库表;这是因为视图更有可能保持与未来版本的向后兼容性。
ms.openlocfilehash: c492b06f2b6e8050e4992837f0f2b7ebba106858
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294752"
---
# <a name="qoe-view-details"></a><span data-ttu-id="e3fd9-104">QoE 视图列表</span><span class="sxs-lookup"><span data-stu-id="e3fd9-104">QoE view details</span></span>
 
<span data-ttu-id="e3fd9-105">视图涵盖从 QoE SQL 数据库返回数据的最常见方案。</span><span class="sxs-lookup"><span data-stu-id="e3fd9-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="e3fd9-106">推荐用于构建自定义报表的视图, 而不是直接访问数据库表;这是因为视图更有可能保持与未来版本的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="e3fd9-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="e3fd9-107">**视图名称**</span><span class="sxs-lookup"><span data-stu-id="e3fd9-107">**View Name**</span></span>|<span data-ttu-id="e3fd9-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="e3fd9-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e3fd9-109">AudioStreamDetail 视图</span><span class="sxs-lookup"><span data-stu-id="e3fd9-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="e3fd9-110">存储有关数据库中每个音频流的信息。</span><span class="sxs-lookup"><span data-stu-id="e3fd9-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="e3fd9-111">MediaLine 视图</span><span class="sxs-lookup"><span data-stu-id="e3fd9-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="e3fd9-112">存储有关数据库中每个媒体行的信息。</span><span class="sxs-lookup"><span data-stu-id="e3fd9-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="e3fd9-113">一个音频会话通常包含一个音频媒体行。</span><span class="sxs-lookup"><span data-stu-id="e3fd9-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="e3fd9-114">一个音频和视频 (A/V) 会话通常包含一个音频媒体线和一个视频媒体行;但是, 如果使用了会议设备或使用了库视图, 则会话可能包含两个视频媒体线。</span><span class="sxs-lookup"><span data-stu-id="e3fd9-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="e3fd9-115">NetworkConfigurationSettings 视图</span><span class="sxs-lookup"><span data-stu-id="e3fd9-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="e3fd9-116">存储有关网络配置的信息。</span><span class="sxs-lookup"><span data-stu-id="e3fd9-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="e3fd9-117">会话视图</span><span class="sxs-lookup"><span data-stu-id="e3fd9-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="e3fd9-118">存储有关在数据库中具有记录的会话的信息。</span><span class="sxs-lookup"><span data-stu-id="e3fd9-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="e3fd9-119">UserAgent 视图</span><span class="sxs-lookup"><span data-stu-id="e3fd9-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="e3fd9-120">存储有关在数据库中具有记录的会话中涉及的用户代理的信息。</span><span class="sxs-lookup"><span data-stu-id="e3fd9-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="e3fd9-121">VideoStreamDetail 视图</span><span class="sxs-lookup"><span data-stu-id="e3fd9-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="e3fd9-122">存储有关数据库中的每个视频流的信息。</span><span class="sxs-lookup"><span data-stu-id="e3fd9-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

