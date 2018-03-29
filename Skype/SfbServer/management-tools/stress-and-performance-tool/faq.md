---
title: 为业务服务器 2015年的压力和性能工具 Skype 的常见问题解答
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype 业务 2015年压力和性能工具的常见问题 (FAQ)，用于找出支持哪些工具配置、 故障排除工具的问题，以及澄清运行压力和性能工具时可能看到的行为.
ms.openlocfilehash: 730f9620e4aa498df26cc24f3c17ea1bd2ad7d5d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="70514-103">为业务服务器 2015年的压力和性能工具 Skype 的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="70514-103">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="70514-104">Skype 业务 2015年压力和性能工具的常见问题 (FAQ)，用于找出支持哪些工具配置、 故障排除工具的问题，以及澄清运行压力和性能工具时可能看到的行为.</span><span class="sxs-lookup"><span data-stu-id="70514-104">Skype for Business 2015 Stress and Performance Tool frequently asked questions (FAQ), useful for finding out what tool configurations are supported, troubleshooting tool issues, and clarifying behaviours you may see when running the Stress and Performance tools.</span></span>
  
 <span data-ttu-id="70514-105">本常见问题解答介绍的一些有关业务服务器 2015年压力和性能工具 Skype 最常问的问题，并可能帮助进行故障排除和工具配置选择。</span><span class="sxs-lookup"><span data-stu-id="70514-105">This FAQ covers some of the most frequently asked questions about the Skype for Business Server 2015 Stress and Performance tool, and may help with troubleshooting and tool configuration choices.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="70514-106">我可以在生产环境中运行 LyncPerfTool.exe 吗？</span><span class="sxs-lookup"><span data-stu-id="70514-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="70514-107">这**不**推荐。</span><span class="sxs-lookup"><span data-stu-id="70514-107">This is **not** recommended.</span></span> <span data-ttu-id="70514-108">该工具会影响生产服务器的性能、 安全性和最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="70514-108">The tool would impact your production server performance, security, and the end user experience.</span></span>
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a><span data-ttu-id="70514-109">我第一次在登录我的用户。</span><span class="sxs-lookup"><span data-stu-id="70514-109">I'm logging my users on for the first time.</span></span> <span data-ttu-id="70514-110">为什么我的服务器运行的较高负载？</span><span class="sxs-lookup"><span data-stu-id="70514-110">Why are my servers running a high load?</span></span>

<span data-ttu-id="70514-111">第一次用户登录时，在后台发生的附加操作。</span><span class="sxs-lookup"><span data-stu-id="70514-111">The first time the users log on, additional operations occur in the background.</span></span> <span data-ttu-id="70514-112">因此，Microsoft SQL Server 后端服务器上的性能可能会下降。</span><span class="sxs-lookup"><span data-stu-id="70514-112">As a result, the performance on the Microsoft SQL Server Back End Server can be degraded.</span></span> <span data-ttu-id="70514-113">建议您的用户的所有运行记录一个简短的测试，然后重新启动客户端之前就开始衡量工具的结果。</span><span class="sxs-lookup"><span data-stu-id="70514-113">It's recommended that you run a short test that logs on all of your users, and then restart the clients before you begin to measure results with the tool.</span></span> <span data-ttu-id="70514-114">Skype 业务服务器不支持每秒，超过 12 并发用户的登录会话，但请注意您的服务器可以处理的实际数目取决于您的硬件配置，并且可能低于受支持的值。</span><span class="sxs-lookup"><span data-stu-id="70514-114">Skype for Business Server doesn't support more than 12 concurrent user logon sessions per second, but please be aware the actual number that can be handled by your servers depends on your hardware configuration, and may be lower than the supported value.</span></span>
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="70514-115">我的客户正在运行内存不足 ！</span><span class="sxs-lookup"><span data-stu-id="70514-115">My clients are running out of memory!</span></span> <span data-ttu-id="70514-116">我应该做什么？</span><span class="sxs-lookup"><span data-stu-id="70514-116">What should I do?</span></span>

