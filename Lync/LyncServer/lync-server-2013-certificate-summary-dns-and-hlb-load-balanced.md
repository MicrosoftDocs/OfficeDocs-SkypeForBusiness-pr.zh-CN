---
title: Lync Server 2013：证书摘要 - 已进行 DNS 和 HLB 负载平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e145e2f1ac3d331906713584b365adf7cd48aec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Lync Server 2013 中的证书摘要 - 已进行 DNS 和 HLB 负载平衡

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-22_

具有 DNS 负载平衡和硬件负载平衡器的 Director 的证书要求将使用一个默认证书, 该默认证书具有适用于 Director 可接收的服务的主题名称和使用者备用名称。 为池中的每个 Director 请求一个证书。 请务必记住, 硬件负载平衡器仅负载平衡来自反向代理的流量。 此外, 在每台服务器上安装了服务器到服务器身份验证用途的 OAuth 令牌证书。

### <a name="certificates-for-director"></a>Director 的证书

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
<th>主题备用名称 (SAN)</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>默认</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>dirpool01.contoso.net</p>
<p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(可选) * contoso.com</p></td>
<td><p>可以从内部托管的证书颁发机构 (CA) 或公共 CA 请求控制器证书。</p>
<p>控制器在来自外围服务器或从边缘服务器中响应来自反向代理的请求。 内部客户端将不使用 Director。</p>
<p>或者是简单 Url 的通配符条目</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>无条目</p></td>
<td><div>

> [!IMPORTANT]  
> 请注意, 最小键长度为 1024, 但你可能会收到一条警告, 指出推荐的最小密钥长度为2048位。


</div>
<p>OAuthTokenIssuer 证书是单一用途的证书, 用于在大规模环境中验证服务器, 并且可以从内部 CA 或公共 CA 请求。 证书是必需的。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

