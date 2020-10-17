---
title: Lync Server 2013：简单 Url 的 DNS 要求
description: Lync Server 2013：简单 Url 的 DNS 要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84cc893fc06e9c57dcad6506d692b4484827b56a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564958"
---
# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a>Lync Server 2013 中简单 Url 的 DNS 要求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-22_

Lync Server 2013 支持简单 Url，使用户加入会议变得更加容易，并使管理员更轻松地进入 Lync Server 管理工具。 有关简单 Url 的详细信息，请参阅 [在 Lync Server 2013 中规划简单 url](lync-server-2013-planning-for-simple-urls.md)。

Lync Server 支持以下三个简单 Url： "符合"、"拨入" 和 "管理员"。您需要为 "满足" 和 "拨入" 设置简单 Url，并且管理员简单 URL 是可选的。 支持简单 URL 所需的域名系统 (DNS) 记录取决于定义这些简单 URL 的方式以及是否要对简单 URL 支持灾难恢复。

<div>

## <a name="simple-url-option-1"></a>简单 URL 选项 1

在选项 1 中，为每个简单 URL 创建新的基 URL。

<div class="">


> [!NOTE]  
> 用户单击简单 URL 会议链接时，DNS A 记录解析为的服务器会确定启动正确的客户端软件。客户端软件启动后，会自动与承载会议的池进行通信。这样，无论简单 URL DNS A 记录会解析为哪个服务器或池，用户都会定向到承载会议内容的相应服务器。



</div>

### <a name="simple-url-option-1"></a>简单 URL 选项 1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>简单 URL</strong></p></td>
<td><p><strong>示例</strong></p></td>
</tr>
<tr class="even">
<td><p>法规</p></td>
<td><p>https://meet.contoso.com、等， https://meet.fabrikam.com 依此类推 (组织中每个 SIP 域一个) </p></td>
</tr>
<tr class="odd">
<td><p>拨入</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>管理员</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


如果使用选项 1，必须定义以下内容：

  - 每个会议简单 URL 都需要一条将 URL 解析为控制器（如果已部署一个控制器）的 IP 地址的 DNS A 记录。如果未部署控制器，则应解析为前端池的负载平衡器的 IP 地址。如果没有部署池，并且正在使用 Standard Edition Server 部署，则 DNS A 记录必须解析为组织中某个 Standard Edition Server 的 IP 地址。
    
    如果组织中具有多个 SIP 域，并且您使用此选项，则必须为每个 SIP 域创建会议简单 URL，并且每个会议简单 URL 都需要一条 DNS A 记录。 例如，如果您同时具有 contoso.com 和 fabrikam.com，则会为和同时创建 DNS A 记录 https://meet.contoso.com https://meet.fabrikam.com 。
    
    或者，如果具有多个 SIP 域，并且要最大限度地减少这些简单 URL 的 DNS 记录和证书要求，请使用本主题后面所述的选项 3。

  - 拨入简单 URL 需要一条将 URL 解析为控制器（如果已部署）的 IP 地址的 DNS A 记录。如果未部署控制器，则应解析为前端池的负载平衡器的 IP 地址。如果没有部署池，并且正在使用 Standard Edition Server 部署，则 DNS A 记录必须解析为组织中某个 Standard Edition Server 的 IP 地址。

  - 管理简单 URL 仅限内部使用。它需要一条将 URL 解析为控制器（如果已部署）的 IP 地址的 DNS A 记录。如果未部署控制器，则应解析为前端池的负载平衡器的 IP 地址。如果没有部署池，并且正在使用 Standard Edition Server 部署，则 DNS A 记录必须解析为组织中某个 Standard Edition Server 的 IP 地址。

</div>

<div>

## <a name="simple-url-option-2"></a>简单 URL 选项 2

在选项 2 中，会议、拨入和管理简单 URL 都具有一个通用的基 URL，如 lync.contoso.com。因此，这些简单 URL 只需要一条 DNS A 记录，以将 lync.contoso.com 解析为控制器池或前端池的 IP 地址。如果没有部署池，并且正在使用 Standard Edition Server 部署，则 DNS A 记录必须解析为组织中某个 Standard Edition Server 的 IP 地址。

