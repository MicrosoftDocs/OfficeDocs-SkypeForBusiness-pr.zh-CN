---
title: 监控服务器内存容量限制 Skype 业务服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 摘要： 了解如何针对业务服务器监视的 Skype 中的服务器内存容量限制。
ms.openlocfilehash: 05913ea5b32a9a40d7c577c4a0795ccb07db211f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20978698"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a><span data-ttu-id="3cc50-103">监控服务器内存容量限制 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="3cc50-103">Monitor for server memory capacity limits in Skype for Business Server</span></span>
 
<span data-ttu-id="3cc50-104">**摘要：** 了解如何针对业务服务器监视的 Skype 中的服务器内存容量限制。</span><span class="sxs-lookup"><span data-stu-id="3cc50-104">**Summary:** Learn how to monitor for server memory capacity limits in Skype for Business Server.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3cc50-105">容量规划是指本主题中的信息仅适用于 Lync 2010 移动客户端和 Mobility Service (Mcx)。</span><span class="sxs-lookup"><span data-stu-id="3cc50-105">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="3cc50-106">由 Lync Server 2013 规划工具提供容量规划的统一通信 Web API (UCWA)，Lync 2013 移动客户端，使用。</span><span class="sxs-lookup"><span data-stu-id="3cc50-106">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span> 

> [!NOTE]
> <span data-ttu-id="3cc50-107">MCX 旧的移动客户端支持不再可用的业务服务器 2019 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="3cc50-107">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="3cc50-108">您的用户需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="3cc50-108">Your users will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="3cc50-109">两个移动性能计数器可以帮助您确定当前使用情况并帮助您规划业务服务器 Mobility Service (Mcx)，以及为 UCWA，监视内存使用量 Skype 的容量。</span><span class="sxs-lookup"><span data-stu-id="3cc50-109">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Skype for Business Server Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="3cc50-110">UCWA，对于计数器类别是**LS:WEB-UCWA**。</span><span class="sxs-lookup"><span data-stu-id="3cc50-110">For UCWA, the counter category is **LS:WEB - UCWA**.</span></span> <span data-ttu-id="3cc50-111">对于 Mobility Service (Mcx)，计数器类别为“**LS:WEB - 移动通信服务**”。</span><span class="sxs-lookup"><span data-stu-id="3cc50-111">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="3cc50-112">要监控的计数器包括：</span><span class="sxs-lookup"><span data-stu-id="3cc50-112">The counters to monitor are:</span></span>
  
- <span data-ttu-id="3cc50-113">**Currently Active Session Count with Active Presence Subscriptions**，它是当前通过 UCWA 或 Mobility Service (Mcx) 注册的终结点的数目，这些终结点具有活动状态订阅（始终连接的移动用户的数目）</span><span class="sxs-lookup"><span data-stu-id="3cc50-113">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>
    
- <span data-ttu-id="3cc50-114">**Currently Active Session Count**，它是当前通过 UCWA 或 Mobility Service 注册的终结点的数目</span><span class="sxs-lookup"><span data-stu-id="3cc50-114">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>
    
<span data-ttu-id="3cc50-115">如果**当前 with Active Presence Subscriptions 的 Active Session Count**和**当前 Active Session Count**之间的差异随着时间的推移小，这意味着大多数移动设备用户具有的始终连接的设备，例如 Android 或Nokia 移动设备 （对于仅 Mcx)。</span><span class="sxs-lookup"><span data-stu-id="3cc50-115">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="3cc50-116">UCWA 始终连接的设备包括运行 Lync 2013 移动客户端的 Apple 和 Android 设备）。</span><span class="sxs-lookup"><span data-stu-id="3cc50-116">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="3cc50-117">如果**当前 Active Session Count**是远大于**当前 with Active Presence Subscriptions 的 Active Session Count**，这表明更多用户正在使用背景终结点设备，如 Apple iOS 设备或下的 Windows PhoneMcx。</span><span class="sxs-lookup"><span data-stu-id="3cc50-117">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="3cc50-118">（Windows Phone 是将注册为此的唯一 Lync 2013 移动客户端）。</span><span class="sxs-lookup"><span data-stu-id="3cc50-118">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>
  
<span data-ttu-id="3cc50-119">您应根据您的预期的用法、 容量规划结果和实时监控的**当前 with Active Presence Subscriptions 的 Active Session Count**和**当前 Active Session Count**性能计数器设置限制Mobility Service 和其他前端服务器计数器。</span><span class="sxs-lookup"><span data-stu-id="3cc50-119">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="3cc50-120">您设置的限制应允许您计算服务器容量并在超出容量时发出警报。</span><span class="sxs-lookup"><span data-stu-id="3cc50-120">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>
  
<span data-ttu-id="3cc50-121">若要确定适当的限制，您需要先确定多少内存有 Mobility Service 的前端服务器上可用。</span><span class="sxs-lookup"><span data-stu-id="3cc50-121">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="3cc50-122">请监控计数器以根据以下公式确定您需要何时规划额外的容量：</span><span class="sxs-lookup"><span data-stu-id="3cc50-122">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>
  
<span data-ttu-id="3cc50-123">总内存使用情况 Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024年 ***当前 with Active Presence Subscriptions 的 Active Session Count** + 400 / 1024年 * (**当前 Active Session Count** - **与当前活动会话的计数活动状态订阅**)</span><span class="sxs-lookup"><span data-stu-id="3cc50-123">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 * **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 * ( **Currently Active Session Count** - **Currently Active Session Count with Active Presence Subscriptions**)</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3cc50-124">Microsoft Lync Server 2010 容量计算器是使用所有启用计划程序，以确定要求将哪些业务服务器，其中包括 CPU、 内存和硬盘驱动器上的 Skype 的公式进行预填充电子表格。</span><span class="sxs-lookup"><span data-stu-id="3cc50-124">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the Skype for Business servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="3cc50-125">您可以[下载电子表格和关联的文档](https://go.microsoft.com/fwlink/p/?LinkID=212657)。</span><span class="sxs-lookup"><span data-stu-id="3cc50-125">You can [download the spreadsheet and an associated document](https://go.microsoft.com/fwlink/p/?LinkID=212657).</span></span> 
  
<span data-ttu-id="3cc50-126">前端服务器所需内存不足，无法在故障转移的情况下支持 Mobility Service。</span><span class="sxs-lookup"><span data-stu-id="3cc50-126">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="3cc50-127">通过使用**Memory\Available Mbytes**计数器，或通过使用前面提到的来规划您预期 Mobility Service 若要使用的内存量的计算公式，您可以监视前端服务器上的当前可用内存。</span><span class="sxs-lookup"><span data-stu-id="3cc50-127">You can monitor the current available memory on the Front End Server by using the **Memory\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>
  
<span data-ttu-id="3cc50-128">如果在前端服务器上的可用内存量低于 1,500 MB 规划预期数量的移动用户时，您需要添加更多的硬件支持 Mobility Service。</span><span class="sxs-lookup"><span data-stu-id="3cc50-128">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="3cc50-129">有关详细信息，请参阅操作文档中的[Skype 业务服务器中的性能监视器移动](monitor-mobility-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc50-129">For more details, see [Monitor mobility for performance in Skype for Business Server](monitor-mobility-performance.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3cc50-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cc50-130">See also</span></span>

[<span data-ttu-id="3cc50-131">监视移动性的 Skype 业务服务器的性能</span><span class="sxs-lookup"><span data-stu-id="3cc50-131">Monitor mobility for performance in Skype for Business Server</span></span>](monitor-mobility-performance.md)