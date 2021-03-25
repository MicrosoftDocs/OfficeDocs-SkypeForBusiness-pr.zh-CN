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
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何使用运行状况仪表板监视会话边界控制器和直接路由之间的连接。
ms.openlocfilehash: cb5e802d904cd2eb364fd480ebcde385e64cf02b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122226"
---
# <a name="health-dashboard-for-direct-routing"></a><span data-ttu-id="1802b-103">直接路由的运行状况仪表板</span><span class="sxs-lookup"><span data-stu-id="1802b-103">Health Dashboard for Direct Routing</span></span>

<span data-ttu-id="1802b-104">使用直接路由的运行状况仪表板可以监视会话边界控制器与 SBC (与) 路由接口之间的连接。</span><span class="sxs-lookup"><span data-stu-id="1802b-104">Health Dashboard for Direct Routing lets you monitor the connection between your Session Border Controller (SBC) and the Direct Routing interface.</span></span>  <span data-ttu-id="1802b-105">使用运行状况仪表板，可以监视有关 SBC、电话服务和 SBC 与直接路由接口之间的网络参数的信息。</span><span class="sxs-lookup"><span data-stu-id="1802b-105">With Health Dashboard, you can monitor information about your SBC, the telephony service, and the network parameters between your SBC and the Direct Routing interface.</span></span> <span data-ttu-id="1802b-106">此信息可帮助你识别问题，包括通话中断的原因。</span><span class="sxs-lookup"><span data-stu-id="1802b-106">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="1802b-107">例如，如果 SBC 上的证书已过期或存在网络问题，SBC 可能会停止发送调用。</span><span class="sxs-lookup"><span data-stu-id="1802b-107">For example, the SBC might stop sending calls if a certificate on the SBC has expired or if there are network issues.</span></span> <span data-ttu-id="1802b-108">请参阅 [管理员角色](using-admin-roles.md) ，了解谁有权访问运行状况仪表板。</span><span class="sxs-lookup"><span data-stu-id="1802b-108">See the [admin roles](using-admin-roles.md) to learn who has access to the health dashboard.</span></span>

<span data-ttu-id="1802b-109">运行状况仪表板监视两个级别的信息：</span><span class="sxs-lookup"><span data-stu-id="1802b-109">Health Dashboard monitors two levels of information:</span></span>

- <span data-ttu-id="1802b-110">连接的 SDC 的总体运行状况</span><span class="sxs-lookup"><span data-stu-id="1802b-110">Overall health of the connected SBCs</span></span>
- <span data-ttu-id="1802b-111">有关连接的 SDC 的详细信息</span><span class="sxs-lookup"><span data-stu-id="1802b-111">Detailed information about the connected SBCs</span></span>

<span data-ttu-id="1802b-112">可以在 Microsoft Teams 和 Skype for Business 管理中心查看运行状况仪表板。</span><span class="sxs-lookup"><span data-stu-id="1802b-112">You can view Health Dashboard in the Microsoft Teams and Skype for Business Admin Center.</span></span>

## <a name="overall-health"></a><span data-ttu-id="1802b-113">总体运行状况</span><span class="sxs-lookup"><span data-stu-id="1802b-113">Overall health</span></span>

<span data-ttu-id="1802b-114">运行状况仪表板提供与连接的 SDC 的总体运行状况相关的以下信息：</span><span class="sxs-lookup"><span data-stu-id="1802b-114">Health Dashboard provides the following information related to overall health of the connected SBCs:</span></span>

 ![显示运行状况仪表板统计信息](media/direct-routing-dashboard-stats1.png)

- <span data-ttu-id="1802b-116">**直接路由摘要** - 显示系统中注册的 SDC 总数。</span><span class="sxs-lookup"><span data-stu-id="1802b-116">**Direct Routing summary** - Shows the total number of SBCs registered in the system.</span></span> <span data-ttu-id="1802b-117">注册意味着租户管理员使用 New-CsOnlinePSTNGateway 添加了 SBC。</span><span class="sxs-lookup"><span data-stu-id="1802b-117">Registration means that the tenant administrator added an SBC by using the New-CsOnlinePSTNGateway command.</span></span> <span data-ttu-id="1802b-118">如果 SBC 已添加到 PowerShell 中，但从未连接，则运行状况仪表板会显示它处于不正常状态。</span><span class="sxs-lookup"><span data-stu-id="1802b-118">If the SBC was added in PowerShell, but never connected, the Health Dashboard shows it in an unhealthy status.</span></span>

