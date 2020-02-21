---
title: 端口摘要-SIP、XMPP 联合身份验证和公共即时消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8fd24bab9596f12060c87937d98cc2a57d0c887
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="43450-102">Lync Server 2013 中的端口摘要-SIP、XMPP 联合身份验证和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="43450-102">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43450-103">_**上次修改的主题：** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="43450-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="43450-104">与 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通信服务器的联合身份验证的端口、协议和防火墙要求与部署的边缘服务器类似。</span><span class="sxs-lookup"><span data-stu-id="43450-104">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="43450-105">客户端通过 TLS/SIP/TCP 443 启动与访问边缘服务的通信。</span><span class="sxs-lookup"><span data-stu-id="43450-105">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="43450-106">但是，联盟伙伴将启动与 MTLS/SIP/TCP 5061 的访问边缘服务的通信。</span><span class="sxs-lookup"><span data-stu-id="43450-106">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="43450-107">若要将防火墙配置为支持公用即时消息连接所需的端口和协议，请首先注意 SIP/MTLS/TCP 5061 是双向的，以确保公共 IM 提供商中的联系人能够联系 Lync 客户端，或与 Lync 联系以联系公共 IM 联系人。</span><span class="sxs-lookup"><span data-stu-id="43450-107">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="43450-108">Windows Live Messenger 可以参与与 Lync 客户端的音频/视频通信。</span><span class="sxs-lookup"><span data-stu-id="43450-108">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="43450-109">此帐户适用于通常在防火墙上支持作为外部用户的 Lync 客户端的防火墙端口和协议配置。</span><span class="sxs-lookup"><span data-stu-id="43450-109">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="43450-110">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="43450-110">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="43450-111">与 Windows Live Messenger 的联盟不需要其他用户/设备许可证，而不能超过 Lync Standard Client Access 许可证（CAL）。</span><span class="sxs-lookup"><span data-stu-id="43450-111">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="43450-112">Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</span><span class="sxs-lookup"><span data-stu-id="43450-112">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="43450-113">与 Messenger 客户联系人的联盟将于2013年3月15日正式结束（中国大陆除外）。</span><span class="sxs-lookup"><span data-stu-id="43450-113">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="43450-114">Skype 将成为以前使用 Messenger 的联盟用户的联合身份验证客户端。</span><span class="sxs-lookup"><span data-stu-id="43450-114">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="43450-115">为在边缘服务器上部署的可扩展消息和状态协议（XMPP）代理定义的端口和协议允许从 XMPP 联合合作伙伴到边缘服务器的通信，还允许从边缘服务器到 XMPP 的通信。联盟伙伴。</span><span class="sxs-lookup"><span data-stu-id="43450-115">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="43450-116">在面向内部的防火墙上定义的规则也是从前端服务器或前端池到边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="43450-116">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="43450-117">防火墙摘要-SIP 联合</span><span class="sxs-lookup"><span data-stu-id="43450-117">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43450-118">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="43450-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="43450-119">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="43450-119">Source IP address</span></span></th>
<th><span data-ttu-id="43450-120">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="43450-120">Destination IP address</span></span></th>
<th><span data-ttu-id="43450-121">备注</span><span class="sxs-lookup"><span data-stu-id="43450-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43450-122">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="43450-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="43450-123">访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="43450-123">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="43450-124">任意</span><span class="sxs-lookup"><span data-stu-id="43450-124">Any</span></span></p></td>
<td><p><span data-ttu-id="43450-125">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="43450-125">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="43450-126">防火墙摘要 – 公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="43450-126">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43450-127">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="43450-127">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="43450-128">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="43450-128">Source IP address</span></span></th>
<th><span data-ttu-id="43450-129">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="43450-129">Destination IP address</span></span></th>
<th><span data-ttu-id="43450-130">备注</span><span class="sxs-lookup"><span data-stu-id="43450-130">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43450-131">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="43450-131">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="43450-132">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="43450-132">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="43450-133">边缘服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="43450-133">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="43450-134">用于使用 SIP 的联盟和公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="43450-134">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43450-135">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="43450-135">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="43450-136">边缘服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="43450-136">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="43450-137">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="43450-137">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="43450-138">用于使用 SIP 的联盟和公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="43450-138">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43450-139">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="43450-139">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="43450-140">客户端</span><span class="sxs-lookup"><span data-stu-id="43450-140">Clients</span></span></p></td>
<td><p><span data-ttu-id="43450-141">边缘服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="43450-141">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="43450-142">用于外部用户访问的客户端到服务器 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="43450-142">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43450-143">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="43450-143">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="43450-144">边缘服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="43450-144">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="43450-145">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="43450-145">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="43450-146">用于与 Windows Live Messenger 的 A/V 会话，前提是配置了公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="43450-146">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43450-147">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="43450-147">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="43450-148">边缘服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="43450-148">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="43450-149">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="43450-149">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="43450-150">对于使用 Windows Live Messenger 的公共 IM 连接是必需的。</span><span class="sxs-lookup"><span data-stu-id="43450-150">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43450-151">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="43450-151">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="43450-152">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="43450-152">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="43450-153">边缘服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="43450-153">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="43450-154">对于使用 Windows Live Messenger 的公共 IM 连接是必需的。</span><span class="sxs-lookup"><span data-stu-id="43450-154">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="43450-155">防火墙摘要-可扩展消息传递和状态协议（XMPP）</span><span class="sxs-lookup"><span data-stu-id="43450-155">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43450-156">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="43450-156">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="43450-157">源（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="43450-157">Source (IP address)</span></span></th>
<th><span data-ttu-id="43450-158">目标（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="43450-158">Destination (IP address)</span></span></th>
<th><span data-ttu-id="43450-159">注释</span><span class="sxs-lookup"><span data-stu-id="43450-159">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43450-160">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="43450-160">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="43450-161">任意</span><span class="sxs-lookup"><span data-stu-id="43450-161">Any</span></span></p></td>
<td><p><span data-ttu-id="43450-162">访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="43450-162">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="43450-163">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="43450-163">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="43450-164">允许与来自联合 XMPP 合作伙伴的边缘服务器 XMPP 代理的通信</span><span class="sxs-lookup"><span data-stu-id="43450-164">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43450-165">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="43450-165">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="43450-166">访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="43450-166">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="43450-167">任意</span><span class="sxs-lookup"><span data-stu-id="43450-167">Any</span></span></p></td>
<td><p><span data-ttu-id="43450-168">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="43450-168">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="43450-169">允许从边缘服务器 XMPP 代理到联合 XMPP 合作伙伴的通信</span><span class="sxs-lookup"><span data-stu-id="43450-169">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43450-170">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="43450-170">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="43450-171">任意</span><span class="sxs-lookup"><span data-stu-id="43450-171">Any</span></span></p></td>
<td><p><span data-ttu-id="43450-172">内部边缘服务器接口 IP</span><span class="sxs-lookup"><span data-stu-id="43450-172">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="43450-173">从前端服务器或前端池上的 XMPP 网关到边缘服务器的内部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="43450-173">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="43450-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43450-174">See Also</span></span>


[<span data-ttu-id="43450-175">Lync Server 2013 中的外部用户访问方案</span><span class="sxs-lookup"><span data-stu-id="43450-175">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="43450-176">确定 Lync Server 2013 的外部 A/V 防火墙和端口要求</span><span class="sxs-lookup"><span data-stu-id="43450-176">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="43450-177">在 Lync Server 2013 中管理 XMPP 联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="43450-177">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

