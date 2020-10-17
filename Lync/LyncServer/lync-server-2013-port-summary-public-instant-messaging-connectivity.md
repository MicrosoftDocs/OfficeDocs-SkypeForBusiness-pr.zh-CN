---
title: Lync Server 2013：端口摘要-公共即时消息连接
description: Lync Server 2013：端口摘要-公共即时消息连接。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4137b5f92e043dc15dc9aa1f0b9593b4d9f7c2ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543058"
---
# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="8b611-103">端口摘要-Lync Server 2013 中的公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="8b611-103">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b611-104">_**上次修改的主题：** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="8b611-104">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="8b611-105">若要将防火墙配置为支持公用即时消息连接所需的端口和协议，请首先注意 SIP/MTLS/TCP 5061 是双向的，以确保公共 IM 提供商中的联系人能够联系 Lync 客户端，或与 Lync 联系以联系公共 IM 联系人。</span><span class="sxs-lookup"><span data-stu-id="8b611-105">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="8b611-106">Windows Live Messenger 可以参与与 Lync 客户端的音频/视频通信。</span><span class="sxs-lookup"><span data-stu-id="8b611-106">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="8b611-107">此帐户适用于通常在防火墙上支持作为外部用户的 Lync 客户端的防火墙端口和协议配置。</span><span class="sxs-lookup"><span data-stu-id="8b611-107">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8b611-108">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="8b611-108">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="8b611-109">与 Windows Live Messenger 的联盟要求在 Lync Standard Client Access 许可证 (CAL) 之外，不需要其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="8b611-109">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="8b611-110">Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</span><span class="sxs-lookup"><span data-stu-id="8b611-110">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="8b611-111">与 Messenger 客户联系人的联盟将于2013年3月15日正式结束（中国大陆除外）。</span><span class="sxs-lookup"><span data-stu-id="8b611-111">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="8b611-112">Skype 将成为以前使用 Messenger 的联盟用户的联合身份验证客户端。</span><span class="sxs-lookup"><span data-stu-id="8b611-112">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="8b611-113">防火墙摘要 – 公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="8b611-113">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b611-114">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="8b611-114">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8b611-115">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8b611-115">Source IP address</span></span></th>
<th><span data-ttu-id="8b611-116">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8b611-116">Destination IP address</span></span></th>
<th><span data-ttu-id="8b611-117">注释</span><span class="sxs-lookup"><span data-stu-id="8b611-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b611-118">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8b611-118">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8b611-119">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="8b611-119">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="8b611-120">边缘服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="8b611-120">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="8b611-121">用于使用 SIP 的联盟和公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="8b611-121">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b611-122">Access/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8b611-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8b611-123">边缘服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="8b611-123">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="8b611-124">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="8b611-124">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="8b611-125">用于使用 SIP 的联盟和公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="8b611-125">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b611-126">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="8b611-126">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8b611-127">客户端</span><span class="sxs-lookup"><span data-stu-id="8b611-127">Clients</span></span></p></td>
<td><p><span data-ttu-id="8b611-128">边缘服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="8b611-128">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="8b611-129">用于外部用户访问的客户端到服务器 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="8b611-129">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b611-130">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="8b611-130">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8b611-131">边缘服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="8b611-131">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="8b611-132">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="8b611-132">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="8b611-133">用于与 Windows Live Messenger 的 A/V 会话，前提是配置了公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="8b611-133">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b611-134">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8b611-134">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8b611-135">边缘服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="8b611-135">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="8b611-136">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="8b611-136">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="8b611-137">对于使用 Windows Live Messenger 的公共 IM 连接是必需的。</span><span class="sxs-lookup"><span data-stu-id="8b611-137">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b611-138">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8b611-138">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8b611-139">Live Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="8b611-139">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="8b611-140">边缘服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="8b611-140">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="8b611-141">对于使用 Windows Live Messenger 的公共 IM 连接是必需的。</span><span class="sxs-lookup"><span data-stu-id="8b611-141">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8b611-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b611-142">See Also</span></span>


[<span data-ttu-id="8b611-143">Lync Server 2013 中的外部用户访问方案</span><span class="sxs-lookup"><span data-stu-id="8b611-143">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="8b611-144">确定 Lync Server 2013 的外部 A/V 防火墙和端口要求</span><span class="sxs-lookup"><span data-stu-id="8b611-144">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

