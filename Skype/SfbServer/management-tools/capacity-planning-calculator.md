---
title: Skype 业务服务器容量规划计算器
ms.author: heidip
author: microsoftheidi
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 摘要：如何使用容量计算器工具。
ms.openlocfilehash: bb17bc7b024900627318dd64b41249c21ff8488b
ms.sourcegitcommit: 6251a2c659909c3972ca2ea0a2bcdab4f334df34
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2018
ms.locfileid: "25692766"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a><span data-ttu-id="7977e-103">Skype 业务服务器容量规划计算器</span><span class="sxs-lookup"><span data-stu-id="7977e-103">Skype for Business Server Capacity Planning Calculator</span></span>
 
<span data-ttu-id="7977e-104">**摘要：** 如何使用容量计算器工具。</span><span class="sxs-lookup"><span data-stu-id="7977e-104">**Summary:** How to use the Capacity Calculator Tool.</span></span>

> [!NOTE]
> <span data-ttu-id="7977e-105">本文引用 Skype 业务服务器 2015年下载，但它适用于：</span><span class="sxs-lookup"><span data-stu-id="7977e-105">This article references Skype for Business Server 2015 downloads, but it applies to:</span></span>
> - <span data-ttu-id="7977e-106">业务服务器 2019 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="7977e-106">Skype for Business Server 2019.</span></span>
> - <span data-ttu-id="7977e-107">Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="7977e-107">Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7977e-108">[业务服务器容量计算器的 Skype](https://www.microsoft.com/en-us/download/details.aspx?id=51196)补充[Skype 业务规划工具](https://www.microsoft.com/en-us/download/details.aspx?id=50357)和[规划您 Skype 业务服务器部署](https://technet.microsoft.com/en-us/library/dn951427)中的文档。</span><span class="sxs-lookup"><span data-stu-id="7977e-108">[Skype for Business Server Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=51196) augments the [Skype for Business Planning Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50357) and the documentation at [Plan for your Skype for Business Server deployment](https://technet.microsoft.com/en-us/library/dn951427).</span></span> <span data-ttu-id="7977e-109">请在阅读指南并使用规划工具创建建议的拓扑之后使用计算器。</span><span class="sxs-lookup"><span data-stu-id="7977e-109">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>
  
<span data-ttu-id="7977e-110">Skype for Business Server 容量计算器帮助您确定服务器要求基于用户和您的组织使用的通信工具的数量。</span><span class="sxs-lookup"><span data-stu-id="7977e-110">The Skype for Business Server Capacity Calculator helps you determine server requirements based on the number of users and the communication tools your organization uses.</span></span> <span data-ttu-id="7977e-111">在确定你的配置文件和你想要为用户启用的功能之后，请使用计算器确定所需的服务器数、内存和带宽。</span><span class="sxs-lookup"><span data-stu-id="7977e-111">After you have determined your user profile and the functions you want to enable for your users, use the calculator to determine the number of servers, memory, and bandwidth you will need.</span></span> <span data-ttu-id="7977e-112">此版本的计算器不针对磁盘 I/O 要求提供指导。</span><span class="sxs-lookup"><span data-stu-id="7977e-112">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>
  
<span data-ttu-id="7977e-p103">如果您拥有有关您的特定用户概况的准确、详细的信息，则可以充分享受计算器带来的好处。例如，启用语音的用户的百分比、每个用户每小时的平均呼叫、呼叫持续时间以及会议中的并发用户百分比可能会对服务器要求造成巨大差异。计算器创建的建议的准确性取决于您提供的信息的准确性。</span><span class="sxs-lookup"><span data-stu-id="7977e-p103">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile. For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements. The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>
  
