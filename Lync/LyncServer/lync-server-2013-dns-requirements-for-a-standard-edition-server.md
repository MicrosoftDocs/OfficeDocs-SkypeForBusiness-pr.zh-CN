---
title: Lync Server 2013： Standard Edition 服务器的 DNS 要求
description: Lync Server 2013： Standard Edition 服务器的 DNS 要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ea0c7219563d62a9d99bd85655b3d3fcb0c551f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574428"
---
# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="c380f-103">Lync Server 2013 中的 Standard Edition server 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="c380f-103">DNS requirements for a Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c380f-104">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="c380f-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="c380f-105">本节介绍部署 Standard Edition Server 所需的域名系统 (DNS) 记录。</span><span class="sxs-lookup"><span data-stu-id="c380f-105">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="c380f-106">Standard Edition Server 的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="c380f-106">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="c380f-107">下表指定了 Lync Server 2013 Standard Edition server 部署的 DNS 要求。</span><span class="sxs-lookup"><span data-stu-id="c380f-107">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c380f-108">部署方案</span><span class="sxs-lookup"><span data-stu-id="c380f-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="c380f-109">DNS 要求</span><span class="sxs-lookup"><span data-stu-id="c380f-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c380f-110">Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="c380f-110">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="c380f-111">将服务器的完全限定域名 (FQDN) 解析为其 IP 地址的内部 A 记录。</span><span class="sxs-lookup"><span data-stu-id="c380f-111">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c380f-112">自动客户端登录</span><span class="sxs-lookup"><span data-stu-id="c380f-112">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="c380f-113">对于每个受支持的 SIP 域，_sipinternaltls 的 SRV 记录。 _tcp c0/>&gt;通过端口5061的域映射到标准版服务器的 FQDN，该服务器会对登录的客户端请求进行身份验证和重定向。</span><span class="sxs-lookup"><span data-stu-id="c380f-113">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="c380f-114">有关详细信息，请参阅 <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 中的自动客户端登录的 DNS 要求</a>。</span><span class="sxs-lookup"><span data-stu-id="c380f-114">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c380f-115">统一通信 (UC) 设备发现设备更新 Web 服务</span><span class="sxs-lookup"><span data-stu-id="c380f-115">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="c380f-116">一个名为为 ucupdates-r2.-r2 的内部 A 记录。 &lt;&gt;解析为 Standard Edition server 托管设备更新 Web 服务的 IP 地址的 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="c380f-116">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="c380f-117">在打开了 UC 设备，但用户从未登录到设备的情况下，设备通过该 A 记录可以发现承载设备更新 Web 服务的服务器并获得更新。</span><span class="sxs-lookup"><span data-stu-id="c380f-117">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="c380f-118">否则，设备在用户首次登录时通过带内设置获得服务器信息。</span><span class="sxs-lookup"><span data-stu-id="c380f-118">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span> <span data-ttu-id="c380f-119">有关详细信息，请参阅操作文档中的 <a href="lync-server-2013-device-update-web-service.md">Lync Server 2013 中的设备更新 Web 服务</a> 。</span><span class="sxs-lookup"><span data-stu-id="c380f-119">For details, see <a href="lync-server-2013-device-update-web-service.md">Device Update Web service in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c380f-120">支持 HTTP 流量的反向代理</span><span class="sxs-lookup"><span data-stu-id="c380f-120">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="c380f-121">将外部 Web 场 FQDN 解析为反向代理的外部 IP 地址的外部 A 记录。</span><span class="sxs-lookup"><span data-stu-id="c380f-121">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="c380f-122">客户端和 UC 设备使用此记录连接到反向代理。</span><span class="sxs-lookup"><span data-stu-id="c380f-122">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="c380f-123">有关详细信息，请参阅规划文档中的 <a href="lync-server-2013-determine-dns-requirements.md">确定 Lync Server 2013 的 DNS 要求</a> 。</span><span class="sxs-lookup"><span data-stu-id="c380f-123">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c380f-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c380f-124">See Also</span></span>


[<span data-ttu-id="c380f-125">Lync Server 2013 中自动客户端登录的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="c380f-125">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[<span data-ttu-id="c380f-126">确定 Lync Server 2013 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="c380f-126">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="c380f-127">Lync Server 2013 中的设备更新 Web 服务</span><span class="sxs-lookup"><span data-stu-id="c380f-127">Device Update Web service in Lync Server 2013</span></span>](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

