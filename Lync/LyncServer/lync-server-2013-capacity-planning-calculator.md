---
title: Lync Server 2013 容量规划计算器
description: Lync Server 2013 容量规划计算器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f78019c98cf280f38249ac52cd063cede5319af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565138"
---
# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a><span data-ttu-id="07ae4-103">使用 Lync Server 2013 的容量规划计算器</span><span class="sxs-lookup"><span data-stu-id="07ae4-103">Using the capacity planning calculator for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07ae4-104">_**上次修改的主题：** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="07ae4-104">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="07ae4-105">Microsoft® Lync™ Server 2013 容量规划计算器可从下载 <https://www.microsoft.com/download/details.aspx?id=36828> 。</span><span class="sxs-lookup"><span data-stu-id="07ae4-105">The Microsoft® Lync™ Server 2013 capacity planning calculator is available for download at <https://www.microsoft.com/download/details.aspx?id=36828>.</span></span> <span data-ttu-id="07ae4-106">它旨在帮助您根据组织中启用的用户数和通信形式来确定服务器要求。</span><span class="sxs-lookup"><span data-stu-id="07ae4-106">It is designed to assist you in determining server requirements based on numbers of users and communication modalities that are enabled at your organization.</span></span> <span data-ttu-id="07ae4-107">输入您的组织的配置文件，计算器将提供可帮助您规划拓扑的建议。</span><span class="sxs-lookup"><span data-stu-id="07ae4-107">You enter your organization’s profile, and the calculator provides recommendations that help you plan your topology.</span></span>

