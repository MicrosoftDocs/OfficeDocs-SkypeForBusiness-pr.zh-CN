---
title: Lync Server 2013： Standard Edition 服务器的 DNS 要求
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
ms.openlocfilehash: 4cdd7a32519fe510819f82619c9086b22b820a52
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a>Lync Server 2013 中的 Standard Edition server 的 DNS 要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-22_

本节介绍部署 Standard Edition Server 所需的域名系统 (DNS) 记录。

<div>

## <a name="dns-records-for-standard-edition-servers"></a>Standard Edition Server 的 DNS 记录

下表指定了 Lync Server 2013 Standard Edition server 部署的 DNS 要求。


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
<td><p>将服务器的完全限定域名 (FQDN) 解析为其 IP 地址的内部 A 记录。</p></td>
</tr>
<tr class="even">
<td><p>自动客户端登录</p></td>
<td><p>对于每个受支持的 SIP 域，_sipinternaltls 的 SRV 记录。 _tcp。&lt;通过&gt;端口5061的域映射到标准版服务器的 FQDN，该服务器会对登录的客户端请求进行身份验证和重定向。 有关详细信息，请参阅<a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 中的自动客户端登录的 DNS 要求</a>。</p></td>
</tr>
<tr class="odd">
<td><p>统一通信 (UC) 设备发现设备更新 Web 服务</p></td>
<td><p>一个名为为 ucupdates-r2.-r2 的内部 A 记录。&lt;解析为&gt; Standard Edition Server 托管设备更新 Web 服务的 IP 地址的 SIP 域。 在打开了 UC 设备，但用户从未登录到设备的情况下，设备通过该 A 记录可以发现承载设备更新 Web 服务的服务器并获得更新。 否则，设备在用户首次登录时通过带内设置获得服务器信息。 有关详细信息，请参阅操作文档中的<a href="lync-server-2013-device-update-web-service.md">Lync Server 2013 中的设备更新 Web 服务</a>。</p></td>
</tr>
<tr class="even">
<td><p>支持 HTTP 流量的反向代理</p></td>
<td><p>将外部 Web 场 FQDN 解析为反向代理的外部 IP 地址的外部 A 记录。 客户端和 UC 设备使用此记录连接到反向代理。 有关详细信息，请参阅规划文档中的<a href="lync-server-2013-determine-dns-requirements.md">确定 Lync Server 2013 的 DNS 要求</a>。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中自动客户端登录的 DNS 要求](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)  


[Lync Server 2013 中的设备更新 Web 服务](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

