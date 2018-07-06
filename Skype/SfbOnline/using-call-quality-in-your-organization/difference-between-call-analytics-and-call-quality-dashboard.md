---
title: 呼叫分析和呼叫质量仪表板
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
description: 了解有关呼叫分析和呼叫质量仪表板以及何时使用它们来监视和解决 Skype for Business 中的呼叫质量问题。
ms.openlocfilehash: 3871db21fef268f9589246b31ee285aa117d0412
ms.sourcegitcommit: 26d93a15c9d4704c08f3fabc5635839ce2456b2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "20205083"
---
# <a name="call-analytics-and-call-quality-dashboard"></a><span data-ttu-id="b8689-103">呼叫分析和呼叫质量仪表板</span><span class="sxs-lookup"><span data-stu-id="b8689-103">Call Analytics and Call Quality Dashboard</span></span>

<span data-ttu-id="b8689-104">Microsoft 团队和 for Business 的 Skype 提供两种方法可以监视和解决呼叫质量问题： 呼叫分析和呼叫质量仪表板。</span><span class="sxs-lookup"><span data-stu-id="b8689-104">Microsoft Teams and Skype for Business give you two ways to monitor and troubleshoot call-quality problems: Call Analytics and Call Quality Dashboard.</span></span> <span data-ttu-id="b8689-105">本文介绍这两类，并告诉您何时使用每个。</span><span class="sxs-lookup"><span data-stu-id="b8689-105">This article describes both and tells you when to use each one.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b8689-106">呼叫分析现已在 Microsoft 团队和 Skype 的业务管理中心，网址为https://admin.teams.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="b8689-106">Call Analytics is now available in the Microsoft Teams and Skype for Business admin center at https://admin.teams.microsoft.com.</span></span> <span data-ttu-id="b8689-107">调用分析中的可用仅最近 30 天的数据。</span><span class="sxs-lookup"><span data-stu-id="b8689-107">Only last 30 days of data is available in Call Analytics.</span></span>
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a><span data-ttu-id="b8689-108">什么是呼叫分析，我何时应使用它？</span><span class="sxs-lookup"><span data-stu-id="b8689-108">What's Call Analytics, and when should I use it?</span></span>

<span data-ttu-id="b8689-109">呼叫分析显示设备、 网络和与特定的呼叫和会议中每个用户的 Microsoft 团队或 Skype 业务帐户相关的连接的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="b8689-109">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user in a Microsoft Teams or Skype for Business account.</span></span> <span data-ttu-id="b8689-110">如果您是 Office 365 管理员，您可以使用调用分析解决的 Microsoft 团队和 Skype for Business 中的呼叫质量和连接问题。</span><span class="sxs-lookup"><span data-stu-id="b8689-110">If you're an Office 365 admin, you can use Call Analytics to troubleshoot call quality and connection problems in Microsoft Teams and Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="b8689-111">帮助台代理权限和网络拓扑上载中将提供新的管理门户在几个月。</span><span class="sxs-lookup"><span data-stu-id="b8689-111">Helpdesk agent permissions and network topology upload will be available in the new admin portal in the coming months.</span></span>

<span data-ttu-id="b8689-112">如果您希望非管理员，例如从外部供应商，帮助台代理用于呼叫的分析，就可以分配权限，以便他们可以使用调用分析，但不是能访问业务管理中心的 Skype 的其余部分：</span><span class="sxs-lookup"><span data-stu-id="b8689-112">If you want non-admins, such as helpdesk agents from an external vendor, to use Call Analytics, you can assign permissions so that they can use Call Analytics but they can't access the rest of the Skype for Business Admin center:</span></span> 
  
- <span data-ttu-id="b8689-113">**第 1 层权限的帮助台代理**： 代理，请参阅一组有限的数据和呼叫分析中的个人身份信息 (PII)。</span><span class="sxs-lookup"><span data-stu-id="b8689-113">**Helpdesk agents with Tier 1 permissions**: Agents see a limited set of data and personally identifiable information (PII) in Call Analytics.</span></span> <span data-ttu-id="b8689-114">它们可以解决呼叫，但它们将交给会议问题的第 2 层代理。</span><span class="sxs-lookup"><span data-stu-id="b8689-114">They can troubleshoot calls, but they will hand off problems with meetings to a Tier 2 agent.</span></span>
    
- <span data-ttu-id="b8689-115">**第 2 层权限的帮助台代理**： 代理，请参阅呼叫分析中的所有可用数据和解决呼叫和会议。</span><span class="sxs-lookup"><span data-stu-id="b8689-115">**Helpdesk agents with Tier 2 permissions**: Agents see all available data in Call Analytics and troubleshoot both calls and meetings.</span></span> <span data-ttu-id="b8689-116">拥有完全访问呼叫日志和客户信息。</span><span class="sxs-lookup"><span data-stu-id="b8689-116">They have full access to call logs and customer information.</span></span>
    