<span data-ttu-id="07ae4-108">计算器创建的建议仅用于规划目的。</span><span class="sxs-lookup"><span data-stu-id="07ae4-108">The recommendations created by the calculator are for planning purposes only.</span></span> <span data-ttu-id="07ae4-109">若要确保已正确设置 Lync Server 2013，需要实际的负载模拟。</span><span class="sxs-lookup"><span data-stu-id="07ae4-109">Actual load simulation is required to ensure that Lync Server 2013 is adequately provisioned.</span></span> <span data-ttu-id="07ae4-110">若要在模拟负载下执行压力测试，请使用 [Lync Server 2013 压力和性能工具](https://go.microsoft.com/fwlink/?linkid=282724)。</span><span class="sxs-lookup"><span data-stu-id="07ae4-110">To perform stress testing under a simulated load, use the [Lync Server 2013 Stress and Performance Tool](https://go.microsoft.com/fwlink/?linkid=282724).</span></span>

<span data-ttu-id="07ae4-111">在确定您要为用户启用的用户配置文件和形式之后，可以使用计算器来规划所需的服务器、内存和带宽的数量。</span><span class="sxs-lookup"><span data-stu-id="07ae4-111">After you have determined your user profile and the modalities that you want to enable for your users, it is time to use the calculator to plan the number of servers, memory, and bandwidth that you need.</span></span> <span data-ttu-id="07ae4-112">此版本的计算器不会提供磁盘 i/o 要求指南。</span><span class="sxs-lookup"><span data-stu-id="07ae4-112">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>

<span data-ttu-id="07ae4-113">此计算器是对 [Microsoft Lync server](https://go.microsoft.com/fwlink/?linkid=282725) 和 [microsoft lync server](lync-server-2013-planning.md)的补充。</span><span class="sxs-lookup"><span data-stu-id="07ae4-113">This calculator complements the [Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725) and [Microsoft Lync Server](lync-server-2013-planning.md).</span></span> <span data-ttu-id="07ae4-114">在您查看指南并使用规划工具创建推荐的拓扑之后，使用计算器。</span><span class="sxs-lookup"><span data-stu-id="07ae4-114">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>

<span data-ttu-id="07ae4-115">如果您具有有关特定用户配置文件的准确、详细信息，则可以从计算器中获益最多。</span><span class="sxs-lookup"><span data-stu-id="07ae4-115">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="07ae4-116">例如，启用了语音的用户的百分比、每个用户每小时平均呼叫数、呼叫持续时间以及会议中并发用户的百分比可能会对服务器的要求产生巨大的影响。</span><span class="sxs-lookup"><span data-stu-id="07ae4-116">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="07ae4-117">计算器所创建的建议的准确性取决于您提供的信息的准确性。</span><span class="sxs-lookup"><span data-stu-id="07ae4-117">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>

<div>

## <a name="using-the-capacity-calculator"></a><span data-ttu-id="07ae4-118">使用容量计算器</span><span class="sxs-lookup"><span data-stu-id="07ae4-118">Using the Capacity Calculator</span></span>

<span data-ttu-id="07ae4-119">计算器是 Microsoft Excel®电子表格。</span><span class="sxs-lookup"><span data-stu-id="07ae4-119">The calculator is a Microsoft Excel® spreadsheet.</span></span> <span data-ttu-id="07ae4-120">橙色的单元格供您输入。</span><span class="sxs-lookup"><span data-stu-id="07ae4-120">Orange-colored cells are for input from you.</span></span> <span data-ttu-id="07ae4-121">默认值是在一个池中 (80000 个用户) 中输入的，但您可以根据组织的需要更改这些值。</span><span class="sxs-lookup"><span data-stu-id="07ae4-121">Default values are entered (80,000 users in one pool with twelve Front End Servers), but you can change these values according to your organization’s needs.</span></span>

<span data-ttu-id="07ae4-122">使用模型包含以下部分。</span><span class="sxs-lookup"><span data-stu-id="07ae4-122">The usage model contains the following sections.</span></span> <span data-ttu-id="07ae4-123">若要计算您的容量需求，请按如下所述输入数据：</span><span class="sxs-lookup"><span data-stu-id="07ae4-123">To calculate your capacity requirements, enter data as described:</span></span>

<span data-ttu-id="07ae4-124">**即时消息和状态**</span><span class="sxs-lookup"><span data-stu-id="07ae4-124">**Instant Messaging and Presence**</span></span>

  - <span data-ttu-id="07ae4-125">在 "用户数" 下，键入将并发登录的用户数。</span><span class="sxs-lookup"><span data-stu-id="07ae4-125">Under Number of Users, type the number of users who will be concurrently signed in.</span></span> <span data-ttu-id="07ae4-126">此数字通常为已设置的用户总数的80%。</span><span class="sxs-lookup"><span data-stu-id="07ae4-126">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="07ae4-127">在大多数情况下，将对100% 的并发用户启用 IM 和状态。</span><span class="sxs-lookup"><span data-stu-id="07ae4-127">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="07ae4-128">默认值为80000。</span><span class="sxs-lookup"><span data-stu-id="07ae4-128">The default is 80,000.</span></span>

  - <span data-ttu-id="07ae4-129">联系人列表中的平均联系人数表示用于验证您的系统要求的联系人数量。</span><span class="sxs-lookup"><span data-stu-id="07ae4-129">Average number of contacts in Contact list indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="07ae4-130">此数字不可更改。</span><span class="sxs-lookup"><span data-stu-id="07ae4-130">This number is not changeable.</span></span>

<span data-ttu-id="07ae4-131">**企业语音**</span><span class="sxs-lookup"><span data-stu-id="07ae4-131">**Enterprise Voice**</span></span>

  - <span data-ttu-id="07ae4-132">在 "启用企业语音的用户" 中，键入启用了企业语音的用户的百分比。</span><span class="sxs-lookup"><span data-stu-id="07ae4-132">In Users enabled for Enterprise Voice, type the percentage of your users who are enabled for Enterprise Voice.</span></span> <span data-ttu-id="07ae4-133">默认值为60%。</span><span class="sxs-lookup"><span data-stu-id="07ae4-133">The default is 60%.</span></span>

  - <span data-ttu-id="07ae4-134">在 "每个用户每小时平均呼叫数" (峰值) 中，键入您预计在高峰负载期间平均用户参与的每小时的呼叫数。</span><span class="sxs-lookup"><span data-stu-id="07ae4-134">In Average number of calls per user per hour (peak), type the number of calls per hour that you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="07ae4-135">默认值为 4。</span><span class="sxs-lookup"><span data-stu-id="07ae4-135">The default is 4.</span></span>

  - <span data-ttu-id="07ae4-136">在 "使用媒体旁路的呼叫百分比" 中，键入用户发出的将绕过中介服务器的呼叫百分比。</span><span class="sxs-lookup"><span data-stu-id="07ae4-136">In Percentage of calls that use media bypass, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="07ae4-137">默认值为65%。</span><span class="sxs-lookup"><span data-stu-id="07ae4-137">The default is 65%.</span></span>

  - <span data-ttu-id="07ae4-138">在与 UC-PSTN 呼叫相关的语音用户的百分比中，键入组织的呼叫的百分比，即 UC-PSTN 电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="07ae4-138">In Percentage of voice users involved in UC-PSTN calls, type the percentage of your organization’s calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="07ae4-139">默认值为60%</span><span class="sxs-lookup"><span data-stu-id="07ae4-139">The default is 60%</span></span>

  - <span data-ttu-id="07ae4-140">在 UC-UC 呼叫中涉及的语音用户的百分比显示为企业语音启用的、仅对 UC UC 呼叫启用的用户的百分比。</span><span class="sxs-lookup"><span data-stu-id="07ae4-140">In Percentage of voice users involved in UC-UC calls shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="07ae4-141">根据为 UC-PSTN 呼叫启用的语音用户百分比输入的内容计算此数字。</span><span class="sxs-lookup"><span data-stu-id="07ae4-141">This number is calculated based on what you input for Percentage of voice users enabled for UC-PSTN calls.</span></span>

<span data-ttu-id="07ae4-142">**会议**</span><span class="sxs-lookup"><span data-stu-id="07ae4-142">**Conferencing**</span></span>

  - <span data-ttu-id="07ae4-143">在 "并发会议的用户百分比" 中，键入将并发参与会议的用户的百分比。</span><span class="sxs-lookup"><span data-stu-id="07ae4-143">In Percentage of users in concurrent conferences, type the percentage of users who will be concurrently participating in conferences.</span></span> <span data-ttu-id="07ae4-144">默认值为5%。</span><span class="sxs-lookup"><span data-stu-id="07ae4-144">The default is 5%.</span></span>

  - <span data-ttu-id="07ae4-145">在 "仅限组 IM 的会议百分比 (无语音) " 中，键入会议将仅涉及即时消息的会议的百分比，否则为  。也就是说，不包含音频组件。</span><span class="sxs-lookup"><span data-stu-id="07ae4-145">In Percentage of conferences with group IM only (no voice), type the percentage of conferences whose conferences will involve instant messaging only; that is, that do not include an audio component.</span></span> <span data-ttu-id="07ae4-146">默认值为10%</span><span class="sxs-lookup"><span data-stu-id="07ae4-146">The default is 10%</span></span>

  - <span data-ttu-id="07ae4-147">在使用电话拨入式会议的用户百分比中，键入将使用电话拨入式会议的会议中的并发参与者的百分比。</span><span class="sxs-lookup"><span data-stu-id="07ae4-147">In Percentage of users using dial-in conferencing, type the percentage of concurrent participants in conferences who will be using dial-in conferencing.</span></span> <span data-ttu-id="07ae4-148">默认值为15%。</span><span class="sxs-lookup"><span data-stu-id="07ae4-148">The default is 15%.</span></span>

  - <span data-ttu-id="07ae4-149">在 "使用语音的会议百分比" 中，键入将包含音频组件的会议所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="07ae4-149">In Percentage of conferences using voice, type the percentage of conferences that will include an audio component.</span></span>
    
      - <span data-ttu-id="07ae4-150">如果20% 的语音会议也将包含常规视频，请选中 "包含视频 (无多视图) " 复选框。</span><span class="sxs-lookup"><span data-stu-id="07ae4-150">If 20% of your voice conferences will also include regular video, select the Including video (no Multi View) check box.</span></span>
    
      - <span data-ttu-id="07ae4-151">如果20% 的会议也将包含多视图视频，请选中 "包含多个视图" 复选框。</span><span class="sxs-lookup"><span data-stu-id="07ae4-151">If 20% of your conferences will also include Multi-View video, select the Including Multi View check box.</span></span>
    
      - <span data-ttu-id="07ae4-152">如果50% 的语音会议也将包含应用程序共享，请选中 "包括应用程序共享" 复选框。</span><span class="sxs-lookup"><span data-stu-id="07ae4-152">If 50% of your voice conferences will also include application sharing, select the Including application sharing check box.</span></span>
    
      - <span data-ttu-id="07ae4-153">如果20% 的语音会议包括数据上载（如 Microsoft PowerPoint®演示文稿），请选中 "包括 web 会议" 复选框。</span><span class="sxs-lookup"><span data-stu-id="07ae4-153">If 20% of your voice conferences include data uploads, such as Microsoft PowerPoint® presentations, select the Including web conferencing check box.</span></span>

<span data-ttu-id="07ae4-154">**移动性**</span><span class="sxs-lookup"><span data-stu-id="07ae4-154">**Mobility**</span></span>

  - <span data-ttu-id="07ae4-155">在 "已启用移动性的用户百分比" 中，键入将启用使用移动设备连接到 Lync Server 的用户的百分比。</span><span class="sxs-lookup"><span data-stu-id="07ae4-155">In Percentage of users enabled for Mobility, type the percentage of your users who will be enabled to connect to Lync Server using mobile devices.</span></span> <span data-ttu-id="07ae4-156">默认值为40%。</span><span class="sxs-lookup"><span data-stu-id="07ae4-156">The default is 40%.</span></span>

<span data-ttu-id="07ae4-157">输入所有必要的信息后，容量计算器估计您的要求。</span><span class="sxs-lookup"><span data-stu-id="07ae4-157">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="07ae4-158">黄色单元格显示基于 Lync Server 2013 性能实验室中执行的测试的 CPU、内存和带宽要求的计算值。</span><span class="sxs-lookup"><span data-stu-id="07ae4-158">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Lync Server 2013 performance labs.</span></span> <span data-ttu-id="07ae4-159">这些数字作为指南提供，并不是每个单独的变体都经过测试和验证。</span><span class="sxs-lookup"><span data-stu-id="07ae4-159">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="07ae4-160">将计算以下值：</span><span class="sxs-lookup"><span data-stu-id="07ae4-160">The following values are calculated:</span></span>

  - <span data-ttu-id="07ae4-161">前端 CPU：如果整个负载与 Microsoft 测试中使用的服务器具有相同规范的一台前端服务器的处理，则为 CPU 使用率的百分比。</span><span class="sxs-lookup"><span data-stu-id="07ae4-161">Front End CPU: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in Microsoft testing.</span></span>

  - <span data-ttu-id="07ae4-162">网络（Mbps）：带宽要求的单位为每秒 (Mbps) 对应的工作负载。</span><span class="sxs-lookup"><span data-stu-id="07ae4-162">Network in Mbps: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>

  - <span data-ttu-id="07ae4-163">内存（GB）：对应工作负荷的 gb (GB) 所需的内存。</span><span class="sxs-lookup"><span data-stu-id="07ae4-163">Memory in GB: Memory required in gigabytes (GB) for the corresponding workload.</span></span>

<span data-ttu-id="07ae4-164">绿色单元格显示有关您输入的使用情况模型的建议。</span><span class="sxs-lookup"><span data-stu-id="07ae4-164">The green cells show recommendations for the usage model that you entered.</span></span>

  - <span data-ttu-id="07ae4-165">前端服务器总数：所需的物理服务器数取决于运行 Lync Server 2013 的专用服务器和双处理器，hex-core，含2260兆周期。</span><span class="sxs-lookup"><span data-stu-id="07ae4-165">Total Front End Servers: The number of physical servers required are based on dedicated servers running Lync Server 2013 with dual processor, hex-core, with 2,260 megacycles.</span></span>

  - <span data-ttu-id="07ae4-166">请注意，建议启用超线程，并已证明可提高支持音频/视频的服务器的性能。</span><span class="sxs-lookup"><span data-stu-id="07ae4-166">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>

  - <span data-ttu-id="07ae4-167">边缘服务器：根据所有并发用户通过边缘服务器通信时所需的边缘服务器的数量。</span><span class="sxs-lookup"><span data-stu-id="07ae4-167">Edge Servers: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="07ae4-168">计算器中不能更改此百分比。</span><span class="sxs-lookup"><span data-stu-id="07ae4-168">This percentage cannot be changed in the calculator.</span></span>

  - <span data-ttu-id="07ae4-169">存档/呼叫详细记录/高级服务存储：存档或监控功能所需的存储数量（如果在组织中已启用）。</span><span class="sxs-lookup"><span data-stu-id="07ae4-169">Archiving/Call Detail Recording/Quality of Experience services Store: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>

  - <span data-ttu-id="07ae4-170">需要 (池必需的后端数据库服务器) ：支持所选工作负荷所需的后端数据库服务器的数量。</span><span class="sxs-lookup"><span data-stu-id="07ae4-170">Back End Database Server Required (Pools Required): The number of back-end database servers required to support the selected workload.</span></span>

<span data-ttu-id="07ae4-171">此外，在前端服务器总数的第一行中，提供了有关服务器和网络上的负载的更多信息，用于组合所有计划的工作负载。</span><span class="sxs-lookup"><span data-stu-id="07ae4-171">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>

  - <span data-ttu-id="07ae4-172">平均 CPU 负载：每个前端服务器的平均 CPU 使用率。</span><span class="sxs-lookup"><span data-stu-id="07ae4-172">Average CPU Load: The average CPU usage per Front End server.</span></span>

  - <span data-ttu-id="07ae4-173">网络（以 Mbps 为单位）：支持所需的带宽分配以支持您输入的使用模式。</span><span class="sxs-lookup"><span data-stu-id="07ae4-173">Network in Mbps: The required bandwidth allocation to support the usage model that you entered.</span></span>

  - <span data-ttu-id="07ae4-174">内存（GB）：每个前端服务器所需的内存（以 gb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="07ae4-174">Memory in GB: Memory, in gigabytes, required for each Front End server.</span></span>

</div>

<div>

## <a name="adjusting-for-your-processors"></a><span data-ttu-id="07ae4-175">针对处理器进行调整</span><span class="sxs-lookup"><span data-stu-id="07ae4-175">Adjusting For Your Processors</span></span>

<span data-ttu-id="07ae4-176">电子表格中的所有 CPU 使用情况图都假定每台服务器都有双处理器、hex-core、2.26 GHz、至少 32 GB 的内存以及8个或更多个具有至少 72 GB 可用磁盘空间的 10000 RPM 硬盘。</span><span class="sxs-lookup"><span data-stu-id="07ae4-176">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>

<span data-ttu-id="07ae4-177">如果你的服务器具有不同的处理器，则可以调整这些数字以匹配你的硬件。</span><span class="sxs-lookup"><span data-stu-id="07ae4-177">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

