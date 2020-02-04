---
title: Lync Server 2013：安装 Lync Server 2013 管理包
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
ms.openlocfilehash: ffc102eccdbaa941e2691df88899c0cc01348838
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a><span data-ttu-id="6d069-102">安装 Lync Server 2013 管理包</span><span class="sxs-lookup"><span data-stu-id="6d069-102">Installing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d069-103">_**主题上次修改时间：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="6d069-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="6d069-104">System Center Operations Manager 本身能够仅监视 Windows 操作系统的一小部分。</span><span class="sxs-lookup"><span data-stu-id="6d069-104">By itself, System Center Operations Manager has the ability to monitor only a small portion of the Windows operating system.</span></span> <span data-ttu-id="6d069-105">但是，你可以通过安装管理包来扩展 System Center Operations Manager 的功能，该软件规定 System Center Operations Manager 可以监视哪些项目，包括应如何监视这些项目以及如何使用警报触发和报告。</span><span class="sxs-lookup"><span data-stu-id="6d069-105">However, you can extend the capabilities of System Center Operations Manager by installing management packs, software that dictates which items System Center Operations Manager can monitor, including how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="6d069-106">Microsoft Lync Server 2013 包括两个 System Center Operations Manager 管理包，它们提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="6d069-106">Microsoft Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="6d069-107">组件和用户管理包（Microsoft.LS.2013.Monitoring.ComponentAndUser.mp）跟踪事件日志中记录的 Lync Server 问题（由性能计数器注册），或记录在呼叫详细记录（CDR）或体验质量（QoE）中。数据库.</span><span class="sxs-lookup"><span data-stu-id="6d069-107">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="6d069-108">对于严重问题，System Center Operations Manager 可以配置为通过电子邮件、即时消息或短消息服务（SMS）消息通知立即通知管理员。</span><span class="sxs-lookup"><span data-stu-id="6d069-108">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="6d069-109">SMS 是用于将文本消息从一个移动设备发送到另一个移动设备的技术。</span><span class="sxs-lookup"><span data-stu-id="6d069-109">SMS is the technology used to send text messages from one mobile device to another.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d069-110">有关配置 Operations Manager 通知的详细信息，请参阅在<A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>TechNet 库中配置通知。</span><span class="sxs-lookup"><span data-stu-id="6d069-110">For more information on configuring Operations Manager notification, see Configuring Notification in the TechNet Library at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="6d069-111">活动监视包（Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp）主动测试重要的 Lync 服务器组件，如登录到系统、交换即时消息或拨打位于公共交换电话上的电话网络（PSTN）。</span><span class="sxs-lookup"><span data-stu-id="6d069-111">The Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="6d069-112">这些测试通过 Lync Server 合成事务 cmdlet 进行。</span><span class="sxs-lookup"><span data-stu-id="6d069-112">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="6d069-113">例如，**Test-CsIM** cmdlet 用来模拟一对测试用户之间的即时消息对话。</span><span class="sxs-lookup"><span data-stu-id="6d069-113">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="6d069-114">如果此模拟消息对话失败，将生成警报。</span><span class="sxs-lookup"><span data-stu-id="6d069-114">If this simulated messaging conversation fails an alert will be generated.</span></span>

<span data-ttu-id="6d069-115">Lync Server 2013 中包含的两个管理包包含大量增强了与 Microsoft Lync Server 2010 一起使用的管理包。</span><span class="sxs-lookup"><span data-stu-id="6d069-115">The two management packs included with Lync Server 2013 include a large number of enhancements over the management packs used with Microsoft Lync Server 2010.</span></span> <span data-ttu-id="6d069-116">例如，Lync Server 2013 组件管理包不仅限于监视 Lync 服务器本身。</span><span class="sxs-lookup"><span data-stu-id="6d069-116">For example, the Lync Server 2013 Component Management Pack is not limited to monitoring Lync Server itself.</span></span> <span data-ttu-id="6d069-117">除了监视 Lync Server 的事件日志和性能计数器，组件管理包还可以跟踪重要项目的性能以及发出警报，如：</span><span class="sxs-lookup"><span data-stu-id="6d069-117">In addition to monitoring event logs and performance counters for Lync Server, the Component Management pack can also track the performance of, and issue alerts for, crucial items such as:</span></span>

  - <span data-ttu-id="6d069-118">\*\*\*\*   如果 internet 信息服务脱机，将发出 internet 信息服务（IIS）警报。</span><span class="sxs-lookup"><span data-stu-id="6d069-118">**Internet Information Services (IIS)**   Alerts will be issued if Internet Information Services goes offline.</span></span> <span data-ttu-id="6d069-119">这一点很重要，因为 Lync Server web 服务依赖于 IIS。</span><span class="sxs-lookup"><span data-stu-id="6d069-119">This is important, because the Lync Server web services rely on IIS.</span></span>

  - <span data-ttu-id="6d069-120">\*\*\*\*   如果系统资源（如可用内存）开始运行较少，将发出进程使用警报。</span><span class="sxs-lookup"><span data-stu-id="6d069-120">**Process usage**   Alerts will be issued if system resources (such as available memory) begin to run low.</span></span> <span data-ttu-id="6d069-121">即使 Lync 服务器对高系统使用率不负责，也会发出这些警报。</span><span class="sxs-lookup"><span data-stu-id="6d069-121">These alerts will be issued even if Lync Server is not responsible for the high system usage.</span></span>

  - <span data-ttu-id="6d069-122">\*\*\*\*   在威胁到服务器的生存能力的硬件或软件问题时，将发出计算机故障事件警报。</span><span class="sxs-lookup"><span data-stu-id="6d069-122">**Computer failure events**   Alerts will be issued in case of a hardware or software issue that threatens the viability of a server.</span></span> <span data-ttu-id="6d069-123">例如，如果服务器似乎存在遇到硬盘故障的危险，则将通知 Lync 服务器管理员。</span><span class="sxs-lookup"><span data-stu-id="6d069-123">For example, Lync Server administrators will be notified if a server appears to be in danger of experiencing a hard disk failure.</span></span>