- <span data-ttu-id="1802b-119">**SBC** - 已配对 SBC 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1802b-119">**SBC** - The FQDN of the paired SBC.</span></span>

- <span data-ttu-id="1802b-120">**网络有效性 (NER)** - NER 通过测量发送的呼叫数与发送给收件人的呼叫数来测量网络传送呼叫的能力。</span><span class="sxs-lookup"><span data-stu-id="1802b-120">**Network Effectiveness Ratio (NER)** - The NER measures the ability of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>  

   <span data-ttu-id="1802b-121">NER 度量网络向远端终端传送调用的能力，不包括导致呼叫拒绝的用户操作。</span><span class="sxs-lookup"><span data-stu-id="1802b-121">The NER measures the ability of networks to deliver calls to the far-end terminal--excluding user actions resulting in call rejections.</span></span>  <span data-ttu-id="1802b-122">如果收件人拒绝了呼叫或将呼叫发送到语音邮件，该呼叫将计为成功的送达。</span><span class="sxs-lookup"><span data-stu-id="1802b-122">If the recipient rejected a call or sent the call to voicemail, the call is counted as a successful delivery.</span></span> <span data-ttu-id="1802b-123">这意味着，应答消息、繁忙信号或没有应答的铃声都被视为成功的呼叫。</span><span class="sxs-lookup"><span data-stu-id="1802b-123">This means that an answer message, a busy signal, or a ring with no answer are all considered successful calls.</span></span>
  
   <span data-ttu-id="1802b-124">例如，假设直接路由向 SBC 发送了调用，并且 SBC 返回 SIP 代码"504 服务器时间过长 - 服务器尝试访问另一台服务器，尝试处理请求时未收到提示响应"。</span><span class="sxs-lookup"><span data-stu-id="1802b-124">For example, assume Direct Routing sent a call to the SBC and the SBC returns SIP code “504 Server Time-out - The server attempted to access another server in attempting to process the request and did not receive a prompt response”.</span></span> <span data-ttu-id="1802b-125">此响应表明 SBC 端存在问题，这会降低此 SBC 的运行状况仪表板上的 NER。</span><span class="sxs-lookup"><span data-stu-id="1802b-125">This response indicates there is an issue on the SBC side, and this will decrease the NER on the Health Dashboard for this SBC.</span></span>
  
   <span data-ttu-id="1802b-126">由于你采取的操作可能取决于受影响的调用数，因此运行状况仪表板显示已分析多少个调用来计算参数。</span><span class="sxs-lookup"><span data-stu-id="1802b-126">Because the action you take might depend on the number of calls affected, Health Dashboard shows how many calls were analyzed to calculate a parameter.</span></span> <span data-ttu-id="1802b-127">如果调用数小于 100，则 NER 可能相当低，但仍为正常。</span><span class="sxs-lookup"><span data-stu-id="1802b-127">If the number of calls is less than 100, the NER might be quite low, but still be normal.</span></span>

   <span data-ttu-id="1802b-128">用于计算 NER 的公式为：</span><span class="sxs-lookup"><span data-stu-id="1802b-128">The formula used to calculate NER is:</span></span>

   <span data-ttu-id="1802b-129">NER = 100 x (应答呼叫 + 用户忙 + 无应答 + 终端拒绝) /总呼叫数</span><span class="sxs-lookup"><span data-stu-id="1802b-129">NER = 100 x (Answered calls + User Busy + Ring no Answer + Terminal Reject Seizures)/Total Calls</span></span>