<span data-ttu-id="70514-117">如果客户端运行内存不足的应减少每 Skype 业务服务器前端池在登录的用户数。</span><span class="sxs-lookup"><span data-stu-id="70514-117">If clients are running out of memory, you should reduce the number of users logged on per Skype for Business Server Front End pool.</span></span> <span data-ttu-id="70514-118">您还可以选择扩展出前结束池，如果是持久性的问题。</span><span class="sxs-lookup"><span data-stu-id="70514-118">You can also choose to scale out Front End pools if the problem is persistent.</span></span>
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a><span data-ttu-id="70514-119">可以运行此工具 Skype 业务服务器上本身？</span><span class="sxs-lookup"><span data-stu-id="70514-119">Can I run this tool on a Skype for Business server, itself?</span></span>

<span data-ttu-id="70514-120">您不应该这样做。</span><span class="sxs-lookup"><span data-stu-id="70514-120">You shouldn't do that.</span></span> <span data-ttu-id="70514-121">由于二进制不匹配，则可能会失败，因为不支持这种情况下，还因为目标是测量服务器上的资源消耗。</span><span class="sxs-lookup"><span data-stu-id="70514-121">This scenario isn't supported because it may fail due to a binary mismatch, and also because the goal is to measure resource consumption on the server.</span></span> <span data-ttu-id="70514-122">实际上那里运行该工具会影响服务器的性能，使您的数据和测量结果。</span><span class="sxs-lookup"><span data-stu-id="70514-122">Actually running the tool there would impact server performance and invalidate your data and measurements.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="70514-123">在虚拟服务器上或在 Microsoft Hyper-V 服务器 2008年/2012年是否可以运行 LyncPerfTool.exe？</span><span class="sxs-lookup"><span data-stu-id="70514-123">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="70514-124">是的您可以。</span><span class="sxs-lookup"><span data-stu-id="70514-124">Yes you can.</span></span>
  
## <a name="what-does-mpop-mean"></a><span data-ttu-id="70514-125">MPOP 是什么意思？</span><span class="sxs-lookup"><span data-stu-id="70514-125">What does MPOP mean?</span></span>

<span data-ttu-id="70514-126">MPOP 是存在的缩短的种说法"多个点"。</span><span class="sxs-lookup"><span data-stu-id="70514-126">MPOP is a shortened way of saying "multiple points of presence".</span></span> <span data-ttu-id="70514-127">MPOP 旨在模拟其中用户登录到 Skype 业务 2015年客户端的多个机器或设备的方案。</span><span class="sxs-lookup"><span data-stu-id="70514-127">MPOP is meant to simulate scenarios where users are logged on to Skype for Business 2015 client from multiple machines or devices.</span></span> <span data-ttu-id="70514-128">请注意，LyncPerfTool.exe，在每个终结点使用的默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="70514-128">Be aware that, in LyncPerfTool.exe, each endpoint uses the default profile.</span></span> <span data-ttu-id="70514-129">换句话说，该配置文件不存在的两个点之间拆分。</span><span class="sxs-lookup"><span data-stu-id="70514-129">In other words, the profile isn't split between two points of presence.</span></span>
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="70514-130">我开始 LyncPerfTool.exe，但什么都没有发生。</span><span class="sxs-lookup"><span data-stu-id="70514-130">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="70514-131">这是怎么回事？</span><span class="sxs-lookup"><span data-stu-id="70514-131">What's going on?</span></span>