<span data-ttu-id="6d069-124">新的管理包还具有增强的报告功能。</span><span class="sxs-lookup"><span data-stu-id="6d069-124">The new management packs also feature enhanced reporting.</span></span> <span data-ttu-id="6d069-125">Lync Server 2013 的新报告包括：</span><span class="sxs-lookup"><span data-stu-id="6d069-125">New reports for Lync Server 2013 include:</span></span>

  - <span data-ttu-id="6d069-126">**端到端方案可用性报告**   此报告详细介绍了关键 Lync 服务器服务（如注册或联机状态）的可用性/正常运行时间。</span><span class="sxs-lookup"><span data-stu-id="6d069-126">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="6d069-127">**容量报告**   使用性能计数器信息，此报告显示系统组件（如内存可用性和处理器使用情况）的趋势。</span><span class="sxs-lookup"><span data-stu-id="6d069-127">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="6d069-128">**组件报告**   此报告列出按 Lync Server 组件分组的顶级警报生成器。</span><span class="sxs-lookup"><span data-stu-id="6d069-128">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="6d069-129">除了这些预定义的报表，Lync Server 2013 的管理包还会自动报告呼叫可靠性（按呼叫详细记录测量）和 QoE 状态（通过质量衡量标准）的警报。</span><span class="sxs-lookup"><span data-stu-id="6d069-129">In addition to these predesigned reports, the management packs for Lync Server 2013 automatically report alerts for both Call Reliability (metrics measured by Call Detail Recording) and QoE states (metrics measured by Quality of Experience).</span></span> <span data-ttu-id="6d069-130">如果已启用 "呼叫详细信息录制"，则可以通过 System Center Operations Manager 控制台完成以下过程来查看呼叫可靠性警报：</span><span class="sxs-lookup"><span data-stu-id="6d069-130">If you have enabled Call Detail Recording, you can review Call Reliability alerts by completing the following procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="6d069-131">展开 "**监视**"，展开 " **Microsoft Lync Server 2013 运行状况**"，展开 "**呼叫可靠性和媒体质量**"，然后单击 "**调用可靠性**"。</span><span class="sxs-lookup"><span data-stu-id="6d069-131">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then click **Call Reliability**.</span></span>

<span data-ttu-id="6d069-132">若要查看体验警报的质量，请从 System Center Operations Manager 控制台完成此过程：</span><span class="sxs-lookup"><span data-stu-id="6d069-132">To view Quality of Experience alerts, complete this procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="6d069-133">展开 "**监视**"，展开 " **Microsoft Lync Server 2013 运行状况**"，展开 "**呼叫可靠性和媒体质量**"，然后展开 "**媒体质量**"。</span><span class="sxs-lookup"><span data-stu-id="6d069-133">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then expand **Media Quality**.</span></span>

<span data-ttu-id="6d069-134">Lync Server 2013 的管理包现在使用计算机级发现，而不是在 Microsoft Lync Server 2010 中使用的集中发现机制。</span><span class="sxs-lookup"><span data-stu-id="6d069-134">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism used in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="6d069-135">这意味着每个 System Center 代理实质上都会发现自己，并报告它是否存在于中央管理服务器。</span><span class="sxs-lookup"><span data-stu-id="6d069-135">This means that each System Center agent essentially discovers itself and reports its existence to the Central Management Server.</span></span> <span data-ttu-id="6d069-136">使用计算机级发现可简化 System Center 基础结构的管理，还允许不同版本的 Lync Server 管理包（例如，lync server 2010 的管理包和 Lync Server 2013 的管理包）同时共存.</span><span class="sxs-lookup"><span data-stu-id="6d069-136">Using machine-level discovery simplifies administration of your System Center infrastructure and also allows different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