- <span data-ttu-id="1802b-130">**平均呼叫持续时间** - 有关平均呼叫持续时间的信息可以帮助你监视呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="1802b-130">**Average call duration** - Information about average call duration can help you monitor the quality of calls.</span></span> <span data-ttu-id="1802b-131">1：1 PSTN 呼叫的平均持续时间为 4 到 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="1802b-131">The average duration of a 1:1 PSTN call is four to five minutes.</span></span>  <span data-ttu-id="1802b-132">但是，对于每个公司，此平均值可能不同。</span><span class="sxs-lookup"><span data-stu-id="1802b-132">However, for each company, this average can differ.</span></span>  <span data-ttu-id="1802b-133">Microsoft 建议为贵公司的平均通话持续时间建立基线。</span><span class="sxs-lookup"><span data-stu-id="1802b-133">Microsoft recommends establishing a baseline for the average call duration for your company.</span></span> <span data-ttu-id="1802b-134">如果此参数明显低于基线，它可能表示用户遇到呼叫质量或可靠性问题，并且比平时挂断时间更早。</span><span class="sxs-lookup"><span data-stu-id="1802b-134">If this parameter goes significantly below the baseline, it might indicate that your users are having issues with call quality or reliability and are hanging up earlier than usual.</span></span> <span data-ttu-id="1802b-135">如果平均呼叫持续时间（例如 15 秒）开始极低，则呼叫者可能会挂断，因为服务未可靠执行。</span><span class="sxs-lookup"><span data-stu-id="1802b-135">If you start seeing extremely low average call duration, for example 15 seconds, callers might be hanging up because your service is not performing reliably.</span></span>

   <span data-ttu-id="1802b-136">由于你采取的操作可能取决于受影响的调用数，因此运行状况仪表板显示已分析多少个调用来计算参数。</span><span class="sxs-lookup"><span data-stu-id="1802b-136">Because the action you take might depend on the number of calls affected, Health Dashboard shows how many calls were analyzed to calculate a parameter.</span></span>

- <span data-ttu-id="1802b-137">**TLS 连接状态** - TLS (传输层安全性) 连接显示直接路由和 SBC 之间的 TLS 连接状态。</span><span class="sxs-lookup"><span data-stu-id="1802b-137">**TLS connectivity status** - TLS (Transport Layer Security) connectivity shows the status of the TLS connections between Direct Routing and the SBC.</span></span> <span data-ttu-id="1802b-138">运行状况仪表板还会分析证书到期日期，如果证书设置为在 30 天内过期，则发出警告，以便管理员可以在服务中断之前续订证书。</span><span class="sxs-lookup"><span data-stu-id="1802b-138">Health Dashboard also analyzes the certificate expiration date and warns if a certificate is set to expire within 30 days so that administrators can renew the certificate before service is disrupted.</span></span>

   <span data-ttu-id="1802b-139">通过单击"警告"消息，可以在右侧弹出窗口中查看详细的问题说明，以及解决问题的建议。</span><span class="sxs-lookup"><span data-stu-id="1802b-139">By clicking the Warning message, you can see a detailed issue description in a popup window on the right and recommendations for how to fix the issue.</span></span>

