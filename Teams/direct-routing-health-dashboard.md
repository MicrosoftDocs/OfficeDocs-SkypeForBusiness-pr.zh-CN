---
title: 直接路由的运行状况仪表板
ms.reviewer: nmurav
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: 了解如何使用运行状况仪表板监视会话边界控制器与直接路由之间的连接。
ms.openlocfilehash: b6ec0c04200fac018b721bfe6c94f8d9bd969a2f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237488"
---
# <a name="health-dashboard-for-direct-routing"></a><span data-ttu-id="700ff-103">直接路由的运行状况仪表板</span><span class="sxs-lookup"><span data-stu-id="700ff-103">Health Dashboard for Direct Routing</span></span>

<span data-ttu-id="700ff-104">直接路由的运行状况仪表板使你可以监视会话边界控制器 (SBC) 和直接路由接口之间的连接。</span><span class="sxs-lookup"><span data-stu-id="700ff-104">Health Dashboard for Direct Routing lets you monitor the connection between your Session Border Controller (SBC) and the Direct Routing interface.</span></span>  <span data-ttu-id="700ff-105">通过运行状况仪表板, 你可以监视你的 SBC、电话服务和你的 SBC 和直接路由接口之间的网络参数的相关信息。</span><span class="sxs-lookup"><span data-stu-id="700ff-105">With Health Dashboard, you can monitor information about your SBC, the telephony service, and the network parameters between your SBC and the Direct Routing interface.</span></span> <span data-ttu-id="700ff-106">此信息可帮助你识别问题, 包括断开呼叫的原因。</span><span class="sxs-lookup"><span data-stu-id="700ff-106">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="700ff-107">例如, 如果 SBC 上的证书已过期或存在网络问题, 则 SBC 可能会停止发送呼叫。</span><span class="sxs-lookup"><span data-stu-id="700ff-107">For example, the SBC might stop sending calls if a certificate on the SBC has expired or if there are network issues.</span></span>  

<span data-ttu-id="700ff-108">运行状况仪表板监视两个级别的信息:</span><span class="sxs-lookup"><span data-stu-id="700ff-108">Health Dashboard monitors two levels of information:</span></span>

- <span data-ttu-id="700ff-109">连接的 SBCs 的整体运行状况</span><span class="sxs-lookup"><span data-stu-id="700ff-109">Overall health of the connected SBCs</span></span>
- <span data-ttu-id="700ff-110">有关连接的 SBCs 的详细信息</span><span class="sxs-lookup"><span data-stu-id="700ff-110">Detailed information about the connected SBCs</span></span>

<span data-ttu-id="700ff-111">可以在 Microsoft 团队和 Skype for Business 管理中心查看运行状况仪表板。</span><span class="sxs-lookup"><span data-stu-id="700ff-111">You can view Health Dashboard in the Microsoft Teams and Skype for Business Admin Center.</span></span>


## <a name="overall-health"></a><span data-ttu-id="700ff-112">整体运行状况</span><span class="sxs-lookup"><span data-stu-id="700ff-112">Overall health</span></span>

<span data-ttu-id="700ff-113">运行状况仪表板提供与连接的 SBCs 的整体运行状况相关的以下信息:</span><span class="sxs-lookup"><span data-stu-id="700ff-113">Health Dashboard provides the following information related to overall health of the connected SBCs:</span></span>

 ![显示运行状况仪表板统计信息](media/direct-routing-dashboard-stats1.png)

- <span data-ttu-id="700ff-115">**直接路由摘要**-显示在系统中注册的 SBCs 总数。</span><span class="sxs-lookup"><span data-stu-id="700ff-115">**Direct Routing summary** - Shows the total number of SBCs registered in the system.</span></span> <span data-ttu-id="700ff-116">注册意味着租户管理员使用 CsOnlinePSTNGateway 命令添加了 SBC。</span><span class="sxs-lookup"><span data-stu-id="700ff-116">Registration means that the tenant administrator added an SBC by using the New-CsOnlinePSTNGateway command.</span></span> <span data-ttu-id="700ff-117">如果 SBC 已添加到 PowerShell 中, 但从未连接, 则运行状况仪表板将显示为 "不正常状态"。</span><span class="sxs-lookup"><span data-stu-id="700ff-117">If the SBC was added in PowerShell, but never connected, the Health Dashboard shows it in an unhealthy status.</span></span>

- <span data-ttu-id="700ff-118">**SBC** -成对的 SBC 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="700ff-118">**SBC** - The FQDN of the paired SBC.</span></span>

