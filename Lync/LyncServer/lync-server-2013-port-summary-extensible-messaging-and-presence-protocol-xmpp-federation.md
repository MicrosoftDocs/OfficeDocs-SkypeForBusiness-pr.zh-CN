---
title: 端口摘要-可扩展消息传递和状态协议 (XMPP) 联合身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b36a74393a8c61d5281bb009d212ee0bb12cf0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="7e816-102">Lync Server 2013 中的端口摘要-可扩展消息和状态协议 (XMPP) 联合</span><span class="sxs-lookup"><span data-stu-id="7e816-102">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e816-103">_**主题上次修改时间:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="7e816-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="7e816-104">为在 Edge 服务器上部署的可扩展消息和状态协议 (XMPP) 代理定义的端口和协议允许从 XMPP 联盟合作伙伴到边缘服务器的通信, 还允许从边缘服务器到 XMPP 的通信。联盟合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="7e816-104">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="7e816-105">规则还在面向内部的防火墙上定义, 从前端服务器或前端池到边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="7e816-105">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="7e816-106">可扩展消息和状态协议的防火墙摘要</span><span class="sxs-lookup"><span data-stu-id="7e816-106">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e816-107">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="7e816-107">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7e816-108">源 (IP 地址)</span><span class="sxs-lookup"><span data-stu-id="7e816-108">Source (IP address)</span></span></th>
<th><span data-ttu-id="7e816-109">目标 (IP 地址)</span><span class="sxs-lookup"><span data-stu-id="7e816-109">Destination (IP address)</span></span></th>
<th><span data-ttu-id="7e816-110">备注</span><span class="sxs-lookup"><span data-stu-id="7e816-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e816-111">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="7e816-111">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="7e816-112">任意</span><span class="sxs-lookup"><span data-stu-id="7e816-112">Any</span></span></p></td>
<td><p><span data-ttu-id="7e816-113">Access Edge 服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="7e816-113">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="7e816-114">适用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="7e816-114">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="7e816-115">允许与联盟 XMPP 合作伙伴的 Edge 服务器 XMPP 代理通信</span><span class="sxs-lookup"><span data-stu-id="7e816-115">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e816-116">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="7e816-116">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="7e816-117">Access Edge 服务接口 IP 地址</span><span class="sxs-lookup"><span data-stu-id="7e816-117">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="7e816-118">任意</span><span class="sxs-lookup"><span data-stu-id="7e816-118">Any</span></span></p></td>
<td><p><span data-ttu-id="7e816-119">适用于 XMPP 的标准服务器到服务器通信端口。</span><span class="sxs-lookup"><span data-stu-id="7e816-119">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="7e816-120">允许从 Edge 服务器 XMPP 代理到联合 XMPP 合作伙伴的通信</span><span class="sxs-lookup"><span data-stu-id="7e816-120">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e816-121">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="7e816-121">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="7e816-122">任意</span><span class="sxs-lookup"><span data-stu-id="7e816-122">Any</span></span></p></td>
<td><p><span data-ttu-id="7e816-123">内部边缘服务器接口 IP</span><span class="sxs-lookup"><span data-stu-id="7e816-123">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="7e816-124">从前端服务器或前端池中的 XMPP 网关到边缘服务器的内部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="7e816-124">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7e816-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e816-125">See Also</span></span>


[<span data-ttu-id="7e816-126">Lync Server 2013 中的示例 XMPP 配置 –  与 Google Talk 的 XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="7e816-126">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="7e816-127">在 Lync Server 2013 中管理组织的 XMPP 联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="7e816-127">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

