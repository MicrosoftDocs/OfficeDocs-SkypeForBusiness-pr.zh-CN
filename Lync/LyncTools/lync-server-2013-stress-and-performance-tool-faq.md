---
title: Lync Server 2013 压力和性能工具常见问题解答
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 445448633bc35b8071455ccd0c8e6ff93c3862b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509209"
---
# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="9cc11-102">Lync Server 2013 压力和性能工具常见问题解答</span><span class="sxs-lookup"><span data-stu-id="9cc11-102">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cc11-103">_**上次修改的主题：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="9cc11-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="9cc11-104">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="9cc11-104">Frequently Asked Questions</span></span>

<span data-ttu-id="9cc11-105">以下是有关 Lync Server 2013 压力和性能工具的常见问题。</span><span class="sxs-lookup"><span data-stu-id="9cc11-105">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="9cc11-106">我可以在生产中运行 LyncPerfTool.exe 吗？</span><span class="sxs-lookup"><span data-stu-id="9cc11-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="9cc11-107">我们不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="9cc11-107">We do not recommend this.</span></span> <span data-ttu-id="9cc11-108">此工具将影响服务器的性能、安全性和用户体验。</span><span class="sxs-lookup"><span data-stu-id="9cc11-108">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="9cc11-109">我是首次登录我的用户。</span><span class="sxs-lookup"><span data-stu-id="9cc11-109">I am logging on my users for the first time.</span></span> <span data-ttu-id="9cc11-110">为什么服务器在如此高的负载中运行？</span><span class="sxs-lookup"><span data-stu-id="9cc11-110">Why are the servers running at such high load?</span></span>

<span data-ttu-id="9cc11-111">用户首次登录时，会发生其他操作。</span><span class="sxs-lookup"><span data-stu-id="9cc11-111">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="9cc11-112">因此，Microsoft SQL Server 后端服务器上的性能将会降级。</span><span class="sxs-lookup"><span data-stu-id="9cc11-112">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="9cc11-113">我们建议您运行一个简短的测试，以在测量结果之前在所有用户上记录日志，然后重新启动客户端。</span><span class="sxs-lookup"><span data-stu-id="9cc11-113">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="9cc11-114">每秒仅支持12个以上的并发用户登录会话，但这取决于您的硬件配置。</span><span class="sxs-lookup"><span data-stu-id="9cc11-114">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="9cc11-115">我的客户端内存不足。</span><span class="sxs-lookup"><span data-stu-id="9cc11-115">My clients are running out of memory.</span></span> <span data-ttu-id="9cc11-116">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="9cc11-116">What should I do?</span></span>

<span data-ttu-id="9cc11-117">如果客户端内存不足，则需要减少每台计算机的用户数。</span><span class="sxs-lookup"><span data-stu-id="9cc11-117">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="9cc11-118">目前，我的客户端是100% 的 CPU。</span><span class="sxs-lookup"><span data-stu-id="9cc11-118">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="9cc11-119">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="9cc11-119">What should I do?</span></span>

<span data-ttu-id="9cc11-120">如果在所有用户登录后，客户端运行的 CPU 非常高，则需要减少每台计算机的用户数。</span><span class="sxs-lookup"><span data-stu-id="9cc11-120">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="9cc11-121">高 CPU 峰值是可接受的，但是如果它是持续的，则需要减少负载。</span><span class="sxs-lookup"><span data-stu-id="9cc11-121">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="9cc11-122">我是否可以在服务器上运行该工具？</span><span class="sxs-lookup"><span data-stu-id="9cc11-122">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="9cc11-123">不正确。</span><span class="sxs-lookup"><span data-stu-id="9cc11-123">No.</span></span> <span data-ttu-id="9cc11-124">此方案不受支持，可能因二进制不匹配而失败。</span><span class="sxs-lookup"><span data-stu-id="9cc11-124">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="9cc11-125">此外，因为点是测量服务器上的资源消耗，所以运行该工具将导致度量无意义。</span><span class="sxs-lookup"><span data-stu-id="9cc11-125">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="9cc11-126">我是否可以在虚拟服务器或 Microsoft Hyper-v Server 2008/2012 上运行 LyncPerfTool.exe？</span><span class="sxs-lookup"><span data-stu-id="9cc11-126">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="9cc11-127">是。</span><span class="sxs-lookup"><span data-stu-id="9cc11-127">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="9cc11-128">MPOP 是什么意思？</span><span class="sxs-lookup"><span data-stu-id="9cc11-128">What does MPOP mean?</span></span>

