---
title: Lync Server 2013：修改 SIP 中继配置设置
description: Lync Server 2013：修改 SIP 中继配置设置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify SIP trunk configuration settings
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49733703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42cb213211a11494a96b5a762734a2b5db49dfbb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562138"
---
# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="4cca0-103">在 Lync Server 2013 中修改 SIP 中继配置设置</span><span class="sxs-lookup"><span data-stu-id="4cca0-103">Modify SIP trunk configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cca0-104">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="4cca0-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="4cca0-p101">SIP 中继配置设置定义了中介服务器和服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。这些设置按下面的指示执行此类操作：</span><span class="sxs-lookup"><span data-stu-id="4cca0-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="4cca0-107">是否应对中继启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="4cca0-107">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="4cca0-108">发送实时传输控制协议 (RTCP) 数据包的条件。</span><span class="sxs-lookup"><span data-stu-id="4cca0-108">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="4cca0-109">每个中继上是否需要安全实时协议 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="4cca0-109">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="4cca0-110">安装 Microsoft Lync Server 2013 时，将为您创建一个全局 SIP 中继配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="4cca0-110">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="4cca0-111">此外，管理员还可以在站点作用域或服务作用域（仅针对 PSTN 网关服务）内创建自定义设置集合。</span><span class="sxs-lookup"><span data-stu-id="4cca0-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="4cca0-112">以后可以使用 Lync Server 控制面板或 Windows PowerShell 修改这些集合中的任何集合。</span><span class="sxs-lookup"><span data-stu-id="4cca0-112">Any of these collections can later be modified using either Lync Server Control Panel or Windows PowerShell.</span></span>

