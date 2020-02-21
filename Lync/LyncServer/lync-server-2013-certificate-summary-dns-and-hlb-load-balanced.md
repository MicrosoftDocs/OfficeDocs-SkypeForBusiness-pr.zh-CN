---
title: Lync Server 2013：证书摘要-DNS 和 HLB 负载平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 055f1eea81f67281384e6a6124b5c72cee6d823f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Lync Server 2013 中的证书摘要-DNS 和 HLB 负载平衡

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

具有 DNS 负载平衡和硬件负载平衡器的 Director 的证书要求将使用一个默认证书，该证书具有可接收的服务的主题名称和使用者替代名称。 为池中的每个控制器请求一个证书。 请务必记住，硬件负载平衡器仅对来自反向代理的流量进行负载平衡。 此外，还有安装在每台服务器上用于服务器到服务器身份验证的 OAuth 令牌证书。

### <a name="certificates-for-director"></a>控制器的证书

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
<th>使用者替代名称 (SAN)</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>默认值</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>dirpool01.contoso.net</p>
<p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>（可选）*.contoso.com</p></td>
<td><p>可以从内部托管的证书颁发机构（CA）或公用 CA 请求控制器证书。</p>
<p>Director 响应来自周边或边缘服务器的反向代理的请求。 内部客户端将不使用控制器。</p>
<p>或者，简单 URL 的通配符条目</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>无条目</p></td>
<td><div>

> [!IMPORTANT]  
> 请注意，最小密钥长度为 1024，但您可能收到一条警告，告知建议的最小密钥长度为 2048 位。


</div>
<p>OAuthTokenIssuer 证书是单用途证书，用于在大型环境中对服务器进行身份验证，并且可从内部 CA 或公共 CA 请求。此证书是必需的。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