- <span data-ttu-id="700ff-119">**网络有效性比率 (NER)** -NER 衡量网络通过测量发送的呼叫数与发送给收件人的呼叫次数之间传递呼叫的能力。</span><span class="sxs-lookup"><span data-stu-id="700ff-119">**Network Effectiveness Ratio (NER)** - The NER measures the ability of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>  

   <span data-ttu-id="700ff-120">NER 衡量网络将呼叫传递到远端终端的能力-不包括用户操作, 从而导致呼叫拒绝。</span><span class="sxs-lookup"><span data-stu-id="700ff-120">The NER measures the ability of networks to deliver calls to the far-end terminal--excluding user actions resulting in call rejections.</span></span>  <span data-ttu-id="700ff-121">如果收件人拒绝呼叫或已将呼叫发送到语音邮件, 则会将呼叫计为成功送达。</span><span class="sxs-lookup"><span data-stu-id="700ff-121">If the recipient rejected a call or sent the call to voicemail, the call is counted as a successful delivery.</span></span> <span data-ttu-id="700ff-122">这意味着应答邮件、占线信号或没有应答的铃声均被视为成功通话。</span><span class="sxs-lookup"><span data-stu-id="700ff-122">This means that an answer message, a busy signal, or a ring with no answer are all considered successful calls.</span></span> 
  
   <span data-ttu-id="700ff-123">例如, 假设直接路由已发送给 SBC 的调用, 并且 SBC 返回 SIP 代码 "504 服务器超时-服务器尝试在尝试处理请求且未收到提示响应时访问另一台服务器"。</span><span class="sxs-lookup"><span data-stu-id="700ff-123">For example, assume Direct Routing sent a call to the SBC and the SBC returns SIP code “504 Server Time-out - The server attempted to access another server in attempting to process the request and did not receive a prompt response”.</span></span> <span data-ttu-id="700ff-124">此响应指示在 SBC 端出现问题, 这将减少此 SBC 的运行状况仪表板上的 NER。</span><span class="sxs-lookup"><span data-stu-id="700ff-124">This response indicates there is an issue on the SBC side, and this will decrease the NER on the Health Dashboard for this SBC.</span></span> 
  
   <span data-ttu-id="700ff-125">由于你采取的操作可能取决于受影响的通话的数量, 因此运行状况仪表板显示分析了多少个调用来计算参数。</span><span class="sxs-lookup"><span data-stu-id="700ff-125">Because the action you take might depend on the number of calls affected, Health Dashboard shows how many calls were analyzed to calculate a parameter.</span></span> <span data-ttu-id="700ff-126">如果通话次数小于 100, 则 NER 可能非常低, 但仍正常。</span><span class="sxs-lookup"><span data-stu-id="700ff-126">If the number of calls is less than 100, the NER might be quite low, but still be normal.</span></span> 

   <span data-ttu-id="700ff-127">用于 calcuate NER 的公式为:</span><span class="sxs-lookup"><span data-stu-id="700ff-127">The formula used to calcuate NER is:</span></span>

   <span data-ttu-id="700ff-128">NER = 接听电话 + 用户占线 + 环无应答 + 终端拒绝病情发作 x 100</span><span class="sxs-lookup"><span data-stu-id="700ff-128">NER = Answered calls + User Busy + Ring no Answer + Terminal Reject Seizures x 100</span></span>

 
- <span data-ttu-id="700ff-129">**平均通话持续时间**-有关平均通话持续时间的信息可以帮助您监控通话的质量。</span><span class="sxs-lookup"><span data-stu-id="700ff-129">**Average call duration** - Information about average call duration can help you monitor the quality of calls.</span></span> <span data-ttu-id="700ff-130">1:1 PSTN 呼叫的平均持续时间为4至5分钟。</span><span class="sxs-lookup"><span data-stu-id="700ff-130">The average duration of a 1:1 PSTN call is four to five minutes.</span></span>  <span data-ttu-id="700ff-131">但是, 对于每个公司, 此平均值可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="700ff-131">However, for each company, this average can differ.</span></span>  <span data-ttu-id="700ff-132">Microsoft 建议为您的公司的平均通话时间建立一个基准。</span><span class="sxs-lookup"><span data-stu-id="700ff-132">Microsoft recommends establishing a baseline for the average call duration for your company.</span></span> <span data-ttu-id="700ff-133">如果此参数显著地低于基准, 它可能表示用户在通话质量或可靠性方面遇到问题, 并且之前挂断。</span><span class="sxs-lookup"><span data-stu-id="700ff-133">If this parameter goes significantly below the baseline, it might indicate that your users are having issues with call quality or reliability and are hanging up earlier than usual.</span></span> <span data-ttu-id="700ff-134">如果您开始看到极低的平均通话持续时间 (例如15秒), 则呼叫方可能会挂断, 因为您的服务不能可靠地执行。</span><span class="sxs-lookup"><span data-stu-id="700ff-134">If you start seeing extremely low average call duration, for example 15 seconds, callers might be hanging up because your service is not performing reliably.</span></span> 

   <span data-ttu-id="700ff-135">由于你采取的操作可能取决于受影响的通话的数量, 因此运行状况仪表板显示分析了多少个调用来计算参数。</span><span class="sxs-lookup"><span data-stu-id="700ff-135">Because the action you take might depend on the number of calls affected, Health Dashboard shows how many calls were analyzed to calculate a parameter.</span></span>

