---
title: Lync Server 2013：简单 URL 的 DNS 要求
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
ms.openlocfilehash: 2a05b5e5afc645c9219d02c8a551e4c0af9d93b0
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a>Lync Server 2013 中简单 URL 的 DNS 要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-22_

Lync Server 2013 支持简单的 Url，从而使你的用户加入会议更容易，并且让你的管理员更容易获得 Lync Server 管理工具。 有关简单 Url 的详细信息，请参阅[在 Lync Server 2013 中规划简单 url](lync-server-2013-planning-for-simple-urls.md)。

Lync 服务器支持以下三个简单的 Url： "开会"、"拨入" 和 "管理员"。您需要为 "满足" 和 "拨入" 设置简单的 Url，"管理员简单 URL" 是可选的。 需要支持简单 Url 的域名系统（DNS）记录取决于你定义这些简单 Url 的方式，以及你是否希望支持简单 Url 的灾难恢复。

<div>

## <a name="simple-url-option-1"></a>简单 URL 选项1

在选项1中，为每个简单的 URL 创建一个新的基本 URL。

<div class="">


> [!NOTE]  
> 当用户单击简单的 URL 会议链接时，DNS A 记录解析到的服务器确定正确的客户端软件以启动。 客户端软件启动后，它将自动与会议所在的池进行通信。 这样，无论简单 URL DNS A 记录解析到哪个服务器或池，用户都将定向到会议内容的相应服务器。



</div>

### <a name="simple-url-option-1"></a>简单 URL 选项1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>简单的 URL</strong></p></td>
<td><p><strong>示例</strong></p></td>
</tr>
<tr class="even">
<td><p>会议</p></td>
<td><p>https://meet.contoso.com， https://meet.fabrikam.com等等（组织中的每个 SIP 域一个）</p></td>
</tr>
<tr class="odd">
<td><p>拨入</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Iis</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


如果使用选项1，则必须定义以下内容：

  - 对于每个 "匹配简单 URL"，你需要一个 DNS A 记录，用于将 URL 解析为 Director 的 IP 地址（如果已部署）。 否则，它应解析为前端池负载平衡器的 IP 地址。 如果尚未部署池，并且使用的是标准版服务器部署，则 DNS A 记录必须解析为你的组织中的一个标准版服务器的 IP 地址。
    
    如果您的组织中有多个 SIP 域，并且您使用此选项，则必须为每个 SIP 域创建 "满足简单 Url"，并且对于每个 "匹配简单 URL" 都需要 DNS A 记录。 例如，如果你同时拥有 contoso.com 和 fabrikam.com，你将为https://meet.contoso.com and 和 AND https://meet.fabrikam.com创建 DNS A 记录。
    
    或者，如果你有多个 SIP 域，并且想要最小化这些简单 Url 的 DNS 记录和证书要求，请按照本主题后面部分所述使用选项3。

  - 对于拨入式简单 URL，你需要一个 DNS A 记录，该记录将 URL 解析为 Director 的 IP 地址（如果已部署）。 否则，它应解析为前端池负载平衡器的 IP 地址。 如果尚未部署池，并且使用的是标准版服务器部署，则 DNS A 记录必须解析为你的组织中的一个标准版服务器的 IP 地址。

  - 管理员简单 URL 仅限内部工作。 它需要一个 DNS A 记录，该记录将 URL 解析为 Director 的 IP 地址（如果已部署）。 否则，它应解析为前端池负载平衡器的 IP 地址。 如果尚未部署池，并且使用的是标准版服务器部署，则 DNS A 记录必须解析为你的组织中的一个标准版服务器的 IP 地址。

</div>

<div>

## <a name="simple-url-option-2"></a>简单 URL 选项2

使用选项2，"开会"、"拨入" 和 "管理员简单 Url" 都具有一个通用的基本 URL，例如 lync.contoso.com。 因此，对于这些简单的 Url，只需要一个 DNS A 记录，用于将 lync.contoso.com 解析为控制器池或前端池的 IP 地址。 如果尚未部署池，并且使用的是标准版服务器部署，则 DNS A 记录必须解析为你的组织中的一个标准版服务器的 IP 地址。