<span data-ttu-id="7977e-116">在使用规划工具和容量规划计算器，您应模拟建议和计划负载以确保 Skype 业务服务器将充分设置。</span><span class="sxs-lookup"><span data-stu-id="7977e-116">Once you have used the Planning Tool and the Capacity Planning Calculator, you should simulate your proposed and planned load to ensure that Skype for Business Server will be adequately provisioned.</span></span> <span data-ttu-id="7977e-117">若要执行压力测试模拟负载下，使用[Skype 的业务 Server 压力和性能工具](https://www.microsoft.com/en-us/download/details.aspx?id=50367)在[Skype 的业务 Server 压力和性能工具](https://technet.microsoft.com/en-us/library/mt631400.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7977e-117">To perform stress testing under a simulated load, use the [Skype for Business Server Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) documented at [Skype for Business Server Stress and Performance Tool](https://technet.microsoft.com/en-us/library/mt631400.aspx).</span></span>
  
## <a name="using-the-capacity-calculator"></a><span data-ttu-id="7977e-118">使用容量计算器</span><span class="sxs-lookup"><span data-stu-id="7977e-118">Using the Capacity Calculator</span></span>

<span data-ttu-id="7977e-119">计算器是一个 Microsoft Excel 电子表格。</span><span class="sxs-lookup"><span data-stu-id="7977e-119">The calculator is a Microsoft Excel spreadsheet.</span></span> <span data-ttu-id="7977e-120">橙色单元格供你输入内容。</span><span class="sxs-lookup"><span data-stu-id="7977e-120">Your input cells are colored orange.</span></span> <span data-ttu-id="7977e-121">默认值 （例如 80,000 在 12 个前端服务器具有一个池中的用户） 的单元格中输入，但不是应更改这些值以匹配您组织的需求。</span><span class="sxs-lookup"><span data-stu-id="7977e-121">Default values are entered in the cells (such as 80,000 users in one pool with twelve Front End Servers), but you should change these values to match your organization's needs.</span></span> 
  
<span data-ttu-id="7977e-p106">使用模型包含以下部分。要计算你的容量要求，请按照所述从工作表顶部开始并向下逐行输入数据：</span><span class="sxs-lookup"><span data-stu-id="7977e-p106">The usage model contains the following sections. To calculate your capacity requirements, enter data as described starting at the top of the sheet and working down row by row:</span></span> 
  
 <span data-ttu-id="7977e-124">**即时消息和状态**</span><span class="sxs-lookup"><span data-stu-id="7977e-124">**Instant Messaging and Presence**</span></span>
  
- <span data-ttu-id="7977e-p107">在“**用户数**”下，键入将一次登录的用户数。此数目通常是已设置的用户总数的 80%。在大多数情况下，将对所有并发用户启用 IM 和状态。默认值为 80,000。</span><span class="sxs-lookup"><span data-stu-id="7977e-p107">Under **Number of Users**, type the number of users who will be signed in at once. This number is typically 80% of the total number of provisioned users. In most situations, 100% of your concurrent users will be enabled for IM and Presence. The default is 80,000.</span></span>
    
- <span data-ttu-id="7977e-p108">**联系人列表中的平均联系人数**表示我们用于验证你的系统要求的联系人数。此数字是固定的，不可更改。</span><span class="sxs-lookup"><span data-stu-id="7977e-p108">**Average number of contacts in Contact list** indicates the number of contacts that we are using to validate your system requirements. This number is fixed and not something you should change.</span></span>
    
  <span data-ttu-id="7977e-131">**企业语音**</span><span class="sxs-lookup"><span data-stu-id="7977e-131">**Enterprise Voice**</span></span>
  
- <span data-ttu-id="7977e-p109">在“**启用企业语音的用户**”中，键入启用企业语音的用户的百分比。默认值为 60%。</span><span class="sxs-lookup"><span data-stu-id="7977e-p109">In **Users enabled for Enterprise Voice**, type the percentage of your users enabled for Enterprise Voice. The default is 60%.</span></span> 
    
- <span data-ttu-id="7977e-p110">在“**每个用户每小时的平均呼叫数（峰值）**”中，键入你预计峰值负载时段内每小时参与用户的平均呼叫数。默认值为 4。</span><span class="sxs-lookup"><span data-stu-id="7977e-p110">In **Average number of calls per user per hour (peak)**, type the number of calls per hour you expect the average user to participate in during times of peak load. The default is 4.</span></span> 
    
- <span data-ttu-id="7977e-p111">在“**使用媒体旁路的呼叫百分比**”中，键入由你的用户拨打的、将绕过中介服务器的呼叫百分比。默认值为 65%，但是如果你的用户所在地理位置较为宽广或者在家工作的用户较多，则该值可能较低。</span><span class="sxs-lookup"><span data-stu-id="7977e-p111">In **Percentage of calls that use media bypass**, type the percentage of calls placed by your users that will bypass the Mediation Server. The default is 65%, but could be lower if you are spread out geographically or have a large percentage of users who work from home.</span></span>
    
- <span data-ttu-id="7977e-138">**语音用户参与 UC-PSTN 呼叫的百分比**，键入组织的呼叫即 UC PSTN 电话呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="7977e-138">In **Percentage of voice users involved in UC-PSTN calls**, type the percentage of your organization's calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="7977e-139">默认值为 60%。</span><span class="sxs-lookup"><span data-stu-id="7977e-139">The default is 60%.</span></span>
    
- <span data-ttu-id="7977e-p113">在“**UC-UC 呼叫中涉及的语音用户百分比**”中，显示启用了企业语音并且只将启用 UC-UC 呼叫的用户百分比。此数目基于你对“**启用 UC-PSTN 呼叫的语音用户百分比**”输入的内容进行计算。</span><span class="sxs-lookup"><span data-stu-id="7977e-p113">**Percentage of voice users involved in UC-UC calls** shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls. This number is calculated based on what you input for **Percentage of voice users enabled for UC-PSTN calls**.</span></span> 
    
  <span data-ttu-id="7977e-142">**会议**</span><span class="sxs-lookup"><span data-stu-id="7977e-142">**Conferencing**</span></span>
  
- <span data-ttu-id="7977e-p114">在“**并发会议中的用户百分比**”中，键入将同时参与会议的用户百分比。默认值为 5%。</span><span class="sxs-lookup"><span data-stu-id="7977e-p114">In **Percentage of users in concurrent conferences**, type the percentage of users who will be participating in conferences at the same time. The default is 5%.</span></span> 
    
- <span data-ttu-id="7977e-p115">在“**仅使用组 IM（无语音）的会议百分比**”中，键入会议仅涉及即时消息而不包括音频的会议百分比。默认值为 10%。</span><span class="sxs-lookup"><span data-stu-id="7977e-p115">In **Percentage of conferences with group IM only (no voice)**, type the percentage of conferences that will involve instant messaging only and do not include audio. The default is 10%</span></span>
    
- <span data-ttu-id="7977e-p116">在“**使用电话拨入式会议的用户百分比**”中，键入会议中一次使用电话拨入式会议的参与者的百分比。默认值为 15%。</span><span class="sxs-lookup"><span data-stu-id="7977e-p116">In **Percentage of users using dial-in conferencing**, type the percentage of participants in conferences who will be using dial-in conferencing at one time. The default is 15%.</span></span>
    
- <span data-ttu-id="7977e-149">在“**使用语音的会议百分比**”中，键入将包括音频的会议百分比。</span><span class="sxs-lookup"><span data-stu-id="7977e-149">In **Percentage of conferences using voice**, type the percentage of conferences that will include audio.</span></span> 
    
  - <span data-ttu-id="7977e-150">如果 20% 的语音会议也将包括普通视频，请选择“**包括视频（无多视图）**”复选框。</span><span class="sxs-lookup"><span data-stu-id="7977e-150">If 20% of your voice conferences will also include regular video, select the **Including video (no Multi View)** check box.</span></span>
    
  - <span data-ttu-id="7977e-151">如果 20% 的会议也将包括多视图视频，请选择“**包括多视图**”复选框。</span><span class="sxs-lookup"><span data-stu-id="7977e-151">If 20% of your conferences will also include Multi-View video, select the **Including Multi View** check box.</span></span>
    
  - <span data-ttu-id="7977e-152">如果 50%的语音会议也将包括应用程序共享，选择**包括应用程序共享**复选框。</span><span class="sxs-lookup"><span data-stu-id="7977e-152">If 50% of your voice conferences will also include application sharing, select the **Including application sharing** check box.</span></span>
    
  - <span data-ttu-id="7977e-153">如果 20% 的语音会议包括数据上载（如 PowerPoint 演示文稿），请选择“**包括 Web 会议**”复选框。</span><span class="sxs-lookup"><span data-stu-id="7977e-153">If 20% of your voice conferences include data uploads, such as PowerPoint presentations, select the **Including web conferencing** check box.</span></span>
    
  <span data-ttu-id="7977e-154">**移动性**</span><span class="sxs-lookup"><span data-stu-id="7977e-154">**Mobility**</span></span>
  
- <span data-ttu-id="7977e-155">**为 Mobility 启用的用户的百分比**，键入您的用户将能够使用移动设备的企业服务器连接到 Skype 的百分比。</span><span class="sxs-lookup"><span data-stu-id="7977e-155">In **Percentage of users enabled for Mobility**, type the percentage of your users who will be enabled to connect to Skype for Business Server using mobile devices.</span></span> <span data-ttu-id="7977e-156">默认值为 40%。</span><span class="sxs-lookup"><span data-stu-id="7977e-156">The default is 40%.</span></span> 
    
<span data-ttu-id="7977e-157">在你输入所有必要信息之后，容量计算器将估计你的要求。</span><span class="sxs-lookup"><span data-stu-id="7977e-157">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="7977e-158">黄色的单元格的 CPU、 内存和带宽要求基于业务服务器性能实验 Skype 中执行的测试显示计算的值。</span><span class="sxs-lookup"><span data-stu-id="7977e-158">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Skype for Business Server performance labs.</span></span> <span data-ttu-id="7977e-159">这些数字仅供参考，并没有针对所有单个变体进行测试和验证。</span><span class="sxs-lookup"><span data-stu-id="7977e-159">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="7977e-160">将计算以下值：</span><span class="sxs-lookup"><span data-stu-id="7977e-160">The following values are calculated:</span></span> 
  
- <span data-ttu-id="7977e-161">**前端 CPU**：当与测试中使用的服务器规格相同的一个前端服务器处理整个负载时的 CPU 使用百分比（请参阅本文末尾的说明）。</span><span class="sxs-lookup"><span data-stu-id="7977e-161">**Front End CPU**: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in testing (see the description at the end of this article).</span></span>
    
- <span data-ttu-id="7977e-162">**网络 (Mbps)**：对应工作负载的带宽要求 (Mbps)。</span><span class="sxs-lookup"><span data-stu-id="7977e-162">**Network in Mbps**: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>
    
- <span data-ttu-id="7977e-163">**内存 (GB)**：对应工作负载所需的内存 (GB)。</span><span class="sxs-lookup"><span data-stu-id="7977e-163">**Memory in GB**: Memory required in gigabytes (GB) for the corresponding workload.</span></span>
    
<span data-ttu-id="7977e-164">绿色单元格显示为您输入的使用模型提供的建议。</span><span class="sxs-lookup"><span data-stu-id="7977e-164">The green cells show recommendations for the usage model that you entered.</span></span> 
  
- <span data-ttu-id="7977e-165">**总前端服务器**： 物理服务器所需数量的基于专用服务器业务服务器运行 Skype，与双处理器，十六核、 2,260 兆周。</span><span class="sxs-lookup"><span data-stu-id="7977e-165">**Total Front End Servers**: The number of physical servers required are based on dedicated servers running Skype for Business Server with dual processor, hex-core, with 2,260 megacycles.</span></span>
    
    <span data-ttu-id="7977e-166">请注意，建议启用超线程，它经过证明可改进支持音频/视频的服务器的性能。</span><span class="sxs-lookup"><span data-stu-id="7977e-166">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>
    
- <span data-ttu-id="7977e-p119">**边缘服务器**：所需的边缘服务器数目基于通过边缘服务器进行通信的所有并发用户的 30% 确定。此百分比不可在计算器中更改。</span><span class="sxs-lookup"><span data-stu-id="7977e-p119">**Edge Servers**: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers. This percentage cannot be changed in the calculator.</span></span> 
    
- <span data-ttu-id="7977e-169">**存档/呼叫详细记录/用户体验质量服务存储**：存档或监视功能（如果你的组织已启用）所需的存储数。</span><span class="sxs-lookup"><span data-stu-id="7977e-169">**Archiving/Call Detail Recording/Quality of Experience services Store**: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>
    
- <span data-ttu-id="7977e-170">**所需的后端数据库服务器（需要池）**：支持所选工作负载所需的后端数据库服务器数目。</span><span class="sxs-lookup"><span data-stu-id="7977e-170">**Back End Database Server Required (Pools Required)**: The number of back-end database servers required to support the selected workload.</span></span>
    
<span data-ttu-id="7977e-171">此外，在“前端服务器总数”旁边的行中，针对综合的所有计划工作负载提供了有关您的服务器和网络上的负载的更多信息。</span><span class="sxs-lookup"><span data-stu-id="7977e-171">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>
  
- <span data-ttu-id="7977e-172">**平均 CPU 负载**：每个前端服务器的平均 CPU 使用。</span><span class="sxs-lookup"><span data-stu-id="7977e-172">**Average CPU Load**: The average CPU usage per Front End server.</span></span>
    
- <span data-ttu-id="7977e-173">**网络 (Mbps)**：支持你输入的使用模型所需的带宽分配。</span><span class="sxs-lookup"><span data-stu-id="7977e-173">**Network in Mbps**: The required bandwidth allocation to support the usage model that you entered.</span></span>
    
- <span data-ttu-id="7977e-174">**内存 (GB)**：每个前端服务器所需的内存 (GB)。</span><span class="sxs-lookup"><span data-stu-id="7977e-174">**Memory in GB**: Memory, in gigabytes, required for each Front End server.</span></span>
    
### <a name="adjusting-for-your-processors"></a><span data-ttu-id="7977e-175">针对处理器进行调整</span><span class="sxs-lookup"><span data-stu-id="7977e-175">Adjusting For Your Processors</span></span>

<span data-ttu-id="7977e-176">电子表格中的所有 CPU 使用数字都假设每台服务器具有双处理器、十六核 (2,260 GHz)、至少 32 GB 内存以及 8 个或以上 10,000-RPM 硬盘驱动器（至少 72 GB 的可用磁盘空间）。</span><span class="sxs-lookup"><span data-stu-id="7977e-176">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span> 
  
<span data-ttu-id="7977e-177">如果您的服务器具有不同的处理器，您可以根据您的硬件调整数字。</span><span class="sxs-lookup"><span data-stu-id="7977e-177">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>
  

