---
title: Lync Server 2013：自动客户端登录的 DNS 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b022d9780d1498f70fd5918894a1412996731004
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>Lync Server 2013 中自动客户端登录的 DNS 要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-19_

本节介绍客户端自动登录所需的域名系统 (DNS) 记录。 部署 Standard Edition Server 或前端池时，可以将客户端配置为使用自动发现登录相应的 Standard Edition Server 或前端池。 如果计划要求客户端手动连接到 Lync Server 2013，则可以跳过此主题。

要支持自动客户端登录，必须执行以下操作：

  - 指定单个服务器或池，以分发客户端登录请求并进行身份验证。它可以是组织中承载用户的现有服务器或池，您也可以指定一个未承载任何用户的专用服务器或池。为了获得高可用性，建议您为此功能指定前端池。

  - 创建内部 DNS SRV 记录以支持此服务器或池的自动客户端登录。
    
    <div>
    

    > [!NOTE]  
    > 在下列记录要求中，SIP 域是指分配给用户的 SIP URI 的主机部分。例如，如果 SIP URI 的形式为 *@contoso.com，则 contoso.com 即为 SIP 域。SIP 域通常不同于内部 Active Directory 域。一个组织也可以支持多个 SIP 域。

    
    </div>

若要为你的客户端启用自动配置，必须创建内部 DNS SRV 记录，将以下记录之一映射到前端池或 Standard Edition 服务器的完全限定域名（FQDN），以便从 Lync 分发登录请求客户端

  - \_sipinternaltls.\_tcp。\<域\> -内部 TLS 连接数

您只需要为将分发登录请求的前端池或 Standard Edition Server 创建单个 SRV 记录。

下表显示虚构的公司 Contoso 所需的某些记录示例，该公司支持 contoso.com 和 retail.contoso.com 这两个 SIP 域。

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>多 SIP 域客户端自动登录所需的 DNS 记录的示例

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>用于分发登录请求的前端池的 FQDN</th>
<th>SIP 域</th>
<th>DNS SRV 记录</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>_sipinternaltls._tcp.contoso.com 域的 SRV 记录，通过端口 5061 映射到 pool01.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>_sipinternaltls._tcp.retail.contoso.com 域的 SRV 记录，通过端口 5061 映射到 pool01.contoso.com</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 默认情况下，DNS 记录的查询遵守用户名与 SRV 记录中的域之间的严格域名匹配。 如果更希望客户端 DNS 查询改用后缀匹配，可以配置 DisableStrictDNSNaming 组策略。 有关详细信息，请参阅规划文档中的在<A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013 中规划客户端和设备</A>。



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>客户端自动登录所需证书和 DNS 记录的示例

本示例使用上表中相同的示例名称。Contoso 组织支持 contoso.com 和 retail.contoso.com 这两个 SIP 域，该组织的所有用户都具有下列某种形式的 SIP URI：

  - \<用户\>@retail contoso.com

  - \<用户\>@contoso .com

</div>

</div>

<span> </span>

</div>

</div>

</div>

