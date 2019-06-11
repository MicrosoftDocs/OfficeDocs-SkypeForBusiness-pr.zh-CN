---
title: 'Lync Server 2013: 标准版服务器的 DNS 要求'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Standard Edition servers
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48183920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19c5e04f23428b073e544b040ed07dc852f1da4c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a>Lync Server 2013 中标准版服务器的 DNS 要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-06-19_

本部分介绍部署标准版服务器时所需的域名系统 (DNS) 记录。

<div>

## <a name="dns-records-for-standard-edition-servers"></a>标准版服务器的 DNS 记录

下表指定了 Lync Server 2013 标准版服务器部署的 DNS 要求。

### <a name="dns-requirements-for-a-standard-edition-server"></a>标准版服务器的 DNS 要求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>部署方案</th>
<th>DNS 要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard Edition Server</p></td>
<td><p>将服务器的完全限定的域名 (FQDN) 解析为其 IP 地址的内部 A 记录。</p></td>
</tr>
<tr class="even">
<td><p>自动客户端登录</p></td>
<td><p>对于每个受支持的 SIP 域, _sipinternaltls _tcp 的 SRV 记录。&lt;通过&gt;端口5061的域映射到标准版服务器的 FQDN, 该服务器对登录的客户端请求进行身份验证和重定向。 有关详细信息, 请参阅<a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 中的自动客户端登录 DNS 要求</a>。</p></td>
</tr>
<tr class="odd">
<td><p>通过统一通信 (UC) 设备进行的设备更新 Web 服务发现</p></td>
<td><p>名为 ucupdates-r2 的内部 A 记录。&lt;SIP 域&gt; , 可解析为托管设备更新 Web 服务的标准版服务器的 IP 地址。 在 UC 设备处于打开状态但用户从未登录到设备的情况下, A 记录允许设备发现服务器托管设备更新 Web 服务并获取更新。 否则, 在用户第一次登录时, 设备将通过带内预配获取服务器信息。</p></td>
</tr>
<tr class="even">
<td><p>支持 HTTP 流量的反向代理</p></td>
<td><p>将外部 web 场 FQDN 解析为反向代理的外部 IP 地址的外部 A 记录。 客户端和 UC 设备使用此记录连接到反向代理。 有关详细信息, 请参阅在规划文档中<a href="lync-server-2013-determine-dns-requirements.md">确定 Lync Server 2013 的 DNS 要求</a>。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