<span data-ttu-id="b8689-117">有关设置呼叫分析的详细信息，请参阅[Set up 商业调用分析的 Skype](set-up-call-analytics.md)。</span><span class="sxs-lookup"><span data-stu-id="b8689-117">For details about setting up Call Analytics, see [Set up Skype for Business Call Analytics](set-up-call-analytics.md).</span></span> <span data-ttu-id="b8689-118">有关帮助台代理与呼叫分析的工作原理的详细信息，请参阅[使用呼叫分析解决质量欠佳的呼叫质量](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="b8689-118">For more information about how Helpdesk agents can work with Call Analytics, see [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a><span data-ttu-id="b8689-119">什么是呼叫质量仪表板中，以及何时使用它？</span><span class="sxs-lookup"><span data-stu-id="b8689-119">What's the Call Quality Dashboard, and when should I use it?</span></span>

<span data-ttu-id="b8689-120">呼叫分析为您提供了有关呼叫质量用户遇到详细的具体信息。</span><span class="sxs-lookup"><span data-stu-id="b8689-120">Call Analytics gives you detailed, specific information about the call quality experienced by users.</span></span> <span data-ttu-id="b8689-121">为何用户 Tony Smith 未有此下午质量欠佳的呼叫？</span><span class="sxs-lookup"><span data-stu-id="b8689-121">Why did user Tony Smith have a poor call this afternoon?</span></span> <span data-ttu-id="b8689-122">使用呼叫分析，Microsoft 团队或业务管理员或培训帮助台代理的 Skype 可以调查设备、 网络、 连接和与 Tony 的呼叫相关的其他因素。</span><span class="sxs-lookup"><span data-stu-id="b8689-122">Using Call Analytics, a Microsoft Teams or Skype for Business admin or trained helpdesk agent can investigate the device, network, connectivity, and other factors related to Tony's call.</span></span>
  
<span data-ttu-id="b8689-123">其中 CA 旨在帮助管理员和帮助台代理排除特定的呼叫，呼叫质量问题呼叫质量仪表板 (CQD) 旨在帮助 Skype 对于业务管理员和网络工程师优化网络。</span><span class="sxs-lookup"><span data-stu-id="b8689-123">Where CA is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, the Call Quality Dashboard (CQD) is designed to help Skype for Business admins and network engineers optimize a network.</span></span> <span data-ttu-id="b8689-124">CQD 从特定的用户将焦点移，而是检查业务组织整个 Skype 聚合信息。</span><span class="sxs-lookup"><span data-stu-id="b8689-124">CQD shifts focus from specific users and instead looks at aggregate information for an entire Skype for Business organization.</span></span> 
  
<span data-ttu-id="b8689-125">也许 Tony 的质量欠佳的呼叫质量是由于还影响多个其他用户的网络问题。</span><span class="sxs-lookup"><span data-stu-id="b8689-125">Maybe Tony's poor call quality is due to a network issue that's also affecting many other users.</span></span> <span data-ttu-id="b8689-126">Tony 的单个呼叫体验不显示在 CQD，但捕获 for Business 使用 Skype 进行的呼叫的总体质量。</span><span class="sxs-lookup"><span data-stu-id="b8689-126">Tony's individual call experience isn't visible in CQD, but the overall quality of calls made using Skype for Business is captured.</span></span> <span data-ttu-id="b8689-127">与 CQD，总体模式可能成为明显，允许网络工程师进行的呼叫质量的明智的评估。</span><span class="sxs-lookup"><span data-stu-id="b8689-127">With the CQD, overall patterns may become apparent, allowing network engineers to make informed assessments of call quality.</span></span> <span data-ttu-id="b8689-128">CQD 提供报告为您提供深入的呼叫质量指标的总体呼叫质量、 服务器到客户端和客户端客户端流和语音质量[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)。</span><span class="sxs-lookup"><span data-stu-id="b8689-128">CQD provides reports of call quality metrics that give you insights into overall call quality, server-client and client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![呼叫质量仪表板中的 Business Admin Center Skype 的屏幕截图。](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
<span data-ttu-id="b8689-131">有关详细信息，请参阅[业务 online Skype 调用质量仪表板的功能](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD)。</span><span class="sxs-lookup"><span data-stu-id="b8689-131">For more details, see [Features of the Call Quality Dashboard for Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span></span>
  
<span data-ttu-id="b8689-132">呼叫分析和 CQD 并行运行和可在独立或一起使用。</span><span class="sxs-lookup"><span data-stu-id="b8689-132">Call Analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="b8689-133">例如，假设 1 层代理确定所需解决呼叫问题的更多帮助。</span><span class="sxs-lookup"><span data-stu-id="b8689-133">For example, say a Tier 1 agent determines that they need more help troubleshooting a call problem.</span></span> <span data-ttu-id="b8689-134">第 1 层代理传入呼叫发送给第 2 层代理，第 1 层代理比呼叫分析中有权访问的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b8689-134">The Tier 1 agent passes the call to a Tier 2 agent, who has access to more information in Call Analytics than the Tier 1 agent.</span></span> <span data-ttu-id="b8689-135">反过来，第 2 层代理可以通知问题的网络工程师。</span><span class="sxs-lookup"><span data-stu-id="b8689-135">In turn, the Tier 2 agent can alert a network engineer to an issue.</span></span> <span data-ttu-id="b8689-136">网络工程师可以检查 CQD 以查看整个网站相关问题可能是参与呼叫问题的原因。</span><span class="sxs-lookup"><span data-stu-id="b8689-136">The network engineer may check CQD to see if an overall site-related issue could be a contributing cause of call problems.</span></span>
  
<span data-ttu-id="b8689-137">有关 CQD 的详细信息，请参阅[打开和使用的 Microsoft 团队和 Skype 业务 online 呼叫质量仪表板](turning-on-and-using-call-quality-dashboard.md)和[维度和度量值的 Microsoft 团队和 Skype 业务 online 呼叫质量仪表板中可用](dimensions-and-measures-available-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="b8689-137">For more information about CQD, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md) and [Dimensions and measures available in Call Quality Dashboard for Microsoft Teams and Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b8689-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="b8689-138">Related topics</span></span>
[<span data-ttu-id="b8689-139">设置 Skype for Business 通话分析</span><span class="sxs-lookup"><span data-stu-id="b8689-139">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="b8689-140">使用通话分析解决 Skype for Business 通话质量不佳的问题</span><span class="sxs-lookup"><span data-stu-id="b8689-140">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

  
 
