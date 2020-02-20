---
title: Lync Server 2013：创建新的中继配置设置集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new collection of trunk configuration settings
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49733647
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f07e5dc814887a7304a48602e04f48a00137bf8f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="f3ae7-102">在 Lync Server 2013 中创建一个新的中继配置设置集合</span><span class="sxs-lookup"><span data-stu-id="f3ae7-102">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3ae7-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f3ae7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f3ae7-p101">SIP 中继配置设置定义了中介服务器和服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。这些设置按下面的指示执行此类操作：</span><span class="sxs-lookup"><span data-stu-id="f3ae7-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="f3ae7-106">是否应对中继启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="f3ae7-107">发送实时传输控制协议 (RTCP) 数据包的条件。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="f3ae7-108">每个中继上是否需要安全实时协议 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="f3ae7-109">安装 Microsoft Lync Server 2013 时，将为您创建一个全局 SIP 中继配置设置集合。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="f3ae7-110">此外，管理员还可以在站点作用域或服务作用域（仅针对 PSTN 网关服务）内创建自定义设置集合。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="f3ae7-111">使用 Lync Server 控制面板创建 SIP 中继配置设置时，可以使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="f3ae7-111">When creating SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3ae7-112">UI 设置</span><span class="sxs-lookup"><span data-stu-id="f3ae7-112">UI Setting</span></span></th>
<th><span data-ttu-id="f3ae7-113">PowerShell 参数</span><span class="sxs-lookup"><span data-stu-id="f3ae7-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="f3ae7-114">说明</span><span class="sxs-lookup"><span data-stu-id="f3ae7-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3ae7-115">Name</span><span class="sxs-lookup"><span data-stu-id="f3ae7-115">Name</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-116">标识</span><span class="sxs-lookup"><span data-stu-id="f3ae7-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-p103">集合的唯一标识符。此属性为只读；您无法更改中继配置设置集合的标识。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ae7-119">说明</span><span class="sxs-lookup"><span data-stu-id="f3ae7-119">Description</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-120">说明</span><span class="sxs-lookup"><span data-stu-id="f3ae7-120">Description</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-121">为管理员提供了存储有关设置的附加信息（例如，中继配置的用途）的方法。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-121">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3ae7-122">支持的最大早期对话数</span><span class="sxs-lookup"><span data-stu-id="f3ae7-122">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-123">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="f3ae7-123">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-124">服务提供商的 PSTN 网关、IP-PBX 或 SBC 可以接收的分叉响应的最大数目，这些响应是针对发送到中介服务器的邀请的。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-124">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ae7-125">加密支持级别</span><span class="sxs-lookup"><span data-stu-id="f3ae7-125">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-126">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="f3ae7-126">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-127">指示用于保护中介服务器与服务提供商的 PSTN 网关、IP-PBX 或 SBC 之间的媒体流量的支持级别。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-127">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="f3ae7-128">对于媒体旁路情况，该值必须与媒体配置中的 EncryptionLevel 设置兼容。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-128">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="f3ae7-129">媒体配置通过使用<a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">set-csmediaconfiguration</a>和<a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">set-csmediaconfiguration</a> cmdlet 进行设置。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-129">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="f3ae7-130">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="f3ae7-130">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="f3ae7-131">Required：必须使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-131">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="f3ae7-132">Optional：如果网关支持 SRTP，将使用 SRTP。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-132">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="f3ae7-133">Not Supported：SRTP 加密不受支持，因此不使用该功能。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-133">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="f3ae7-p105">仅当网关配置为使用传输层安全性 (TLS) 时，才会使用 SRTPMode。如果将网关配置为使用传输控制协议 (TCP)，则 SRTPMode 会在内部设置为“Not Supported”。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3ae7-136">引用支持</span><span class="sxs-lookup"><span data-stu-id="f3ae7-136">Refer support</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-137">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="f3ae7-137">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="f3ae7-138">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="f3ae7-138">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-139">如果设置为“允许将引用发送到网关”<strong></strong>，则指示中继支持接收来自中介服务器的引用请求。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-139">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="f3ae7-140">如果设置为“允许使用第三方呼叫控制的引用”<strong></strong>，则指示 3pcc 协议可用于允许转接的呼叫绕过宿主网站。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-140">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="f3ae7-141">3pcc 也称为&quot;第三方控件，&quot;在使用第三方连接一对呼叫者时（例如，操作员将来自某人 a 的呼叫放入个人 B 时）发生此事件。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-141">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ae7-142">启用媒体旁路</span><span class="sxs-lookup"><span data-stu-id="f3ae7-142">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-143">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="f3ae7-143">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-p107">指示是否为此中继启用媒体旁路。仅当启用了“集中式媒体处理”<strong></strong>时才能启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3ae7-146">集中式媒体处理</span><span class="sxs-lookup"><span data-stu-id="f3ae7-146">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-147">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="f3ae7-147">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-p108">指示是否有已知的媒体终结点。（例如，PSTN 网关就是一个已知的媒体端点，其中媒体终端与信号终端具有相同的 IP。）</span><span class="sxs-lookup"><span data-stu-id="f3ae7-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ae7-150">启用 RTP 闭锁</span><span class="sxs-lookup"><span data-stu-id="f3ae7-150">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-151">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="f3ae7-151">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-p109">指示 SIP 中继是否支持 RTP 闭锁。RTP 闭锁是一种通过 NAT（网络地址转换器）设备或防火墙实现 RTP/RTCP 连接的技术。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3ae7-154">启用呼叫转移历史记录</span><span class="sxs-lookup"><span data-stu-id="f3ae7-154">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-155">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="f3ae7-155">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-156">指示是否通过中继转移呼叫历史记录信息。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-156">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ae7-157">启用转移 P-Asserted-Identity 数据</span><span class="sxs-lookup"><span data-stu-id="f3ae7-157">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-158">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="f3ae7-158">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-p110">指示 P-Asserted-Identity (PAI) 标头是否随呼叫一起转移。PAI 标头提供了一种验证呼叫者身份的方法。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3ae7-161">启用出站路由故障转移计时器</span><span class="sxs-lookup"><span data-stu-id="f3ae7-161">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-162">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="f3ae7-162">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-p111">指示是否将网关在 10 秒内未应答的出站呼叫路由到下一个可用中继；如果没有任何其他中继，则将自动放弃呼叫。在网络和网关响应较慢的组织中，这可能会导致不必要地放弃一些呼叫。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ae7-165">关联的 PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="f3ae7-165">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-166">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="f3ae7-166">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-167">分配给中继的 PSTN 用法的集合。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-167">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3ae7-168">要测试的已转换号码</span><span class="sxs-lookup"><span data-stu-id="f3ae7-168">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-169">不适用</span><span class="sxs-lookup"><span data-stu-id="f3ae7-169">N/A</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-170">可用于对中继配置设置执行临时测试的电话号码。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-170">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ae7-171">关联的转换规则</span><span class="sxs-lookup"><span data-stu-id="f3ae7-171">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-172">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="f3ae7-172">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-173">应用于出站路由处理的呼叫（路由到 PBX 或 PSTN 目标的呼叫）的电话号码转换规则的集合。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-173">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3ae7-174">被叫号码转换规则</span><span class="sxs-lookup"><span data-stu-id="f3ae7-174">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-175">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="f3ae7-175">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-176">分配给中继的出站主叫号码转换规则的集合。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-176">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ae7-177">要测试的电话号码</span><span class="sxs-lookup"><span data-stu-id="f3ae7-177">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-178">不适用</span><span class="sxs-lookup"><span data-stu-id="f3ae7-178">N/A</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-179">可用于对转换规则执行临时测试的电话号码。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-179">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3ae7-180">主叫号码</span><span class="sxs-lookup"><span data-stu-id="f3ae7-180">Calling number</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-181">不适用</span><span class="sxs-lookup"><span data-stu-id="f3ae7-181">N/A</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-182">指示要测试的电话号码是呼叫者的电话号码。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-182">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3ae7-183">被叫号码</span><span class="sxs-lookup"><span data-stu-id="f3ae7-183">Called number</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-184">不适用</span><span class="sxs-lookup"><span data-stu-id="f3ae7-184">N/A</span></span></p></td>
<td><p><span data-ttu-id="f3ae7-185">指示要测试的电话号码是被呼叫的人员的电话号码。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-185">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f3ae7-186">Lync Server Remove-cstrunkconfiguration cmdlet 支持未在 Lync Server 控制面板中显示的其他属性。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-186">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="f3ae7-187">有关详细信息，请参阅<A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">remove-cstrunkconfiguration</A> cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-187">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="f3ae7-188">使用 Lync Server 控制面板创建新的中继配置设置</span><span class="sxs-lookup"><span data-stu-id="f3ae7-188">To create new trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f3ae7-189">在 "Lync Server 控制面板" 中，单击 "**语音路由**"，然后单击 "**中继配置**"。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-189">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="f3ae7-190">在“Trunk 配置”\*\*\*\* 选项卡上，单击“新建”\*\*\*\*，然后单击“站点 Trunk”\*\*\*\* 以创建站点作用域的新设置，或“池 Trunk”\*\*\*\* 创建服务作用域的新设置。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-190">On the **Trunk Configuration** tab, click **New**, and then click **Site trunk** to create the new settings at the site scope, or **Pool trunk** to create the new settings at the service scope.</span></span>

