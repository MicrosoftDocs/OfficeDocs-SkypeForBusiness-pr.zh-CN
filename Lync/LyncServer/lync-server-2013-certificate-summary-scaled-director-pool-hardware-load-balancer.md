---
title: 证书摘要 - 扩展的控制器池、硬件负载平衡器
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
ms.openlocfilehash: efcecbd1ec0c486e888a8c7303e450f75abf05bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Lync Server 2013 中的证书摘要 - 扩展的控制器池、硬件负载平衡器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-20_

带有硬件负载平衡器的 Director 的证书要求将使用一个默认证书，该默认证书具有 "接受方名称" 和 "使用者备用名称"，用于控制器池可以接收的服务。 为池中的每个 Director 请求一个证书。 此外，在每台服务器上安装了服务器到服务器身份验证用途的 OAuth 令牌证书。

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
<th>主题备用名称（SAN）</th>
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
<p>（可选） * contoso.com</p></td>
<td><p>可以从内部托管的证书颁发机构（CA）或公共 CA 请求控制器证书。</p>
<p>控制器在来自外围服务器或从边缘服务器中响应来自反向代理的请求。</p>
<p>或者是简单 Url 的通配符条目</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>无条目</p></td>
<td>


> [!IMPORTANT]
> 请注意，最小键长度为1024，但你可能会收到一条警告，指出推荐的最小密钥长度为2048位。


<p>OAuthTokenIssuer 证书是单一用途的证书，用于在大规模环境中验证服务器，并且可以从内部 CA 或公共 CA 请求。 证书是必需的。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

