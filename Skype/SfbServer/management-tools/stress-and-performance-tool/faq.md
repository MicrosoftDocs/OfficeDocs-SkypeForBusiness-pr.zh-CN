---
title: 为业务服务器 2015年压力和性能工具 Skype 常见问题
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype 的业务 2015年压力和性能工具： 常见问题 (FAQ)，用于查找支持哪些工具配置、 疑难解答工具问题并阐明时运行压力和性能工具可能会看到的行为.
ms.openlocfilehash: f71ff02d1bcb6bb858aa4e00144e55bf43c4cbd5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873448"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="14969-103">为业务服务器 2015年压力和性能工具 Skype 常见问题</span><span class="sxs-lookup"><span data-stu-id="14969-103">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="14969-104">Skype 的业务 2015年压力和性能工具： 常见问题 (FAQ)，用于查找支持哪些工具配置、 疑难解答工具问题并阐明时运行压力和性能工具可能会看到的行为.</span><span class="sxs-lookup"><span data-stu-id="14969-104">Skype for Business 2015 Stress and Performance Tool frequently asked questions (FAQ), useful for finding out what tool configurations are supported, troubleshooting tool issues, and clarifying behaviours you may see when running the Stress and Performance tools.</span></span>
  
 <span data-ttu-id="14969-105">本常见问题解答介绍一些有关 Business Server 2015 压力和性能工具 Skype 的最常见问题，可帮助具有疑难解答和工具的配置选项。</span><span class="sxs-lookup"><span data-stu-id="14969-105">This FAQ covers some of the most frequently asked questions about the Skype for Business Server 2015 Stress and Performance tool, and may help with troubleshooting and tool configuration choices.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="14969-106">可以在生产中运行 LyncPerfTool.exe？</span><span class="sxs-lookup"><span data-stu-id="14969-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="14969-107">这**不**建议使用。</span><span class="sxs-lookup"><span data-stu-id="14969-107">This is **not** recommended.</span></span> <span data-ttu-id="14969-108">该工具将影响您的生产服务器性能、 安全性和最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="14969-108">The tool would impact your production server performance, security, and the end user experience.</span></span>
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a><span data-ttu-id="14969-109">我正在登录第一次的我的用户。</span><span class="sxs-lookup"><span data-stu-id="14969-109">I'm logging my users on for the first time.</span></span> <span data-ttu-id="14969-110">为什么我服务器正在运行的高负载</span><span class="sxs-lookup"><span data-stu-id="14969-110">Why are my servers running a high load?</span></span>

<span data-ttu-id="14969-111">第一次用户登录时，在后台发生其他操作。</span><span class="sxs-lookup"><span data-stu-id="14969-111">The first time the users log on, additional operations occur in the background.</span></span> <span data-ttu-id="14969-112">因此，可以降低 Microsoft SQL Server 后端服务器上的性能。</span><span class="sxs-lookup"><span data-stu-id="14969-112">As a result, the performance on the Microsoft SQL Server Back End Server can be degraded.</span></span> <span data-ttu-id="14969-113">建议您的用户，所有运行小测验的日志，然后开始测量结果使用工具之前重新启动客户端。</span><span class="sxs-lookup"><span data-stu-id="14969-113">It's recommended that you run a short test that logs on all of your users, and then restart the clients before you begin to measure results with the tool.</span></span> <span data-ttu-id="14969-114">Skype 业务服务器不支持超过 12 并发用户登录会话 / 秒，但请注意您的服务器可以处理的实际数目取决于您的硬件配置，并且可能低于受支持的值。</span><span class="sxs-lookup"><span data-stu-id="14969-114">Skype for Business Server doesn't support more than 12 concurrent user logon sessions per second, but please be aware the actual number that can be handled by your servers depends on your hardware configuration, and may be lower than the supported value.</span></span>
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="14969-115">我的客户端内存不足运行 ！</span><span class="sxs-lookup"><span data-stu-id="14969-115">My clients are running out of memory!</span></span> <span data-ttu-id="14969-116">应该怎样做？</span><span class="sxs-lookup"><span data-stu-id="14969-116">What should I do?</span></span>

