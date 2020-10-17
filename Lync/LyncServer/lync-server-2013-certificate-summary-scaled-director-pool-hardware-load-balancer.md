---
title: 证书摘要-扩展的控制器池、硬件负载平衡器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c08fb5710e25bf4504d7cb2d10020138221b22c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507919"
---
# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Lync Server 2013 中的证书摘要-扩展的控制器池、硬件负载平衡器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-20_

带有硬件负载平衡器的控制器的证书要求将使用一个默认证书，该证书具有一个主题名称和使用者替代名称，用于控制器池可以接收的服务。 为池中的每个控制器请求一个证书。 此外，每台服务器上还安装了用于进行服务器到服务器身份验证的 OAuth Token 证书。

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a>使用硬件负载平衡器的缩放控制器的证书

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
<th>Comments</th>
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
<td><p>可以从内部托管的证书颁发机构 (CA) 或公共 CA 请求控制器证书。</p>
<p>Director 响应来自周边或边缘服务器的反向代理的请求。</p>
<p>或者，简单 URL 的通配符条目</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>无条目</p></td>
<td>


> [!IMPORTANT]
> 请注意，最小密钥长度为 1024，但您可能收到一条警告，告知建议的最小密钥长度为 2048 位。


<p>OAuthTokenIssuer 证书是单用途证书，用于在大型环境中对服务器进行身份验证，并且可从内部 CA 或公共 CA 请求。此证书是必需的。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

