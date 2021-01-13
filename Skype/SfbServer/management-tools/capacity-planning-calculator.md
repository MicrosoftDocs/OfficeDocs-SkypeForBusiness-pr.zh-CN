---
title: Skype for Business Server 容量计划计算器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: ca7266f5a18e21dbb964f18a791de9b8903a7f0c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802992"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a><span data-ttu-id="b2938-103">Skype for Business Server 容量计划计算器</span><span class="sxs-lookup"><span data-stu-id="b2938-103">Skype for Business Server Capacity Planning Calculator</span></span>
 
<span data-ttu-id="b2938-104">**摘要：** 如何使用容量计算器工具。</span><span class="sxs-lookup"><span data-stu-id="b2938-104">**Summary:** How to use the Capacity Calculator Tool.</span></span>

> [!NOTE]
> <span data-ttu-id="b2938-105">本文引用 Skype for Business Server 2015 下载，但它适用于：</span><span class="sxs-lookup"><span data-stu-id="b2938-105">This article references Skype for Business Server 2015 downloads, but it applies to:</span></span>
> - <span data-ttu-id="b2938-106">Skype for Business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="b2938-106">Skype for Business Server 2019.</span></span>
> - <span data-ttu-id="b2938-107">Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="b2938-107">Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b2938-108">[Skype for Business Server 2015 容量](https://www.microsoft.com/download/details.aspx?id=51196)计算器和 Skype for Business Server [2019 容量](https://www.microsoft.com/download/details.aspx?id=57509)计算器分别扩充了 Skype for Business[规划](https://www.microsoft.com/download/details.aspx?id=50357)工具和部署文档 (Plan for your Skype for Business [Server 2015 deployment](../plan-your-deployment/plan-your-deployment.md) and Plan for your Skype for Business Server [2019 deployment](../../SfBServer2019/plan/plan-your-deployment-2019.md) respectively) .</span><span class="sxs-lookup"><span data-stu-id="b2938-108">The [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196) and [Skype for Business Server 2019 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=57509) augment the [Skype for Business Planning Tool](https://www.microsoft.com/download/details.aspx?id=50357) and your deployment documentation ([Plan for your Skype for Business Server 2015 deployment](../plan-your-deployment/plan-your-deployment.md) and [Plan for your Skype for Business Server 2019 deployment](../../SfBServer2019/plan/plan-your-deployment-2019.md) respectively).</span></span> <span data-ttu-id="b2938-109">查看指南并使用规划工具创建推荐的拓扑后，使用计算器。</span><span class="sxs-lookup"><span data-stu-id="b2938-109">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>
  
<span data-ttu-id="b2938-110">Skype for Business Server 容量计算器可帮助你根据组织使用的用户数和通信工具确定服务器要求。</span><span class="sxs-lookup"><span data-stu-id="b2938-110">The Skype for Business Server Capacity Calculator helps you determine server requirements based on the number of users and the communication tools your organization uses.</span></span> <span data-ttu-id="b2938-111">确定用户配置文件和要为用户启用的功能后，使用计算器确定所需的服务器数、内存和带宽。</span><span class="sxs-lookup"><span data-stu-id="b2938-111">After you have determined your user profile and the functions you want to enable for your users, use the calculator to determine the number of servers, memory, and bandwidth you will need.</span></span> <span data-ttu-id="b2938-112">此版本的计算器不提供磁盘 I/O 要求的指南。</span><span class="sxs-lookup"><span data-stu-id="b2938-112">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>
  
<span data-ttu-id="b2938-113">如果你拥有有关特定用户配置文件的准确、详细信息，则可以从计算器中获益最多。</span><span class="sxs-lookup"><span data-stu-id="b2938-113">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="b2938-114">例如，启用语音的用户百分比、每个用户每小时的平均呼叫数、呼叫持续时间以及会议中的并发用户的百分比可能会对服务器要求产生巨大差异。</span><span class="sxs-lookup"><span data-stu-id="b2938-114">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="b2938-115">计算器创建的建议的准确性取决于您提供的信息的准确性。</span><span class="sxs-lookup"><span data-stu-id="b2938-115">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>
  