<span data-ttu-id="4cca0-113">使用 Lync Server 控制面板修改 SIP 中继配置设置时，可以使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="4cca0-113">When modifying SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4cca0-114">UI 设置</span><span class="sxs-lookup"><span data-stu-id="4cca0-114">UI Setting</span></span></th>
<th><span data-ttu-id="4cca0-115">PowerShell 参数</span><span class="sxs-lookup"><span data-stu-id="4cca0-115">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="4cca0-116">说明</span><span class="sxs-lookup"><span data-stu-id="4cca0-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4cca0-117">Name</span><span class="sxs-lookup"><span data-stu-id="4cca0-117">Name</span></span></p></td>
<td><p><span data-ttu-id="4cca0-118">标识</span><span class="sxs-lookup"><span data-stu-id="4cca0-118">Identity</span></span></p></td>
<td><p><span data-ttu-id="4cca0-p103">集合的唯一标识符。此属性为只读；您无法更改中继配置设置集合的标识。</span><span class="sxs-lookup"><span data-stu-id="4cca0-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cca0-121">说明</span><span class="sxs-lookup"><span data-stu-id="4cca0-121">Description</span></span></p></td>
<td><p><span data-ttu-id="4cca0-122">说明</span><span class="sxs-lookup"><span data-stu-id="4cca0-122">Description</span></span></p></td>
<td><p><span data-ttu-id="4cca0-123">为管理员提供了存储有关设置的附加信息（例如，中继配置的用途）的方法。</span><span class="sxs-lookup"><span data-stu-id="4cca0-123">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cca0-124">支持的最大早期对话数</span><span class="sxs-lookup"><span data-stu-id="4cca0-124">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="4cca0-125">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="4cca0-125">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="4cca0-126">服务提供商的 PSTN 网关、IP-PBX 或 SBC 可以接收的分叉响应的最大数目，这些响应是针对发送到中介服务器的邀请的。</span><span class="sxs-lookup"><span data-stu-id="4cca0-126">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cca0-127">加密支持级别</span><span class="sxs-lookup"><span data-stu-id="4cca0-127">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="4cca0-128">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="4cca0-128">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="4cca0-129">指示用于保护中介服务器与服务提供商的 PSTN 网关、IP-PBX 或 SBC 之间的媒体流量的支持级别。</span><span class="sxs-lookup"><span data-stu-id="4cca0-129">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="4cca0-130">对于媒体旁路情况，该值必须与媒体配置中的 EncryptionLevel 设置兼容。</span><span class="sxs-lookup"><span data-stu-id="4cca0-130">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="4cca0-131">媒体配置通过使用 <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">set-csmediaconfiguration</a> 和 <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">set-csmediaconfiguration</a> cmdlet 进行设置。</span><span class="sxs-lookup"><span data-stu-id="4cca0-131">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="4cca0-132">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="4cca0-132">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="4cca0-133">Required：必须使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="4cca0-133">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="4cca0-134">Optional：如果网关支持 SRTP，将使用 SRTP。</span><span class="sxs-lookup"><span data-stu-id="4cca0-134">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="4cca0-135">Not Supported：SRTP 加密不受支持，因此不使用该功能。</span><span class="sxs-lookup"><span data-stu-id="4cca0-135">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="4cca0-p105">仅当网关配置为使用传输层安全性 (TLS) 时，才会使用 SRTPMode。如果将网关配置为使用传输控制协议 (TCP)，则 SRTPMode 会在内部设置为“Not Supported”。</span><span class="sxs-lookup"><span data-stu-id="4cca0-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cca0-138">引用支持</span><span class="sxs-lookup"><span data-stu-id="4cca0-138">Refer support</span></span></p></td>
<td><p><span data-ttu-id="4cca0-139">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="4cca0-139">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="4cca0-140">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="4cca0-140">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="4cca0-141">如果设置为“允许将引用发送到网关”<strong></strong>，则指示中继支持接收来自中介服务器的引用请求。</span><span class="sxs-lookup"><span data-stu-id="4cca0-141">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="4cca0-142">如果设置为“允许使用第三方呼叫控制的引用”<strong></strong>，则指示 3pcc 协议可用于允许转接的呼叫绕过宿主网站。</span><span class="sxs-lookup"><span data-stu-id="4cca0-142">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="4cca0-143">3pcc 也称为 &quot; "第三方控制"， &quot; 当第三方用于连接一对 (呼叫者时，将发生此事件。例如，操作员将来自人员 a 的呼叫放入个人 B) 中。</span><span class="sxs-lookup"><span data-stu-id="4cca0-143">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cca0-144">启用媒体旁路</span><span class="sxs-lookup"><span data-stu-id="4cca0-144">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="4cca0-145">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="4cca0-145">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="4cca0-p107">指示是否为此中继启用媒体旁路。仅当启用了“集中式媒体处理”<strong></strong>时才能启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="4cca0-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cca0-148">集中式媒体处理</span><span class="sxs-lookup"><span data-stu-id="4cca0-148">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="4cca0-149">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="4cca0-149">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="4cca0-p108">指示是否有已知的媒体终结点。（例如，PSTN 网关就是一个已知的媒体端点，其中媒体终端与信号终端具有相同的 IP。）</span><span class="sxs-lookup"><span data-stu-id="4cca0-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cca0-152">启用 RTP 闭锁</span><span class="sxs-lookup"><span data-stu-id="4cca0-152">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="4cca0-153">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="4cca0-153">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="4cca0-p109">指示 SIP 中继是否支持 RTP 闭锁。RTP 闭锁是一种通过 NAT（网络地址转换器）设备或防火墙实现 RTP/RTCP 连接的技术。</span><span class="sxs-lookup"><span data-stu-id="4cca0-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cca0-156">启用呼叫转移历史记录</span><span class="sxs-lookup"><span data-stu-id="4cca0-156">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="4cca0-157">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="4cca0-157">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="4cca0-158">指示是否通过中继转移呼叫历史记录信息。</span><span class="sxs-lookup"><span data-stu-id="4cca0-158">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cca0-159">启用转移 P-Asserted-Identity 数据</span><span class="sxs-lookup"><span data-stu-id="4cca0-159">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="4cca0-160">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="4cca0-160">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="4cca0-p110">指示 P-Asserted-Identity (PAI) 标头是否随呼叫一起转移。PAI 标头提供了一种验证呼叫者身份的方法。</span><span class="sxs-lookup"><span data-stu-id="4cca0-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cca0-163">启用出站路由故障转移计时器</span><span class="sxs-lookup"><span data-stu-id="4cca0-163">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="4cca0-164">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="4cca0-164">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="4cca0-p111">指示是否将网关在 10 秒内未应答的出站呼叫路由到下一个可用中继；如果没有任何其他中继，则将自动放弃呼叫。在网络和网关响应较慢的组织中，这可能会导致不必要地放弃一些呼叫。</span><span class="sxs-lookup"><span data-stu-id="4cca0-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cca0-167">关联的 PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="4cca0-167">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="4cca0-168">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="4cca0-168">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="4cca0-169">分配给中继的 PSTN 用法的集合。</span><span class="sxs-lookup"><span data-stu-id="4cca0-169">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cca0-170">要测试的已转换号码</span><span class="sxs-lookup"><span data-stu-id="4cca0-170">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="4cca0-171">不适用</span><span class="sxs-lookup"><span data-stu-id="4cca0-171">N/A</span></span></p></td>
<td><p><span data-ttu-id="4cca0-172">可用于对中继配置设置执行临时测试的电话号码。</span><span class="sxs-lookup"><span data-stu-id="4cca0-172">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cca0-173">关联的转换规则</span><span class="sxs-lookup"><span data-stu-id="4cca0-173">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="4cca0-174">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="4cca0-174">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="4cca0-175">应用于出站路由处理的呼叫（路由到 PBX 或 PSTN 目标的呼叫）的电话号码转换规则的集合。</span><span class="sxs-lookup"><span data-stu-id="4cca0-175">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cca0-176">被叫号码转换规则</span><span class="sxs-lookup"><span data-stu-id="4cca0-176">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="4cca0-177">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="4cca0-177">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="4cca0-178">分配给中继的出站主叫号码转换规则的集合。</span><span class="sxs-lookup"><span data-stu-id="4cca0-178">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cca0-179">要测试的电话号码</span><span class="sxs-lookup"><span data-stu-id="4cca0-179">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="4cca0-180">不适用</span><span class="sxs-lookup"><span data-stu-id="4cca0-180">N/A</span></span></p></td>
<td><p><span data-ttu-id="4cca0-181">可用于对转换规则执行临时测试的电话号码。</span><span class="sxs-lookup"><span data-stu-id="4cca0-181">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cca0-182">主叫号码</span><span class="sxs-lookup"><span data-stu-id="4cca0-182">Calling number</span></span></p></td>
<td><p><span data-ttu-id="4cca0-183">不适用</span><span class="sxs-lookup"><span data-stu-id="4cca0-183">N/A</span></span></p></td>
<td><p><span data-ttu-id="4cca0-184">指示要测试的电话号码是呼叫者的电话号码。</span><span class="sxs-lookup"><span data-stu-id="4cca0-184">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cca0-185">被叫号码</span><span class="sxs-lookup"><span data-stu-id="4cca0-185">Called number</span></span></p></td>
<td><p><span data-ttu-id="4cca0-186">不适用</span><span class="sxs-lookup"><span data-stu-id="4cca0-186">N/A</span></span></p></td>
<td><p><span data-ttu-id="4cca0-187">指示要测试的电话号码是被呼叫的人员的电话号码。</span><span class="sxs-lookup"><span data-stu-id="4cca0-187">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="4cca0-188">Lync Server Remove-cstrunkconfiguration cmdlet 支持未在 Lync Server 控制面板中显示的其他属性。</span><span class="sxs-lookup"><span data-stu-id="4cca0-188">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="4cca0-189">有关详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">remove-cstrunkconfiguration</A> cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="4cca0-189">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="4cca0-190">使用 Lync Server 控制面板修改 SIP 中继配置设置</span><span class="sxs-lookup"><span data-stu-id="4cca0-190">To modify SIP trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4cca0-191">在 "Lync Server 控制面板" 中，单击 " **语音路由**"，然后单击 " **中继配置**"。</span><span class="sxs-lookup"><span data-stu-id="4cca0-191">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="4cca0-p113">在“Trunk 配置”\*\*\*\* 选项卡上，双击要修改的中继配置设置。请注意，您一次只能编辑一个设置集合。如果要对多个集合进行同一更改，请改用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4cca0-p113">On the **Trunk Configuration** tab, double-click the trunk configuration settings to be modified. Note that you can only edit one collection of settings at a time. If you would like to make the same changes on multiple collections, use Windows PowerShell instead.</span></span>

3.  <span data-ttu-id="4cca0-195">在 " **编辑中继配置** " 对话框中，进行适当的选择，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="4cca0-195">In the **Edit Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

4.  <span data-ttu-id="4cca0-p114">集合的“状态”\*\*\*\* 属性将更新为“未提交”\*\*\*\*。若要提交更改和删除集合，请单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4cca0-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

5.  <span data-ttu-id="4cca0-198">在“未提交的语音配置设置”\*\*\*\* 对话框中，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4cca0-198">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="4cca0-199">在“Microsoft Lync Server 2013 控制面板”\*\*\*\* 对话框中，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4cca0-199">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

