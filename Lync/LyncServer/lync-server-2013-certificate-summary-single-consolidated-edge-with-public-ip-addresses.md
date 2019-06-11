---
title: 证书摘要 - 使用公用 IP 地址的单一合并边缘
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Single consolidated edge with public IP addresses
ms:assetid: 25b8ae7a-e5a0-43c0-92ae-7e144d5e4a36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204747(v=OCS.15)
ms:contentKeyID: 48183653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07c5bce784c6d05393b38b68c2558362bcb9525f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Lync Server 2013 中的证书摘要 - 使用公用 IP 地址的单一合并边缘

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-08_

Microsoft Lync Server 2013 使用证书互相验证其他服务器的身份, 并将从服务器到服务器和服务器的数据加密到客户端。 证书要求与服务器相关联的域名系统 (DNS) 记录与证书上的使用者名称 (SN) 和使用者备用名称 (SAN) 相匹配。 若要成功映射服务器、DNS 记录和证书条目, 必须仔细规划你希望的服务器在 DNS 中注册的完全限定的域名以及证书上的 SN 和 SAN 条目。

从公共证书颁发机构 (CA) 请求分配给边缘服务器的外部接口的证书。 以下文章列出了在为统一通信提供证书方面成功提供证书的公共 Ca: [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395)当请求证书时, 可以使用 Lync 服务器生成的证书申请部署向导或手动创建请求, 或由公共 CA 提供的流程创建请求。 分配证书时, 证书将分配给访问边缘服务接口、Web 会议边缘服务接口和音频/视频身份验证服务。 不应将音频/视频身份验证服务与不使用证书来加密音频和视频流的 A/V 边缘服务混淆。 内部边缘服务器接口可以使用来自内部 (到你的组织) CA 或来自公共 CA 的证书的证书。 内部接口证书仅使用 SN, 并且不需要或使用 SAN 条目。

<div>


> [!NOTE]
> 下表显示了 "主题备用名称" 列表中的第二个 SIP 条目 (sip.fabrikam.com) 以供参考。 对于你的组织中的每个 SIP 域, 你需要添加 "证书主题备用名称" 列表中列出的相应 FQDN。



</div>

<div>

## <a name="certificates-required-for-single-consolidated-edge-with-public-ip-addresses"></a>具有公共 IP 地址的单个统一边缘所需的证书


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
<th>使用者备用名称 (SAN)/Order</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>单个统一边缘 (外部边缘)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>证书必须来自公共 CA, 并且必须具有服务器 EKU 和客户端 EKU, 前提是要部署与 AOL 的公共 IM 连接。 证书已分配给外部边缘接口, 用于:</p>
<ul>
<li><p>访问边缘</p></li>
<li><p>会议边缘</p></li>
<li><p>A/V 边缘</p></li>
</ul>
<p>请注意, San 会根据拓扑生成器中的定义自动添加到证书。 根据需要为其他 SIP 域和其他需要支持的条目添加 SAN 条目。 主题名称是在 SAN 中复制的, 并且必须存在才能正确操作。</p></td>
</tr>
<tr class="even">
<td><p>单个统一边缘 (内部边缘)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>不需要 SAN</p></td>
<td><p>证书可以由公共或专用 CA 颁发, 并且必须包含服务器 EKU。 证书已分配给内部边缘接口。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>证书摘要-公共即时消息连接


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
<th>主题名称</th>
<th>使用者备用名称 (SAN)/Order</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部/访问边缘</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>证书必须来自公共 CA, 并且必须具有服务器 EKU 和客户端 EKU, 前提是要部署与 AOL 的公共 IM 连接。 证书已分配给外部边缘接口, 用于:</p>
<ul>
<li><p>访问边缘</p></li>
<li><p>会议边缘</p></li>
<li><p>A/V 边缘</p></li>
</ul>
<p>请注意, San 会根据拓扑生成器中的定义自动添加到证书。 根据需要为其他 SIP 域和其他需要支持的条目添加 SAN 条目。 主题名称是在 SAN 中复制的, 并且必须存在才能正确操作。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>可扩展消息和状态协议的证书摘要


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
<th>主题名称</th>
<th>使用者备用名称 (SAN)/Order</th>
<th>备注</th>
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
<p><strong>*.contoso.com</strong></p></td>
<td><p>前三个 SAN 条目是完整边缘服务器的常规 SAN 条目。 Contoso.com 是与根域级别的 XMPP 合作伙伴进行联盟所需的条目。 此条目将允许具有后缀 * contoso.com 的所有域的 XMPP。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

