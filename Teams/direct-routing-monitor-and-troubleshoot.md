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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: 本文介绍如何监视直接路由配置并对其进行故障排除。
ms.openlocfilehash: c1cb84cd8ee764c58441ad9d5d33f18b77336a40
ms.sourcegitcommit: 3197f3ffca2b2315be9fd0c702ccc8c87383c893
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2019
ms.locfileid: "35062376"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="5b0e6-103">对直接路由进行监视和故障排除</span><span class="sxs-lookup"><span data-stu-id="5b0e6-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="5b0e6-104">本文介绍如何监视直接路由配置并对其进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="5b0e6-105">使用直接路由拨打和接听电话的功能包括以下组件:</span><span class="sxs-lookup"><span data-stu-id="5b0e6-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="5b0e6-106">会话边框控制器 (SBCs)</span><span class="sxs-lookup"><span data-stu-id="5b0e6-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="5b0e6-107">在 Microsoft 云中直接路由组件</span><span class="sxs-lookup"><span data-stu-id="5b0e6-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="5b0e6-108">电信中继</span><span class="sxs-lookup"><span data-stu-id="5b0e6-108">Telecom trunks</span></span> 

<span data-ttu-id="5b0e6-109">如果您在解决问题时遇到困难, 请与 SBC 供应商或 Microsoft 打开支持案例。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-109">If you have difficulties troubleshooting issues, please open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="5b0e6-110">Microsoft 正在致力于为疑难解答和监视提供更多工具。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="5b0e6-111">请定期查看文档以获取更新。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="5b0e6-112">使用会话初始协议 (SIP) 选项消息监视会话边框控制器的可用性</span><span class="sxs-lookup"><span data-stu-id="5b0e6-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="5b0e6-113">直接路由使用由会话边界控制器发送的 SIP 选项监视 SBC 运行状况。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="5b0e6-114">租户管理员无需执行任何操作即可启用 SIP 选项监视。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="5b0e6-115">当做出路由决策时, 将考虑所收集的信息。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="5b0e6-116">例如, 如果对于特定用户, 有多种可用于路由呼叫的 SBCs, 直接路由将考虑从每个 SBC 收到的 SIP 选项信息来确定路由。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="5b0e6-117">下图显示了配置示例:</span><span class="sxs-lookup"><span data-stu-id="5b0e6-117">The following diagram shows an example of the configuration:</span></span> 

![SIP 选项配置示例](media/sip-options-config-example.png)

<span data-ttu-id="5b0e6-119">当用户拨打号码 + 1 425 \<> 任何七位数字时, 直接路由会评估路由。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="5b0e6-120">路由中有两个 SBCs: sbc1.contoso.com 和 sbc2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="5b0e6-121">两个 SBCs 在路由中具有同等优先级。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="5b0e6-122">在选取 SBC 之前, 路由机制会根据 SBC 何时发送 SIP 选项来评估 SBCs 的运行状况。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="5b0e6-123">如果发送呼叫时统计信息显示 SBC 按固定间隔发送选项, 则该 SBC 被认为状态良好。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends Options on a regular interval.</span></span>  

<span data-ttu-id="5b0e6-124">直接路由计算常规间隔, 方法是在发出呼叫并添加五分钟之前, 在 SBC 发送选项的两倍。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-124">Direct Routing calculates regular intervals by taking two times the average when the SBC sends options before making the call and adding five minutes.</span></span> 

<span data-ttu-id="5b0e6-125">例如, 假设以下内容:</span><span class="sxs-lookup"><span data-stu-id="5b0e6-125">For example, assume the following:</span></span> 

- <span data-ttu-id="5b0e6-126">SBC 配置为每分钟发送选项。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-126">An SBC is configured to send options every minute.</span></span> 
- <span data-ttu-id="5b0e6-127">SBC 的配对时间为 11.00 AM。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-127">The SBC was paired at 11.00 AM.</span></span>  
- <span data-ttu-id="5b0e6-128">SBC 在 11.01 AM、11.02 AM 等位置发送选项。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-128">The SBC sends options at 11.01 AM, 11.02 AM, and so on.</span></span>  
- <span data-ttu-id="5b0e6-129">在11.15 中, 用户进行呼叫, 路由机制将选择此 SBC。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-129">At 11.15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="5b0e6-130">应用以下逻辑: 当 SBC 发送选项时的平均时间间隔的两倍 (一分钟加1分钟 = 2 分钟) 加五分钟 = 7 分钟。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-130">The following logic is applied: Two times the average interval when the SBC sends options (one minute plus one minute = two minutes) plus five minutes = seven minutes.</span></span> <span data-ttu-id="5b0e6-131">这是 SBC 的常规间隔值。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-131">This is the value of the regular interval for the SBC.</span></span>
 