<span data-ttu-id="14969-117">如果客户端运行的内存不足，您应减少每 Skype 业务 Server 前端池记录的用户数。</span><span class="sxs-lookup"><span data-stu-id="14969-117">If clients are running out of memory, you should reduce the number of users logged on per Skype for Business Server Front End pool.</span></span> <span data-ttu-id="14969-118">您还可以选择扩展注销前端池，如果问题是持久。</span><span class="sxs-lookup"><span data-stu-id="14969-118">You can also choose to scale out Front End pools if the problem is persistent.</span></span>
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a><span data-ttu-id="14969-119">可以运行此工具在业务服务器 Skype 本身？</span><span class="sxs-lookup"><span data-stu-id="14969-119">Can I run this tool on a Skype for Business server, itself?</span></span>

<span data-ttu-id="14969-120">不应执行的操作。</span><span class="sxs-lookup"><span data-stu-id="14969-120">You shouldn't do that.</span></span> <span data-ttu-id="14969-121">此方案中不受支持，因为由于二进制不匹配，则可能会失败，也因为的目标是以测量的服务器上的资源消耗。</span><span class="sxs-lookup"><span data-stu-id="14969-121">This scenario isn't supported because it may fail due to a binary mismatch, and also because the goal is to measure resource consumption on the server.</span></span> <span data-ttu-id="14969-122">实际上那里运行该工具将影响服务器性能，并使您的数据和度量值无效。</span><span class="sxs-lookup"><span data-stu-id="14969-122">Actually running the tool there would impact server performance and invalidate your data and measurements.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="14969-123">在虚拟服务器或 Microsoft HYPER-V Server 2008/2012 上是否可以运行 LyncPerfTool.exe？</span><span class="sxs-lookup"><span data-stu-id="14969-123">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="14969-124">您可以是。</span><span class="sxs-lookup"><span data-stu-id="14969-124">Yes you can.</span></span>
  
## <a name="what-does-mpop-mean"></a><span data-ttu-id="14969-125">MPOP 是什么意思？</span><span class="sxs-lookup"><span data-stu-id="14969-125">What does MPOP mean?</span></span>

<span data-ttu-id="14969-126">MPOP 缩短的像是说"多点状态"。</span><span class="sxs-lookup"><span data-stu-id="14969-126">MPOP is a shortened way of saying "multiple points of presence".</span></span> <span data-ttu-id="14969-127">MPOP 旨在模拟其中用户登录到 Skype for Business 2015 客户端从多个计算机或设备的方案。</span><span class="sxs-lookup"><span data-stu-id="14969-127">MPOP is meant to simulate scenarios where users are logged on to Skype for Business 2015 client from multiple machines or devices.</span></span> <span data-ttu-id="14969-128">请注意，在 LyncPerfTool.exe，每个终结点使用的默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="14969-128">Be aware that, in LyncPerfTool.exe, each endpoint uses the default profile.</span></span> <span data-ttu-id="14969-129">换句话说，该配置文件不是两个状态点之间拆分。</span><span class="sxs-lookup"><span data-stu-id="14969-129">In other words, the profile isn't split between two points of presence.</span></span>
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="14969-130">我启动 LyncPerfTool.exe 但不是会变化。</span><span class="sxs-lookup"><span data-stu-id="14969-130">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="14969-131">这是怎么回事？</span><span class="sxs-lookup"><span data-stu-id="14969-131">What's going on?</span></span>

