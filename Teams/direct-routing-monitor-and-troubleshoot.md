---
title: 对直接路由进行监视和故障排除
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何监视和排查直接路由配置问题，包括会话边界控制器、直接路由组件和电信中继。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74a67493fa2f9647e6cd0364bb4c9d6a3c05e48a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121400"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="84bad-103">对直接路由进行监视和故障排除</span><span class="sxs-lookup"><span data-stu-id="84bad-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="84bad-104">本文介绍如何监视和排查直接路由配置问题。</span><span class="sxs-lookup"><span data-stu-id="84bad-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="84bad-105">使用直接路由进行和接收调用的能力涉及以下组件：</span><span class="sxs-lookup"><span data-stu-id="84bad-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="84bad-106">会话边界控制器 (SDC) </span><span class="sxs-lookup"><span data-stu-id="84bad-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="84bad-107">Microsoft 云中的直接路由组件</span><span class="sxs-lookup"><span data-stu-id="84bad-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="84bad-108">电信中继</span><span class="sxs-lookup"><span data-stu-id="84bad-108">Telecom trunks</span></span> 

<span data-ttu-id="84bad-109">如果难以排查问题，可以与 SBC 供应商或 Microsoft 建立支持案例。</span><span class="sxs-lookup"><span data-stu-id="84bad-109">If you have difficulties troubleshooting issues, you can open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="84bad-110">Microsoft 正在努力提供更多用于故障排除和监视的工具。</span><span class="sxs-lookup"><span data-stu-id="84bad-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="84bad-111">请定期查看文档了解更新。</span><span class="sxs-lookup"><span data-stu-id="84bad-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="84bad-112">使用会话启动协议监视会话边界控制器的可用性 (SIP) 选项消息</span><span class="sxs-lookup"><span data-stu-id="84bad-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="84bad-113">直接路由使用会话边界控制器发送的 SIP 选项来监视 SBC 运行状况。</span><span class="sxs-lookup"><span data-stu-id="84bad-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="84bad-114">租户管理员无需执行任何操作来启用 SIP 选项监视。</span><span class="sxs-lookup"><span data-stu-id="84bad-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="84bad-115">做出路由决策时，会考虑收集的信息。</span><span class="sxs-lookup"><span data-stu-id="84bad-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="84bad-116">例如，对于特定用户，如果有几个 SBC 可用于路由呼叫，则直接路由会考虑从每个 SBC 收到的 SIP 选项信息来确定路由。</span><span class="sxs-lookup"><span data-stu-id="84bad-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="84bad-117">下图显示了配置的示例：</span><span class="sxs-lookup"><span data-stu-id="84bad-117">The following diagram shows an example of the configuration:</span></span> 

![SIP 选项配置示例](media/sip-options-config-example.png)

<span data-ttu-id="84bad-119">当用户调用号码 +1 425 时 \<any seven digits> ，直接路由将评估路由。</span><span class="sxs-lookup"><span data-stu-id="84bad-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="84bad-120">路由中有两个 SDC：sbc1.contoso.com 和 sbc2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="84bad-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="84bad-121">这两个 SDC 在路由中具有相同的优先级。</span><span class="sxs-lookup"><span data-stu-id="84bad-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="84bad-122">在选取 SBC 之前，路由机制根据 SBC 上次发送 SIP 选项的时间评估 SBC 的运行状况。</span><span class="sxs-lookup"><span data-stu-id="84bad-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="84bad-123">如果发送呼叫时的统计数据显示 SBC 每分钟发送一次选项，则认为 SBC 正常。</span><span class="sxs-lookup"><span data-stu-id="84bad-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends options every minute.</span></span>  

<span data-ttu-id="84bad-124">进行调用时，将应用以下逻辑：</span><span class="sxs-lookup"><span data-stu-id="84bad-124">When a call is made, the following logic applies:</span></span>

- <span data-ttu-id="84bad-125">SBC 在上午 11：00 配对。</span><span class="sxs-lookup"><span data-stu-id="84bad-125">The SBC was paired at 11:00 AM.</span></span>  
- <span data-ttu-id="84bad-126">SBC 在上午 11：01、上午 11：02 发送选项，等等。</span><span class="sxs-lookup"><span data-stu-id="84bad-126">The SBC sends options at 11:01 AM, 11:02 AM, and so on.</span></span>  
- <span data-ttu-id="84bad-127">在 11：15，用户进行调用，路由机制选择此 SBC。</span><span class="sxs-lookup"><span data-stu-id="84bad-127">At 11:15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="84bad-128">直接路由采用常规间隔选项三次 (常规间隔为一分钟) 。</span><span class="sxs-lookup"><span data-stu-id="84bad-128">Direct Routing takes the regular interval options three times (the regular interval is one minute).</span></span> <span data-ttu-id="84bad-129">如果在过去三分钟内发送了选项，则 SBC 被视为正常。</span><span class="sxs-lookup"><span data-stu-id="84bad-129">If options were send during the last three minutes, the SBC is considered healthy.</span></span>

