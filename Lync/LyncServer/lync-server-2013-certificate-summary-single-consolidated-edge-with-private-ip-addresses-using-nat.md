---
title: Lync Server 2013：证书摘要-使用 NAT 的具有专用 IP 地址的单一合并边缘
description: Lync Server 2013：证书摘要-使用 NAT 的专用 IP 地址的单一合并边缘。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 6de6680e-5f47-48e6-8e06-4994d710ea6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398519(v=OCS.15)
ms:contentKeyID: 48184433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53c8fa23bd7d5a2faf91da956d363474095a09d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572198"
---
# <a name="certificate-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Lync Server 2013 中的证书摘要-使用 NAT 的专用 IP 地址的单一合并边缘

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

Microsoft Lync Server 2013 使用证书对其他服务器进行相互身份验证，并将数据从服务器和服务器加密到客户端。 证书要求与服务器关联的域名系统 (DNS) 记录的名称与证书上的使用者名称 (SN) 和使用者替代名称 (SAN) 匹配。 要成功映射服务器、DNS 记录和证书条目，您必须仔细规划在 DNS 中注册的目标服务器完全限定域名以及证书上的 SN 和 SAN 条目。

为边缘服务器的外部接口分配的证书是从 (CA) 的公共证书颁发机构请求的。 以下文章中列出了在为统一通信提供证书方面已成功展示的公共 CAs： [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395) 。 请求证书时，可以使用 Lync Server 部署向导生成的证书请求，或使用 Lync Server 命令行管理程序 cmdlet 或由公共 CA 提供的进程手动创建请求。 有关用于证书管理的 Lync Server 命令行管理程序 cmdlet 的详细信息，请参阅 [Lync server 2013 中的证书和身份验证 cmdlet](https://docs.microsoft.com/powershell/module/skype/) 分配证书时，会将证书分配给访问边缘服务接口、Web 会议边缘服务接口和音频/视频身份验证服务。 不应将音频/视频身份验证服务与 A/V 边缘服务相混淆，该服务不使用证书来加密音频和视频流。 内部边缘服务器接口可以使用从内部 (到组织) CA 或来自公共 CA 的证书的证书。 内部接口证书仅使用 SN，无需或不会使用 SAN 条目。

<div>


> [!NOTE]  
> 下表显示了使用者替代名称列表中的第二个 SIP 条目 (sip.fabrikam.com) 以供参考。对于组织中的每个 SIP 域，需要添加证书使用者替代名称列表中列出的对应 FQDN。



</div>

<div>

## <a name="certificates-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat"></a>单个合并边缘所需的证书和使用 NAT 的专用 IP 地址


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>组件</th>
<th>使用者名称 (SN)</th>
<th>使用者替代名称 (SAN)/顺序</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>单个合并边缘（外部边缘）</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>如果要部署与 AOL 的公共 IM 连接，则证书必须来自公共 CA，并且必须具有服务器 EKU 和客户端 EKU。证书将分配给以下组件的外部边缘接口：</p>
<ul>
<li><p>访问边缘</p></li>
<li><p>会议边缘</p></li>
<li><p>A/V 边缘</p></li>
</ul>
<p>请注意，SAN 将基于拓扑生成器中的定义自动添加到证书中。您可以根据需要为其他 SIP 域添加 SAN 条目以及需要支持的其他条目。</p></td>
</tr>
<tr class="even">
<td><p>单个合并边缘（内部边缘）</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>不需要 SAN</p></td>
<td><p>证书可由公共或私有 CA 颁发，且必须包含服务器 EKU。证书将分配给内部边缘接口。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>证书摘要 – 公共即时消息连接


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>组件</th>
<th>使用者名称</th>
<th>使用者替代名称 (SAN)/顺序</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>访问/边缘外部</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>如果要部署与 AOL 的公共 IM 连接，则证书必须来自公共 CA，并且必须具有服务器 EKU 和客户端 EKU。证书将分配给以下组件的外部边缘接口：</p>
<ul>
<li><p>访问边缘</p></li>
<li><p>会议边缘</p></li>
<li><p>A/V 边缘</p></li>
</ul>
<p>请注意，根据拓扑生成器中的定义，SAN 将自动添加到证书中。根据需要为其他 SIP 域和其他需要支持的条目添加 SAN 条目。将在 SAN 中复制使用者名称，并且该名称必须在正确的操作中显示。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>可扩展消息传递和状态协议的证书摘要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>组件</th>
<th>使用者名称</th>
<th>使用者替代名称 (SAN)/顺序</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>分配到边缘服务器或边缘池的访问边缘服务</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*. contoso.com</strong></p></td>
<td><p>前三个 SAN 条目是完整边缘服务器的常规 SAN 条目。 contoso.com 是在根域级别与 XMPP 合作伙伴联盟所需的条目。 此条目将允许所有后缀为 *.contoso.com 的域使用 XMPP。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

