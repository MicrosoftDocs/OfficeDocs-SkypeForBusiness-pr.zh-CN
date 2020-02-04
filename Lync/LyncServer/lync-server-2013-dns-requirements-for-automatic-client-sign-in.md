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
ms.openlocfilehash: 6d033621382587367630d9119c2176e976cb2c2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>Lync Server 2013 中自动客户端登录的 DNS 要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-06-19_

本部分介绍自动客户端登录所需的域名系统（DNS）记录。 部署标准版服务器或前端池时，可以将客户端配置为使用自动发现登录到相应的标准版服务器或前端池。 如果您计划要求客户手动连接到 Lync Server 2013，则可以跳过本主题。

若要支持自动客户端登录，必须：

  - 指定单个服务器或池以分发和验证客户端登录请求。 这可以是组织中托管用户的现有服务器或池，也可以指定专用服务器或池用于托管无用户的此用途。 为了获得高可用性，建议你为此函数指定一个前端池。

  - 创建内部 DNS SRV 记录以支持此服务器或池的自动客户端登录。
    
    <div>
    

    > [!NOTE]  
    > 在以下记录要求中，SIP 域指的是分配给用户的 SIP Uri 的主机部分。 例如，如果 SIP Uri 的形式是 * @contoso，则 contoso.com 是 SIP 域。 SIP 域通常与内部 Active Directory 域不同。 组织还可以支持多个 SIP 域。

    
    </div>

若要为你的客户端启用自动配置，你必须创建内部 DNS SRV 记录，将以下记录之一映射到分发来自 Lync 的登录请求的前端池或标准版服务器的完全限定的域名（FQDN）台

  - \_sipinternaltls.\_tcp。\<域\> -用于内部 TLS 连接

你只需要为前端池或标准版服务器创建单个 SRV 记录，或者将分发登录请求。

下表显示了虚构公司 Contoso 所需的一些示例记录，它支持 contoso.com 和 retail.contoso.com 的 SIP 域。

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>自动客户端登录多个 SIP 域所需的 DNS 记录示例

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
<td><p>映射到 pool01.contoso.com 的端口5061上的 _sipinternaltls _tcp .com 域的 SRV 记录</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>将 pool01.contoso.com 映射到的端口5061上的 _sipinternaltls 的 _tcp retail .com 域的 SRV 记录</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 默认情况下，DNS 记录的查询将遵循用户名和 SRV 记录中的域之间的严格域名匹配。 如果你希望客户端 DNS 查询改为使用后缀匹配，则可以配置 DisableStrictDNSNaming 组策略。 有关详细信息，请参阅规划文档中的<A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013 中的客户端和设备规划</A>。



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>自动客户端登录所需的证书和 DNS 记录示例

此示例使用上表中的相同示例名称。 Contoso 组织支持 contoso.com 和 retail.contoso.com 的 SIP 域，并且其所有用户都具有以下形式之一的 SIP URI：

  - \<用户\>@retail contoso.com

  - \<用户\>@contoso .com

</div>

</div>

<span> </span>

</div>

</div>

</div>