<span data-ttu-id="14969-132">检查以查看在用户连接的服务器上的活动终结点总数计数器。</span><span class="sxs-lookup"><span data-stu-id="14969-132">Check the Total Active Endpoints counter on the servers to see if the users are connecting.</span></span> <span data-ttu-id="14969-133">如果用户不连接，请确认您 Skype 业务服务器 2015年配置。</span><span class="sxs-lookup"><span data-stu-id="14969-133">If the users aren't connecting, verify your Skype for Business Server 2015 configuration.</span></span> <span data-ttu-id="14969-134">问题您看到了通常发生的原因之一服务器名称、 用户前缀或密码不正确。</span><span class="sxs-lookup"><span data-stu-id="14969-134">The issue you're seeing usually occurs because one of server name, user prefix, or password, is incorrect.</span></span> <span data-ttu-id="14969-135">记下外部客户端应指定访问代理服务器和目标值。</span><span class="sxs-lookup"><span data-stu-id="14969-135">Take note that external clients should specify Access Proxy and TargetServer values.</span></span> <span data-ttu-id="14969-136">验证配置文件中的端口号。</span><span class="sxs-lookup"><span data-stu-id="14969-136">Verify the port number in the configuration file.</span></span>
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a><span data-ttu-id="14969-137">如何确保内容正在衡量？</span><span class="sxs-lookup"><span data-stu-id="14969-137">How can I be sure that something is being measured?</span></span>

<span data-ttu-id="14969-138">有 LyncPerfTool 性能计数器来指示用户连接和执行操作，但请确保正在度量操作的最简单方式是以登录到一个具有业务 2015年客户端 Skype 帐户并执行这些操作操作自己。</span><span class="sxs-lookup"><span data-stu-id="14969-138">There are LyncPerfTool performance counters that indicate whether or not users are connecting and performing actions, but the easiest way to make sure actions are being measured is to log on to one of the accounts with a Skype for Business 2015 client and do those actions yourself.</span></span> <span data-ttu-id="14969-139">检查的结果，以确认度量做。</span><span class="sxs-lookup"><span data-stu-id="14969-139">Check the results to confirm measurements were taken.</span></span>
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a><span data-ttu-id="14969-140">我已安装的 Lync Server 2010 容量规划工具和/或 Lync Server 2013 容量规划工具。</span><span class="sxs-lookup"><span data-stu-id="14969-140">I have Lync Server 2010 Capacity Planning Tools and/or Lync Server 2013 Capacity Planning tools installed.</span></span> <span data-ttu-id="14969-141">是的正常？</span><span class="sxs-lookup"><span data-stu-id="14969-141">Is that okay?</span></span>

 <span data-ttu-id="14969-142">这些工具具有互操作性问题 ！</span><span class="sxs-lookup"><span data-stu-id="14969-142">These tools have interoperability issues!</span></span> <span data-ttu-id="14969-143">您必须先卸载所有以前版本的这些工具从业务 Server 2015 压力 Skype 获取有效的数据和性能工具。</span><span class="sxs-lookup"><span data-stu-id="14969-143">You must uninstall all the previous versions of these tools to get valid data from the Skype for Business Server 2015 Stress and Performance tool.</span></span>
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="14969-144">压力和性能工具将设置 CAA 呼叫信息服务器拓扑结构？</span><span class="sxs-lookup"><span data-stu-id="14969-144">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="14969-145">否，工具不会执行此操作。</span><span class="sxs-lookup"><span data-stu-id="14969-145">No, the tools won't do this.</span></span> <span data-ttu-id="14969-146">工具仅创建用户、 联系人和通讯组列表，以模拟用户负载。</span><span class="sxs-lookup"><span data-stu-id="14969-146">The tools only create users, contacts, and distribution lists, to simulate user load.</span></span>
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="14969-147">工具支持的用户的最大号码是什么？</span><span class="sxs-lookup"><span data-stu-id="14969-147">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="14969-148">在测试中，我们已创建 80,000 用户总共和执行测试约 30,000 运行这些工具的用户。</span><span class="sxs-lookup"><span data-stu-id="14969-148">In testing, we've created up to a total of 80,000 users, and executed tests totaling 30,000 users running these tools.</span></span> <span data-ttu-id="14969-149">我们建议最多 120,000 用户，尽管技术限制允许较高的值。</span><span class="sxs-lookup"><span data-stu-id="14969-149">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher values.</span></span> <span data-ttu-id="14969-150">请记住这些值依赖的服务器和您的环境中的硬件。</span><span class="sxs-lookup"><span data-stu-id="14969-150">Remember that these values depend on the server and hardware in your environment.</span></span>
  

