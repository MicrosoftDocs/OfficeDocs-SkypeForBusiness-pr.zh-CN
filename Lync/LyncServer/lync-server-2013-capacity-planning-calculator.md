---
title: Lync Server 2013 容量规划计算器
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
ms.openlocfilehash: 26abf069d7c1686fe8abb804d6de4508ba6333fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a><span data-ttu-id="2b4d9-102">使用 Lync Server 2013 的容量计划计算器</span><span class="sxs-lookup"><span data-stu-id="2b4d9-102">Using the capacity planning calculator for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b4d9-103">_**主题上次修改时间：** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="2b4d9-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="2b4d9-104">可通过下载 Microsoft® Lync™ Server 2013 容量规划计算器<http://www.microsoft.com/en-us/download/details.aspx?id=36828>。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-104">The Microsoft® Lync™ Server 2013 capacity planning calculator is available for download at <http://www.microsoft.com/en-us/download/details.aspx?id=36828>.</span></span> <span data-ttu-id="2b4d9-105">它旨在帮助你根据你的组织中启用的用户数和通信形式来确定服务器要求。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-105">It is designed to assist you in determining server requirements based on numbers of users and communication modalities that are enabled at your organization.</span></span> <span data-ttu-id="2b4d9-106">输入你的组织的配置文件，计算器将提供帮助你规划拓扑的建议。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-106">You enter your organization’s profile, and the calculator provides recommendations that help you plan your topology.</span></span>