- <span data-ttu-id="1802b-140">**SIP 选项状态** - 默认情况下，SBC 每分钟发送一次选项消息。</span><span class="sxs-lookup"><span data-stu-id="1802b-140">**SIP options status** – By default, the SBC sends options messages every minute.</span></span> <span data-ttu-id="1802b-141">此配置可能因不同的 SBC 供应商而异。</span><span class="sxs-lookup"><span data-stu-id="1802b-141">This configuration can vary for different SBC vendors.</span></span> <span data-ttu-id="1802b-142">如果未发送或未配置 SIP 选项，直接路由会发出警告。</span><span class="sxs-lookup"><span data-stu-id="1802b-142">Direct Routing warns if the SIP options are not sent or are not configured.</span></span> <span data-ttu-id="1802b-143">有关 SIP 选项监视以及 SBC 可标记为无法正常工作的条件的详细信息，请参阅监视和排查直接 [路由问题](direct-routing-monitor-and-troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="1802b-143">For more information about SIP options monitoring, and conditions when an SBC can be marked as not functional, see [Monitor and troubleshoot Direct Routing](direct-routing-monitor-and-troubleshoot.md).</span></span>

- <span data-ttu-id="1802b-144">**详细 SIP 选项状态** - 除了显示 SIP 选项流存在问题外，运行状况仪表板还提供错误的详细说明。</span><span class="sxs-lookup"><span data-stu-id="1802b-144">**Detailed SIP options status** - In addition to showing that there is an issue with SIP options flow, the Health Dashboard also provides detailed descriptions of the errors.</span></span> <span data-ttu-id="1802b-145">可以通过单击"警告"消息访问说明。</span><span class="sxs-lookup"><span data-stu-id="1802b-145">You can access the description by clicking the “Warning” message.</span></span> <span data-ttu-id="1802b-146">右侧弹出窗口会显示详细的错误说明。</span><span class="sxs-lookup"><span data-stu-id="1802b-146">A pop-up window on the right will show the detailed error description.</span></span>

   <span data-ttu-id="1802b-147">SIP 选项状态消息的可能值如下所示：</span><span class="sxs-lookup"><span data-stu-id="1802b-147">Possible values for SIP options status messages are as follows:</span></span>

    - <span data-ttu-id="1802b-148">活动 - SBC 处于活动状态 -- Microsoft Direct Routing 服务会定期看到选项流动。</span><span class="sxs-lookup"><span data-stu-id="1802b-148">Active – The SBC is active--Microsoft Direct Routing service sees the options flowing on a regular interval.</span></span>

    - <span data-ttu-id="1802b-149">警告，无 SIP 选项 - 使用 New-CsOnlinePSTNGateway 命令创建的数据库 (会话边界控制器) 。</span><span class="sxs-lookup"><span data-stu-id="1802b-149">Warning, no SIP options - The Session Border Controller exists in the database (your administrator created it using the command New-CsOnlinePSTNGateway).</span></span> <span data-ttu-id="1802b-150">它配置为发送 SIP 选项，但直接路由服务从未看到从此 SBC 返回的 SIP 选项。</span><span class="sxs-lookup"><span data-stu-id="1802b-150">It is configured to send SIP options, but the Direct Routing service never saw the SIP options coming back from this SBC.</span></span>

    - <span data-ttu-id="1802b-151">警告，未配置 SIP 消息 - 未打开使用 SIP 选项的中继监视。</span><span class="sxs-lookup"><span data-stu-id="1802b-151">Warning, SIP Messages aren't configured - Trunk monitoring using SIP options isn’t turned on.</span></span> <span data-ttu-id="1802b-152">Microsoft 呼叫系统使用 SIP 选项和传输层安全性 (TLS) 握手监视来检测应用程序级别连接的会话边界控制器 (SDC) 的运行状况。</span><span class="sxs-lookup"><span data-stu-id="1802b-152">Microsoft Calling System uses SIP options and Transport Layer Security (TLS) handshake monitoring to detect the health of the connected Session Border Controllers (SBCs) at the application level.</span></span> <span data-ttu-id="1802b-153">如果可以通过 ping) 在网络级别访问此 (，但证书已过期或 SIP 堆栈不起作用，则你将遇到问题。</span><span class="sxs-lookup"><span data-stu-id="1802b-153">You’ll have problems if this trunk can be reached at the network level (by ping), but the certificate has expired or the SIP stack doesn’t work.</span></span> <span data-ttu-id="1802b-154">为了帮助尽早识别此类问题，Microsoft 建议启用发送 SIP 选项。</span><span class="sxs-lookup"><span data-stu-id="1802b-154">To help identify such problems early, Microsoft recommends enabling sending SIP options.</span></span> <span data-ttu-id="1802b-155">请查看 SBC 制造商文档以配置发送 SIP 选项。</span><span class="sxs-lookup"><span data-stu-id="1802b-155">Check your SBC manufacturer documentation to configure sending SIP options.</span></span>

- <span data-ttu-id="1802b-156">**并发调用容量** - 可以通过将 New- 或 Set-CsOnlinePSTNGateway 命令与 -MaxConcurrentSessions 参数一起指定 SBC 可以处理的并发调用的限制。</span><span class="sxs-lookup"><span data-stu-id="1802b-156">**Concurrent calls capacity** - You can specify the limit of concurrent calls that an SBC can handle by using the New- or Set-CsOnlinePSTNGateway command with the -MaxConcurrentSessions parameter.</span></span> <span data-ttu-id="1802b-157">此参数计算直接路由使用特定 SBC 发送或接收的调用数，并将其与限制集进行比较。</span><span class="sxs-lookup"><span data-stu-id="1802b-157">This parameter calculates how many calls were sent or received by Direct Routing using a specific SBC and compares it with the limit set.</span></span> <span data-ttu-id="1802b-158">注意：如果 SBC 还处理对不同 PBX 的调用，此数字不会显示实际并发调用。</span><span class="sxs-lookup"><span data-stu-id="1802b-158">Note:  If the SBC also handles calls to different PBXs, this number will not show the actual concurrent calls.</span></span>

## <a name="detailed-information-for-each-sbc"></a><span data-ttu-id="1802b-159">每个 SBC 的详细信息</span><span class="sxs-lookup"><span data-stu-id="1802b-159">Detailed information for each SBC</span></span>

<span data-ttu-id="1802b-160">还可以查看特定 SBC 的详细信息，如以下屏幕截图所示：</span><span class="sxs-lookup"><span data-stu-id="1802b-160">You can also view the detailed information for a specific SBC as shown in the following screenshot:</span></span>

![运行状况仪表板 SBC 详细信息](media/direct-routing-dashboard-SBC-detail1.png)

<span data-ttu-id="1802b-162">详细视图显示以下附加参数：</span><span class="sxs-lookup"><span data-stu-id="1802b-162">The detailed view shows the following additional parameters:</span></span>

- <span data-ttu-id="1802b-163">**TLS 连接状态** – 这是与"总体运行状况"页上相同的指标;</span><span class="sxs-lookup"><span data-stu-id="1802b-163">**TLS Connectivity status** – this is the same metric as on the “Overall Health” page;</span></span>

- <span data-ttu-id="1802b-164">**TLS 连接上次状态** – 显示 SBC 与直接路由服务建立 TLS 连接的时间;</span><span class="sxs-lookup"><span data-stu-id="1802b-164">**TLS Connectivity last status** – shows time when the SBC made a TLS connection to the Direct Routing service;</span></span>

- <span data-ttu-id="1802b-165">**SIP 选项状态** - 与"总体运行状况"页上的指标相同。</span><span class="sxs-lookup"><span data-stu-id="1802b-165">**SIP options status** – the same metric as on the “Overall Health” page.</span></span>

- <span data-ttu-id="1802b-166">**上次检查的 SIP 选项** – 上次收到 SIP 选项的时间。</span><span class="sxs-lookup"><span data-stu-id="1802b-166">**SIP options last checked** – time when the SIP options were received last time.</span></span>

- <span data-ttu-id="1802b-167">**SBC 状态** - 基于所有受监视参数的 SBC 总体状态。</span><span class="sxs-lookup"><span data-stu-id="1802b-167">**SBC status** – overall status of the SBC, based on all monitored parameters.</span></span>

- <span data-ttu-id="1802b-168">**并发调用**- 显示 SBC 处理的并发调用数。</span><span class="sxs-lookup"><span data-stu-id="1802b-168">**Concurrent call**- shows  how many concurrent calls the SBC handled.</span></span> <span data-ttu-id="1802b-169">此信息可用于预测所需的并发通道数并查看趋势。</span><span class="sxs-lookup"><span data-stu-id="1802b-169">This information is useful to predict the number of concurrent channels you need and see the trend.</span></span> <span data-ttu-id="1802b-170">可以按天数滑动数据，并按入站/出 (/所有流的呼叫) 。</span><span class="sxs-lookup"><span data-stu-id="1802b-170">You can slide the data by number of days and call direction (inbound/outbound/All streams).</span></span>

- <span data-ttu-id="1802b-171">**网络参数** - 从直接路由接口到会话边界控制器测量所有网络参数。</span><span class="sxs-lookup"><span data-stu-id="1802b-171">**Network parameters** - All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="1802b-172">有关建议值的信息，请参阅为 [Microsoft Teams](./prepare-network.md)准备组织的网络，并查看客户边缘到 Microsoft Edge 的建议值。</span><span class="sxs-lookup"><span data-stu-id="1802b-172">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](./prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

   - <span data-ttu-id="1802b-173">抖动 - 是使用 RTCP 和 RTP 控制协议在两个终结点之间计算的网络传播延迟 (毫秒) 。</span><span class="sxs-lookup"><span data-stu-id="1802b-173">Jitter – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

   - <span data-ttu-id="1802b-174">数据包丢失 – 是未能到达的数据包的度量值;它是在两个终结点之间计算的。</span><span class="sxs-lookup"><span data-stu-id="1802b-174">Packet Loss – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

   - <span data-ttu-id="1802b-175">延迟 - (往返时间) 是发送信号所花的时间长度加上接收该信号的确认所花的时间长度。</span><span class="sxs-lookup"><span data-stu-id="1802b-175">Latency - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="1802b-176">此时间延迟由信号的两个点之间的传播时间组成。</span><span class="sxs-lookup"><span data-stu-id="1802b-176">This time delay consists of the propagation times between the two points of a signal.</span></span>

   <span data-ttu-id="1802b-177">可以按天数滑动数据，并按入站/出 (/所有流的呼叫) 。</span><span class="sxs-lookup"><span data-stu-id="1802b-177">You can slide the data by number of days and call direction (inbound/outbound/All streams).</span></span>

<span data-ttu-id="1802b-178">**网络有效性比率** - 此参数与"总体运行状况"仪表板上显示的参数相同，但可以选择按时序或调用方向对数据进行切片。</span><span class="sxs-lookup"><span data-stu-id="1802b-178">**Network Effectiveness ratio** - This is the same parameter that appears on the Overall Health dashboard, but with the option to slice the data by time series or call direction.</span></span>