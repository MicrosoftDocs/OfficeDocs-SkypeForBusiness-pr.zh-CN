---
title: Lync Server 2013 应力和性能工具常见问题
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffcfbca3a2cf58e4e7b87619bb78dabbe42b16bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="f6d67-102">Lync Server 2013 应力和性能工具常见问题</span><span class="sxs-lookup"><span data-stu-id="f6d67-102">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6d67-103">_**主题上次修改时间:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="f6d67-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="f6d67-104">常见问题</span><span class="sxs-lookup"><span data-stu-id="f6d67-104">Frequently Asked Questions</span></span>

<span data-ttu-id="f6d67-105">下面是一些有关 Lync Server 2013 应力和性能工具的常见问题。</span><span class="sxs-lookup"><span data-stu-id="f6d67-105">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="f6d67-106">是否可以在生产中运行 LyncPerfTool？</span><span class="sxs-lookup"><span data-stu-id="f6d67-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="f6d67-107">我们不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="f6d67-107">We do not recommend this.</span></span> <span data-ttu-id="f6d67-108">此工具将影响服务器性能、安全性和用户体验。</span><span class="sxs-lookup"><span data-stu-id="f6d67-108">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="f6d67-109">我是第一次登录用户。</span><span class="sxs-lookup"><span data-stu-id="f6d67-109">I am logging on my users for the first time.</span></span> <span data-ttu-id="f6d67-110">为什么服务器在如此高的负载中运行？</span><span class="sxs-lookup"><span data-stu-id="f6d67-110">Why are the servers running at such high load?</span></span>

<span data-ttu-id="f6d67-111">用户首次登录时, 将发生其他操作。</span><span class="sxs-lookup"><span data-stu-id="f6d67-111">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="f6d67-112">因此, Microsoft SQL Server 后端服务器上的性能将降级。</span><span class="sxs-lookup"><span data-stu-id="f6d67-112">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="f6d67-113">我们建议你运行一个简短测试, 该测试将在你测量结果之前登录所有用户, 然后重新启动客户端。</span><span class="sxs-lookup"><span data-stu-id="f6d67-113">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="f6d67-114">我们不支持每秒超过12个并发用户登录会话, 但这取决于你的硬件配置。</span><span class="sxs-lookup"><span data-stu-id="f6d67-114">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="f6d67-115">我的客户端内存不足。</span><span class="sxs-lookup"><span data-stu-id="f6d67-115">My clients are running out of memory.</span></span> <span data-ttu-id="f6d67-116">我该怎么办？</span><span class="sxs-lookup"><span data-stu-id="f6d67-116">What should I do?</span></span>

<span data-ttu-id="f6d67-117">如果客户端内存不足, 则需要减少每台计算机的用户数。</span><span class="sxs-lookup"><span data-stu-id="f6d67-117">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="f6d67-118">我的客户始终处于 100% 的 CPU。</span><span class="sxs-lookup"><span data-stu-id="f6d67-118">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="f6d67-119">我该怎么办？</span><span class="sxs-lookup"><span data-stu-id="f6d67-119">What should I do?</span></span>

<span data-ttu-id="f6d67-120">如果您的客户在所有用户登录后都使用非常高的 CPU 运行, 则您需要减少每台计算机的用户数。</span><span class="sxs-lookup"><span data-stu-id="f6d67-120">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="f6d67-121">高 CPU 峰值可接受, 但如果持续, 则需要减少负载。</span><span class="sxs-lookup"><span data-stu-id="f6d67-121">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="f6d67-122">是否可以在服务器上运行该工具？</span><span class="sxs-lookup"><span data-stu-id="f6d67-122">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="f6d67-123">不能。</span><span class="sxs-lookup"><span data-stu-id="f6d67-123">No.</span></span> <span data-ttu-id="f6d67-124">此方案不受支持, 并且可能会由于二进制不匹配而失败。</span><span class="sxs-lookup"><span data-stu-id="f6d67-124">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="f6d67-125">此外, 由于点用于测量服务器上的资源占用, 因此运行工具会使度量变得毫无意义。</span><span class="sxs-lookup"><span data-stu-id="f6d67-125">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="f6d67-126">我是否可以在虚拟服务器或 Microsoft Hyper-v Server 2008/2012 上运行 LyncPerfTool？</span><span class="sxs-lookup"><span data-stu-id="f6d67-126">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="f6d67-127">是。</span><span class="sxs-lookup"><span data-stu-id="f6d67-127">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="f6d67-128">MPOP 的含义是什么？</span><span class="sxs-lookup"><span data-stu-id="f6d67-128">What does MPOP mean?</span></span>

