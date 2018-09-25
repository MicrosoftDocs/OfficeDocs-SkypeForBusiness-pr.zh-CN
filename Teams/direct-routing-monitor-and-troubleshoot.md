---
title: 监视和故障排除直接路由
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service:
- msteams
- skype-for-business-online
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: 本文介绍如何监视和解决直接路由配置。
ms.openlocfilehash: 46fd5ad046551d30bf3822d11864edc2a5353a26
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014930"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="b583e-103">监视和故障排除直接路由</span><span class="sxs-lookup"><span data-stu-id="b583e-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="b583e-104">本文介绍如何监视和解决直接路由配置。</span><span class="sxs-lookup"><span data-stu-id="b583e-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="b583e-105">发起和接收呼叫使用直接路由中的功能涉及以下组件：</span><span class="sxs-lookup"><span data-stu-id="b583e-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="b583e-106">会话边界控制器 (Sbc)</span><span class="sxs-lookup"><span data-stu-id="b583e-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="b583e-107">Microsoft 云直接路由组件</span><span class="sxs-lookup"><span data-stu-id="b583e-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="b583e-108">电信中继</span><span class="sxs-lookup"><span data-stu-id="b583e-108">Telecom trunks</span></span> 

<span data-ttu-id="b583e-109">如果您有难题解决问题，请打开与您的 SBC 供应商或 Microsoft 支持案例。</span><span class="sxs-lookup"><span data-stu-id="b583e-109">If you have difficulties troubleshooting issues, please open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="b583e-110">Microsoft 从事的故障排除与监视提供更多工具。</span><span class="sxs-lookup"><span data-stu-id="b583e-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="b583e-111">请检查定期更新的文档。</span><span class="sxs-lookup"><span data-stu-id="b583e-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="b583e-112">使用会话初始协议 (SIP) Options 消息的会话边界控制器的监控可用性</span><span class="sxs-lookup"><span data-stu-id="b583e-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) Options messages</span></span>

<span data-ttu-id="b583e-113">直接路由使用 SIP 的选项，发送的会话边界控制器来监视 SBC 运行状况。</span><span class="sxs-lookup"><span data-stu-id="b583e-113">Direct Routing uses SIP Options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="b583e-114">没有要启用 SIP Options 监控租户管理员所需的操作。</span><span class="sxs-lookup"><span data-stu-id="b583e-114">There are no actions required from the tenant administrator to enable the SIP Options monitoring.</span></span> <span data-ttu-id="b583e-115">收集的信息考虑时做出路由决定。</span><span class="sxs-lookup"><span data-stu-id="b583e-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="b583e-116">例如，如果为某个特定用户，有几个可用于路由呼叫的 Sbc，直接路由认为收到来自每个 SBC 来确定路由的 SIP Options 信息。</span><span class="sxs-lookup"><span data-stu-id="b583e-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP Options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="b583e-117">下图显示了配置的一个示例：</span><span class="sxs-lookup"><span data-stu-id="b583e-117">The following diagram shows an example of the configuration:</span></span> 

![SIP 选项配置示例](media/sip-options-config-example.png)

<span data-ttu-id="b583e-119">当用户发出呼叫号码 +1 425\<任意七位数字 >，直接路由计算路由。</span><span class="sxs-lookup"><span data-stu-id="b583e-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="b583e-120">作为路由中有两个 SBCs: sbc1.contoso.com 和 sbc2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="b583e-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="b583e-121">这两个 SBCs 作为路由中具有相同的优先级。</span><span class="sxs-lookup"><span data-stu-id="b583e-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="b583e-122">选取 SBC 之前, 的路由机制计算 SBCs 基于 SBC 发送 SIP 选项时的运行状况上次时间。</span><span class="sxs-lookup"><span data-stu-id="b583e-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP Options last time.</span></span> 

<span data-ttu-id="b583e-123">SBC 被视为正常运行，如果时刻发送呼叫的统计信息显示 SBC 发送定期的选项。</span><span class="sxs-lookup"><span data-stu-id="b583e-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends Options on a regular interval.</span></span>  

<span data-ttu-id="b583e-124">直接路由计算的时间间隔定期 SBC 在发起呼叫和添加五分钟之前发送选项时，按照两次的平均值。</span><span class="sxs-lookup"><span data-stu-id="b583e-124">Direct Routing calculates regular intervals by taking two times the average when the SBC sends Options before making the call and adding five minutes.</span></span> 

<span data-ttu-id="b583e-125">例如，假定以下几点：</span><span class="sxs-lookup"><span data-stu-id="b583e-125">For example, assume the following:</span></span> 

