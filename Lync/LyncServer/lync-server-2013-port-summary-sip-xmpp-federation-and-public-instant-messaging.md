---
title: 端口摘要-SIP、XMPP 联合身份验证和公共即时消息
description: 端口摘要-SIP、XMPP 联盟和公共即时消息。
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
ms.openlocfilehash: 7c58dbf7bdd56b4678d56f96a11332219bb40c17
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566350"
---
# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="bec76-103">Lync Server 2013 中的端口摘要-SIP、XMPP 联合身份验证和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="bec76-103">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bec76-104">_**上次修改的主题：** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="bec76-104">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="bec76-105">与 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通信服务器的联合身份验证的端口、协议和防火墙要求与部署的边缘服务器类似。</span><span class="sxs-lookup"><span data-stu-id="bec76-105">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="bec76-106">客户端通过 TLS/SIP/TCP 443 启动与访问边缘服务的通信。</span><span class="sxs-lookup"><span data-stu-id="bec76-106">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="bec76-107">但是，联盟伙伴将启动与 MTLS/SIP/TCP 5061 的访问边缘服务的通信。</span><span class="sxs-lookup"><span data-stu-id="bec76-107">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="bec76-108">若要将防火墙配置为支持公用即时消息连接所需的端口和协议，请首先注意 SIP/MTLS/TCP 5061 是双向的，以确保公共 IM 提供商中的联系人能够联系 Lync 客户端，或与 Lync 联系以联系公共 IM 联系人。</span><span class="sxs-lookup"><span data-stu-id="bec76-108">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="bec76-109">Windows Live Messenger 可以参与与 Lync 客户端的音频/视频通信。</span><span class="sxs-lookup"><span data-stu-id="bec76-109">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="bec76-110">此帐户适用于通常在防火墙上支持作为外部用户的 Lync 客户端的防火墙端口和协议配置。</span><span class="sxs-lookup"><span data-stu-id="bec76-110">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="bec76-111">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="bec76-111">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="bec76-112">与 Windows Live Messenger 的联盟要求在 Lync Standard Client Access 许可证 (CAL) 之外，不需要其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="bec76-112">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="bec76-113">Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</span><span class="sxs-lookup"><span data-stu-id="bec76-113">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="bec76-114">与 Messenger 客户联系人的联盟将于2013年3月15日正式结束（中国大陆除外）。</span><span class="sxs-lookup"><span data-stu-id="bec76-114">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="bec76-115">Skype 将成为以前使用 Messenger 的联盟用户的联合身份验证客户端。</span><span class="sxs-lookup"><span data-stu-id="bec76-115">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="bec76-116">为可扩展消息和状态协议定义的端口和协议 (XMPP 在边缘服务器上部署) 代理允许从 XMPP 联合合作伙伴到边缘服务器的通信，还允许从边缘服务器到 XMPP 联盟伙伴的通信。</span><span class="sxs-lookup"><span data-stu-id="bec76-116">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="bec76-117">在面向内部的防火墙上定义的规则也是从前端服务器或前端池到边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="bec76-117">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="bec76-118">防火墙摘要-SIP 联合</span><span class="sxs-lookup"><span data-stu-id="bec76-118">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bec76-119">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="bec76-119">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="bec76-120">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="bec76-120">Source IP address</span></span></th>
<th><span data-ttu-id="bec76-121">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="bec76-121">Destination IP address</span></span></th>
<th><span data-ttu-id="bec76-122">注释</span><span class="sxs-lookup"><span data-stu-id="bec76-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bec76-123">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="bec76-123">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="bec76-124">访问边缘服务公用 IP 地址</span><span class="sxs-lookup"><span data-stu-id="bec76-124">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="bec76-125">任何</span><span class="sxs-lookup"><span data-stu-id="bec76-125">Any</span></span></p></td>
<td><p><span data-ttu-id="bec76-126">对于使用 SIP 的联盟和公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="bec76-126">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="bec76-127">防火墙摘要 – 公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="bec76-127">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bec76-128">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="bec76-128">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="bec76-129">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="bec76-129">Source IP address</span></span></th>
<th><span data-ttu-id="bec76-130">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="bec76-130">Destination IP address</span></span></th>
<th><span data-ttu-id="bec76-131">注释</span><span class="sxs-lookup"><span data-stu-id="bec76-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bec76-132">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="bec76-132">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="bec76-133">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="bec76-133">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="bec76-134">边缘服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="bec76-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="bec76-135">用于使用 SIP 的联盟和公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="bec76-135">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bec76-136">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="bec76-136">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="bec76-137">边缘服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="bec76-137">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="bec76-138">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="bec76-138">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="bec76-139">用于使用 SIP 的联盟和公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="bec76-139">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bec76-140">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="bec76-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="bec76-141">客户端</span><span class="sxs-lookup"><span data-stu-id="bec76-141">Clients</span></span></p></td>
<td><p><span data-ttu-id="bec76-142">边缘服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="bec76-142">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="bec76-143">用于外部用户访问的客户端到服务器 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="bec76-143">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bec76-144">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="bec76-144">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="bec76-145">边缘服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="bec76-145">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="bec76-146">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="bec76-146">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="bec76-147">用于与 Windows Live Messenger 的 A/V 会话，前提是配置了公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="bec76-147">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bec76-148">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="bec76-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="bec76-149">边缘服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="bec76-149">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="bec76-150">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="bec76-150">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="bec76-151">对于使用 Windows Live Messenger 的公共 IM 连接是必需的。</span><span class="sxs-lookup"><span data-stu-id="bec76-151">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bec76-152">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="bec76-152">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="bec76-153">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="bec76-153">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="bec76-154">边缘服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="bec76-154">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="bec76-155">对于使用 Windows Live Messenger 的公共 IM 连接是必需的。</span><span class="sxs-lookup"><span data-stu-id="bec76-155">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="bec76-156">防火墙摘要-可扩展消息传递和状态协议 (XMPP) </span><span class="sxs-lookup"><span data-stu-id="bec76-156">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bec76-157">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="bec76-157">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="bec76-158">源（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="bec76-158">Source (IP address)</span></span></th>
<th><span data-ttu-id="bec76-159">目标（IP 地址）</span><span class="sxs-lookup"><span data-stu-id="bec76-159">Destination (IP address)</span></span></th>
<th><span data-ttu-id="bec76-160">Comments</span><span class="sxs-lookup"><span data-stu-id="bec76-160">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bec76-161">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="bec76-161">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="bec76-162">任何</span><span class="sxs-lookup"><span data-stu-id="bec76-162">Any</span></span></p></td>
<td><p><span data-ttu-id="bec76-163">访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="bec76-163">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="bec76-164">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="bec76-164">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="bec76-165">允许与来自联合 XMPP 合作伙伴的边缘服务器 XMPP 代理的通信</span><span class="sxs-lookup"><span data-stu-id="bec76-165">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bec76-166">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="bec76-166">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="bec76-167">访问边缘服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="bec76-167">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="bec76-168">任何</span><span class="sxs-lookup"><span data-stu-id="bec76-168">Any</span></span></p></td>
<td><p><span data-ttu-id="bec76-169">用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="bec76-169">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="bec76-170">允许从边缘服务器 XMPP 代理到联合 XMPP 合作伙伴的通信</span><span class="sxs-lookup"><span data-stu-id="bec76-170">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bec76-171">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="bec76-171">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="bec76-172">任何</span><span class="sxs-lookup"><span data-stu-id="bec76-172">Any</span></span></p></td>
<td><p><span data-ttu-id="bec76-173">内部边缘服务器接口 IP</span><span class="sxs-lookup"><span data-stu-id="bec76-173">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="bec76-174">从前端服务器或前端池上的 XMPP 网关到边缘服务器的内部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="bec76-174">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bec76-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bec76-175">See Also</span></span>


[<span data-ttu-id="bec76-176">Lync Server 2013 中的外部用户访问方案</span><span class="sxs-lookup"><span data-stu-id="bec76-176">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="bec76-177">确定 Lync Server 2013 的外部 A/V 防火墙和端口要求</span><span class="sxs-lookup"><span data-stu-id="bec76-177">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="bec76-178">在 Lync Server 2013 中管理 XMPP 联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="bec76-178">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

