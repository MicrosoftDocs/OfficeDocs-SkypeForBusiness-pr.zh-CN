---
title: 验证试点池与旧池的共存情况
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 若要验证试点池与旧池的共存情况的过程。
ms.openlocfilehash: ed3809bdde3109bdbd341c42eed0dc1d8cecd11f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231341"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="d9b48-103">验证试点池与旧池的共存情况</span><span class="sxs-lookup"><span data-stu-id="d9b48-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="d9b48-104">**本文中**</span><span class="sxs-lookup"><span data-stu-id="d9b48-104">**In this article**</span></span>
  
[<span data-ttu-id="d9b48-105">确认 Skype 业务服务器 2019年服务已启动</span><span class="sxs-lookup"><span data-stu-id="d9b48-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="d9b48-106">打开 Skype 业务 Server 2019 Control Panel</span><span class="sxs-lookup"><span data-stu-id="d9b48-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="d9b48-107">请勿尝试在旧拓扑生成器中打开拓扑</span><span class="sxs-lookup"><span data-stu-id="d9b48-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="d9b48-108">部署试点池后，您需要验证通过使用管理工具来查看池信息的两个池的共存情况。</span><span class="sxs-lookup"><span data-stu-id="d9b48-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="d9b48-109">对于业务服务器 2019年池和旧池 Skype，您必须使用业务 Server 2019 控制面板和拓扑生成器工具 Skype。</span><span class="sxs-lookup"><span data-stu-id="d9b48-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="d9b48-110">确认 Skype 业务服务器 2019年服务已启动</span><span class="sxs-lookup"><span data-stu-id="d9b48-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="d9b48-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="d9b48-111"></span></span>

1. <span data-ttu-id="d9b48-112">从业务 Server 2019 前端服务器的 Skype，导航到管理工具 \ 服务小程序。</span><span class="sxs-lookup"><span data-stu-id="d9b48-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="d9b48-113">确认以下服务都在前端服务器上运行：</span><span class="sxs-lookup"><span data-stu-id="d9b48-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="d9b48-114">集中日志记录服务代理</span><span class="sxs-lookup"><span data-stu-id="d9b48-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="d9b48-115">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="d9b48-115">Application Sharing</span></span>
    - <span data-ttu-id="d9b48-116">音频测试服务</span><span class="sxs-lookup"><span data-stu-id="d9b48-116">Audio Test Service</span></span>
    - <span data-ttu-id="d9b48-117">音频/视频会议</span><span class="sxs-lookup"><span data-stu-id="d9b48-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="d9b48-118">呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="d9b48-118">Call Park</span></span>
    - <span data-ttu-id="d9b48-119">会议公告</span><span class="sxs-lookup"><span data-stu-id="d9b48-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="d9b48-120">会议助理</span><span class="sxs-lookup"><span data-stu-id="d9b48-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="d9b48-121">前端</span><span class="sxs-lookup"><span data-stu-id="d9b48-121">Front-End</span></span>
    - <span data-ttu-id="d9b48-122">IM 会议</span><span class="sxs-lookup"><span data-stu-id="d9b48-122">IM Conferencing</span></span>
    - <span data-ttu-id="d9b48-123">中介</span><span class="sxs-lookup"><span data-stu-id="d9b48-123">Mediation</span></span>
    - <span data-ttu-id="d9b48-124">副本复制程序代理</span><span class="sxs-lookup"><span data-stu-id="d9b48-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="d9b48-125">响应组</span><span class="sxs-lookup"><span data-stu-id="d9b48-125">Response Group</span></span>
    - <span data-ttu-id="d9b48-126">Web 会议</span><span class="sxs-lookup"><span data-stu-id="d9b48-126">Web Conferencing</span></span>
    - <span data-ttu-id="d9b48-127">XMPP 转换网关</span><span class="sxs-lookup"><span data-stu-id="d9b48-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="d9b48-128">打开 Skype 业务 Server 2019 Control Panel</span><span class="sxs-lookup"><span data-stu-id="d9b48-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="d9b48-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="d9b48-129"></span></span>

<span data-ttu-id="d9b48-130">从业务服务器 2019年部署您 Skype 前端服务器，打开 Skype 业务 Server 2019 控制面板，然后选择旧池。</span><span class="sxs-lookup"><span data-stu-id="d9b48-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="d9b48-131">重复打开业务服务器 2019年池 Skype 的过程。</span><span class="sxs-lookup"><span data-stu-id="d9b48-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d9b48-132">上的业务服务器 2019 Skype，必须将 Silverlight 升级到 Silverlight 版本 5 之前 Skype 用于业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="d9b48-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="d9b48-133">此拓扑现在包含旧和 Skype 业务服务器 2019年服务器角色。</span><span class="sxs-lookup"><span data-stu-id="d9b48-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="d9b48-134">请勿尝试在旧拓扑生成器中打开拓扑</span><span class="sxs-lookup"><span data-stu-id="d9b48-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="d9b48-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="d9b48-135"></span></span>

<span data-ttu-id="d9b48-136">如果您尝试打开使用旧拓扑生成器的拓扑，则会收到以下错误消息。</span><span class="sxs-lookup"><span data-stu-id="d9b48-136">If you attempt to open the topology using the legacy Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="d9b48-137">只能使用 Skype 业务 Server 2019 拓扑生成器查看拓扑。</span><span class="sxs-lookup"><span data-stu-id="d9b48-137">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="d9b48-138">业务 Server 2019 拓扑生成器的 Skype 必须用于业务服务器 2019年的 Skype 和旧安装创建池。</span><span class="sxs-lookup"><span data-stu-id="d9b48-138">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

