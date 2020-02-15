---
title: Skype for Business Server 容量规划计算器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 摘要：如何使用容量计算器工具。
ms.openlocfilehash: 1bb1c9cde82c1f2d6e487c3bc28520b630d59210
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031076"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a><span data-ttu-id="ca06a-103">Skype for Business Server 容量规划计算器</span><span class="sxs-lookup"><span data-stu-id="ca06a-103">Skype for Business Server Capacity Planning Calculator</span></span>
 
<span data-ttu-id="ca06a-104">**摘要：** 如何使用容量计算器工具。</span><span class="sxs-lookup"><span data-stu-id="ca06a-104">**Summary:** How to use the Capacity Calculator Tool.</span></span>

> [!NOTE]
> <span data-ttu-id="ca06a-105">本文引用 Skype for business Server 2015 下载，但它适用于：</span><span class="sxs-lookup"><span data-stu-id="ca06a-105">This article references Skype for Business Server 2015 downloads, but it applies to:</span></span>
> - <span data-ttu-id="ca06a-106">Skype for Business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="ca06a-106">Skype for Business Server 2019.</span></span>
> - <span data-ttu-id="ca06a-107">Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="ca06a-107">Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ca06a-108">[Skype For Business server 2015 容量计算器](https://www.microsoft.com/download/details.aspx?id=51196)和[Skype for Business Server 2019 容量计算器](https://www.microsoft.com/download/details.aspx?id=57509)增强了[skype for business 规划工具](https://www.microsoft.com/download/details.aspx?id=50357)和部署文档（[规划 Skype For business server 2015 部署](../plan-your-deployment/plan-your-deployment.md)并[规划 skype for business server 2019 部署](../../SfBServer2019/plan/plan-your-deployment-2019.md)）。</span><span class="sxs-lookup"><span data-stu-id="ca06a-108">The [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196) and [Skype for Business Server 2019 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=57509) augment the [Skype for Business Planning Tool](https://www.microsoft.com/download/details.aspx?id=50357) and your deployment documentation ([Plan for your Skype for Business Server 2015 deployment](../plan-your-deployment/plan-your-deployment.md) and [Plan for your Skype for Business Server 2019 deployment](../../SfBServer2019/plan/plan-your-deployment-2019.md) respectively).</span></span> <span data-ttu-id="ca06a-109">在您查看指南并使用规划工具创建推荐的拓扑之后，使用计算器。</span><span class="sxs-lookup"><span data-stu-id="ca06a-109">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>
  
<span data-ttu-id="ca06a-110">Skype for Business Server 容量计算器可帮助您根据您的组织使用的用户数和通信工具来确定服务器要求。</span><span class="sxs-lookup"><span data-stu-id="ca06a-110">The Skype for Business Server Capacity Calculator helps you determine server requirements based on the number of users and the communication tools your organization uses.</span></span> <span data-ttu-id="ca06a-111">确定您的用户配置文件和要为用户启用的功能之后，请使用计算器确定所需的服务器、内存和带宽的数量。</span><span class="sxs-lookup"><span data-stu-id="ca06a-111">After you have determined your user profile and the functions you want to enable for your users, use the calculator to determine the number of servers, memory, and bandwidth you will need.</span></span> <span data-ttu-id="ca06a-112">此版本的计算器不会提供磁盘 i/o 要求指南。</span><span class="sxs-lookup"><span data-stu-id="ca06a-112">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>
  
<span data-ttu-id="ca06a-113">如果您具有有关特定用户配置文件的准确、详细信息，则可以从计算器中获益最多。</span><span class="sxs-lookup"><span data-stu-id="ca06a-113">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="ca06a-114">例如，启用了语音的用户的百分比、每个用户每小时平均呼叫数、呼叫持续时间以及会议中并发用户的百分比可能会对服务器的要求产生巨大的影响。</span><span class="sxs-lookup"><span data-stu-id="ca06a-114">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="ca06a-115">计算器所创建的建议的准确性取决于您提供的信息的准确性。</span><span class="sxs-lookup"><span data-stu-id="ca06a-115">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>
  
