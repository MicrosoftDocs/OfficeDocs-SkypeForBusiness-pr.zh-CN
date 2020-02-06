---
title: Skype for Business Server 2015 的常见问题应力和性能工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Skype for Business 2015 应力和性能工具常见问题（FAQ），用于找出支持哪些工具配置、疑难解答工具问题，并阐明在运行压力和性能工具时可能会看到的 behaviours.
ms.openlocfilehash: 2847ecd54389f64d6961cc72ecb94d87e847b0b0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816181"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="4d24b-103">Skype for Business Server 2015 的常见问题应力和性能工具</span><span class="sxs-lookup"><span data-stu-id="4d24b-103">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="4d24b-104">Skype for Business 2015 应力和性能工具常见问题（FAQ），用于找出支持哪些工具配置、疑难解答工具问题，并阐明在运行压力和性能工具时可能会看到的 behaviours.</span><span class="sxs-lookup"><span data-stu-id="4d24b-104">Skype for Business 2015 Stress and Performance Tool frequently asked questions (FAQ), useful for finding out what tool configurations are supported, troubleshooting tool issues, and clarifying behaviours you may see when running the Stress and Performance tools.</span></span>
  
 <span data-ttu-id="4d24b-105">本常见问题解答介绍了有关 Skype for Business Server 2015 应力和性能工具的一些最常见问题，并且可能会帮助你解决问题和工具配置选择。</span><span class="sxs-lookup"><span data-stu-id="4d24b-105">This FAQ covers some of the most frequently asked questions about the Skype for Business Server 2015 Stress and Performance tool, and may help with troubleshooting and tool configuration choices.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="4d24b-106">是否可以在生产中运行 LyncPerfTool？</span><span class="sxs-lookup"><span data-stu-id="4d24b-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="4d24b-107">建议**不要**这样做。</span><span class="sxs-lookup"><span data-stu-id="4d24b-107">This is **not** recommended.</span></span> <span data-ttu-id="4d24b-108">该工具将影响生产服务器性能、安全性和最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="4d24b-108">The tool would impact your production server performance, security, and the end user experience.</span></span>
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a><span data-ttu-id="4d24b-109">我是首次登录我的用户。</span><span class="sxs-lookup"><span data-stu-id="4d24b-109">I'm logging my users on for the first time.</span></span> <span data-ttu-id="4d24b-110">为什么我的服务器运行的负载很高？</span><span class="sxs-lookup"><span data-stu-id="4d24b-110">Why are my servers running a high load?</span></span>

<span data-ttu-id="4d24b-111">用户首次登录时，会在后台执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="4d24b-111">The first time the users log on, additional operations occur in the background.</span></span> <span data-ttu-id="4d24b-112">因此，Microsoft SQL Server 后端服务器上的性能可能会降级。</span><span class="sxs-lookup"><span data-stu-id="4d24b-112">As a result, the performance on the Microsoft SQL Server Back End Server can be degraded.</span></span> <span data-ttu-id="4d24b-113">建议你先运行一个简短测试，该测试将在你的所有用户上登录，然后重新启动客户端，然后再开始使用该工具测量结果。</span><span class="sxs-lookup"><span data-stu-id="4d24b-113">It's recommended that you run a short test that logs on all of your users, and then restart the clients before you begin to measure results with the tool.</span></span> <span data-ttu-id="4d24b-114">Skype for Business Server 不支持每秒并发用户登录会话的次数超过12个，但请注意，你的服务器可以处理的实际数字取决于你的硬件配置，并且可能低于支持的值。</span><span class="sxs-lookup"><span data-stu-id="4d24b-114">Skype for Business Server doesn't support more than 12 concurrent user logon sessions per second, but please be aware the actual number that can be handled by your servers depends on your hardware configuration, and may be lower than the supported value.</span></span>
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="4d24b-115">我的客户的内存不足！</span><span class="sxs-lookup"><span data-stu-id="4d24b-115">My clients are running out of memory!</span></span> <span data-ttu-id="4d24b-116">我该怎么办？</span><span class="sxs-lookup"><span data-stu-id="4d24b-116">What should I do?</span></span>

