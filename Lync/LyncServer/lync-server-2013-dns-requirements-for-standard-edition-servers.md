---
title: Lync Server 2013： Standard Edition 服务器的 DNS 要求
description: Lync Server 2013： Standard Edition 服务器的 DNS 要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Standard Edition servers
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48183920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc93549e07fb82304ad76b051730eab972530764
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570668"
---
# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="d1792-103">Lync Server 2013 中的 Standard Edition 服务器的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="d1792-103">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1792-104">_**上次修改的主题：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="d1792-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="d1792-105">本节介绍部署 Standard Edition Server 所需的域名系统 (DNS) 记录。</span><span class="sxs-lookup"><span data-stu-id="d1792-105">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="d1792-106">Standard Edition Server 的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="d1792-106">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="d1792-107">下表指定了 Lync Server 2013 Standard Edition server 部署的 DNS 要求。</span><span class="sxs-lookup"><span data-stu-id="d1792-107">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>

### <a name="dns-requirements-for-a-standard-edition-server"></a><span data-ttu-id="d1792-108">Standard Edition Server 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="d1792-108">DNS Requirements for a Standard Edition Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1792-109">部署方案</span><span class="sxs-lookup"><span data-stu-id="d1792-109">Deployment scenario</span></span></th>
<th><span data-ttu-id="d1792-110">DNS 要求</span><span class="sxs-lookup"><span data-stu-id="d1792-110">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1792-111">Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="d1792-111">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="d1792-112">将服务器的完全限定域名 (FQDN) 解析为其 IP 地址的内部 A 记录。</span><span class="sxs-lookup"><span data-stu-id="d1792-112">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1792-113">自动客户端登录</span><span class="sxs-lookup"><span data-stu-id="d1792-113">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="d1792-114">对于每个受支持的 SIP 域，_sipinternaltls 的 SRV 记录。 _tcp c0/>&gt;通过端口5061的域映射到标准版服务器的 FQDN，该服务器会对登录的客户端请求进行身份验证和重定向。</span><span class="sxs-lookup"><span data-stu-id="d1792-114">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="d1792-115">有关详细信息，请参阅 <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 中的自动客户端登录的 DNS 要求</a>。</span><span class="sxs-lookup"><span data-stu-id="d1792-115">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1792-116">统一通信 (UC) 设备发现设备更新 Web 服务</span><span class="sxs-lookup"><span data-stu-id="d1792-116">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="d1792-117">一个名为为 ucupdates-r2.-r2 的内部 A 记录。 &lt;&gt;解析为 Standard Edition server 托管设备更新 Web 服务的 IP 地址的 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="d1792-117">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="d1792-118">在打开了 UC 设备，但用户从未登录到设备的情况下，设备通过该 A 记录可以发现承载设备更新 Web 服务的服务器并获得更新。</span><span class="sxs-lookup"><span data-stu-id="d1792-118">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="d1792-119">否则，设备在用户首次登录时通过带内设置获得服务器信息。</span><span class="sxs-lookup"><span data-stu-id="d1792-119">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1792-120">支持 HTTP 流量的反向代理</span><span class="sxs-lookup"><span data-stu-id="d1792-120">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="d1792-121">将外部 Web 场 FQDN 解析为反向代理的外部 IP 地址的外部 A 记录。</span><span class="sxs-lookup"><span data-stu-id="d1792-121">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="d1792-122">客户端和 UC 设备使用此记录连接到反向代理。</span><span class="sxs-lookup"><span data-stu-id="d1792-122">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="d1792-123">有关详细信息，请参阅规划文档中的 <a href="lync-server-2013-determine-dns-requirements.md">确定 Lync Server 2013 的 DNS 要求</a> 。</span><span class="sxs-lookup"><span data-stu-id="d1792-123">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

