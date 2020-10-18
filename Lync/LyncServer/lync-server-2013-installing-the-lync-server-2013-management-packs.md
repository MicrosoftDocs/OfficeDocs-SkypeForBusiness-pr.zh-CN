---
title: Lync Server 2013：安装 Lync Server 2013 管理包
description: Lync Server 2013：安装 Lync Server 2013 管理包。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbb50146474211c12dbd95801ed2b20f6bbfd8c9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573828"
---
# <a name="installing-the-lync-server-2013-management-packs"></a><span data-ttu-id="779ec-103">安装 Lync Server 2013 管理包</span><span class="sxs-lookup"><span data-stu-id="779ec-103">Installing the Lync Server 2013 management packs</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="779ec-104">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="779ec-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="779ec-105">System Center Operations Manager 本身能够仅监视 Windows 操作系统的一小部分。</span><span class="sxs-lookup"><span data-stu-id="779ec-105">By itself, System Center Operations Manager has the ability to monitor only a small portion of the Windows operating system.</span></span> <span data-ttu-id="779ec-106">但是，可以通过安装管理包来扩展 System Center Operations Manager 的功能，该软件指示 System Center Operations Manager 可以监视的项目，包括应如何监视这些项目以及应如何触发和报告警报。</span><span class="sxs-lookup"><span data-stu-id="779ec-106">However, you can extend the capabilities of System Center Operations Manager by installing management packs, software that dictates which items System Center Operations Manager can monitor, including how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="779ec-107">Microsoft Lync Server 2013 包括两个 System Center Operations Manager 管理包，它们提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="779ec-107">Microsoft Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="779ec-108">组件和用户管理包 (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) 跟踪在事件日志中记录的、由性能计数器注册的 Lync Server 问题，或记录在 (CDR) 的呼叫详细记录中，或在 QoE (数据库的体验质量) 。</span><span class="sxs-lookup"><span data-stu-id="779ec-108">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="779ec-109">对于关键问题，可以将 System Center Operations Manager 配置为通过电子邮件、即时消息或短信服务立即通知管理员 (SMS) 消息传递。</span><span class="sxs-lookup"><span data-stu-id="779ec-109">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="779ec-110">SMS 是一种可用来将文本消息从一个移动设备发送到另一个移动设备的技术。</span><span class="sxs-lookup"><span data-stu-id="779ec-110">SMS is the technology used to send text messages from one mobile device to another.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="779ec-111">有关配置 Operations Manager 通知的详细信息，请参阅 TechNet Library 中的配置通知 <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A> 。</span><span class="sxs-lookup"><span data-stu-id="779ec-111">For more information on configuring Operations Manager notification, see Configuring Notification in the TechNet Library at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="779ec-112">Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) 主动测试关键 Lync Server 组件，例如登录系统、交换即时消息或呼叫位于公用电话交换网 (PSTN) 的电话。</span><span class="sxs-lookup"><span data-stu-id="779ec-112">The Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="779ec-113">这些测试通过使用 Lync Server 综合事务 cmdlet 进行。</span><span class="sxs-lookup"><span data-stu-id="779ec-113">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="779ec-114">例如，**Test-CsIM** cmdlet 可用来模拟一对测试用户之间的即时消息对话。</span><span class="sxs-lookup"><span data-stu-id="779ec-114">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="779ec-115">如果这种模拟的消息对话失败，则会生成一个警报。</span><span class="sxs-lookup"><span data-stu-id="779ec-115">If this simulated messaging conversation fails an alert will be generated.</span></span>

<span data-ttu-id="779ec-116">Lync Server 2013 附带的两个管理包包含大量针对 Microsoft Lync Server 2010 使用的管理包的增强功能。</span><span class="sxs-lookup"><span data-stu-id="779ec-116">The two management packs included with Lync Server 2013 include a large number of enhancements over the management packs used with Microsoft Lync Server 2010.</span></span> <span data-ttu-id="779ec-117">例如，Lync Server 2013 组件管理包并不局限于监视 Lync Server 本身。</span><span class="sxs-lookup"><span data-stu-id="779ec-117">For example, the Lync Server 2013 Component Management Pack is not limited to monitoring Lync Server itself.</span></span> <span data-ttu-id="779ec-118">除了监视 Lync Server 的事件日志和性能计数器，组件管理包还可以跟踪关键项目的性能，并发出警报，如：</span><span class="sxs-lookup"><span data-stu-id="779ec-118">In addition to monitoring event logs and performance counters for Lync Server, the Component Management pack can also track the performance of, and issue alerts for, crucial items such as:</span></span>

  - <span data-ttu-id="779ec-119">\*\*Internet Information Services (IIS) \*\*    如果 Internet 信息服务脱机，将发出警报。</span><span class="sxs-lookup"><span data-stu-id="779ec-119">**Internet Information Services (IIS)**   Alerts will be issued if Internet Information Services goes offline.</span></span> <span data-ttu-id="779ec-120">这一点很重要，因为 Lync Server web 服务依赖于 IIS。</span><span class="sxs-lookup"><span data-stu-id="779ec-120">This is important, because the Lync Server web services rely on IIS.</span></span>

  - <span data-ttu-id="779ec-121">**进程使用率**    如果系统资源 (如可用内存) 开始运行不足，则会发出警报。</span><span class="sxs-lookup"><span data-stu-id="779ec-121">**Process usage**   Alerts will be issued if system resources (such as available memory) begin to run low.</span></span> <span data-ttu-id="779ec-122">即使 Lync Server 不负责高系统使用率，也会发出这些警报。</span><span class="sxs-lookup"><span data-stu-id="779ec-122">These alerts will be issued even if Lync Server is not responsible for the high system usage.</span></span>

  - <span data-ttu-id="779ec-123">**计算机故障事件**    在威胁到服务器的生存能力的硬件或软件出现问题时，将发出警报。</span><span class="sxs-lookup"><span data-stu-id="779ec-123">**Computer failure events**   Alerts will be issued in case of a hardware or software issue that threatens the viability of a server.</span></span> <span data-ttu-id="779ec-124">例如，如果服务器似乎有遇到硬盘故障的危险，则会通知 Lync Server 管理员。</span><span class="sxs-lookup"><span data-stu-id="779ec-124">For example, Lync Server administrators will be notified if a server appears to be in danger of experiencing a hard disk failure.</span></span>