- <span data-ttu-id="700ff-136">**Tls 连接状态**-Tls (传输层安全性) 连接性显示了直接路由和 SBC 之间的 TLS 连接状态。</span><span class="sxs-lookup"><span data-stu-id="700ff-136">**TLS connectivity status** - TLS (Transport Layer Security) connectivity shows the status of the TLS connections between Direct Routing and the SBC.</span></span> <span data-ttu-id="700ff-137">运行状况仪表板还会分析证书过期日期, 并在30天内将证书设置为过期, 以便管理员可以在服务中断之前续订证书。</span><span class="sxs-lookup"><span data-stu-id="700ff-137">Health Dashboard also analyzes the certificate expiration date and warns if a certificate is set to expire within 30 days so that administrators can renew the certificate before service is disrupted.</span></span>

   <span data-ttu-id="700ff-138">通过单击该警告消息, 你可以在右侧的弹出窗口中查看详细的问题说明, 并提供有关如何解决该问题的建议。</span><span class="sxs-lookup"><span data-stu-id="700ff-138">By clicking the Warning message, you can see a detailed issue description in a popup window on the right and recommendations for how to fix the issue.</span></span>

- <span data-ttu-id="700ff-139">**SIP 选项状态**-默认情况下, SBC 每分钟发送选项消息。</span><span class="sxs-lookup"><span data-stu-id="700ff-139">**SIP options status** – By default, the SBC sends options messages every minute.</span></span> <span data-ttu-id="700ff-140">对于不同的 SBC 供应商, 此配置可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="700ff-140">This configuration can vary for different SBC vendors.</span></span> <span data-ttu-id="700ff-141">如果 SIP 选项未发送或未配置, 直接路由将发出警告。</span><span class="sxs-lookup"><span data-stu-id="700ff-141">Direct Routing warns if the SIP options are not sent or are not configured.</span></span> <span data-ttu-id="700ff-142">有关 SIP 选项监视和条件的详细信息, 可将 SBC 标记为不起作用, 请参阅[监视直接路由和解决直接路由问题](direct-routing-monitor-and-troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="700ff-142">For more information about SIP options monitoring, and conditions when an SBC can be marked as not functional, see [Monitor and troubleshoot Direct Routing](direct-routing-monitor-and-troubleshoot.md).</span></span>

- <span data-ttu-id="700ff-143">**详细 SIP 选项状态**-除了显示 SIP 选项流出现问题外, "运行状况" 仪表板还提供错误的详细描述。</span><span class="sxs-lookup"><span data-stu-id="700ff-143">**Detailed SIP options status** - In addition to showing that there is an issue with SIP options flow, the Health Dashboard also provides detailed descriptions of the errors.</span></span> <span data-ttu-id="700ff-144">您可以通过单击 "警告" 消息来访问说明。</span><span class="sxs-lookup"><span data-stu-id="700ff-144">You can access the description by clicking the “Warning” message.</span></span> <span data-ttu-id="700ff-145">右侧的弹出窗口将显示详细的错误描述。</span><span class="sxs-lookup"><span data-stu-id="700ff-145">A pop-up window on the right will show the detailed error description.</span></span>

   <span data-ttu-id="700ff-146">SIP 选项状态消息的可能值如下所示:</span><span class="sxs-lookup"><span data-stu-id="700ff-146">Possible values for SIP options status messages are as follows:</span></span>

    - <span data-ttu-id="700ff-147">活动-SBC 处于活动状态-Microsoft 直接路由服务发现选项按固定间隔流动。</span><span class="sxs-lookup"><span data-stu-id="700ff-147">Active – The SBC is active--Microsoft Direct Routing service sees the options flowing on a regular interval.</span></span>

    - <span data-ttu-id="700ff-148">警告, 无 SIP 选项-数据库中存在会话边框控制器 (管理员使用命令 New-CsOnlinePSTNGateway 创建了该控制器)。</span><span class="sxs-lookup"><span data-stu-id="700ff-148">Warning, no SIP options - The Session Border Controller exists in the database (your administrator created it using the command New-CsOnlinePSTNGateway).</span></span> <span data-ttu-id="700ff-149">它配置为发送 SIP 选项, 但直接路由服务从未看到从该 SBC 返回的 SIP 选项。</span><span class="sxs-lookup"><span data-stu-id="700ff-149">It is configured to send SIP options, but the Direct Routing service never saw the SIP options coming back from this SBC.</span></span>

    - <span data-ttu-id="700ff-150">警告, SIP 消息未配置-使用 SIP 选项的中继监视未处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="700ff-150">Warning, SIP Messages aren't configured - Trunk monitoring using SIP options isn’t turned on.</span></span> <span data-ttu-id="700ff-151">Microsoft 调用系统使用 SIP 选项和传输层安全性 (TLS) 握手监视在应用程序级别检测连接的会话边界控制器 (SBCs) 的运行状况。</span><span class="sxs-lookup"><span data-stu-id="700ff-151">Microsoft Calling System uses SIP options and Transport Layer Security (TLS) handshake monitoring to detect the health of the connected Session Border Controllers (SBCs) at the application level.</span></span> <span data-ttu-id="700ff-152">如果可以在网络级别达到此主干 (通过 ping), 但证书已过期或 SIP 堆栈不起作用, 则会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="700ff-152">You’ll have problems if this trunk can be reached at the network level (by ping), but the certificate has expired or the SIP stack doesn’t work.</span></span> <span data-ttu-id="700ff-153">为了帮助及早识别此类问题, Microsoft 建议启用发送 SIP 选项。</span><span class="sxs-lookup"><span data-stu-id="700ff-153">To help identify such problems early, Microsoft recommends enabling sending SIP options.</span></span> <span data-ttu-id="700ff-154">请查看 SBC 制造商的文档, 以配置发送 SIP 选项。</span><span class="sxs-lookup"><span data-stu-id="700ff-154">Check your SBC manufacturer documentation to configure sending SIP options.</span></span> 

- <span data-ttu-id="700ff-155">**并发通话容量**-你可以通过使用带有-MaxConcurrentSessions 参数的 New 或 CsOnlinePSTNGateway 命令指定 SBC 可以处理的并发调用的限制。</span><span class="sxs-lookup"><span data-stu-id="700ff-155">**Concurrent calls capacity** - You can specify the limit of concurrent calls that an SBC can handle by using the New- or Set-CsOnlinePSTNGateway command with the -MaxConcurrentSessions parameter.</span></span> <span data-ttu-id="700ff-156">此参数通过使用特定的 SBC 直接路由来计算发送或接收的通话次数, 并将其与设置的限制进行比较。</span><span class="sxs-lookup"><span data-stu-id="700ff-156">This parameter calculates how many calls were sent or received by Direct Routing using a specific SBC and compares it with the limit set.</span></span> <span data-ttu-id="700ff-157">注意: 如果 SBC 还处理不同 Pbx 的调用, 此数字将不会显示实际的并发呼叫。</span><span class="sxs-lookup"><span data-stu-id="700ff-157">Note:  If the SBC also handles calls to different PBXs, this number will not show the actual concurrent calls.</span></span>


## <a name="detailed-information-for-each-sbc"></a><span data-ttu-id="700ff-158">每个 SBC 的详细信息</span><span class="sxs-lookup"><span data-stu-id="700ff-158">Detailed information for each SBC</span></span>

<span data-ttu-id="700ff-159">你还可以查看特定 SBC 的详细信息, 如以下屏幕截图所示:</span><span class="sxs-lookup"><span data-stu-id="700ff-159">You can also view the detailed information for a specific SBC as shown in the following screenshot:</span></span>

![运行状况仪表板 SBC 详细信息](media/direct-routing-dashboard-SBC-detail1.png)


<span data-ttu-id="700ff-161">"详细信息" 视图显示以下附加参数:</span><span class="sxs-lookup"><span data-stu-id="700ff-161">The detailed view shows the following additional parameters:</span></span>

- <span data-ttu-id="700ff-162">**TLS 连接状态**-这与 "整体运行状况" 页面上的跃点相同;</span><span class="sxs-lookup"><span data-stu-id="700ff-162">**TLS Connectivity status** – this is the same metric as on the “Overall Health” page;</span></span>

- <span data-ttu-id="700ff-163">**TLS 连接上次状态**-显示当 SBC 与直接路由服务建立 TLS 连接时的时间;</span><span class="sxs-lookup"><span data-stu-id="700ff-163">**TLS Connectivity last status** – shows time when the SBC made a TLS connection to the Direct Routing service;</span></span>

- <span data-ttu-id="700ff-164">**SIP 选项状态**-与 "整体运行状况" 页面上的指标相同。</span><span class="sxs-lookup"><span data-stu-id="700ff-164">**SIP options status** – the same metric as on the “Overall Health” page.</span></span>

- <span data-ttu-id="700ff-165">**Sip 选项上次检查**时间-上次收到 sip 选项的时间。</span><span class="sxs-lookup"><span data-stu-id="700ff-165">**SIP options last checked** – time when the SIP options were received last time.</span></span>

- <span data-ttu-id="700ff-166">**SBC 状态**–基于所有受监视的参数的 sbc 的整体状态。</span><span class="sxs-lookup"><span data-stu-id="700ff-166">**SBC status** – overall status of the SBC, based on all monitored parameters.</span></span>

- <span data-ttu-id="700ff-167">**同时拨打**-显示已处理 SBC 的并发调用数。</span><span class="sxs-lookup"><span data-stu-id="700ff-167">**Concurrent call**- shows  how many concurrent calls the SBC handled.</span></span> <span data-ttu-id="700ff-168">此信息对预测所需的并发信道的数量很有用, 并且可以看到趋势。</span><span class="sxs-lookup"><span data-stu-id="700ff-168">This information is useful to predict the number of concurrent channels you need and see the trend.</span></span> <span data-ttu-id="700ff-169">你可以按天数和呼叫方向 (入站/出站/所有流) 将数据滑动。</span><span class="sxs-lookup"><span data-stu-id="700ff-169">You can slide the data by number of days and call direction (inbound/outbound/All streams).</span></span>

- <span data-ttu-id="700ff-170">**网络参数**-从直接路由接口到会话边界控制器测量所有网络参数。</span><span class="sxs-lookup"><span data-stu-id="700ff-170">**Network parameters** - All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="700ff-171">有关推荐值的信息, 请参阅为[Microsoft 团队准备组织的网络](https://docs.microsoft.com/en-us/microsoftteams/prepare-network), 并查看客户边缘到 microsoft Edge 推荐值。</span><span class="sxs-lookup"><span data-stu-id="700ff-171">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/prepare-network), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

   - <span data-ttu-id="700ff-172">抖动——使用 RTCP (RTP 控制协议) 在两个终结点之间计算的网络传播延迟时间变化的毫秒度量。</span><span class="sxs-lookup"><span data-stu-id="700ff-172">Jitter – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

   - <span data-ttu-id="700ff-173">数据包丢失-这是一种无法送达数据包的指标;它在两个终结点之间进行计算。</span><span class="sxs-lookup"><span data-stu-id="700ff-173">Packet Loss – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

   - <span data-ttu-id="700ff-174">Latancy-(也称为往返行程时间) 是发送信号所用的时间长度加上接收该信号的确认所用的时间长度。</span><span class="sxs-lookup"><span data-stu-id="700ff-174">Latancy - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgement of that signal to be received.</span></span> <span data-ttu-id="700ff-175">此时间延迟由信号的两个点之间的传播时间组成。</span><span class="sxs-lookup"><span data-stu-id="700ff-175">This time delay consists of the propagation times between the two points of a signal.</span></span>

   <span data-ttu-id="700ff-176">你可以按天数和呼叫方向 (入站/出站/所有流) 将数据滑动。</span><span class="sxs-lookup"><span data-stu-id="700ff-176">You can slide the data by number of days and call direction (inbound/outbound/All streams).</span></span>

<span data-ttu-id="700ff-177">**网络有效性比率**-这是在整个运行状况仪表板上显示的同一参数, 但通过按时间系列或呼叫方向对数据进行切片的选项也是如此。</span><span class="sxs-lookup"><span data-stu-id="700ff-177">**Network Effectiveness ratio** - This is the same parameter that appears on the Overall Health dashboard, but with the option to slice the data by time series or call direction.</span></span>