<span data-ttu-id="4d24b-117">如果客户端内存不足，您应该减少每个 Skype for business 服务器前端池登录的用户数。</span><span class="sxs-lookup"><span data-stu-id="4d24b-117">If clients are running out of memory, you should reduce the number of users logged on per Skype for Business Server Front End pool.</span></span> <span data-ttu-id="4d24b-118">如果问题持续存在，还可以选择缩小前端池。</span><span class="sxs-lookup"><span data-stu-id="4d24b-118">You can also choose to scale out Front End pools if the problem is persistent.</span></span>
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a><span data-ttu-id="4d24b-119">是否可以在 Skype for Business 服务器上运行此工具？</span><span class="sxs-lookup"><span data-stu-id="4d24b-119">Can I run this tool on a Skype for Business server, itself?</span></span>

<span data-ttu-id="4d24b-120">不应执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4d24b-120">You shouldn't do that.</span></span> <span data-ttu-id="4d24b-121">此方案不受支持，因为它可能会因二进制不匹配而失败，也可能是因为目标是测量服务器上的资源占用。</span><span class="sxs-lookup"><span data-stu-id="4d24b-121">This scenario isn't supported because it may fail due to a binary mismatch, and also because the goal is to measure resource consumption on the server.</span></span> <span data-ttu-id="4d24b-122">实际运行工具会影响服务器性能并使你的数据和度量无效。</span><span class="sxs-lookup"><span data-stu-id="4d24b-122">Actually running the tool there would impact server performance and invalidate your data and measurements.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="4d24b-123">我是否可以在虚拟服务器或 Microsoft Hyper-v Server 2008/2012 上运行 LyncPerfTool？</span><span class="sxs-lookup"><span data-stu-id="4d24b-123">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="4d24b-124">是的，可以。</span><span class="sxs-lookup"><span data-stu-id="4d24b-124">Yes you can.</span></span>
  
## <a name="what-does-mpop-mean"></a><span data-ttu-id="4d24b-125">MPOP 的含义是什么？</span><span class="sxs-lookup"><span data-stu-id="4d24b-125">What does MPOP mean?</span></span>

<span data-ttu-id="4d24b-126">MPOP 是说出 "多个状态点" 的简写方式。</span><span class="sxs-lookup"><span data-stu-id="4d24b-126">MPOP is a shortened way of saying "multiple points of presence".</span></span> <span data-ttu-id="4d24b-127">MPOP 旨在模拟用户从多台计算机或设备登录到 Skype for Business 2015 客户端的方案。</span><span class="sxs-lookup"><span data-stu-id="4d24b-127">MPOP is meant to simulate scenarios where users are logged on to Skype for Business 2015 client from multiple machines or devices.</span></span> <span data-ttu-id="4d24b-128">请注意，在 LyncPerfTool 中，每个终结点都使用默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="4d24b-128">Be aware that, in LyncPerfTool.exe, each endpoint uses the default profile.</span></span> <span data-ttu-id="4d24b-129">换句话说，配置文件不会在两个状态点之间拆分。</span><span class="sxs-lookup"><span data-stu-id="4d24b-129">In other words, the profile isn't split between two points of presence.</span></span>
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="4d24b-130">我启动了 LyncPerfTool，但没有发生任何事情。</span><span class="sxs-lookup"><span data-stu-id="4d24b-130">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="4d24b-131">这是怎么回事？</span><span class="sxs-lookup"><span data-stu-id="4d24b-131">What's going on?</span></span>