<span data-ttu-id="779ec-125">新管理包的主要功能还包括增强的报告功能。</span><span class="sxs-lookup"><span data-stu-id="779ec-125">The new management packs also feature enhanced reporting.</span></span> <span data-ttu-id="779ec-126">Lync Server 2013 的新报告包括：</span><span class="sxs-lookup"><span data-stu-id="779ec-126">New reports for Lync Server 2013 include:</span></span>

  - <span data-ttu-id="779ec-127">**端到端方案可用性报告**    此报告详细说明了关键 Lync Server 服务（如注册或状态）的可用性/正常运行时间。</span><span class="sxs-lookup"><span data-stu-id="779ec-127">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="779ec-128">**容量报告**    使用性能计数器信息，此报告显示系统组件（如内存可用性和处理器使用率）的趋势。</span><span class="sxs-lookup"><span data-stu-id="779ec-128">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="779ec-129">**组件报告**    此报告列出了按 Lync Server 组件分组的顶部警报生成器。</span><span class="sxs-lookup"><span data-stu-id="779ec-129">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="779ec-130">除了这些预先设计的报告之外，Lync Server 2013 的管理包还会自动报告呼叫可靠性 (指标（按呼叫详细记录) 和 QoE 状态进行度量， (由 "体验质量") 衡量的指标）。</span><span class="sxs-lookup"><span data-stu-id="779ec-130">In addition to these predesigned reports, the management packs for Lync Server 2013 automatically report alerts for both Call Reliability (metrics measured by Call Detail Recording) and QoE states (metrics measured by Quality of Experience).</span></span> <span data-ttu-id="779ec-131">如果已启用呼叫详细信息记录，可以通过 System Center Operations Manager 控制台完成以下过程来查看呼叫可靠性警报：</span><span class="sxs-lookup"><span data-stu-id="779ec-131">If you have enabled Call Detail Recording, you can review Call Reliability alerts by completing the following procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="779ec-132">依次展开“监控”\*\*\*\*、“Microsoft Lync Server 2013 运行状况”\*\*\*\*、“呼叫可靠性和媒体质量”\*\*\*\*，然后单击“呼叫可靠性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="779ec-132">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then click **Call Reliability**.</span></span>

<span data-ttu-id="779ec-133">若要查看 "体验质量" 警报，请从 System Center Operations Manager 控制台完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="779ec-133">To view Quality of Experience alerts, complete this procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="779ec-134">依次展开“监控”\*\*\*\*、“Microsoft Lync Server 2013 运行状况”\*\*\*\*、“呼叫可靠性和媒体质量”\*\*\*\*，然后展开“媒体质量”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="779ec-134">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then expand **Media Quality**.</span></span>

<span data-ttu-id="779ec-135">Lync Server 2013 的管理包现在使用计算机级发现，而不是在 Microsoft Lync Server 2010 中使用的集中发现机制。</span><span class="sxs-lookup"><span data-stu-id="779ec-135">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism used in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="779ec-136">这意味着，每个 System Center 代理实质上都会发现自己并报告它是否存在于中央管理服务器中。</span><span class="sxs-lookup"><span data-stu-id="779ec-136">This means that each System Center agent essentially discovers itself and reports its existence to the Central Management Server.</span></span> <span data-ttu-id="779ec-137">使用计算机级别发现可简化对 System Center 基础结构的管理，还允许不同版本的 Lync Server 管理包 (例如，lync server 2010 的管理包和 Lync Server 2013 的管理包) 可共存。</span><span class="sxs-lookup"><span data-stu-id="779ec-137">Using machine-level discovery simplifies administration of your System Center infrastructure and also allows different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

