---
title: Lync Server 2013：端口摘要-公共即时消息连接
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
ms.openlocfilehash: 16430849221631d9b540f5ee51b0a07758a38b05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="b6d2b-102">端口摘要-Lync Server 2013 中的公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="b6d2b-102">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6d2b-103">_**主题上次修改时间：** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="b6d2b-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="b6d2b-104">若要为支持公共即时消息连接所需的端口和协议配置防火墙，请首先注意 SIP/MTLS/TCP 5061 是双向的，以确保公共 IM 提供商联系 Lync 客户端的能力或 Lync 联系公共 IM 联系人。</span><span class="sxs-lookup"><span data-stu-id="b6d2b-104">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="b6d2b-105">Windows Live Messenger 可参与 Lync 客户端的音频/视频通信。</span><span class="sxs-lookup"><span data-stu-id="b6d2b-105">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="b6d2b-106">此帐户适用于通常在防火墙上支持 Lync 客户端作为外部用户的防火墙端口和协议配置。</span><span class="sxs-lookup"><span data-stu-id="b6d2b-106">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b6d2b-107">Lync 比以往更多，是一种强大的工具，用于跨组织和全球各地的人员进行连接。</span><span class="sxs-lookup"><span data-stu-id="b6d2b-107">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="b6d2b-108">与 Windows Live Messenger 的联盟要求除 Lync 标准客户端访问许可证（CAL）之外没有其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="b6d2b-108">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="b6d2b-109">Skype 联盟将添加到此列表，使 Lync 用户可以通过 IM 和语音与成百上千人联系。</span><span class="sxs-lookup"><span data-stu-id="b6d2b-109">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="b6d2b-110">与 Messenger 客户联系人的联盟将于2013年3月15日（中国大陆除外）正式结束。</span><span class="sxs-lookup"><span data-stu-id="b6d2b-110">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="b6d2b-111">Skype 将成为以前使用 Messenger 的联盟用户的联合身份验证客户端。</span><span class="sxs-lookup"><span data-stu-id="b6d2b-111">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="b6d2b-112">防火墙摘要-公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="b6d2b-112">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b6d2b-113">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="b6d2b-113">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b6d2b-114">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b6d2b-114">Source IP address</span></span></th>
<th><span data-ttu-id="b6d2b-115">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b6d2b-115">Destination IP address</span></span></th>
<th><span data-ttu-id="b6d2b-116">备注</span><span class="sxs-lookup"><span data-stu-id="b6d2b-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6d2b-117">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b6d2b-117">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b6d2b-118">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="b6d2b-118">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b6d2b-119">Edge 服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="b6d2b-119">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="b6d2b-120">对于使用 SIP 的联盟和公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="b6d2b-120">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6d2b-121">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b6d2b-121">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b6d2b-122">Edge 服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="b6d2b-122">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="b6d2b-123">公共 IM 连接合作伙伴</span><span class="sxs-lookup"><span data-stu-id="b6d2b-123">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b6d2b-124">对于使用 SIP 的联盟和公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="b6d2b-124">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6d2b-125">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b6d2b-125">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b6d2b-126">客户端</span><span class="sxs-lookup"><span data-stu-id="b6d2b-126">Clients</span></span></p></td>
<td><p><span data-ttu-id="b6d2b-127">Edge 服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="b6d2b-127">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="b6d2b-128">外部用户访问的客户端到服务器 SIP 通信。</span><span class="sxs-lookup"><span data-stu-id="b6d2b-128">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6d2b-129">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b6d2b-129">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b6d2b-130">Edge 服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="b6d2b-130">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="b6d2b-131">实时 Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="b6d2b-131">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b6d2b-132">如果配置了公用 IM 连接，则用于带有 Windows Live Messenger 的 A/V 会话。</span><span class="sxs-lookup"><span data-stu-id="b6d2b-132">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6d2b-133">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b6d2b-133">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b6d2b-134">Edge 服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="b6d2b-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="b6d2b-135">实时 Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="b6d2b-135">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b6d2b-136">对于具有 Windows Live Messenger 的公共 IM 连接，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="b6d2b-136">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6d2b-137">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b6d2b-137">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b6d2b-138">实时 Messenger 客户端</span><span class="sxs-lookup"><span data-stu-id="b6d2b-138">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b6d2b-139">Edge 服务器访问接口</span><span class="sxs-lookup"><span data-stu-id="b6d2b-139">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="b6d2b-140">对于具有 Windows Live Messenger 的公共 IM 连接，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="b6d2b-140">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b6d2b-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6d2b-141">See Also</span></span>


[<span data-ttu-id="b6d2b-142">Lync Server 2013 中的外部用户访问方案</span><span class="sxs-lookup"><span data-stu-id="b6d2b-142">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="b6d2b-143">确定 Lync Server 2013 的外部 A/V 防火墙和端口要求</span><span class="sxs-lookup"><span data-stu-id="b6d2b-143">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