<span data-ttu-id="84bad-130">如果示例中的 SBC 在上午 11：12 到上午 11：15 之间的任意时间段发送了选项 (则调用) ，则被视为正常。</span><span class="sxs-lookup"><span data-stu-id="84bad-130">If the SBC in the example sent options at any period between 11:12 AM and 11:15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="84bad-131">如果没有，SBC 将从路由降级。</span><span class="sxs-lookup"><span data-stu-id="84bad-131">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="84bad-132">降级意味着不会先尝试 SBC。</span><span class="sxs-lookup"><span data-stu-id="84bad-132">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="84bad-133">例如，我们有一 sbc1.contoso.com sbc2.contoso.com 优先级的优先级。</span><span class="sxs-lookup"><span data-stu-id="84bad-133">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="84bad-134">如果 sbc1.contoso.com 如前文所述定期发送 SIP 选项，则将其降级。</span><span class="sxs-lookup"><span data-stu-id="84bad-134">If sbc1.contoso.com does not send SIP options on a regular interval as previously described, it is demoted.</span></span> <span data-ttu-id="84bad-135">接下来，sbc2.contoso.com 尝试进行调用。</span><span class="sxs-lookup"><span data-stu-id="84bad-135">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="84bad-136">如果 sbc2.contoso.con 无法传递调用，则 sbc1.contoso.com (降级) 重试，然后再生成失败。</span><span class="sxs-lookup"><span data-stu-id="84bad-136">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

<span data-ttu-id="84bad-137">如果一 (两个或多个) SDC 被视为正常且相等，Fisher-Yates随机执行以在 SDC 之间分配调用。</span><span class="sxs-lookup"><span data-stu-id="84bad-137">If two (or more) SBCs in one route are considered healthy and equal, Fisher-Yates shuffle is applied to distribute the calls between the SBCs.</span></span>

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="84bad-138">监视呼叫质量分析仪表板和 SBC 日志</span><span class="sxs-lookup"><span data-stu-id="84bad-138">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="84bad-139">在某些情况下，尤其是在初始配对期间，可能会存在与 SDC 或直接路由服务配置错误相关的问题。</span><span class="sxs-lookup"><span data-stu-id="84bad-139">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs or the Direct Routing service.</span></span> 

<span data-ttu-id="84bad-140">可以使用以下工具监视配置：</span><span class="sxs-lookup"><span data-stu-id="84bad-140">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="84bad-141">呼叫质量仪表板</span><span class="sxs-lookup"><span data-stu-id="84bad-141">Call Quality Dashboard</span></span> 
- <span data-ttu-id="84bad-142">SBC 日志</span><span class="sxs-lookup"><span data-stu-id="84bad-142">SBC logs</span></span> 

<span data-ttu-id="84bad-143">直接路由服务向调用分析或 SBC 日志报告非常描述性的错误代码。</span><span class="sxs-lookup"><span data-stu-id="84bad-143">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="84bad-144">呼叫质量仪表板提供有关呼叫质量和可靠性的信息。</span><span class="sxs-lookup"><span data-stu-id="84bad-144">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="84bad-145">若要详细了解如何使用呼叫分析排查问题，请参阅为 Microsoft Teams 和[Skype for Business Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)启用和使用呼叫质量仪表板和使用呼叫分析来排查呼叫[质量不佳的问题](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)。</span><span class="sxs-lookup"><span data-stu-id="84bad-145">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="84bad-146">在呼叫失败时，呼叫分析提供标准 SIP 代码来帮助进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="84bad-146">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![呼叫失败的示例 SIP 代码](media/failed-response-code.png)

<span data-ttu-id="84bad-148">但是，只有当调用到达直接路由的内部组件并失败时，调用分析才能提供帮助。</span><span class="sxs-lookup"><span data-stu-id="84bad-148">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="84bad-149">如果 SBC 配对问题或 SIP"邀请"被拒绝的问题 (例如，中继 FQDN 的名称未正确配置) ，呼叫分析将无用。</span><span class="sxs-lookup"><span data-stu-id="84bad-149">In case of issues with SBC pairing or issues where SIP "Invite" was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="84bad-150">在这种情况下，请参阅 SBC 日志。</span><span class="sxs-lookup"><span data-stu-id="84bad-150">In this case, refer to the SBC logs.</span></span> <span data-ttu-id="84bad-151">直接路由向 SDC 发送问题的详细说明;这些问题可以从 SBC 日志中读取。</span><span class="sxs-lookup"><span data-stu-id="84bad-151">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span>