---
title: DNS 摘要-可扩展消息传递和状态协议 (XMPP) 联盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ac2e44382aa75b61ae4e2966b5ef87fd977e798
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532129"
---
# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="299fd-102">Lync Server 2013 中的 DNS 摘要-可扩展消息和状态协议 (XMPP) 联盟</span><span class="sxs-lookup"><span data-stu-id="299fd-102">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="299fd-103">_**上次修改的主题：** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="299fd-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="299fd-104">若要在部署中配置可扩展消息和状态协议 (XMPP) ，请创建两个域名系统 (DNS) 中的记录，该外部 DNS 服务器会将这些记录解析为您的边缘服务器或边缘池的访问边缘服务。</span><span class="sxs-lookup"><span data-stu-id="299fd-104">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two Domain Name System (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="299fd-105">可扩展消息传递和状态协议的 DNS 摘要</span><span class="sxs-lookup"><span data-stu-id="299fd-105">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="299fd-106">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="299fd-106">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="299fd-107">FQDN</span><span class="sxs-lookup"><span data-stu-id="299fd-107">FQDN</span></span></th>
<th><span data-ttu-id="299fd-108">IP 地址/FQDN 主机记录</span><span class="sxs-lookup"><span data-stu-id="299fd-108">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="299fd-109">映射位置/注释</span><span class="sxs-lookup"><span data-stu-id="299fd-109">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="299fd-110">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="299fd-110">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="299fd-111">_xmpp server._tcp .com</span><span class="sxs-lookup"><span data-stu-id="299fd-111">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="299fd-112">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="299fd-112">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="299fd-113">访问边缘服务或边缘池上的 XMPP 代理外部接口。对于所有内部 SIP 域，请根据需要对启用了 XMPP 联系人的用户通过外部策略、用户所在的网站策略或应用到启用 Lync 的用户的用户策略的配置来使用。</span><span class="sxs-lookup"><span data-stu-id="299fd-113">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="299fd-114">还必须在 XMPP 联盟伙伴策略中配置允许的 XMPP 域。</span><span class="sxs-lookup"><span data-stu-id="299fd-114">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="299fd-115">有关其他详细信息，请参阅 <strong>另请参阅</strong> 主题中的主题</span><span class="sxs-lookup"><span data-stu-id="299fd-115">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="299fd-116">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="299fd-116">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="299fd-117">xmpp.contoso.com（举例）</span><span class="sxs-lookup"><span data-stu-id="299fd-117">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="299fd-118">边缘服务器或边缘池托管 XMPP 代理上的访问边缘服务的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="299fd-118">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="299fd-119">指向承载 XMPP 代理服务的访问边缘服务或边缘池。</span><span class="sxs-lookup"><span data-stu-id="299fd-119">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="299fd-120">一般而言，您创建的 SRV 记录将指向此主机（A 或 AAAA）记录</span><span class="sxs-lookup"><span data-stu-id="299fd-120">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="299fd-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="299fd-121">See Also</span></span>


[<span data-ttu-id="299fd-122">在 Lync Server 2013 中设置 XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="299fd-122">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  


[<span data-ttu-id="299fd-123">确定 Lync Server 2013 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="299fd-123">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