请注意，如果组织中具有多个 SIP 域，则仍必须为每个 SIP 域创建会议简单 URL，并且每个会议简单 URL 都需要一条 DNS A 记录。 在本例中，尽管三种简单 URL 都基于 lync.contoso.com，但 fabrikam.com 的那个会议简单 URL 具有不同的基 URL。 在此示例中，必须为和和创建 DNS A https://lync.contoso.com 记录 https://lync.fabrikam.com 。 简单 URL 选项 3 提供了在具有多个 SIP 域的情况下处理命名和 DNS A 记录的另一种方法。

### <a name="simple-url-option-2"></a>简单 URL 选项 2

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>简单 URL</strong></p></td>
<td><p><strong>示例</strong></p></td>
</tr>
<tr class="even">
<td><p>法规</p></td>
<td><p>https://lync.contoso.com/Meet、等， https://lync.fabrikam.com/Meet 依此类推 (组织中每个 SIP 域一个) </p></td>
</tr>
<tr class="odd">
<td><p>拨入</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>管理员</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a>简单 URL 选项 3

如果具有许多 SIP 域，并且希望每个 SIP 域具有单独的简单 URL，同时最大限度地减少这些简单 URL 的 DNS 记录和证书要求，则选项 3 是最有用的。在本例中，只需一个 DNS A 记录，此记录可将 lync.contoso.com 解析为控制器池或前端池的 IP 地址。

### <a name="simple-url-option-3"></a>简单 URL 选项 3

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>简单 URL</strong></p></td>
<td><p><strong>示例</strong></p></td>
</tr>
<tr class="even">
<td><p>法规</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>拨入</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p>管理员</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a>简单 URL 的灾难恢复选项

如果您有多个包含前端池的网站，并且您的 DNS 提供程序支持 GeoDNS，则您可以设置简单 Url 的 DNS 记录以支持灾难恢复，这样即使一个完整的前端池停止运行，简单 URL 功能也会继续进行。 此灾难恢复功能支持“会议”和“拨入”简单 URL。

若要进行此配置，请创建两个 GeoDNS 地址。每个地址具有两个 DNS A 或 CNAME 记录，这些记录解析到出于灾难恢复目的配对在一起的两个池。一个 GeoDNS 地址用于内部访问，并解析到两个池的内部 Web FQDN 或负载平衡器 IP 地址。另一个 GeoDNS 地址用于外部访问，并解析到两个池的外部 Web FQDN 或负载平衡器 IP 地址。下面是使用池的 FQDN 的“会议”简单 URL 的示例。

   ```console
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```console
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

然后，创建将“会议”简单 URL（如 meet.contoso.com）解析到两个 GeoDNS 地址的 CNAME 记录。

<div class="">


> [!NOTE]  
> 如果您的网络使用<EM>发夹</EM>（通过外部链接路由所有简单 URL 通信，包括来自您组织内部的通信），您可以只配置外部 GeoDNS 地址并将“会议”简单 URL 仅解析到该外部地址。



</div>

使用此方法时，您可以将每个 GeoDNS 地址配置为使用循环方法向两个池分发请求，或主要连接到一个池（如地理位置上接近的池）并仅在连接失败的情况下使用另一个池。

您可以对“拨入”简单 URL 设置相同的配置。 为此，请创建如前一示例中的其他记录，并 `dialin` `meet` 在 DNS 记录中替换。 对于“管理”简单 URL，请使用本节前面所列的三个选项之一。

设置完此配置后，您必须使用监控应用程序来设置 HTTP 监控以留意故障。 对于外部访问，请进行监视以确保对两个池的外部 web FQDN 或负载平衡器 IP 地址的 HTTPS GET 自动发现请求成功。 例如，以下请求不得包含任何 **ACCEPT** 标头且必须返回 **200 OK**。

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

对于内部访问，您必须监控两个池的内部 Web FQDN 或负载平衡器 IP 地址上的端口 5061。如果检测到任何连接失败，这些池的 VIP 必须关闭端口 80、443 和 444。

</div>

</div>

<span> </span>

</div>

</div>

</div>

