---
title: Lync Server 2013：Standard Edition 服务器的 DNS 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7508fea0fa6640546bda4f1ecb559821d468803d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="7f04d-102">Lync Server 2013 中 Standard Edition 服务器的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="7f04d-102">DNS requirements for a Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f04d-103">_**主题上次修改时间:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="7f04d-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="7f04d-104">本部分介绍部署标准版服务器时所需的域名系统 (DNS) 记录。</span><span class="sxs-lookup"><span data-stu-id="7f04d-104">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="7f04d-105">标准版服务器的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="7f04d-105">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="7f04d-106">下表指定了 Lync Server 2013 标准版服务器部署的 DNS 要求。</span><span class="sxs-lookup"><span data-stu-id="7f04d-106">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f04d-107">部署方案</span><span class="sxs-lookup"><span data-stu-id="7f04d-107">Deployment scenario</span></span></th>
<th><span data-ttu-id="7f04d-108">DNS 要求</span><span class="sxs-lookup"><span data-stu-id="7f04d-108">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f04d-109">Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="7f04d-109">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="7f04d-110">将服务器的完全限定的域名 (FQDN) 解析为其 IP 地址的内部 A 记录。</span><span class="sxs-lookup"><span data-stu-id="7f04d-110">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f04d-111">自动客户端登录</span><span class="sxs-lookup"><span data-stu-id="7f04d-111">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="7f04d-112">对于每个受支持的 SIP 域, _sipinternaltls _tcp 的 SRV 记录。&lt;通过&gt;端口5061的域映射到标准版服务器的 FQDN, 该服务器对登录的客户端请求进行身份验证和重定向。</span><span class="sxs-lookup"><span data-stu-id="7f04d-112">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="7f04d-113">有关详细信息, 请参阅<a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 中的自动客户端登录 DNS 要求</a>。</span><span class="sxs-lookup"><span data-stu-id="7f04d-113">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f04d-114">通过统一通信 (UC) 设备进行的设备更新 Web 服务发现</span><span class="sxs-lookup"><span data-stu-id="7f04d-114">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="7f04d-115">名为 ucupdates-r2 的内部 A 记录。&lt;SIP 域&gt; , 可解析为托管设备更新 Web 服务的标准版服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7f04d-115">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="7f04d-116">在 UC 设备处于打开状态但用户从未登录到设备的情况下, A 记录允许设备发现服务器托管设备更新 Web 服务并获取更新。</span><span class="sxs-lookup"><span data-stu-id="7f04d-116">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="7f04d-117">否则, 在用户第一次登录时, 设备将通过带内预配获取服务器信息。</span><span class="sxs-lookup"><span data-stu-id="7f04d-117">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span> <span data-ttu-id="7f04d-118">有关详细信息, 请参阅操作文档中<a href="lync-server-2013-device-update-web-service.md">Lync Server 2013 中的 "设备更新" Web 服务</a>。</span><span class="sxs-lookup"><span data-stu-id="7f04d-118">For details, see <a href="lync-server-2013-device-update-web-service.md">Device Update Web service in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f04d-119">支持 HTTP 流量的反向代理</span><span class="sxs-lookup"><span data-stu-id="7f04d-119">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="7f04d-120">将外部 web 场 FQDN 解析为反向代理的外部 IP 地址的外部 A 记录。</span><span class="sxs-lookup"><span data-stu-id="7f04d-120">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="7f04d-121">客户端和 UC 设备使用此记录连接到反向代理。</span><span class="sxs-lookup"><span data-stu-id="7f04d-121">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="7f04d-122">有关详细信息, 请参阅在规划文档中<a href="lync-server-2013-determine-dns-requirements.md">确定 Lync Server 2013 的 DNS 要求</a>。</span><span class="sxs-lookup"><span data-stu-id="7f04d-122">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7f04d-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f04d-123">See Also</span></span>


[<span data-ttu-id="7f04d-124">Lync Server 2013 中自动客户端登录的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="7f04d-124">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[<span data-ttu-id="7f04d-125">确定 Lync Server 2013 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="7f04d-125">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="7f04d-126">Lync Server 2013 中的设备更新 Web 服务</span><span class="sxs-lookup"><span data-stu-id="7f04d-126">Device Update Web service in Lync Server 2013</span></span>](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

