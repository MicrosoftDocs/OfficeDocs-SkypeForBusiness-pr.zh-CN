---
title: Skype for Business Server 2015 压力和性能工具常见问题解答
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype for Business 2015 Stress and Performance Tool 常见问题 (FAQ) ， useful for finding out what tool configurations are supported， troubleshooting tool issues， and clarifying questions you may see when running the Stress and Performance tools.
ms.openlocfilehash: 4c9a8acca21e4e4bb8f6b6e0a5ff1f68484e6b1c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814962"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="e2233-103">Skype for Business Server 2015 压力和性能工具常见问题解答</span><span class="sxs-lookup"><span data-stu-id="e2233-103">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="e2233-104">Skype for Business 2015 Stress and Performance Tool 常见问题 (FAQ) ， useful for finding out what tool configurations are supported， troubleshooting tool issues， and clarifying questions you may see when running the Stress and Performance tools.</span><span class="sxs-lookup"><span data-stu-id="e2233-104">Skype for Business 2015 Stress and Performance Tool frequently asked questions (FAQ), useful for finding out what tool configurations are supported, troubleshooting tool issues, and clarifying behaviours you may see when running the Stress and Performance tools.</span></span>
  
 <span data-ttu-id="e2233-105">此常见问题解答涵盖有关 Skype for Business Server 2015 Stress and Performance 工具的一些最常见的问题，有助于进行故障排除和工具配置选择。</span><span class="sxs-lookup"><span data-stu-id="e2233-105">This FAQ covers some of the most frequently asked questions about the Skype for Business Server 2015 Stress and Performance tool, and may help with troubleshooting and tool configuration choices.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="e2233-106">能否在生产LyncPerfTool.exe运行？</span><span class="sxs-lookup"><span data-stu-id="e2233-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="e2233-107">不建议 **这样做** 。</span><span class="sxs-lookup"><span data-stu-id="e2233-107">This is **not** recommended.</span></span> <span data-ttu-id="e2233-108">该工具将影响生产服务器的性能、安全性和最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="e2233-108">The tool would impact your production server performance, security, and the end user experience.</span></span>
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a><span data-ttu-id="e2233-109">我第一次登录我的用户。</span><span class="sxs-lookup"><span data-stu-id="e2233-109">I'm logging my users on for the first time.</span></span> <span data-ttu-id="e2233-110">为什么我的服务器运行高负载？</span><span class="sxs-lookup"><span data-stu-id="e2233-110">Why are my servers running a high load?</span></span>

<span data-ttu-id="e2233-111">用户首次登录时，将在后台执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="e2233-111">The first time the users log on, additional operations occur in the background.</span></span> <span data-ttu-id="e2233-112">因此，后端服务器上Microsoft SQL Server性能可能会下降。</span><span class="sxs-lookup"><span data-stu-id="e2233-112">As a result, the performance on the Microsoft SQL Server Back End Server can be degraded.</span></span> <span data-ttu-id="e2233-113">建议您运行一个对所有用户进行登录的简短测试，然后重新启动客户端，然后再开始使用该工具测量结果。</span><span class="sxs-lookup"><span data-stu-id="e2233-113">It's recommended that you run a short test that logs on all of your users, and then restart the clients before you begin to measure results with the tool.</span></span> <span data-ttu-id="e2233-114">Skype for Business Server 每秒支持多于 12 个并发用户登录会话，但请注意，服务器可以处理的实际数量取决于硬件配置，并且可能低于支持的值。</span><span class="sxs-lookup"><span data-stu-id="e2233-114">Skype for Business Server doesn't support more than 12 concurrent user logon sessions per second, but please be aware the actual number that can be handled by your servers depends on your hardware configuration, and may be lower than the supported value.</span></span>
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="e2233-115">我的客户端内存不足！</span><span class="sxs-lookup"><span data-stu-id="e2233-115">My clients are running out of memory!</span></span> <span data-ttu-id="e2233-116">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="e2233-116">What should I do?</span></span>

