---
title: 端口摘要-可扩展消息传递和状态协议（XMPP）联盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b72ab2f2912a78ee30e9c032592a704eccbab8bf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Lync Server 2013 中的端口摘要-可扩展消息传递和状态协议（XMPP）联盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-20_

为在边缘服务器上部署的可扩展消息和状态协议（XMPP）代理定义的端口和协议允许从 XMPP 联合合作伙伴到边缘服务器的通信，还允许从边缘服务器到 XMPP 的通信。联盟伙伴。 在面向内部的防火墙上定义的规则也是从前端服务器或前端池到边缘服务器或边缘池。

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>可扩展消息传递和状态协议的防火墙摘要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>协议/TCP 或 UDP/端口</th>
<th>源（IP 地址）</th>
<th>目标（IP 地址）</th>
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>任意</p></td>
<td><p>访问边缘服务接口 IP 地址</p></td>
<td><p>用于 XMPP 的标准服务器到服务器通信端口。 允许与来自联合 XMPP 合作伙伴的边缘服务器 XMPP 代理的通信</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>访问边缘服务接口 IP 地址</p></td>
<td><p>任意</p></td>
<td><p>用于 XMPP 的标准服务器到服务器通信端口。 允许从边缘服务器 XMPP 代理到联合 XMPP 合作伙伴的通信</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>任意</p></td>
<td><p>内部边缘服务器接口 IP</p></td>
<td><p>从前端服务器或前端池上的 XMPP 网关到边缘服务器的内部 XMPP 流量</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的示例 XMPP 配置–与 Google 对话的 XMPP 联盟](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[在 Lync Server 2013 中管理 XMPP 联盟伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

