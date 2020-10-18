---
title: Lync Server 2013：移动性的证书要求
description: Lync Server 2013：移动性的证书要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51af74b3efc1ffcb4fe38d7431e315f9b55af943
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575198"
---
# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a>Lync Server 2013 中的移动性证书要求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-24_

如果您部署移动功能并支持移动客户端的自动发现，则您需要在证书上包含某些使用者替代名称条目，以支持来自移动客户端的安全连接。

您需要在以下证书上包含使用者替代名称条目以实现自动发现：

  - 控制器池

  - 前端池

  - 反向代理

本节介绍了实现自动发现所需的证书上的使用者替代名称条目。

<div>


> [!NOTE]  
> 使用内部证书颁发结构重新颁发证书通常是一个简单的过程，但向反向代理所使用的公共证书中添加多个使用者替代名称条目的成本很高。 如果您具有多个 SIP 域（这会导致添加使用者替代名称的成本很高），则您可将反向代理配置为对初始自动发现服务请求使用 HTTP，而不是使用 HTTPS（默认配置）。 有关详细信息，请参阅 <A href="lync-server-2013-technical-requirements-for-mobility.md">Lync Server 2013 中的移动技术要求</A>。



</div>

### <a name="director-pool-certificate-requirements"></a>控制器池证书要求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>说明</th>
<th>使用者替代名称条目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自动发现服务 URL</p></td>
<td><p>SAN = lyncdiscoverinternal.。 &lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自动发现服务 URL</p></td>
<td><p>SAN = lyncdiscover.。 &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 或者，也可以使用 SAN = *。 &lt;sipdomain&gt;



</div>

### <a name="front-end-pool-certificate-requirements"></a>前端池证书要求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>说明</th>
<th>使用者替代名称条目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自动发现服务 URL</p></td>
<td><p>SAN = lyncdiscoverinternal.。 &lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自动发现服务 URL</p></td>
<td><p>SAN = lyncdiscover.。 &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 或者，也可以使用 SAN = *。 &lt;sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>反向代理（公共 CA）证书要求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>说明</th>
<th>使用者替代名称条目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部自动发现服务 URL</p></td>
<td><p>SAN = lyncdiscover.。 &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 将此 SAN 分配给为反向代理上的 SSL 侦听器分配的证书。



</div>

<div>


> [!NOTE]  
> 反向代理侦听器将包含外部 Web 服务 URL 的主题备用名称 (s)  (例如，如果已部署可选控制器) ，则为 SAN = lyncwebextpool01 和 dirwebexternal.contoso.com。



</div>

</div>

<span> </span>

</div>

</div>

</div>