<span data-ttu-id="4d24b-132">检查服务器上的 "活动终结点总数" 计数器以查看用户是否连接。</span><span class="sxs-lookup"><span data-stu-id="4d24b-132">Check the Total Active Endpoints counter on the servers to see if the users are connecting.</span></span> <span data-ttu-id="4d24b-133">如果用户未连接，请验证您的 Skype for business Server 2015 配置。</span><span class="sxs-lookup"><span data-stu-id="4d24b-133">If the users aren't connecting, verify your Skype for Business Server 2015 configuration.</span></span> <span data-ttu-id="4d24b-134">由于其中一个服务器名称、用户前缀或密码不正确，因此你所看到的问题通常会出现。</span><span class="sxs-lookup"><span data-stu-id="4d24b-134">The issue you're seeing usually occurs because one of server name, user prefix, or password, is incorrect.</span></span> <span data-ttu-id="4d24b-135">请注意，外部客户端应指定访问代理服务器和 TargetServer 值。</span><span class="sxs-lookup"><span data-stu-id="4d24b-135">Take note that external clients should specify Access Proxy and TargetServer values.</span></span> <span data-ttu-id="4d24b-136">验证配置文件中的端口号。</span><span class="sxs-lookup"><span data-stu-id="4d24b-136">Verify the port number in the configuration file.</span></span>
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a><span data-ttu-id="4d24b-137">如何确定正在测量的内容？</span><span class="sxs-lookup"><span data-stu-id="4d24b-137">How can I be sure that something is being measured?</span></span>

<span data-ttu-id="4d24b-138">有 LyncPerfTool 性能计数器可指示用户是否连接和执行操作，但确保操作的最简单方法是使用 Skype for Business 2015 客户端登录到其中一个帐户，并执行这些操作行动。</span><span class="sxs-lookup"><span data-stu-id="4d24b-138">There are LyncPerfTool performance counters that indicate whether or not users are connecting and performing actions, but the easiest way to make sure actions are being measured is to log on to one of the accounts with a Skype for Business 2015 client and do those actions yourself.</span></span> <span data-ttu-id="4d24b-139">检查结果以确认已采取度量。</span><span class="sxs-lookup"><span data-stu-id="4d24b-139">Check the results to confirm measurements were taken.</span></span>
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a><span data-ttu-id="4d24b-140">我已安装 Lync Server 2010 容量规划工具和/或 Lync Server 2013 容量规划工具。</span><span class="sxs-lookup"><span data-stu-id="4d24b-140">I have Lync Server 2010 Capacity Planning Tools and/or Lync Server 2013 Capacity Planning tools installed.</span></span> <span data-ttu-id="4d24b-141">这好吗？</span><span class="sxs-lookup"><span data-stu-id="4d24b-141">Is that okay?</span></span>

 <span data-ttu-id="4d24b-142">这些工具具有互操作性问题！</span><span class="sxs-lookup"><span data-stu-id="4d24b-142">These tools have interoperability issues!</span></span> <span data-ttu-id="4d24b-143">你必须卸载这些工具的所有早期版本才能从 Skype for Business Server 2015 应力和性能工具获取有效数据。</span><span class="sxs-lookup"><span data-stu-id="4d24b-143">You must uninstall all the previous versions of these tools to get valid data from the Skype for Business Server 2015 Stress and Performance tool.</span></span>
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="4d24b-144">压力和性能工具是否会设置 CAA 呼叫信息服务器拓扑？</span><span class="sxs-lookup"><span data-stu-id="4d24b-144">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="4d24b-145">否，工具不会执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4d24b-145">No, the tools won't do this.</span></span> <span data-ttu-id="4d24b-146">工具仅创建用户、联系人和通讯组列表，以模拟用户负载。</span><span class="sxs-lookup"><span data-stu-id="4d24b-146">The tools only create users, contacts, and distribution lists, to simulate user load.</span></span>
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="4d24b-147">工具支持的最大用户数是多少？</span><span class="sxs-lookup"><span data-stu-id="4d24b-147">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="4d24b-148">在测试中，我们最多可创建80000个用户和执行的测试，这些测试将运行这些工具的30000用户总计。</span><span class="sxs-lookup"><span data-stu-id="4d24b-148">In testing, we've created up to a total of 80,000 users, and executed tests totaling 30,000 users running these tools.</span></span> <span data-ttu-id="4d24b-149">我们建议最多120000用户，尽管技术限制允许使用更高的值。</span><span class="sxs-lookup"><span data-stu-id="4d24b-149">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher values.</span></span> <span data-ttu-id="4d24b-150">请记住，这些值取决于环境中的服务器和硬件。</span><span class="sxs-lookup"><span data-stu-id="4d24b-150">Remember that these values depend on the server and hardware in your environment.</span></span>
  

