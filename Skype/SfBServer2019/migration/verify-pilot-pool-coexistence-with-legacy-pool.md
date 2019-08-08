---
title: 验证试点池与旧池的共存情况
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 用于验证与旧版池共存的引导池的过程。
ms.openlocfilehash: e71160a2a20d4a80979e3c3c4875c19db181f2da
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243748"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="840ad-103">验证试点池与旧池的共存情况</span><span class="sxs-lookup"><span data-stu-id="840ad-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="840ad-104">**在本文中**</span><span class="sxs-lookup"><span data-stu-id="840ad-104">**In this article**</span></span>
  
[<span data-ttu-id="840ad-105">验证 Skype for business Server 2019 服务是否已启动</span><span class="sxs-lookup"><span data-stu-id="840ad-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="840ad-106">打开 "Skype for Business 服务器2019控制面板"</span><span class="sxs-lookup"><span data-stu-id="840ad-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="840ad-107">不要尝试在旧版拓扑生成器中打开拓扑</span><span class="sxs-lookup"><span data-stu-id="840ad-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="840ad-108">部署试验池后, 您需要通过使用管理工具查看池信息来验证两个池的共存。</span><span class="sxs-lookup"><span data-stu-id="840ad-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="840ad-109">对于 Skype for business Server 2019 池和旧版池, 必须使用 Skype for Business Server 2019 控制面板和拓扑生成器工具。</span><span class="sxs-lookup"><span data-stu-id="840ad-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="840ad-110">验证 Skype for business Server 2019 服务是否已启动</span><span class="sxs-lookup"><span data-stu-id="840ad-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="840ad-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="840ad-111"></span></span>

1. <span data-ttu-id="840ad-112">从 Skype for Business 服务器2019前端服务器, 导航到 "管理 Tools\Services" 小程序。</span><span class="sxs-lookup"><span data-stu-id="840ad-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="840ad-113">验证以下服务是否在前端服务器上运行:</span><span class="sxs-lookup"><span data-stu-id="840ad-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="840ad-114">集中日志记录服务代理</span><span class="sxs-lookup"><span data-stu-id="840ad-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="840ad-115">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="840ad-115">Application Sharing</span></span>
    - <span data-ttu-id="840ad-116">音频测试服务</span><span class="sxs-lookup"><span data-stu-id="840ad-116">Audio Test Service</span></span>
    - <span data-ttu-id="840ad-117">音频/视频会议</span><span class="sxs-lookup"><span data-stu-id="840ad-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="840ad-118">呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="840ad-118">Call Park</span></span>
    - <span data-ttu-id="840ad-119">会议公告</span><span class="sxs-lookup"><span data-stu-id="840ad-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="840ad-120">会议助理</span><span class="sxs-lookup"><span data-stu-id="840ad-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="840ad-121">前端</span><span class="sxs-lookup"><span data-stu-id="840ad-121">Front-End</span></span>
    - <span data-ttu-id="840ad-122">IM 会议</span><span class="sxs-lookup"><span data-stu-id="840ad-122">IM Conferencing</span></span>
    - <span data-ttu-id="840ad-123">中介</span><span class="sxs-lookup"><span data-stu-id="840ad-123">Mediation</span></span>
    - <span data-ttu-id="840ad-124">复制副本复制器代理</span><span class="sxs-lookup"><span data-stu-id="840ad-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="840ad-125">响应组</span><span class="sxs-lookup"><span data-stu-id="840ad-125">Response Group</span></span>
    - <span data-ttu-id="840ad-126">Web 会议</span><span class="sxs-lookup"><span data-stu-id="840ad-126">Web Conferencing</span></span>
    - <span data-ttu-id="840ad-127">XMPP 翻译网关</span><span class="sxs-lookup"><span data-stu-id="840ad-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="840ad-128">打开 "Skype for Business 服务器2019控制面板"</span><span class="sxs-lookup"><span data-stu-id="840ad-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="840ad-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="840ad-129"></span></span>

<span data-ttu-id="840ad-130">在 Skype for business Server 2019 部署的前端服务器中, 打开 Skype for business Server 2019 控制面板, 然后选择 "旧版" 池。</span><span class="sxs-lookup"><span data-stu-id="840ad-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="840ad-131">重复该过程以打开 Skype for Business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="840ad-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="840ad-132">在 Skype for business Server 2019 上, 在使用 Skype for Business 服务器控制面板之前, 必须将 Silverlight 升级到 Silverlight 版本5。</span><span class="sxs-lookup"><span data-stu-id="840ad-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="840ad-133">此拓扑现在包括旧版和 Skype for business Server 2019 服务器角色。</span><span class="sxs-lookup"><span data-stu-id="840ad-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="840ad-134">不要尝试在旧版拓扑生成器中打开拓扑</span><span class="sxs-lookup"><span data-stu-id="840ad-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="840ad-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="840ad-135"></span></span>

<span data-ttu-id="840ad-136">拓扑仅可使用 Skype for Business Server 2019 拓扑生成器查看。</span><span class="sxs-lookup"><span data-stu-id="840ad-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="840ad-137">必须使用 Skype for business Server 2019 拓扑生成器为 Skype for business Server 2019 和旧式安装创建池。</span><span class="sxs-lookup"><span data-stu-id="840ad-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