- <span data-ttu-id="b583e-126">配置 SBC 发送选项每分钟。</span><span class="sxs-lookup"><span data-stu-id="b583e-126">An SBC is configured to send Options every minute.</span></span> 
- <span data-ttu-id="b583e-127">SBC 已配对在上午 11: 00。</span><span class="sxs-lookup"><span data-stu-id="b583e-127">The SBC was paired at 11.00 AM.</span></span>  
- <span data-ttu-id="b583e-128">SBC 发送选项在 11.01 AM、 11.02 AM，依此类推。</span><span class="sxs-lookup"><span data-stu-id="b583e-128">The SBC sends options at 11.01 AM, 11.02 AM, and so on.</span></span>  
- <span data-ttu-id="b583e-129">在 11.15，用户发出呼叫和路由机制选择此 SBC。</span><span class="sxs-lookup"><span data-stu-id="b583e-129">At 11.15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="b583e-130">应用以下逻辑： 当 SBC plus 五分钟 = 七个分钟发送选项 （一个分钟再加上一个分钟 = 两分钟） 的两倍的平均时间间隔。</span><span class="sxs-lookup"><span data-stu-id="b583e-130">The following logic is applied: Two times the average interval when the SBC sends Options (one minute plus one minute = two minutes) plus five minutes = seven minutes.</span></span> <span data-ttu-id="b583e-131">这是 SBC 的正则时间间隔的值。</span><span class="sxs-lookup"><span data-stu-id="b583e-131">This is the value of the regular interval for the SBC.</span></span>
 
<span data-ttu-id="b583e-132">如果在我们的示例 SBC 发送在上午 11: 08 11 15 上午: （建立呼叫的时间） 之间的任何时间段的选项，则被视为正常运行。</span><span class="sxs-lookup"><span data-stu-id="b583e-132">If the SBC in our example sent options at any period between 11.08 AM and 11.15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="b583e-133">否则，将从路由降级 SBC。</span><span class="sxs-lookup"><span data-stu-id="b583e-133">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="b583e-134">降级意味着不会在首次尝试 SBC。</span><span class="sxs-lookup"><span data-stu-id="b583e-134">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="b583e-135">例如，我们有 sbc1.contoso.com 和 sbc2.contoso.com 具有相同的优先级。</span><span class="sxs-lookup"><span data-stu-id="b583e-135">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="b583e-136">如果 sbc1.contoso.com 不发送 SIP 定期的选项，如上面所述，它将被降级。</span><span class="sxs-lookup"><span data-stu-id="b583e-136">If sbc1.contoso.com does not send SIP Options on a regular interval as described above, it is demoted.</span></span> <span data-ttu-id="b583e-137">接下来，sbc2.contoso.com 尝试进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="b583e-137">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="b583e-138">如果 sbc2.contoso.con 无法传送呼叫，才会生成失败 （降级） sbc1.contoso.com 将再次尝试。</span><span class="sxs-lookup"><span data-stu-id="b583e-138">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="b583e-139">监视呼叫质量分析仪表板和 SBC 日志</span><span class="sxs-lookup"><span data-stu-id="b583e-139">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="b583e-140">在某些情况下，尤其是在初始配对，可能会出现与配置不正确的 Sbc 和/或直接路由服务相关的问题。</span><span class="sxs-lookup"><span data-stu-id="b583e-140">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs and/or the Direct Routing service.</span></span> 

<span data-ttu-id="b583e-141">您可以使用以下工具来监视您的配置：</span><span class="sxs-lookup"><span data-stu-id="b583e-141">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="b583e-142">通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="b583e-142">Call Quality Dashboard</span></span> 
- <span data-ttu-id="b583e-143">SBC 日志</span><span class="sxs-lookup"><span data-stu-id="b583e-143">SBC logs</span></span> 

<span data-ttu-id="b583e-144">直接路由服务已向呼叫分析或 SBC 日志报告非常描述性错误代码。</span><span class="sxs-lookup"><span data-stu-id="b583e-144">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="b583e-145">呼叫质量仪表板提供有关呼叫质量和可靠性的信息。</span><span class="sxs-lookup"><span data-stu-id="b583e-145">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="b583e-146">若要了解有关如何使用调用分析的问题进行疑难解答的详细信息，请参阅[打开和使用的 Microsoft 团队和 Skype 业务 online 呼叫质量仪表板](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard)和[使用呼叫分析解决质量欠佳的呼叫质量](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)。</span><span class="sxs-lookup"><span data-stu-id="b583e-146">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="b583e-147">呼叫失败时调用分析提供标准 SIP 代码，以帮助您进行疑难解答。</span><span class="sxs-lookup"><span data-stu-id="b583e-147">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![呼叫失败的示例 SIP 代码](media/failed-response-code.png)

<span data-ttu-id="b583e-149">但是，呼叫到达的直接路由的内部组件和失败时，仅可帮助呼叫的分析。</span><span class="sxs-lookup"><span data-stu-id="b583e-149">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="b583e-150">出现时 SBC 配对问题或 SIP"邀请"被拒绝 （例如，中继配置 FQDN 不正确的名称），其中的问题，将不帮助呼叫的分析。</span><span class="sxs-lookup"><span data-stu-id="b583e-150">In case of issues with SBC pairing or issues where SIP “Invite” was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="b583e-151">在这种情况下，请参阅 SBC 日志。</span><span class="sxs-lookup"><span data-stu-id="b583e-151">In this case, please refer to the SBC logs.</span></span> <span data-ttu-id="b583e-152">直接路由将问题的详细的说明发送给 SBCs;可以从 SBC 日志读取这些问题。</span><span class="sxs-lookup"><span data-stu-id="b583e-152">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
