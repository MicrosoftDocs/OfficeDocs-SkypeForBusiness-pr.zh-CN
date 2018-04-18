---
title: 调用分析和呼叫质量仪表板之间的区别是什么？
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 了解如何调用分析和呼叫质量控制板以及何时使用它们来监视并排除在业务的 Skype 通话质量问题。
ms.openlocfilehash: 869b4373d6e1bea65700532b52959aa2126d94d9
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="whats-the-difference-between-call-analytics-and-call-quality-dashboard"></a><span data-ttu-id="07c2f-103">调用分析和呼叫质量仪表板之间的区别是什么？</span><span class="sxs-lookup"><span data-stu-id="07c2f-103">What's the difference between Call Analytics and Call Quality Dashboard?</span></span>

<span data-ttu-id="07c2f-104">Skype 业务为您提供了两种方法可以监视并排除呼叫质量问题： 调用分析和呼叫质量仪表板。</span><span class="sxs-lookup"><span data-stu-id="07c2f-104">Skype for Business gives you two ways to monitor and troubleshoot call-quality problems: Call Analytics and Call Quality Dashboard.</span></span> <span data-ttu-id="07c2f-105">这篇文章介绍这两类，并告诉您何时使用每个。</span><span class="sxs-lookup"><span data-stu-id="07c2f-105">This article describes both and tells you when to use each one.</span></span>
  
> [!NOTE]
> <span data-ttu-id="07c2f-106">调用分析目前在预览中。</span><span class="sxs-lookup"><span data-stu-id="07c2f-106">Call Analytics is currently in preview.</span></span> <span data-ttu-id="07c2f-107">文本和此处所述的图像可能会不匹配您的体验。</span><span class="sxs-lookup"><span data-stu-id="07c2f-107">Text and images described here may not match your experience.</span></span> 
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a><span data-ttu-id="07c2f-108">调用的分析，是什么和什么时候应该使用它吗？</span><span class="sxs-lookup"><span data-stu-id="07c2f-108">What's Call Analytics, and when should I use it?</span></span>

<span data-ttu-id="07c2f-109">调用分析显示有关设备、 网络和连接与特定的电话和 Skype 业务帐户的每个用户的会议详细的信息。</span><span class="sxs-lookup"><span data-stu-id="07c2f-109">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user in a Skype for Business account.</span></span> <span data-ttu-id="07c2f-110">如果您是 Skype 业务管理员，可以使用调用分析诊断 Skype 业务呼叫质量和连接问题。</span><span class="sxs-lookup"><span data-stu-id="07c2f-110">If you're a Skype for Business admin, you can use Call Analytics to troubleshoot Skype for Business call quality and connection problems.</span></span>
  
<span data-ttu-id="07c2f-111">如果想让非管理员，帮助台代理从外部供应商，如用于调用的分析，您可以分配权限，以便他们可以使用调用分析但不是能访问业务管理中心的 Skype 的其余部分：</span><span class="sxs-lookup"><span data-stu-id="07c2f-111">If you want non-admins, such as helpdesk agents from an external vendor, to use Call Analytics, you can assign permissions so that they can use Call Analytics but they can't access the rest of the Skype for Business Admin center:</span></span> 
  
- <span data-ttu-id="07c2f-112">**使用第 1 层权限的帮助台代理**： 代理查看一组有限的数据和调用分析中的个人身份信息 (PII)。</span><span class="sxs-lookup"><span data-stu-id="07c2f-112">**Helpdesk agents with Tier 1 permissions**: Agents see a limited set of data and personally identifiable information (PII) in Call Analytics.</span></span> <span data-ttu-id="07c2f-113">它们可以解决电话，但他们将交接问题会议到第 2 层工程师。</span><span class="sxs-lookup"><span data-stu-id="07c2f-113">They can troubleshoot calls, but they will hand off problems with meetings to a Tier 2 agent.</span></span>
    
- <span data-ttu-id="07c2f-114">**第 2 层的权限与帮助台代理**： 代理查看所有可用的数据调用分析中，并解决联络和会议。</span><span class="sxs-lookup"><span data-stu-id="07c2f-114">**Helpdesk agents with Tier 2 permissions**: Agents see all available data in Call Analytics and troubleshoot both calls and meetings.</span></span> <span data-ttu-id="07c2f-115">它们具有完全访问权限来调用日志和客户信息。</span><span class="sxs-lookup"><span data-stu-id="07c2f-115">They have full access to call logs and customer information.</span></span>
    