<span data-ttu-id="2b4d9-107">计算器创建的建议仅供规划之用。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-107">The recommendations created by the calculator are for planning purposes only.</span></span> <span data-ttu-id="2b4d9-108">要确保已充分设置 Lync Server 2013，需要实际的负载模拟。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-108">Actual load simulation is required to ensure that Lync Server 2013 is adequately provisioned.</span></span> <span data-ttu-id="2b4d9-109">若要在模拟负载下执行压力测试，请使用[Lync Server 2013 应力和性能工具](http://go.microsoft.com/fwlink/?linkid=282724)。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-109">To perform stress testing under a simulated load, use the [Lync Server 2013 Stress and Performance Tool](http://go.microsoft.com/fwlink/?linkid=282724).</span></span>

<span data-ttu-id="2b4d9-110">确定要为用户启用的用户配置文件和形式后，可以使用计算器来计划所需的服务器、内存和带宽的数量。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-110">After you have determined your user profile and the modalities that you want to enable for your users, it is time to use the calculator to plan the number of servers, memory, and bandwidth that you need.</span></span> <span data-ttu-id="2b4d9-111">此版本的计算器不针对磁盘 I/O 要求提供指导。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-111">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>

<span data-ttu-id="2b4d9-112">此计算器补充[Microsoft Lync server](http://go.microsoft.com/fwlink/?linkid=282725)和[microsoft lync server](lync-server-2013-planning.md)。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-112">This calculator complements the [Microsoft Lync Server](http://go.microsoft.com/fwlink/?linkid=282725) and [Microsoft Lync Server](lync-server-2013-planning.md).</span></span> <span data-ttu-id="2b4d9-113">请在阅读指南并使用规划工具创建建议的拓扑之后使用计算器。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-113">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>

<span data-ttu-id="2b4d9-p105">如果您拥有有关您的特定用户概况的准确、详细的信息，则可以充分享受计算器带来的好处。例如，启用语音的用户的百分比、每个用户每小时的平均呼叫、呼叫持续时间以及会议中的并发用户百分比可能会对服务器要求造成巨大差异。计算器创建的建议的准确性取决于您提供的信息的准确性。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-p105">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile. For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements. The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>

<div>

## <a name="using-the-capacity-calculator"></a><span data-ttu-id="2b4d9-117">使用容量计算器</span><span class="sxs-lookup"><span data-stu-id="2b4d9-117">Using the Capacity Calculator</span></span>

<span data-ttu-id="2b4d9-118">计算器是 Microsoft Excel®电子表格。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-118">The calculator is a Microsoft Excel® spreadsheet.</span></span> <span data-ttu-id="2b4d9-119">橙色的单元格用于输入。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-119">Orange-colored cells are for input from you.</span></span> <span data-ttu-id="2b4d9-120">输入默认值（在一个池中有十二个前端服务器的80000用户），但您可以根据组织的需要更改这些值。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-120">Default values are entered (80,000 users in one pool with twelve Front End Servers), but you can change these values according to your organization’s needs.</span></span>

<span data-ttu-id="2b4d9-121">使用模型包含以下部分。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-121">The usage model contains the following sections.</span></span> <span data-ttu-id="2b4d9-122">若要计算容量要求，请按如下所述输入数据：</span><span class="sxs-lookup"><span data-stu-id="2b4d9-122">To calculate your capacity requirements, enter data as described:</span></span>

<span data-ttu-id="2b4d9-123">**即时消息和状态**</span><span class="sxs-lookup"><span data-stu-id="2b4d9-123">**Instant Messaging and Presence**</span></span>

  - <span data-ttu-id="2b4d9-124">在 "用户数" 下，键入将同时登录的用户数。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-124">Under Number of Users, type the number of users who will be concurrently signed in.</span></span> <span data-ttu-id="2b4d9-125">此数目通常是已设置的用户总数的 80%。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-125">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="2b4d9-126">在大多数情况下，将对所有并发用户启用 IM 和状态。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-126">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="2b4d9-127">默认值为 80,000。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-127">The default is 80,000.</span></span>

  - <span data-ttu-id="2b4d9-128">联系人列表中的平均联系人数表示我们用于验证你的系统要求的联系人数。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-128">Average number of contacts in Contact list indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="2b4d9-129">此号码不可更改。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-129">This number is not changeable.</span></span>

<span data-ttu-id="2b4d9-130">**企业语音**</span><span class="sxs-lookup"><span data-stu-id="2b4d9-130">**Enterprise Voice**</span></span>

  - <span data-ttu-id="2b4d9-131">在 "已启用企业语音的用户" 中，键入已启用企业语音的用户的百分比。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-131">In Users enabled for Enterprise Voice, type the percentage of your users who are enabled for Enterprise Voice.</span></span> <span data-ttu-id="2b4d9-132">默认值为 60%。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-132">The default is 60%.</span></span>

  - <span data-ttu-id="2b4d9-133">在 "每个用户每小时平均通话次数（峰值）" 中，键入预计平均用户在高峰负载的时间内参与的每小时通话次数。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-133">In Average number of calls per user per hour (peak), type the number of calls per hour that you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="2b4d9-134">默认值为 4。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-134">The default is 4.</span></span>

  - <span data-ttu-id="2b4d9-135">在“使用媒体旁路的呼叫百分比”中，键入由你的用户拨打的、将绕过中介服务器的呼叫百分比。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-135">In Percentage of calls that use media bypass, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="2b4d9-136">默认值为65%。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-136">The default is 65%.</span></span>

  - <span data-ttu-id="2b4d9-137">在“UC-PSTN 呼叫中涉及的语音用户百分比”中，键入你的组织的呼叫属于 UC-PSTN 电话呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-137">In Percentage of voice users involved in UC-PSTN calls, type the percentage of your organization’s calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="2b4d9-138">默认值为60%</span><span class="sxs-lookup"><span data-stu-id="2b4d9-138">The default is 60%</span></span>

  - <span data-ttu-id="2b4d9-139">在 UC-UC 通话中涉及的语音用户的百分比显示启用了企业语音的用户的百分比，仅适用于 UC-UC 呼叫。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-139">In Percentage of voice users involved in UC-UC calls shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="2b4d9-140">此数目基于你对“启用 UC-PSTN 呼叫的语音用户百分比”输入的内容进行计算。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-140">This number is calculated based on what you input for Percentage of voice users enabled for UC-PSTN calls.</span></span>

<span data-ttu-id="2b4d9-141">**会议**</span><span class="sxs-lookup"><span data-stu-id="2b4d9-141">**Conferencing**</span></span>

  - <span data-ttu-id="2b4d9-142">在 "并发会议中的用户百分比" 中，键入将同时参与会议的用户的百分比。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-142">In Percentage of users in concurrent conferences, type the percentage of users who will be concurrently participating in conferences.</span></span> <span data-ttu-id="2b4d9-143">默认值为 5%。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-143">The default is 5%.</span></span>

  - <span data-ttu-id="2b4d9-144">按仅限群组 IM （无语音）的会议的百分比，键入会议将仅涉及即时消息的会议百分比;也就是说，不包括音频组件。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-144">In Percentage of conferences with group IM only (no voice), type the percentage of conferences whose conferences will involve instant messaging only; that is, that do not include an audio component.</span></span> <span data-ttu-id="2b4d9-145">默认值为 10%。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-145">The default is 10%</span></span>

  - <span data-ttu-id="2b4d9-146">在使用电话拨入式会议的用户百分比中，键入会议中将使用电话拨入式会议的并发参与者的百分比。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-146">In Percentage of users using dial-in conferencing, type the percentage of concurrent participants in conferences who will be using dial-in conferencing.</span></span> <span data-ttu-id="2b4d9-147">默认值为 15%。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-147">The default is 15%.</span></span>

  - <span data-ttu-id="2b4d9-148">在使用语音的会议百分比中，键入将包含音频组件的会议的百分比。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-148">In Percentage of conferences using voice, type the percentage of conferences that will include an audio component.</span></span>
    
      - <span data-ttu-id="2b4d9-149">如果 20% 的语音会议也将包括普通视频，请选择“包括视频（无多视图）”复选框。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-149">If 20% of your voice conferences will also include regular video, select the Including video (no Multi View) check box.</span></span>
    
      - <span data-ttu-id="2b4d9-150">如果 20% 的会议也将包括多视图视频，请选择“包括多视图”复选框。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-150">If 20% of your conferences will also include Multi-View video, select the Including Multi View check box.</span></span>
    
      - <span data-ttu-id="2b4d9-151">如果 50% 的语音会议也将包括应用程序共享，请选择“包括应用程序共享”复选框。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-151">If 50% of your voice conferences will also include application sharing, select the Including application sharing check box.</span></span>
    
      - <span data-ttu-id="2b4d9-152">如果您的语音会议的20% 包括数据上载（如 Microsoft PowerPoint®演示文稿），请选中 "包括 web 会议" 复选框。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-152">If 20% of your voice conferences include data uploads, such as Microsoft PowerPoint® presentations, select the Including web conferencing check box.</span></span>

<span data-ttu-id="2b4d9-153">**移动性**</span><span class="sxs-lookup"><span data-stu-id="2b4d9-153">**Mobility**</span></span>

  - <span data-ttu-id="2b4d9-154">在 "为移动启用的用户百分比" 中，键入将启用其使用移动设备连接到 Lync Server 的用户的百分比。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-154">In Percentage of users enabled for Mobility, type the percentage of your users who will be enabled to connect to Lync Server using mobile devices.</span></span> <span data-ttu-id="2b4d9-155">默认值为 40%。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-155">The default is 40%.</span></span>

<span data-ttu-id="2b4d9-156">在你输入所有必要信息之后，容量计算器将估计你的要求。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-156">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="2b4d9-157">黄色单元格根据 Lync Server 2013 性能实验室中执行的测试显示 CPU、内存和带宽要求的计算值。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-157">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Lync Server 2013 performance labs.</span></span> <span data-ttu-id="2b4d9-158">这些数字仅供参考，并没有针对所有单个变体进行测试和验证。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-158">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="2b4d9-159">将计算以下值：</span><span class="sxs-lookup"><span data-stu-id="2b4d9-159">The following values are calculated:</span></span>

  - <span data-ttu-id="2b4d9-160">前端 CPU：如果整个负载由一台前端服务器处理，与 Microsoft 测试中使用的服务器相同，则为 CPU 使用率的百分比。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-160">Front End CPU: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in Microsoft testing.</span></span>

  - <span data-ttu-id="2b4d9-161">网络 (Mbps)：对应工作负载的带宽要求 (Mbps)。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-161">Network in Mbps: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>

  - <span data-ttu-id="2b4d9-162">内存 (GB)：对应工作负载所需的内存 (GB)。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-162">Memory in GB: Memory required in gigabytes (GB) for the corresponding workload.</span></span>

<span data-ttu-id="2b4d9-163">绿色单元格显示为您输入的使用模型提供的建议。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-163">The green cells show recommendations for the usage model that you entered.</span></span>

  - <span data-ttu-id="2b4d9-164">前端服务器总数：所需的物理服务器数基于运行 Lync Server 2013 的专用服务器（采用双处理器，十六进制），2260兆周期。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-164">Total Front End Servers: The number of physical servers required are based on dedicated servers running Lync Server 2013 with dual processor, hex-core, with 2,260 megacycles.</span></span>

  - <span data-ttu-id="2b4d9-165">请注意，建议启用超线程，它经过证明可改进支持音频/视频的服务器的性能。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-165">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>

  - <span data-ttu-id="2b4d9-166">边缘服务器：所需的边缘服务器数目基于通过边缘服务器进行通信的所有并发用户的 30% 确定。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-166">Edge Servers: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="2b4d9-167">此百分比不可在计算器中更改。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-167">This percentage cannot be changed in the calculator.</span></span>

  - <span data-ttu-id="2b4d9-168">存档/呼叫详细记录/用户体验质量服务存储：存档或监视功能（如果你的组织已启用）所需的存储数。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-168">Archiving/Call Detail Recording/Quality of Experience services Store: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>

  - <span data-ttu-id="2b4d9-169">所需的后端数据库服务器（需要池）：支持所选工作负载所需的后端数据库服务器数目。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-169">Back End Database Server Required (Pools Required): The number of back-end database servers required to support the selected workload.</span></span>

<span data-ttu-id="2b4d9-170">此外，在“前端服务器总数”旁边的行中，针对综合的所有计划工作负载提供了有关您的服务器和网络上的负载的更多信息。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-170">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>

  - <span data-ttu-id="2b4d9-171">平均 CPU 负载：每个前端服务器的平均 CPU 使用。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-171">Average CPU Load: The average CPU usage per Front End server.</span></span>

  - <span data-ttu-id="2b4d9-172">网络 (Mbps)：支持你输入的使用模型所需的带宽分配。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-172">Network in Mbps: The required bandwidth allocation to support the usage model that you entered.</span></span>

  - <span data-ttu-id="2b4d9-173">内存 (GB)：每个前端服务器所需的内存 (GB)。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-173">Memory in GB: Memory, in gigabytes, required for each Front End server.</span></span>

</div>

<div>

## <a name="adjusting-for-your-processors"></a><span data-ttu-id="2b4d9-174">针对处理器进行调整</span><span class="sxs-lookup"><span data-stu-id="2b4d9-174">Adjusting For Your Processors</span></span>

<span data-ttu-id="2b4d9-175">电子表格中的所有 CPU 使用数字都假设每台服务器具有双处理器、十六核 (2,260 GHz)、至少 32 GB 内存以及 8 个或以上 10,000-RPM 硬盘驱动器（至少 72 GB 的可用磁盘空间）。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-175">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>

<span data-ttu-id="2b4d9-176">如果您的服务器具有不同的处理器，您可以根据您的硬件调整数字。</span><span class="sxs-lookup"><span data-stu-id="2b4d9-176">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