<span data-ttu-id="5b0e6-132">如果我们的示例中的 SBC 在 11.08 AM 和 11.15 AM 之间的任何时间段内发送选项 (进行调用的时间), 它将被视为 "正常"。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-132">If the SBC in our example sent options at any period between 11.08 AM and 11.15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="5b0e6-133">如果不是, 则 SBC 将从路由降级。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-133">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="5b0e6-134">降级意味着不会首先尝试 SBC。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-134">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="5b0e6-135">例如, 我们有具有同等优先级的 sbc1.contoso.com 和 sbc2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-135">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="5b0e6-136">如果 sbc1.contoso.com 不按上述方式发送 SIP 选项, 则会将其降级。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-136">If sbc1.contoso.com does not send SIP options on a regular interval as described above, it is demoted.</span></span> <span data-ttu-id="5b0e6-137">接下来, sbc2.contoso.com 尝试通话。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-137">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="5b0e6-138">如果 sbc2 无法送达呼叫, 则会在生成故障之前再次尝试 sbc1.contoso.com (已降级)。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-138">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

<span data-ttu-id="5b0e6-139">如果一个路线中的两个 (或更多) SBCs concidered 完好且相等, Fisher-Yates 的无序应用以 distrubute SBCs 之间的通话。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-139">If two (or more) SBCs in one route concidered healthy and equal, Fisher-Yates shuffle applied to distrubute the calls between the SBCs.</span></span>

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="5b0e6-140">监控通话质量分析仪表板和 SBC 日志</span><span class="sxs-lookup"><span data-stu-id="5b0e6-140">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="5b0e6-141">在某些情况下, 特别是在初始配对过程中, 可能存在与 SBCs 和/或直接路由服务的错误配置相关的问题。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-141">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs and/or the Direct Routing service.</span></span> 

<span data-ttu-id="5b0e6-142">可以使用以下工具监视配置:</span><span class="sxs-lookup"><span data-stu-id="5b0e6-142">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="5b0e6-143">呼叫质量仪表板</span><span class="sxs-lookup"><span data-stu-id="5b0e6-143">Call Quality Dashboard</span></span> 
- <span data-ttu-id="5b0e6-144">SBC 日志</span><span class="sxs-lookup"><span data-stu-id="5b0e6-144">SBC logs</span></span> 

<span data-ttu-id="5b0e6-145">直接路由服务有很高描述性错误代码报告给调用分析或 SBC 日志。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-145">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="5b0e6-146">通话质量仪表板提供有关通话质量和可靠性的信息。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-146">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="5b0e6-147">若要了解有关如何使用呼叫分析解决问题的详细信息, 请参阅[打开和使用 Microsoft 团队和 Skype for Business Online 的呼叫质量仪表板](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)和[使用呼叫分析解决较差的通话质量](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-147">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="5b0e6-148">在呼叫失败的情况下, 呼叫分析提供标准 SIP 代码来帮助您进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-148">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![通话失败的 SIP 代码示例](media/failed-response-code.png)

<span data-ttu-id="5b0e6-150">但是, 只有当呼叫到达直接路由的内部组件并失败时, 呼叫分析才会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-150">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="5b0e6-151">如果 SBC 配对出现问题或出现 SIP "Invite" 被拒绝的问题 (例如, 中继 FQDN 的名称配置错误), 则呼叫分析将不会提供帮助。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-151">In case of issues with SBC pairing or issues where SIP “Invite” was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="5b0e6-152">在这种情况下, 请参阅 SBC 日志。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-152">In this case, please refer to the SBC logs.</span></span> <span data-ttu-id="5b0e6-153">直接路由将问题的详细描述发送到 SBCs;可以从 SBC 日志中读取这些问题。</span><span class="sxs-lookup"><span data-stu-id="5b0e6-153">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