<span data-ttu-id="e2233-117">如果客户端内存不足，应减少每个 Skype for Business Server 前端池登录的用户数。</span><span class="sxs-lookup"><span data-stu-id="e2233-117">If clients are running out of memory, you should reduce the number of users logged on per Skype for Business Server Front End pool.</span></span> <span data-ttu-id="e2233-118">如果问题持续存在，还可以选择扩展前端池。</span><span class="sxs-lookup"><span data-stu-id="e2233-118">You can also choose to scale out Front End pools if the problem is persistent.</span></span>
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a><span data-ttu-id="e2233-119">能否在 Skype for Business 服务器本身运行此工具？</span><span class="sxs-lookup"><span data-stu-id="e2233-119">Can I run this tool on a Skype for Business server, itself?</span></span>

<span data-ttu-id="e2233-120">你不应这样做。</span><span class="sxs-lookup"><span data-stu-id="e2233-120">You shouldn't do that.</span></span> <span data-ttu-id="e2233-121">此方案不受支持，因为它可能由于二进制不匹配而失败，还因为目标是测量服务器上资源消耗。</span><span class="sxs-lookup"><span data-stu-id="e2233-121">This scenario isn't supported because it may fail due to a binary mismatch, and also because the goal is to measure resource consumption on the server.</span></span> <span data-ttu-id="e2233-122">实际上，在那里运行该工具会影响服务器性能，并且会使你的数据和度量失效。</span><span class="sxs-lookup"><span data-stu-id="e2233-122">Actually running the tool there would impact server performance and invalidate your data and measurements.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="e2233-123">我能否在LyncPerfTool.exe服务器或 Microsoft Hyper-V Server 2008/2012 中运行？</span><span class="sxs-lookup"><span data-stu-id="e2233-123">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="e2233-124">可以。</span><span class="sxs-lookup"><span data-stu-id="e2233-124">Yes you can.</span></span>
  
## <a name="what-does-mpop-mean"></a><span data-ttu-id="e2233-125">MPOP 意味着什么？</span><span class="sxs-lookup"><span data-stu-id="e2233-125">What does MPOP mean?</span></span>

<span data-ttu-id="e2233-126">MPOP 是一种表示"多点状态"的缩短方式。</span><span class="sxs-lookup"><span data-stu-id="e2233-126">MPOP is a shortened way of saying "multiple points of presence".</span></span> <span data-ttu-id="e2233-127">MPOP 旨在模拟用户从多台计算机或设备登录到 Skype for Business 2015 客户端的方案。</span><span class="sxs-lookup"><span data-stu-id="e2233-127">MPOP is meant to simulate scenarios where users are logged on to Skype for Business 2015 client from multiple machines or devices.</span></span> <span data-ttu-id="e2233-128">请注意，在LyncPerfTool.exe，每个终结点都使用默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="e2233-128">Be aware that, in LyncPerfTool.exe, each endpoint uses the default profile.</span></span> <span data-ttu-id="e2233-129">换句话说，配置文件不会在两个状态点之间拆分。</span><span class="sxs-lookup"><span data-stu-id="e2233-129">In other words, the profile isn't split between two points of presence.</span></span>
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="e2233-130">我LyncPerfTool.exe，但没有任何变化。</span><span class="sxs-lookup"><span data-stu-id="e2233-130">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="e2233-131">What's going on?</span><span class="sxs-lookup"><span data-stu-id="e2233-131">What's going on?</span></span>