<span data-ttu-id="f6d67-129">MPOP 代表多点状态。</span><span class="sxs-lookup"><span data-stu-id="f6d67-129">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="f6d67-130">它旨在模拟用户从多台计算机登录到 Lync 2013 的情形。</span><span class="sxs-lookup"><span data-stu-id="f6d67-130">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="f6d67-131">请注意, 在 LyncPerfTool 中, 每个终结点使用默认配置文件 (即, 配置文件未在两个状态点之间拆分)。</span><span class="sxs-lookup"><span data-stu-id="f6d67-131">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="f6d67-132">我启动了 LyncPerfTool, 但没有发生任何事情。</span><span class="sxs-lookup"><span data-stu-id="f6d67-132">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="f6d67-133">这是怎么回事？</span><span class="sxs-lookup"><span data-stu-id="f6d67-133">What’s going on?</span></span>

<span data-ttu-id="f6d67-134">检查客户端上的 "活动终结点总数" 计数器以查看用户是否连接。</span><span class="sxs-lookup"><span data-stu-id="f6d67-134">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="f6d67-135">如果用户未连接, 请验证您的 Lync Server 2013 配置。</span><span class="sxs-lookup"><span data-stu-id="f6d67-135">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="f6d67-136">出现此问题的原因通常是服务器名称、用户前缀或密码不正确。</span><span class="sxs-lookup"><span data-stu-id="f6d67-136">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="f6d67-137">请注意, 外部客户端应将访问代理服务器指定为 TargetServer 值。</span><span class="sxs-lookup"><span data-stu-id="f6d67-137">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="f6d67-138">验证配置文件中的端口。</span><span class="sxs-lookup"><span data-stu-id="f6d67-138">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="f6d67-139">如何知道发生了什么情况？</span><span class="sxs-lookup"><span data-stu-id="f6d67-139">How do I know something is happening?</span></span>

<span data-ttu-id="f6d67-140">各种 LyncPerfTool 性能计数器指示用户是否在连接和执行操作。</span><span class="sxs-lookup"><span data-stu-id="f6d67-140">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="f6d67-141">但是, 要检查的一种简单方法是使用 Lync 2013 登录到其中一个帐户, 并执行所需的操作。</span><span class="sxs-lookup"><span data-stu-id="f6d67-141">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="f6d67-142">我已安装实时通信服务器 2007 R2 容量规划工具和/或 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="f6d67-142">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="f6d67-143">是否确定？</span><span class="sxs-lookup"><span data-stu-id="f6d67-143">Is that OK?</span></span>

<span data-ttu-id="f6d67-144">不能。</span><span class="sxs-lookup"><span data-stu-id="f6d67-144">No.</span></span> <span data-ttu-id="f6d67-145">存在互操作性问题, 必须卸载本产品的所有早期版本。</span><span class="sxs-lookup"><span data-stu-id="f6d67-145">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="f6d67-146">压力和性能工具是否会设置 CAA 呼叫信息服务器拓扑？</span><span class="sxs-lookup"><span data-stu-id="f6d67-146">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="f6d67-147">不能。</span><span class="sxs-lookup"><span data-stu-id="f6d67-147">No.</span></span> <span data-ttu-id="f6d67-148">这些工具仅创建用户、联系人和通讯组列表, 并模拟用户负载。</span><span class="sxs-lookup"><span data-stu-id="f6d67-148">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="f6d67-149">工具支持的最大用户数是多少？</span><span class="sxs-lookup"><span data-stu-id="f6d67-149">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="f6d67-150">我们最多可创建80000个用户和执行的测试, 这些测试共30000个用户, 使用这些工具。</span><span class="sxs-lookup"><span data-stu-id="f6d67-150">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="f6d67-151">我们建议最多120000用户, 尽管技术限制允许使用较高的值, 具体取决于可用的客户端和服务器硬件。</span><span class="sxs-lookup"><span data-stu-id="f6d67-151">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