<span data-ttu-id="b2938-116">使用规划工具和容量规划计算器后，应模拟建议和计划的负载，以确保充分预配 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="b2938-116">Once you have used the Planning Tool and the Capacity Planning Calculator, you should simulate your proposed and planned load to ensure that Skype for Business Server will be adequately provisioned.</span></span> <span data-ttu-id="b2938-117">若要在模拟负载下执行压力测试，请使用 [Skype for Business Server](https://www.microsoft.com/download/details.aspx?id=50367) 压力和性能工具（在 Skype for Business Server 压力和性能工具 [中记录](https://technet.microsoft.com/library/mt631400.aspx)）。</span><span class="sxs-lookup"><span data-stu-id="b2938-117">To perform stress testing under a simulated load, use the [Skype for Business Server Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) documented at [Skype for Business Server Stress and Performance Tool](https://technet.microsoft.com/library/mt631400.aspx).</span></span>
  
## <a name="using-the-capacity-calculator"></a><span data-ttu-id="b2938-118">使用容量计算器</span><span class="sxs-lookup"><span data-stu-id="b2938-118">Using the Capacity Calculator</span></span>

<span data-ttu-id="b2938-119">计算器是 Microsoft Excel 电子表格。</span><span class="sxs-lookup"><span data-stu-id="b2938-119">The calculator is a Microsoft Excel spreadsheet.</span></span> <span data-ttu-id="b2938-120">输入单元格的颜色为橙色。</span><span class="sxs-lookup"><span data-stu-id="b2938-120">Your input cells are colored orange.</span></span> <span data-ttu-id="b2938-121">默认值在单元格 (For Skype for Business Server 2015 中输入，一个池中有 80，000 个用户具有 12 台前端服务器，而对于 Skype for Business Server 2019，一个池中有 106，000 个用户具有 16 个前端服务器) ，但应更改这些值以满足组织的需求。</span><span class="sxs-lookup"><span data-stu-id="b2938-121">Default values are entered in the cells (For Skype for Business Server 2015, 80,000 users in one pool with twelve Front End Servers, while for Skype for Business Server 2019, 106,000 users in one pool with sixteen Front End Servers), but you should change these values to match your organization's needs.</span></span>
  
<span data-ttu-id="b2938-122">使用模型包含以下部分。</span><span class="sxs-lookup"><span data-stu-id="b2938-122">The usage model contains the following sections.</span></span> <span data-ttu-id="b2938-123">若要计算容量要求，请按如下所述输入数据：从工作表顶部开始并按行向下工作：</span><span class="sxs-lookup"><span data-stu-id="b2938-123">To calculate your capacity requirements, enter data as described starting at the top of the sheet and working down row by row:</span></span> 
  
 <span data-ttu-id="b2938-124">**即时消息和状态**</span><span class="sxs-lookup"><span data-stu-id="b2938-124">**Instant Messaging and Presence**</span></span>
  
- <span data-ttu-id="b2938-125">在 **"用户数"** 下，键入将同时登录的用户数。</span><span class="sxs-lookup"><span data-stu-id="b2938-125">Under **Number of Users**, type the number of users who will be signed in at once.</span></span> <span data-ttu-id="b2938-126">此数字通常是已设置用户总数的 80%。</span><span class="sxs-lookup"><span data-stu-id="b2938-126">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="b2938-127">在大多数情况下，将为 100% 的并发用户启用 IM 和状态。</span><span class="sxs-lookup"><span data-stu-id="b2938-127">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="b2938-128">Skype for Business Server 2015 的默认值为 80，000，Skype for Business Server 2019 的默认值为 106，000 个用户。</span><span class="sxs-lookup"><span data-stu-id="b2938-128">The default is 80,000 for Skype for Business Server 2015, and 106,000 users for Skype for Business Server 2019.</span></span>
    
- <span data-ttu-id="b2938-129">**联系人列表中的平均联系人** 数指示我们用于验证系统要求的联系人数量。</span><span class="sxs-lookup"><span data-stu-id="b2938-129">**Average number of contacts in Contact list** indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="b2938-130">此数字是固定的，不应更改。</span><span class="sxs-lookup"><span data-stu-id="b2938-130">This number is fixed and not something you should change.</span></span>
    
  <span data-ttu-id="b2938-131">**企业语音**</span><span class="sxs-lookup"><span data-stu-id="b2938-131">**Enterprise Voice**</span></span>
  
- <span data-ttu-id="b2938-132">在 **"启用企业语音** 中，键入为用户启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="b2938-132">In **Users enabled for Enterprise Voice**, type the percentage of your users enabled for Enterprise Voice.</span></span> <span data-ttu-id="b2938-133">默认值为 60%。</span><span class="sxs-lookup"><span data-stu-id="b2938-133">The default is 60%.</span></span> 
    
- <span data-ttu-id="b2938-134">在 **每个用户** 每小时呼叫数 (峰值) 中，键入预计平均用户在高峰负载期间参与的每小时呼叫数。</span><span class="sxs-lookup"><span data-stu-id="b2938-134">In **Average number of calls per user per hour (peak)**, type the number of calls per hour you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="b2938-135">默认值为 4。</span><span class="sxs-lookup"><span data-stu-id="b2938-135">The default is 4.</span></span> 
    
- <span data-ttu-id="b2938-136">在 **"使用媒体旁路的** 呼叫百分比"中，键入将绕过中介服务器的用户所呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="b2938-136">In **Percentage of calls that use media bypass**, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="b2938-137">默认值为 65%，但如果分散在地理位置或拥有大量在家工作的用户，则可能会较低。</span><span class="sxs-lookup"><span data-stu-id="b2938-137">The default is 65%, but could be lower if you are spread out geographically or have a large percentage of users who work from home.</span></span>
    
- <span data-ttu-id="b2938-138">在 **UC-PSTN** 呼叫中涉及的语音用户的百分比中，键入组织的呼叫（即 UC-PSTN 电话呼叫）的百分比。</span><span class="sxs-lookup"><span data-stu-id="b2938-138">In **Percentage of voice users involved in UC-PSTN calls**, type the percentage of your organization's calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="b2938-139">默认值为 60%。</span><span class="sxs-lookup"><span data-stu-id="b2938-139">The default is 60%.</span></span>
    
- <span data-ttu-id="b2938-140">**UC-UC** 呼叫中涉及的语音用户的百分比显示为仅启用 UC-UC 呼叫企业语音的用户的百分比。</span><span class="sxs-lookup"><span data-stu-id="b2938-140">**Percentage of voice users involved in UC-UC calls** shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="b2938-141">此号码是根据您为启用 **UC-PSTN** 呼叫的语音用户百分比输入的。</span><span class="sxs-lookup"><span data-stu-id="b2938-141">This number is calculated based on what you input for **Percentage of voice users enabled for UC-PSTN calls**.</span></span> 
    
  <span data-ttu-id="b2938-142">**会议**</span><span class="sxs-lookup"><span data-stu-id="b2938-142">**Conferencing**</span></span>
  
- <span data-ttu-id="b2938-143">在 **并发会议的用户百分比中**，键入将同时参与会议的用户百分比。</span><span class="sxs-lookup"><span data-stu-id="b2938-143">In **Percentage of users in concurrent conferences**, type the percentage of users who will be participating in conferences at the same time.</span></span> <span data-ttu-id="b2938-144">默认值为 5%。</span><span class="sxs-lookup"><span data-stu-id="b2938-144">The default is 5%.</span></span> 
    
- <span data-ttu-id="b2938-145">在 **仅包含组 IM** 的会议的百分比 (没有语音) ，请键入仅涉及即时消息且不包括音频的会议百分比。</span><span class="sxs-lookup"><span data-stu-id="b2938-145">In **Percentage of conferences with group IM only (no voice)**, type the percentage of conferences that will involve instant messaging only and do not include audio.</span></span> <span data-ttu-id="b2938-146">默认值为 10%</span><span class="sxs-lookup"><span data-stu-id="b2938-146">The default is 10%</span></span>
    
- <span data-ttu-id="b2938-147">在 **"使用电话拨入** 式会议的用户百分比"中，键入一次使用电话拨入式会议的会议参与者的百分比。</span><span class="sxs-lookup"><span data-stu-id="b2938-147">In **Percentage of users using dial-in conferencing**, type the percentage of participants in conferences who will be using dial-in conferencing at one time.</span></span> <span data-ttu-id="b2938-148">默认值为 15%。</span><span class="sxs-lookup"><span data-stu-id="b2938-148">The default is 15%.</span></span>
    
- <span data-ttu-id="b2938-149">在 **"使用语音的会议百分比"** 中，键入将包含音频的会议百分比。</span><span class="sxs-lookup"><span data-stu-id="b2938-149">In **Percentage of conferences using voice**, type the percentage of conferences that will include audio.</span></span> 
    
  - <span data-ttu-id="b2938-150">如果 20% 的语音会议还将包含常规视频，请选中"包括视频 (**无** 多视图) 复选框。</span><span class="sxs-lookup"><span data-stu-id="b2938-150">If 20% of your voice conferences will also include regular video, select the **Including video (no Multi View)** check box.</span></span>
    
  - <span data-ttu-id="b2938-151">如果 20% 的会议还将包含多视图视频，请选中" **包括多视图"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="b2938-151">If 20% of your conferences will also include Multi-View video, select the **Including Multi View** check box.</span></span>
    
  - <span data-ttu-id="b2938-152">如果 50% 的语音会议还将包含应用程序共享，请选中" **包括应用程序共享"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="b2938-152">If 50% of your voice conferences will also include application sharing, select the **Including application sharing** check box.</span></span>
    
  - <span data-ttu-id="b2938-153">如果 20% 的语音会议包括数据上载（如 PowerPoint 演示文稿），请选中"包括 **Web 会议"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="b2938-153">If 20% of your voice conferences include data uploads, such as PowerPoint presentations, select the **Including web conferencing** check box.</span></span>
    
  <span data-ttu-id="b2938-154">**移动性**</span><span class="sxs-lookup"><span data-stu-id="b2938-154">**Mobility**</span></span>
  
- <span data-ttu-id="b2938-155">在 **启用移动功能的用户的** 百分比中，键入将允许使用移动设备连接到 Skype for Business Server 的用户百分比。</span><span class="sxs-lookup"><span data-stu-id="b2938-155">In **Percentage of users enabled for Mobility**, type the percentage of your users who will be enabled to connect to Skype for Business Server using mobile devices.</span></span> <span data-ttu-id="b2938-156">默认值为 40%。</span><span class="sxs-lookup"><span data-stu-id="b2938-156">The default is 40%.</span></span> 
    
<span data-ttu-id="b2938-157">输入所有必需信息后，容量计算器会估计您的要求。</span><span class="sxs-lookup"><span data-stu-id="b2938-157">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="b2938-158">黄色单元格根据 Skype for Business Server 性能实验室中执行的测试显示 CPU、内存和带宽要求的计算值。</span><span class="sxs-lookup"><span data-stu-id="b2938-158">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Skype for Business Server performance labs.</span></span> <span data-ttu-id="b2938-159">这些数字作为指南提供，不是每个变体都经过测试和验证。</span><span class="sxs-lookup"><span data-stu-id="b2938-159">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="b2938-160">计算以下值：</span><span class="sxs-lookup"><span data-stu-id="b2938-160">The following values are calculated:</span></span> 
  
- <span data-ttu-id="b2938-161">**前端 CPU：** 如果整个负载由与测试中使用的服务器规格相同的一台前端服务器处理，则 CPU 使用率的百分比 (请参阅本文末尾的说明) 。</span><span class="sxs-lookup"><span data-stu-id="b2938-161">**Front End CPU**: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in testing (see the description at the end of this article).</span></span>
    
- <span data-ttu-id="b2938-162">**网络（以 Mbps** 表示）：相应工作负荷的带宽要求 (Mbps) 兆位。</span><span class="sxs-lookup"><span data-stu-id="b2938-162">**Network in Mbps**: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>
    
- <span data-ttu-id="b2938-163">**内存（以 GB** 为单位）：对应工作负荷所需的内存 (GB) GB。</span><span class="sxs-lookup"><span data-stu-id="b2938-163">**Memory in GB**: Memory required in gigabytes (GB) for the corresponding workload.</span></span>
    
<span data-ttu-id="b2938-164">绿色单元格显示您输入的使用模型的建议。</span><span class="sxs-lookup"><span data-stu-id="b2938-164">The green cells show recommendations for the usage model that you entered.</span></span> 
  
- <span data-ttu-id="b2938-165">前端服务器总数：所需的物理服务器数量基于运行 Skype for Business Server 2015（具有双处理器、十六核、2，260 兆周）或 Skype for Business Server 2019（Intel Xeon E5-2673 v3、双处理器、十六核）的专用服务器。</span><span class="sxs-lookup"><span data-stu-id="b2938-165">**Total Front End Servers**: The number of physical servers required are based on dedicated servers running Skype for Business Server 2015 with dual processor, hex-core, with 2,260 megacycles, or Skype for Business Server 2019 with Intel Xeon E5-2673 v3, dual processor, hex-core.</span></span>
    
    <span data-ttu-id="b2938-166">请注意，建议启用超线程，并且已证明为支持音频/视频的服务器提高性能。</span><span class="sxs-lookup"><span data-stu-id="b2938-166">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>
    
- <span data-ttu-id="b2938-167">**边缘服务器**：所需的边缘服务器数量，基于通过边缘服务器进行通信的所有并发用户的 30%。</span><span class="sxs-lookup"><span data-stu-id="b2938-167">**Edge Servers**: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="b2938-168">计算器中无法更改此百分比。</span><span class="sxs-lookup"><span data-stu-id="b2938-168">This percentage cannot be changed in the calculator.</span></span> 
    
- <span data-ttu-id="b2938-169">**存档/呼叫详细信息记录/用户体验** 质量服务存储：存档或监控功能所需的存储数量（如果在你的组织中已启用）。</span><span class="sxs-lookup"><span data-stu-id="b2938-169">**Archiving/Call Detail Recording/Quality of Experience services Store**: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>
    
- <span data-ttu-id="b2938-170">**后端数据库服务器 (池必需) ：** 支持所选工作负荷所需的后端数据库服务器的数量。</span><span class="sxs-lookup"><span data-stu-id="b2938-170">**Back End Database Server Required (Pools Required)**: The number of back-end database servers required to support the selected workload.</span></span>
    
<span data-ttu-id="b2938-171">此外，在前端服务器总数旁边的行中，还提供了有关所有计划工作负荷组合在一起的服务器和网络负载详细信息。</span><span class="sxs-lookup"><span data-stu-id="b2938-171">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>
  
- <span data-ttu-id="b2938-172">**平均 CPU 负载**：每个前端服务器的平均 CPU 使用率。</span><span class="sxs-lookup"><span data-stu-id="b2938-172">**Average CPU Load**: The average CPU usage per Front End server.</span></span>
    
- <span data-ttu-id="b2938-173">**网络（以 Mbps** 表示）：支持您输入的使用模型所需的带宽分配。</span><span class="sxs-lookup"><span data-stu-id="b2938-173">**Network in Mbps**: The required bandwidth allocation to support the usage model that you entered.</span></span>
    
- <span data-ttu-id="b2938-174">**内存（GB）：** 每个前端服务器所需的内存（以 GB 为单位）。</span><span class="sxs-lookup"><span data-stu-id="b2938-174">**Memory in GB**: Memory, in gigabytes, required for each Front End server.</span></span>
    
### <a name="adjusting-for-your-processors"></a><span data-ttu-id="b2938-175">针对处理器进行调整</span><span class="sxs-lookup"><span data-stu-id="b2938-175">Adjusting For Your Processors</span></span>

<span data-ttu-id="b2938-176">电子表格中所有 CPU 使用率数据都假定每个 Skype for Business Server 2015 服务器都有一个双处理器、2.26 GHz 的十六核、至少 32 GB 的内存以及 8 个或多个 10，000 RPM 硬盘驱动器，其中至少具有 72 GB 的可用磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="b2938-176">All the CPU usage figures in the spreadsheet assume that each Skype for Business Server 2015 server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span> <span data-ttu-id="b2938-177">对于每个 Skype for Business Server 2019 服务器，电子表格中所有 CPU 使用率数据都假设每个服务器都有一个双处理器、具有 Intel Xeon E5-2673 v3 的十六核、至少 64 GB 的内存以及 8 个或多个 10，000 RPM 硬盘驱动器，其中至少具有 72 GB 的可用磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="b2938-177">For each Skype for Business Server 2019 server, all the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with Intel Xeon E5-2673 v3, at least 64 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>
  
<span data-ttu-id="b2938-178">如果您的服务器具有不同的处理器，您可以调整数字以匹配您的硬件。</span><span class="sxs-lookup"><span data-stu-id="b2938-178">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>
  