<span data-ttu-id="e2233-132">检查服务器上总活动终结点计数器，以查看用户是否正在连接。</span><span class="sxs-lookup"><span data-stu-id="e2233-132">Check the Total Active Endpoints counter on the servers to see if the users are connecting.</span></span> <span data-ttu-id="e2233-133">如果用户未连接，请验证 Skype for Business Server 2015 配置。</span><span class="sxs-lookup"><span data-stu-id="e2233-133">If the users aren't connecting, verify your Skype for Business Server 2015 configuration.</span></span> <span data-ttu-id="e2233-134">您看到的问题通常是因为其中一个服务器名称、用户前缀或密码不正确。</span><span class="sxs-lookup"><span data-stu-id="e2233-134">The issue you're seeing usually occurs because one of server name, user prefix, or password, is incorrect.</span></span> <span data-ttu-id="e2233-135">请注意，外部客户端应指定访问代理和 TargetServer 值。</span><span class="sxs-lookup"><span data-stu-id="e2233-135">Take note that external clients should specify Access Proxy and TargetServer values.</span></span> <span data-ttu-id="e2233-136">验证配置文件中的端口号。</span><span class="sxs-lookup"><span data-stu-id="e2233-136">Verify the port number in the configuration file.</span></span>
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a><span data-ttu-id="e2233-137">如何确定正在衡量某些内容？</span><span class="sxs-lookup"><span data-stu-id="e2233-137">How can I be sure that something is being measured?</span></span>

<span data-ttu-id="e2233-138">LyncPerfTool 性能计数器用于指示用户是否正在连接和操作，但确保衡量操作的最简单方法是使用 Skype for Business 2015 客户端登录到其中一个帐户，然后自己执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="e2233-138">There are LyncPerfTool performance counters that indicate whether or not users are connecting and performing actions, but the easiest way to make sure actions are being measured is to log on to one of the accounts with a Skype for Business 2015 client and do those actions yourself.</span></span> <span data-ttu-id="e2233-139">检查结果以确认已进行测量。</span><span class="sxs-lookup"><span data-stu-id="e2233-139">Check the results to confirm measurements were taken.</span></span>
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a><span data-ttu-id="e2233-140">我安装了 Lync Server 2010 容量规划工具和/或 Lync Server 2013 容量规划工具。</span><span class="sxs-lookup"><span data-stu-id="e2233-140">I have Lync Server 2010 Capacity Planning Tools and/or Lync Server 2013 Capacity Planning tools installed.</span></span> <span data-ttu-id="e2233-141">可以吗？</span><span class="sxs-lookup"><span data-stu-id="e2233-141">Is that okay?</span></span>

 <span data-ttu-id="e2233-142">这些工具具有互操作性问题！</span><span class="sxs-lookup"><span data-stu-id="e2233-142">These tools have interoperability issues!</span></span> <span data-ttu-id="e2233-143">必须卸载这些工具的所有以前版本，才能从 Skype for Business Server 2015 压力和性能工具获取有效数据。</span><span class="sxs-lookup"><span data-stu-id="e2233-143">You must uninstall all the previous versions of these tools to get valid data from the Skype for Business Server 2015 Stress and Performance tool.</span></span>
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="e2233-144">压力和性能工具将设置 CAA 呼叫信息服务器拓扑吗？</span><span class="sxs-lookup"><span data-stu-id="e2233-144">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="e2233-145">不，工具不会这样做。</span><span class="sxs-lookup"><span data-stu-id="e2233-145">No, the tools won't do this.</span></span> <span data-ttu-id="e2233-146">这些工具仅创建用户、联系人和通讯组列表，以模拟用户负载。</span><span class="sxs-lookup"><span data-stu-id="e2233-146">The tools only create users, contacts, and distribution lists, to simulate user load.</span></span>
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="e2233-147">工具支持的最大用户数是什么？</span><span class="sxs-lookup"><span data-stu-id="e2233-147">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="e2233-148">在测试中，我们创建了多达 80，000 个用户，并执行了总共 30，000 个用户运行这些工具的测试。</span><span class="sxs-lookup"><span data-stu-id="e2233-148">In testing, we've created up to a total of 80,000 users, and executed tests totaling 30,000 users running these tools.</span></span> <span data-ttu-id="e2233-149">我们建议最多 120，000 个用户，尽管技术限制允许更高的值。</span><span class="sxs-lookup"><span data-stu-id="e2233-149">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher values.</span></span> <span data-ttu-id="e2233-150">请记住，这些值取决于您的环境中的服务器和硬件。</span><span class="sxs-lookup"><span data-stu-id="e2233-150">Remember that these values depend on the server and hardware in your environment.</span></span>
  

