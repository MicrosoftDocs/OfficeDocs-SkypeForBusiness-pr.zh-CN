---
title: 验证试点池与旧池的共存情况
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 用于验证与旧版池共存的引导池的过程。
ms.openlocfilehash: e9fe944c03c88aad2ca2b40f0e995842363e7a85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751654"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="de8ae-103">验证试点池与旧池的共存情况</span><span class="sxs-lookup"><span data-stu-id="de8ae-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="de8ae-104">**本文内容：**</span><span class="sxs-lookup"><span data-stu-id="de8ae-104">**In this article**</span></span>
  
[<span data-ttu-id="de8ae-105">验证 Skype for Business Server 2019 服务是否已启动</span><span class="sxs-lookup"><span data-stu-id="de8ae-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="de8ae-106">打开 "Skype for Business Server 2019 控制面板"</span><span class="sxs-lookup"><span data-stu-id="de8ae-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="de8ae-107">不要尝试在旧版拓扑生成器中打开拓扑</span><span class="sxs-lookup"><span data-stu-id="de8ae-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="de8ae-108">部署试点池之后，需要使用管理工具查看池信息来验证两个池是否共存。</span><span class="sxs-lookup"><span data-stu-id="de8ae-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="de8ae-109">对于 Skype for business Server 2019 池和旧版池，您必须使用 Skype for Business Server 2019 控制面板和拓扑生成器工具。</span><span class="sxs-lookup"><span data-stu-id="de8ae-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="de8ae-110">验证 Skype for Business Server 2019 服务是否已启动</span><span class="sxs-lookup"><span data-stu-id="de8ae-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="de8ae-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="de8ae-111"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="de8ae-112">在 Skype for Business Server 2019 前端服务器中，导航到 "管理" Tools\Services 小程序。</span><span class="sxs-lookup"><span data-stu-id="de8ae-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="de8ae-113">确认以下服务正在前端服务器上运行：</span><span class="sxs-lookup"><span data-stu-id="de8ae-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="de8ae-114">集中日志记录服务代理</span><span class="sxs-lookup"><span data-stu-id="de8ae-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="de8ae-115">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="de8ae-115">Application Sharing</span></span>
    - <span data-ttu-id="de8ae-116">音频测试服务</span><span class="sxs-lookup"><span data-stu-id="de8ae-116">Audio Test Service</span></span>
    - <span data-ttu-id="de8ae-117">音频/视频会议</span><span class="sxs-lookup"><span data-stu-id="de8ae-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="de8ae-118">Call Park － 呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="de8ae-118">Call Park</span></span>
    - <span data-ttu-id="de8ae-119">会议通知</span><span class="sxs-lookup"><span data-stu-id="de8ae-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="de8ae-120">会议助理</span><span class="sxs-lookup"><span data-stu-id="de8ae-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="de8ae-121">前端</span><span class="sxs-lookup"><span data-stu-id="de8ae-121">Front-End</span></span>
    - <span data-ttu-id="de8ae-122">IM 会议</span><span class="sxs-lookup"><span data-stu-id="de8ae-122">IM Conferencing</span></span>
    - <span data-ttu-id="de8ae-123">中介</span><span class="sxs-lookup"><span data-stu-id="de8ae-123">Mediation</span></span>
    - <span data-ttu-id="de8ae-124">副本复制器代理</span><span class="sxs-lookup"><span data-stu-id="de8ae-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="de8ae-125">Response Group － 响应组</span><span class="sxs-lookup"><span data-stu-id="de8ae-125">Response Group</span></span>
    - <span data-ttu-id="de8ae-126">Web 会议</span><span class="sxs-lookup"><span data-stu-id="de8ae-126">Web Conferencing</span></span>
    - <span data-ttu-id="de8ae-127">XMPP 转换网关</span><span class="sxs-lookup"><span data-stu-id="de8ae-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="de8ae-128">打开 "Skype for Business Server 2019 控制面板"</span><span class="sxs-lookup"><span data-stu-id="de8ae-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="de8ae-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="de8ae-129"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="de8ae-130">在 Skype for business Server 2019 部署的前端服务器中，打开 Skype for Business Server 2019 控制面板，然后选择旧版池。</span><span class="sxs-lookup"><span data-stu-id="de8ae-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="de8ae-131">重复此过程以打开 Skype for Business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="de8ae-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="de8ae-132">在 Skype for business Server 2019 上，在使用 Skype for Business Server 控制面板之前，必须将 Silverlight 升级到 Silverlight 版本5。</span><span class="sxs-lookup"><span data-stu-id="de8ae-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="de8ae-133">此拓扑现在包括旧版和 Skype for business Server 2019 服务器角色。</span><span class="sxs-lookup"><span data-stu-id="de8ae-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="de8ae-134">不要尝试在旧版拓扑生成器中打开拓扑</span><span class="sxs-lookup"><span data-stu-id="de8ae-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="de8ae-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="de8ae-135"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="de8ae-136">仅可以使用 Skype for Business Server 2019 拓扑生成器查看拓扑。</span><span class="sxs-lookup"><span data-stu-id="de8ae-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="de8ae-137">Skype for Business Server 2019 拓扑生成器必须用于为 Skype for business Server 2019 和旧安装创建池。</span><span class="sxs-lookup"><span data-stu-id="de8ae-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