请注意，如果你的组织中有多个 SIP 域，你仍然必须为每个 SIP 域创建 "满足简单 Url"，并且你需要针对每个 "每个简单 URL" 的 DNS A 记录。 在此示例中，虽然三个简单的 Url 都基于 lync.contoso.com，但 fabrikam.com 的另一个基本 url 是使用不同的基本 URL 设置的。 在此示例中，你必须为https://lync.contoso.com和https://lync.fabrikam.com的 DNS 创建 DNS A 记录。 简单 URL 选项3显示了处理命名和 DNS A 记录的另一种方法（如果你有多个 SIP 域）。

### <a name="simple-url-option-2"></a>简单 URL 选项2

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>简单的 URL</strong></p></td>
<td><p><strong>示例</strong></p></td>
</tr>
<tr class="even">
<td><p>会议</p></td>
<td><p>https://lync.contoso.com/Meet， https://lync.fabrikam.com/Meet等等（组织中的每个 SIP 域一个）</p></td>
</tr>
<tr class="odd">
<td><p>拨入</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Iis</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a>简单 URL 选项3

如果你有多个 SIP 域，而你希望它们具有单独的简单 Url，但想要将这些简单 Url 的 DNS 记录和证书要求降到最低，则选项3非常有用。 在此示例中，只需要一个 DNS A 记录，该记录可将 lync.contoso.com 解析为控制器池或前端池的 IP 地址。

### <a name="simple-url-option-3"></a>简单 URL 选项3

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>简单的 URL</strong></p></td>
<td><p><strong>示例</strong></p></td>
</tr>
<tr class="even">
<td><p>会议</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>拨入</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Iis</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a>简单 Url 的灾难恢复选项

如果你有多个包含前端池的网站，并且 DNS 提供程序支持 GeoDNS，你可以为简单的 Url 设置 DNS 记录以支持灾难恢复，以便即使一个完整的前端池停止运行，简单的 URL 功能也会继续。 此灾难恢复功能支持 "开会" 和 "拨入" 简单 Url。

若要配置此设置，请创建两个 GeoDNS 地址。 每个地址都有两个 DNS A 或 CNAME 记录，它们可解析为两个池，这些记录结合在一起以供灾难恢复之用。 一个 GeoDNS 地址用于内部访问，并解析为两个池的内部 web FQDN 或负载平衡器 IP 地址。 其他 GeoDNS 地址用于外部访问，并解析为两个池的外部 web FQDN 或负载平衡器 IP 地址。 下面是使用池的 Fqdn 的 "满足简单 URL" 的示例。

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

然后，创建将您的 "满足简单 URL" （如 meet.contoso.com）解析为两个 GeoDNS 地址的 CNAME 记录。

<div class="">


> [!NOTE]  
> 如果你的网络使用<EM>hairpinning</EM> （通过外部链接路由所有简单的 URL 流量，包括来自你的组织内的流量），则只需配置外部 GeoDNS 地址并将你的 "仅限" 简单 url 解析为仅外部地址即可。



</div>

使用此方法时，你可以将每个 GeoDNS 地址配置为使用循环复用方法将请求分配到两个池，或主要连接到一个池（如位于地理位置较近的池），并使用另一个池（仅限情况连接失败。

你可以为拨入式简单 URL 设置相同配置。 若要执行此操作，请创建如前面的示例中所示`dialin`的`meet`其他记录，并在 DNS 记录中替换。 对于 "管理员简单 URL"，请使用本节前面列出的三个选项之一。

设置此配置后，必须使用监视应用程序设置 HTTP 监视以监视失败。 对于外部访问，监视器确保对两个池的外部 web FQDN 或负载平衡器 IP 地址的 HTTPS 获取自动发现请求成功。 例如，以下请求不得包含任何**ACCEPT**标头，并且必须返回**200 OK**。

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

对于内部访问，你必须在两个池的内部 web FQDN 或负载平衡器 IP 地址上监视端口5061。 如果检测到任何连接失败，这些池的 VIP 必须关闭端口80、443和444。

</div>

</div>

<span> </span>

</div>

</div>

</div>