3.  <span data-ttu-id="f3ae7-p113">在“选择站点”\*\*\*\* 或“选择服务”\*\*\*\* 对话框（根据您是创建站点作用域还是服务作用域设置显示的对话框），选择新配置设置的位置，然后单击“确定”\*\*\*\*。如果对话框为空，则意味着没有位置可创建新设置；例如，如果“选择站点”\*\*\*\* 对话框为空，则意味着您的所有站点已分配有中继配置站点的集合，并且每个站点（以及每个服务）只能承载一个此类集合。在此情况下，您可删除现有集合并创建新的集合，或只修改现有集合。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-p113">In the **Select a Site** or the **Select a Service** dialog box (the dialog box that appears will depend on whether you are creating site-scoped or service-scoped settings) select the location for the new configuration settings and then click **OK**. If the dialog box is blank, that means there is no place to create the new settings; for example, if the **Select a Site** dialog box is blank that means that all of your sites have already been assigned a collection of trunk configuration sites, and each site (and each service) can only host one such collection. In that case, you can either delete the existing collection and create a new collection, or simply modify the existing collection.</span></span>

4.  <span data-ttu-id="f3ae7-194">在“新建 Trunk 配置”\*\*\*\* 对话框中，进行适当的选择，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-194">In the **New Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

5.  <span data-ttu-id="f3ae7-p114">集合的“状态”\*\*\*\* 属性将更新为“未提交”\*\*\*\*。若要提交更改和删除集合，请单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

6.  <span data-ttu-id="f3ae7-197">在“未提交的语音配置设置”\*\*\*\* 对话框中，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

7.  <span data-ttu-id="f3ae7-198">在“Microsoft Lync Server 2013 控制面板”\*\*\*\* 对话框中，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f3ae7-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