<span data-ttu-id="70514-132">检查总有效终结点计数器，以查看用户连接的服务器上。</span><span class="sxs-lookup"><span data-stu-id="70514-132">Check the Total Active Endpoints counter on the servers to see if the users are connecting.</span></span> <span data-ttu-id="70514-133">如果用户不能连接，请验证您 Skype 业务服务器 2015年配置。</span><span class="sxs-lookup"><span data-stu-id="70514-133">If the users aren't connecting, verify your Skype for Business Server 2015 configuration.</span></span> <span data-ttu-id="70514-134">因为一个服务器名称、 用户前缀，或密码不正确，通常可以看到的问题出现。</span><span class="sxs-lookup"><span data-stu-id="70514-134">The issue you're seeing usually occurs because one of server name, user prefix, or password, is incorrect.</span></span> <span data-ttu-id="70514-135">请注意，外部客户端应指定访问代理服务器和目标服务器的值。</span><span class="sxs-lookup"><span data-stu-id="70514-135">Take note that external clients should specify Access Proxy and TargetServer values.</span></span> <span data-ttu-id="70514-136">验证配置文件中的端口号。</span><span class="sxs-lookup"><span data-stu-id="70514-136">Verify the port number in the configuration file.</span></span>
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a><span data-ttu-id="70514-137">如何能够确保内容正在衡量？</span><span class="sxs-lookup"><span data-stu-id="70514-137">How can I be sure that something is being measured?</span></span>

<span data-ttu-id="70514-138">有 LyncPerfTool 性能计数器指示用户连接并执行操作，但确保正在测量操作的最简单方法就是登录到其中一个与 Skype 业务 2015年客户端的帐户并执行那些操作您自己。</span><span class="sxs-lookup"><span data-stu-id="70514-138">There are LyncPerfTool performance counters that indicate whether or not users are connecting and performing actions, but the easiest way to make sure actions are being measured is to log on to one of the accounts with a Skype for Business 2015 client and do those actions yourself.</span></span> <span data-ttu-id="70514-139">检查结果确认测量拍摄。</span><span class="sxs-lookup"><span data-stu-id="70514-139">Check the results to confirm measurements were taken.</span></span>
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a><span data-ttu-id="70514-140">我有安装 Lync Server 2010 容量规划工具和/或 Lync 服务器 2013年容量规划工具。</span><span class="sxs-lookup"><span data-stu-id="70514-140">I have Lync Server 2010 Capacity Planning Tools and/or Lync Server 2013 Capacity Planning tools installed.</span></span> <span data-ttu-id="70514-141">是这样可以吗？</span><span class="sxs-lookup"><span data-stu-id="70514-141">Is that okay?</span></span>

 <span data-ttu-id="70514-142">这些工具具有互操作性问题 ！</span><span class="sxs-lookup"><span data-stu-id="70514-142">These tools have interoperability issues!</span></span> <span data-ttu-id="70514-143">您必须卸载这些工具来获得有效的数据从 Skype 业务服务器 2015年压力和性能工具的所有以前版本。</span><span class="sxs-lookup"><span data-stu-id="70514-143">You must uninstall all the previous versions of these tools to get valid data from the Skype for Business Server 2015 Stress and Performance tool.</span></span>
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="70514-144">将压力和性能工具，设置 CAA 调用信息服务器拓扑结构？</span><span class="sxs-lookup"><span data-stu-id="70514-144">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="70514-145">否，这些工具将不会执行此操作。</span><span class="sxs-lookup"><span data-stu-id="70514-145">No, the tools won't do this.</span></span> <span data-ttu-id="70514-146">工具只能创建用户、 联系人和通讯组列表、 要模拟的用户负载。</span><span class="sxs-lookup"><span data-stu-id="70514-146">The tools only create users, contacts, and distribution lists, to simulate user load.</span></span>
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="70514-147">最大的工具支持的用户数是什么？</span><span class="sxs-lookup"><span data-stu-id="70514-147">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="70514-148">在测试中，我们总共可以有 80000 用户，创建并执行总额为 3 万名用户运行这些工具的测试。</span><span class="sxs-lookup"><span data-stu-id="70514-148">In testing, we've created up to a total of 80,000 users, and executed tests totaling 30,000 users running these tools.</span></span> <span data-ttu-id="70514-149">建议最多的 120000 个用户，尽管技术限制允许较高的值。</span><span class="sxs-lookup"><span data-stu-id="70514-149">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher values.</span></span> <span data-ttu-id="70514-150">请记住，这些值取决于服务器和硬件在您的环境中。</span><span class="sxs-lookup"><span data-stu-id="70514-150">Remember that these values depend on the server and hardware in your environment.</span></span>
  