<span data-ttu-id="9cc11-129">MPOP 代表多点状态。</span><span class="sxs-lookup"><span data-stu-id="9cc11-129">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="9cc11-130">它旨在模拟用户从多台计算机登录到 Lync 2013 的情况。</span><span class="sxs-lookup"><span data-stu-id="9cc11-130">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="9cc11-131">请注意，在 LyncPerfTool.exe 中，每个终结点使用默认配置文件 (也就是说，配置文件不会在两个状态点) 进行拆分。</span><span class="sxs-lookup"><span data-stu-id="9cc11-131">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="9cc11-132">我 LyncPerfTool.exe 启动，但不会发生任何事情。</span><span class="sxs-lookup"><span data-stu-id="9cc11-132">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="9cc11-133">这是怎么回事？</span><span class="sxs-lookup"><span data-stu-id="9cc11-133">What’s going on?</span></span>

<span data-ttu-id="9cc11-134">检查客户端上的活动终结点总数计数器，以查看用户是否正在连接。</span><span class="sxs-lookup"><span data-stu-id="9cc11-134">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="9cc11-135">如果用户未连接，请验证 Lync Server 2013 配置。</span><span class="sxs-lookup"><span data-stu-id="9cc11-135">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="9cc11-136">出现此问题的原因通常是服务器名称、用户前缀或密码不正确。</span><span class="sxs-lookup"><span data-stu-id="9cc11-136">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="9cc11-137">请注意，外部客户端应将访问代理指定为 TargetServer 值。</span><span class="sxs-lookup"><span data-stu-id="9cc11-137">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="9cc11-138">验证配置文件中的端口。</span><span class="sxs-lookup"><span data-stu-id="9cc11-138">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="9cc11-139">我如何知道发生了什么情况？</span><span class="sxs-lookup"><span data-stu-id="9cc11-139">How do I know something is happening?</span></span>

<span data-ttu-id="9cc11-140">各种 LyncPerfTool 性能计数器指示用户是否正在连接和执行操作。</span><span class="sxs-lookup"><span data-stu-id="9cc11-140">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="9cc11-141">但是，要进行检查的一种简单方法是使用 Lync 2013 登录帐户之一并执行所需的操作。</span><span class="sxs-lookup"><span data-stu-id="9cc11-141">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="9cc11-142">我安装了实时通信服务器 2007 R2 容量规划工具和/或 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="9cc11-142">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="9cc11-143">这是正常的吗？</span><span class="sxs-lookup"><span data-stu-id="9cc11-143">Is that OK?</span></span>

<span data-ttu-id="9cc11-144">不正确。</span><span class="sxs-lookup"><span data-stu-id="9cc11-144">No.</span></span> <span data-ttu-id="9cc11-145">存在互操作性问题，您必须卸载此产品的所有早期版本。</span><span class="sxs-lookup"><span data-stu-id="9cc11-145">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="9cc11-146">压力和性能工具是否会设置 CAA 呼叫信息服务器拓扑？</span><span class="sxs-lookup"><span data-stu-id="9cc11-146">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="9cc11-147">不正确。</span><span class="sxs-lookup"><span data-stu-id="9cc11-147">No.</span></span> <span data-ttu-id="9cc11-148">工具只创建用户、联系人和通讯组列表，并模拟用户负载。</span><span class="sxs-lookup"><span data-stu-id="9cc11-148">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="9cc11-149">工具支持的最大用户数是多少？</span><span class="sxs-lookup"><span data-stu-id="9cc11-149">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="9cc11-150">我们总共创建了80000个用户并执行了使用这些工具总计30000个用户的测试。</span><span class="sxs-lookup"><span data-stu-id="9cc11-150">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="9cc11-151">我们建议最多为120000个用户，尽管技术限制允许更高的价值，具体取决于可用的客户端和服务器硬件。</span><span class="sxs-lookup"><span data-stu-id="9cc11-151">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