<span data-ttu-id="07c2f-116">有关调用分析设置的详细信息，请参阅[设置业务调用分析的 Skype](set-up-call-analytics.md)。</span><span class="sxs-lookup"><span data-stu-id="07c2f-116">For details about setting up Call Analytics, see [Set up Skype for Business Call Analytics](set-up-call-analytics.md).</span></span> <span data-ttu-id="07c2f-117">有关如何帮助台代理调用分析处理的详细信息，请参阅[使用调用分析诊断较差的呼叫质量](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="07c2f-117">For more information about how Helpdesk agents can work with Call Analytics, see [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a><span data-ttu-id="07c2f-118">呼叫质量面板中，是什么和什么时候应该使用它吗？</span><span class="sxs-lookup"><span data-stu-id="07c2f-118">What's the Call Quality Dashboard, and when should I use it?</span></span>

<span data-ttu-id="07c2f-119">调用分析为您提供了有关用户遇到通话质量的详细的具体信息。</span><span class="sxs-lookup"><span data-stu-id="07c2f-119">Call Analytics gives you detailed, specific information about the call quality experienced by users.</span></span> <span data-ttu-id="07c2f-120">为什么用户 Tony Smith 未有差调用此下午？</span><span class="sxs-lookup"><span data-stu-id="07c2f-120">Why did user Tony Smith have a poor call this afternoon?</span></span> <span data-ttu-id="07c2f-121">使用调用分析，商业管理或经过培训的技术支持代理 Skype 可以调查设备、 网络、 连接性和与 Tony 的调用相关的其他因素。</span><span class="sxs-lookup"><span data-stu-id="07c2f-121">Using Call Analytics, a Skype for Business admin or trained helpdesk agent can investigate the device, network, connectivity, and other factors related to Tony's call.</span></span>
  
<span data-ttu-id="07c2f-122">其中 CA 旨在帮助管理员和帮助台代理解决特定呼叫，通话质量问题呼叫质量仪表板 (CQD) 旨在帮助 Skype 业务管理员和网络工程师优化网络。</span><span class="sxs-lookup"><span data-stu-id="07c2f-122">Where CA is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, the Call Quality Dashboard (CQD) is designed to help Skype for Business admins and network engineers optimize a network.</span></span> <span data-ttu-id="07c2f-123">CQD 从特定用户将焦点移，而是检查整个 Skype 业务组织的聚合信息。</span><span class="sxs-lookup"><span data-stu-id="07c2f-123">CQD shifts focus from specific users and instead looks at aggregate information for an entire Skype for Business organization.</span></span> 
  
<span data-ttu-id="07c2f-124">也许 Tony 的差的呼叫质量是由于网络问题，也影响许多其他用户。</span><span class="sxs-lookup"><span data-stu-id="07c2f-124">Maybe Tony's poor call quality is due to a network issue that's also affecting many other users.</span></span> <span data-ttu-id="07c2f-125">Tony 的单个呼叫体验 CQD 中, 看不到但被捕获的业务使用 Skype 电话的整体质量。</span><span class="sxs-lookup"><span data-stu-id="07c2f-125">Tony's individual call experience isn't visible in CQD, but the overall quality of calls made using Skype for Business is captured.</span></span> <span data-ttu-id="07c2f-126">使用 CQD，整体模式可能会变得明显，允许网络工程师进行明智的呼叫质量评估。</span><span class="sxs-lookup"><span data-stu-id="07c2f-126">With the CQD, overall patterns may become apparent, allowing network engineers to make informed assessments of call quality.</span></span> <span data-ttu-id="07c2f-127">CQD 提供呼叫质量测量数据，为您提供深入的洞察力的报告总体呼叫质量、 服务器端和客户端客户端流和语音质量[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)。</span><span class="sxs-lookup"><span data-stu-id="07c2f-127">CQD provides reports of call quality metrics that give you insights into overall call quality, server-client and client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![在业务管理中心的 Skype 通话质量仪表板的屏幕快照。](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
<span data-ttu-id="07c2f-130">有关更多详细信息，请参阅[的联机业务 Skype 呼叫质量仪表板的功能](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD)。</span><span class="sxs-lookup"><span data-stu-id="07c2f-130">For more details, see [Features of the Call Quality Dashboard for Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span></span>
  
<span data-ttu-id="07c2f-131">调用分析和 CQD 并行运行，而且可以单独或一起使用。</span><span class="sxs-lookup"><span data-stu-id="07c2f-131">Call Analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="07c2f-132">例如，假设第 1 层工程师确定他们需要诊断呼叫问题的更多帮助。</span><span class="sxs-lookup"><span data-stu-id="07c2f-132">For example, say a Tier 1 agent determines that they need more help troubleshooting a call problem.</span></span> <span data-ttu-id="07c2f-133">第 1 层工程师通过调用第 2 层工程师，第 1 层工程师比调用分析中具有访问权限的详细信息。</span><span class="sxs-lookup"><span data-stu-id="07c2f-133">The Tier 1 agent passes the call to a Tier 2 agent, who has access to more information in Call Analytics than the Tier 1 agent.</span></span> <span data-ttu-id="07c2f-134">反过来，第 2 层工程师可以提醒问题的网络工程师。</span><span class="sxs-lookup"><span data-stu-id="07c2f-134">In turn, the Tier 2 agent can alert a network engineer to an issue.</span></span> <span data-ttu-id="07c2f-135">网络工程师可能检查 CQD 整体网站有关的问题可能是特约呼叫问题的原因。</span><span class="sxs-lookup"><span data-stu-id="07c2f-135">The network engineer may check CQD to see if an overall site-related issue could be a contributing cause of call problems.</span></span>
  
<span data-ttu-id="07c2f-136">CQD 有关详细信息，请参阅[打开并使用 Microsoft 小组和 Skype 的在线业务的呼叫质量面板](turning-on-and-using-call-quality-dashboard.md)和[维度和度量值在 Microsoft 小组和 Skype 的在线业务呼叫质量仪表板中可用](dimensions-and-measures-available-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="07c2f-136">For more information about CQD, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md) and [Dimensions and measures available in Call Quality Dashboard for Microsoft Teams and Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="07c2f-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="07c2f-137">Related topics</span></span>
[<span data-ttu-id="07c2f-138">设置 Skype for Business 通话分析</span><span class="sxs-lookup"><span data-stu-id="07c2f-138">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="07c2f-139">使用通话分析解决 Skype for Business 通话质量不佳的问题</span><span class="sxs-lookup"><span data-stu-id="07c2f-139">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

  
 