<span data-ttu-id="ca06a-116">在使用规划工具和容量规划计算器后，应模拟建议和计划的负载，以确保已充分设置 Skype for business Server。</span><span class="sxs-lookup"><span data-stu-id="ca06a-116">Once you have used the Planning Tool and the Capacity Planning Calculator, you should simulate your proposed and planned load to ensure that Skype for Business Server will be adequately provisioned.</span></span> <span data-ttu-id="ca06a-117">若要在模拟负载下执行压力测试，请使用 Skype for business [Server 压力和性能工具](https://technet.microsoft.com/library/mt631400.aspx)中记录的[Skype For business Server 压力和性能工具](https://www.microsoft.com/download/details.aspx?id=50367)。</span><span class="sxs-lookup"><span data-stu-id="ca06a-117">To perform stress testing under a simulated load, use the [Skype for Business Server Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) documented at [Skype for Business Server Stress and Performance Tool](https://technet.microsoft.com/library/mt631400.aspx).</span></span>
  
## <a name="using-the-capacity-calculator"></a><span data-ttu-id="ca06a-118">使用容量计算器</span><span class="sxs-lookup"><span data-stu-id="ca06a-118">Using the Capacity Calculator</span></span>

<span data-ttu-id="ca06a-119">计算器是 Microsoft Excel 电子表格。</span><span class="sxs-lookup"><span data-stu-id="ca06a-119">The calculator is a Microsoft Excel spreadsheet.</span></span> <span data-ttu-id="ca06a-120">您的输入单元格的颜色为橙色。</span><span class="sxs-lookup"><span data-stu-id="ca06a-120">Your input cells are colored orange.</span></span> <span data-ttu-id="ca06a-121">默认值在单元格中输入（对于在具有十二台前端服务器的一个池中的 Skype for Business Server 2015、80000用户），而对于 Skype for Business Server 2019，则使用一个池中的106000用户进行16台前端服务器，但应将这些值更改为满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="ca06a-121">Default values are entered in the cells (For Skype for Business Server 2015, 80,000 users in one pool with twelve Front End Servers, while for Skype for Business Server 2019, 106,000 users in one pool with sixteen Front End Servers), but you should change these values to match your organization's needs.</span></span>
  
<span data-ttu-id="ca06a-122">使用模型包含以下部分。</span><span class="sxs-lookup"><span data-stu-id="ca06a-122">The usage model contains the following sections.</span></span> <span data-ttu-id="ca06a-123">若要计算您的容量要求，请按照工作表顶部的说明输入数据，并逐行工作：</span><span class="sxs-lookup"><span data-stu-id="ca06a-123">To calculate your capacity requirements, enter data as described starting at the top of the sheet and working down row by row:</span></span> 
  
 <span data-ttu-id="ca06a-124">**即时消息和状态**</span><span class="sxs-lookup"><span data-stu-id="ca06a-124">**Instant Messaging and Presence**</span></span>
  
- <span data-ttu-id="ca06a-125">在 "**用户数**" 下，键入将一次性登录的用户数。</span><span class="sxs-lookup"><span data-stu-id="ca06a-125">Under **Number of Users**, type the number of users who will be signed in at once.</span></span> <span data-ttu-id="ca06a-126">此数字通常为已设置的用户总数的80%。</span><span class="sxs-lookup"><span data-stu-id="ca06a-126">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="ca06a-127">在大多数情况下，将对100% 的并发用户启用 IM 和状态。</span><span class="sxs-lookup"><span data-stu-id="ca06a-127">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="ca06a-128">默认值为80000（适用于 Skype for business Server 2015）和106000适用于 Skype for business Server 2019 的用户。</span><span class="sxs-lookup"><span data-stu-id="ca06a-128">The default is 80,000 for Skype for Business Server 2015, and 106,000 users for Skype for Business Server 2019.</span></span>
    
- <span data-ttu-id="ca06a-129">**联系人列表中的平均联系人数**表示用于验证您的系统要求的联系人数量。</span><span class="sxs-lookup"><span data-stu-id="ca06a-129">**Average number of contacts in Contact list** indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="ca06a-130">此号码是固定的，不是应该更改的内容。</span><span class="sxs-lookup"><span data-stu-id="ca06a-130">This number is fixed and not something you should change.</span></span>
    
  <span data-ttu-id="ca06a-131">**企业语音**</span><span class="sxs-lookup"><span data-stu-id="ca06a-131">**Enterprise Voice**</span></span>
  
- <span data-ttu-id="ca06a-132">在 "**启用企业语音的用户**" 中，键入启用了企业语音的用户的百分比。</span><span class="sxs-lookup"><span data-stu-id="ca06a-132">In **Users enabled for Enterprise Voice**, type the percentage of your users enabled for Enterprise Voice.</span></span> <span data-ttu-id="ca06a-133">默认值为60%。</span><span class="sxs-lookup"><span data-stu-id="ca06a-133">The default is 60%.</span></span> 
    
- <span data-ttu-id="ca06a-134">在 "每个**用户每小时的平均呼叫数（峰值）**" 中，键入预计在高峰负载期间平均用户参与的每小时的呼叫数。</span><span class="sxs-lookup"><span data-stu-id="ca06a-134">In **Average number of calls per user per hour (peak)**, type the number of calls per hour you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="ca06a-135">默认值为 4。</span><span class="sxs-lookup"><span data-stu-id="ca06a-135">The default is 4.</span></span> 
    
- <span data-ttu-id="ca06a-136">在 "**使用媒体旁路的呼叫百分比**" 中，键入用户发出的将绕过中介服务器的呼叫百分比。</span><span class="sxs-lookup"><span data-stu-id="ca06a-136">In **Percentage of calls that use media bypass**, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="ca06a-137">默认值为65%，但如果分散在不同地理位置或拥有在家工作的大量用户，则可能会降低。</span><span class="sxs-lookup"><span data-stu-id="ca06a-137">The default is 65%, but could be lower if you are spread out geographically or have a large percentage of users who work from home.</span></span>
    
- <span data-ttu-id="ca06a-138">在**与 uc-pstn 呼叫相关的语音用户的百分比**中，键入组织的呼叫的百分比，即 UC-pstn 电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="ca06a-138">In **Percentage of voice users involved in UC-PSTN calls**, type the percentage of your organization's calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="ca06a-139">默认值为60%。</span><span class="sxs-lookup"><span data-stu-id="ca06a-139">The default is 60%.</span></span>
    
- <span data-ttu-id="ca06a-140">**Uc-uc 呼叫中涉及的语音用户所占的百分比**显示为企业语音启用的、仅对 uc uc 呼叫启用的用户的百分比。</span><span class="sxs-lookup"><span data-stu-id="ca06a-140">**Percentage of voice users involved in UC-UC calls** shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="ca06a-141">根据**为 UC-PSTN 呼叫启用的语音用户百分比**输入的内容计算此数字。</span><span class="sxs-lookup"><span data-stu-id="ca06a-141">This number is calculated based on what you input for **Percentage of voice users enabled for UC-PSTN calls**.</span></span> 
    
  <span data-ttu-id="ca06a-142">**会议**</span><span class="sxs-lookup"><span data-stu-id="ca06a-142">**Conferencing**</span></span>
  
- <span data-ttu-id="ca06a-143">在 "**并发会议的用户百分比**" 中，键入将同时参与会议的用户的百分比。</span><span class="sxs-lookup"><span data-stu-id="ca06a-143">In **Percentage of users in concurrent conferences**, type the percentage of users who will be participating in conferences at the same time.</span></span> <span data-ttu-id="ca06a-144">默认值为5%。</span><span class="sxs-lookup"><span data-stu-id="ca06a-144">The default is 5%.</span></span> 
    
- <span data-ttu-id="ca06a-145">在 "**仅限组 IM （无语音）的会议百分比**" 中，键入将仅涉及即时消息且不包含音频的会议所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="ca06a-145">In **Percentage of conferences with group IM only (no voice)**, type the percentage of conferences that will involve instant messaging only and do not include audio.</span></span> <span data-ttu-id="ca06a-146">默认值为10%</span><span class="sxs-lookup"><span data-stu-id="ca06a-146">The default is 10%</span></span>
    
- <span data-ttu-id="ca06a-147">在**使用电话拨入式会议的用户百分比**中，键入会议中一次使用电话拨入式会议的参与者的百分比。</span><span class="sxs-lookup"><span data-stu-id="ca06a-147">In **Percentage of users using dial-in conferencing**, type the percentage of participants in conferences who will be using dial-in conferencing at one time.</span></span> <span data-ttu-id="ca06a-148">默认值为15%。</span><span class="sxs-lookup"><span data-stu-id="ca06a-148">The default is 15%.</span></span>
    
- <span data-ttu-id="ca06a-149">在 "**使用语音的会议百分比**" 中，键入将包含音频的会议所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="ca06a-149">In **Percentage of conferences using voice**, type the percentage of conferences that will include audio.</span></span> 
    
  - <span data-ttu-id="ca06a-150">如果20% 的语音会议也将包含常规视频，请选中 "**包含视频（无多视图）** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="ca06a-150">If 20% of your voice conferences will also include regular video, select the **Including video (no Multi View)** check box.</span></span>
    
  - <span data-ttu-id="ca06a-151">如果20% 的会议也将包含多视图视频，请选中 "**包含多个视图**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="ca06a-151">If 20% of your conferences will also include Multi-View video, select the **Including Multi View** check box.</span></span>
    
  - <span data-ttu-id="ca06a-152">如果50% 的语音会议也将包含应用程序共享，请选中 "**包括应用程序共享**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="ca06a-152">If 50% of your voice conferences will also include application sharing, select the **Including application sharing** check box.</span></span>
    
  - <span data-ttu-id="ca06a-153">如果20% 的语音会议包括数据上载（如 PowerPoint 演示文稿），请选中 "**包括 web 会议**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="ca06a-153">If 20% of your voice conferences include data uploads, such as PowerPoint presentations, select the **Including web conferencing** check box.</span></span>
    
  <span data-ttu-id="ca06a-154">**移动性**</span><span class="sxs-lookup"><span data-stu-id="ca06a-154">**Mobility**</span></span>
  
- <span data-ttu-id="ca06a-155">在 "**已启用移动性的用户百分比**" 中，键入将启用使用移动设备连接到 Skype For business Server 的用户的百分比。</span><span class="sxs-lookup"><span data-stu-id="ca06a-155">In **Percentage of users enabled for Mobility**, type the percentage of your users who will be enabled to connect to Skype for Business Server using mobile devices.</span></span> <span data-ttu-id="ca06a-156">默认值为40%。</span><span class="sxs-lookup"><span data-stu-id="ca06a-156">The default is 40%.</span></span> 
    
<span data-ttu-id="ca06a-157">输入所有必要的信息后，容量计算器估计您的要求。</span><span class="sxs-lookup"><span data-stu-id="ca06a-157">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="ca06a-158">黄色单元格根据在 Skype for Business Server 性能实验室中执行的测试，显示 CPU、内存和带宽要求的计算值。</span><span class="sxs-lookup"><span data-stu-id="ca06a-158">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Skype for Business Server performance labs.</span></span> <span data-ttu-id="ca06a-159">这些数字作为指南提供，并不是每个单独的变体都经过测试和验证。</span><span class="sxs-lookup"><span data-stu-id="ca06a-159">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="ca06a-160">将计算以下值：</span><span class="sxs-lookup"><span data-stu-id="ca06a-160">The following values are calculated:</span></span> 
  
- <span data-ttu-id="ca06a-161">**前端 cpu**：如果整个负载与测试中使用的服务器具有相同规范的一台前端服务器的处理，则 cpu 使用率的百分比（请参阅本文末尾的说明）。</span><span class="sxs-lookup"><span data-stu-id="ca06a-161">**Front End CPU**: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in testing (see the description at the end of this article).</span></span>
    
- <span data-ttu-id="ca06a-162">**网络（以 mbps**为单位）：带宽要求对应工作负载的带宽要求为每秒兆位（Mbps）。</span><span class="sxs-lookup"><span data-stu-id="ca06a-162">**Network in Mbps**: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>
    
- <span data-ttu-id="ca06a-163">**内存（gb**）：针对相应工作负荷的内存，以千兆字节（GB）为单位。</span><span class="sxs-lookup"><span data-stu-id="ca06a-163">**Memory in GB**: Memory required in gigabytes (GB) for the corresponding workload.</span></span>
    
<span data-ttu-id="ca06a-164">绿色单元格显示有关您输入的使用情况模型的建议。</span><span class="sxs-lookup"><span data-stu-id="ca06a-164">The green cells show recommendations for the usage model that you entered.</span></span> 
  
- <span data-ttu-id="ca06a-165">**前端服务器总数**：所需的物理服务器数基于运行 Skype For business server 2015 的专用服务器，使用双处理器、hex-core、2260兆周期或 Skype For business server 2019 与 Intel 2673 v3、双处理器、hex-core。</span><span class="sxs-lookup"><span data-stu-id="ca06a-165">**Total Front End Servers**: The number of physical servers required are based on dedicated servers running Skype for Business Server 2015 with dual processor, hex-core, with 2,260 megacycles, or Skype for Business Server 2019 with Intel Xeon E5-2673 v3, dual processor, hex-core.</span></span>
    
    <span data-ttu-id="ca06a-166">请注意，建议启用超线程，并已证明可提高支持音频/视频的服务器的性能。</span><span class="sxs-lookup"><span data-stu-id="ca06a-166">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>
    
- <span data-ttu-id="ca06a-167">**边缘服务器**：根据所有并发用户通过边缘服务器通信时所需的边缘服务器的数量。</span><span class="sxs-lookup"><span data-stu-id="ca06a-167">**Edge Servers**: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="ca06a-168">计算器中不能更改此百分比。</span><span class="sxs-lookup"><span data-stu-id="ca06a-168">This percentage cannot be changed in the calculator.</span></span> 
    
- <span data-ttu-id="ca06a-169">**存档/呼叫详细记录/高级服务存储**：存档或监控功能所需的存储数量（如果在组织中已启用）。</span><span class="sxs-lookup"><span data-stu-id="ca06a-169">**Archiving/Call Detail Recording/Quality of Experience services Store**: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>
    
- <span data-ttu-id="ca06a-170">**必需的后端数据库服务器（需要池）**：支持所选工作负荷所需的后端数据库服务器的数量。</span><span class="sxs-lookup"><span data-stu-id="ca06a-170">**Back End Database Server Required (Pools Required)**: The number of back-end database servers required to support the selected workload.</span></span>
    
<span data-ttu-id="ca06a-171">此外，在前端服务器总数的第一行中，提供了有关服务器和网络上的负载的更多信息，用于组合所有计划的工作负载。</span><span class="sxs-lookup"><span data-stu-id="ca06a-171">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>
  
- <span data-ttu-id="ca06a-172">**平均 Cpu 负载**：每个前端服务器的平均 cpu 使用率。</span><span class="sxs-lookup"><span data-stu-id="ca06a-172">**Average CPU Load**: The average CPU usage per Front End server.</span></span>
    
- <span data-ttu-id="ca06a-173">**网络（以 Mbps 为单位**）：支持所需的带宽分配以支持您输入的使用模式。</span><span class="sxs-lookup"><span data-stu-id="ca06a-173">**Network in Mbps**: The required bandwidth allocation to support the usage model that you entered.</span></span>
    
- <span data-ttu-id="ca06a-174">**内存（gb**）：每个前端服务器所需的内存（以 gb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="ca06a-174">**Memory in GB**: Memory, in gigabytes, required for each Front End server.</span></span>
    
### <a name="adjusting-for-your-processors"></a><span data-ttu-id="ca06a-175">针对处理器进行调整</span><span class="sxs-lookup"><span data-stu-id="ca06a-175">Adjusting For Your Processors</span></span>

<span data-ttu-id="ca06a-176">电子表格中的所有 CPU 使用情况图假定每个 Skype for Business Server 2015 服务器都具有双处理器、16 GHz 16 2.26 进制的内存、至少有 32 GB 的内存以及8个或更多个至少具有 72 GB 可用磁盘空间的 10000 RPM 硬盘。</span><span class="sxs-lookup"><span data-stu-id="ca06a-176">All the CPU usage figures in the spreadsheet assume that each Skype for Business Server 2015 server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span> <span data-ttu-id="ca06a-177">对于每个 Skype for Business Server 2019 服务器，电子表格中的所有 CPU 使用情况图都会假定每台服务器都有双处理器、hex-core 和英特尔至强 2673 v3、至少 64 GB 的内存以及至少有 72 GB 可用磁盘的8个或更多 10000 RPM 的硬盘驱动器复杂.</span><span class="sxs-lookup"><span data-stu-id="ca06a-177">For each Skype for Business Server 2019 server, all the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with Intel Xeon E5-2673 v3, at least 64 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>
  
<span data-ttu-id="ca06a-178">如果你的服务器具有不同的处理器，则可以调整这些数字以匹配你的硬件。</span><span class="sxs-lookup"><span data-stu-id="ca06a-178">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>
  
