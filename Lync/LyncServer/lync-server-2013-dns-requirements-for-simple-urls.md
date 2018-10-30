---
title: Lync Server 2013：简单 URL 的 DNS 要求
TOCTitle: 简单 URL 的 DNS 要求
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425874(v=OCS.15)
ms:contentKeyID: 49312527
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中简单 URL 的 DNS 要求

 

_**上一次修改主题：** 2015-03-09_

Lync Server 2013 支持的简单 URL 既便于用户参加会议，又便于管理员访问 Lync Server 管理工具。有关简单 URL 的详细信息，请参阅 [在 Lync Server 2013 中规划简单 URL](lync-server-2013-planning-for-simple-urls.md)。

Lync Server 支持以下三种简单 URL：会议、拨入和管理。必须设置会议和拨入简单 URL，而管理简单 URL 是可选的。支持简单 URL 所需的域名系统 (DNS) 记录取决于定义这些简单 URL 的方式以及是否要对简单 URL 支持灾难恢复。

## 简单 URL 选项 1

在选项 1 中，为每个简单 URL 创建新的基 URL。

> [!NOTE]  
> 用户单击简单 URL 会议链接时，DNS A 记录解析为的服务器会确定启动正确的客户端软件。客户端软件启动后，会自动与承载会议的池进行通信。这样，无论简单 URL DNS A 记录会解析为哪个服务器或池，用户都会定向到承载会议内容的相应服务器。



### 简单 URL 选项 1

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
<td><p>会议</p></td>
<td><p>https://meet.contoso.com、https://meet.fabrikam.com 等（组织中的每个 SIP 域都有一个）</p></td>
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
    
    如果组织中具有多个 SIP 域，并且您使用此选项，则必须为每个 SIP 域创建会议简单 URL，并且每个会议简单 URL 都需要一条 DNS A 记录。例如，如果同时具有 contoso.com 和 fabrikam.com，则需为 https://meet.contoso.com 和 https://meet.fabrikam.com 都创建 DNS A 记录。
    
    或者，如果具有多个 SIP 域，并且要最大限度地减少这些简单 URL 的 DNS 记录和证书要求，请使用本主题后面所述的选项 3。

  - 拨入简单 URL 需要一条将 URL 解析为控制器（如果已部署）的 IP 地址的 DNS A 记录。如果未部署控制器，则应解析为前端池的负载平衡器的 IP 地址。如果没有部署池，并且正在使用 Standard Edition Server 部署，则 DNS A 记录必须解析为组织中某个 Standard Edition Server 的 IP 地址。

  - 管理简单 URL 仅限内部使用。它需要一条将 URL 解析为控制器（如果已部署）的 IP 地址的 DNS A 记录。如果未部署控制器，则应解析为前端池的负载平衡器的 IP 地址。如果没有部署池，并且正在使用 Standard Edition Server 部署，则 DNS A 记录必须解析为组织中某个 Standard Edition Server 的 IP 地址。

## 简单 URL 选项 2

在选项 2 中，会议、拨入和管理简单 URL 都具有一个通用的基 URL，如 lync.contoso.com。因此，这些简单 URL 只需要一条 DNS A 记录，以将 lync.contoso.com 解析为控制器池或前端池的 IP 地址。如果没有部署池，并且正在使用 Standard Edition Server 部署，则 DNS A 记录必须解析为组织中某个 Standard Edition Server 的 IP 地址。

请注意，如果组织中具有多个 SIP 域，则仍必须为每个 SIP 域创建会议简单 URL，并且每个会议简单 URL 都需要一条 DNS A 记录。在本例中，尽管三种简单 URL 都基于 lync.contoso.com，但 fabrikam.com 的那个会议简单 URL 具有不同的基 URL。在本例中，必须同时为 https://lync.contoso.com 和 https://lync.fabrikam.com 创建 DNS A 记录。简单 URL 选项 3 提供了在具有多个 SIP 域的情况下处理命名和 DNS A 记录的另一种方法。

### 简单 URL 选项 2

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
<td><p>会议</p></td>
<td><p>https://lync.contoso.com/Meet、https://lync.fabrikam.com/Meet 等（组织中的每个 SIP 域都有一个）</p></td>
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


## 简单 URL 选项 3

如果具有许多 SIP 域，并且希望每个 SIP 域具有单独的简单 URL，同时最大限度地减少这些简单 URL 的 DNS 记录和证书要求，则选项 3 是最有用的。在本例中，只需一个 DNS A 记录，此记录可将 lync.contoso.com 解析为控制器池或前端池的 IP 地址。

### 简单 URL 选项 3

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
<td><p>会议</p></td>
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


## 简单 URL 的灾难恢复选项

如果您有多个包含前端池的网站并且您的 DNS 提供程序支持 GeoDNS，则可以将简单 URL 的 DNS 记录设置为支持灾难恢复，这样，即使整个前端池出现故障，简单 URL 功能也能继续运行。此灾难恢复功能支持“会议”和“拨入”简单 URL。

若要进行此配置，请创建两个 GeoDNS 地址。每个地址具有两个 DNS A 或 CNAME 记录，这些记录解析到出于灾难恢复目的配对在一起的两个池。一个 GeoDNS 地址用于内部访问，并解析到两个池的内部 Web FQDN 或负载平衡器 IP 地址。另一个 GeoDNS 地址用于外部访问，并解析到两个池的外部 Web FQDN 或负载平衡器 IP 地址。下面是使用池的 FQDN 的“会议”简单 URL 的示例。

    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com

&nbsp;

    Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com

然后，创建将“会议”简单 URL（如 meet.contoso.com）解析到两个 GeoDNS 地址的 CNAME 记录。

> [!NOTE]  
> 如果您的网络使用 <em>发夹</em>（通过外部链接路由所有简单 URL 通信，包括来自您组织内部的通信），您可以只配置外部 GeoDNS 地址并将“会议”简单 URL 仅解析到该外部地址。



使用此方法时，您可以将每个 GeoDNS 地址配置为使用循环方法向两个池分发请求，或主要连接到一个池（如地理位置上接近的池）并仅在连接失败的情况下使用另一个池。

您可以对“拨入”简单 URL 设置相同的配置。为此，请额外创建几个记录（如上一个示例中的记录），并在 DNS 记录中将 `dialin` 替代为 `meet`。对于“管理”简单 URL，请使用本节前面所列的三个选项之一。

设置完此配置后，您必须使用监控应用程序来设置 HTTP 监控以留意故障。对于外部访问，请通过监控确保 HTTPS GET 自动发现请求成功发送到两个池的外部 Web FQDN 或负载平衡器 IP 地址。例如，以下请求不得包含任何 **ACCEPT** 标头且必须返回 **200 OK**。

    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root

对于内部访问，您必须监控两个池的内部 Web FQDN 或负载平衡器 IP 地址上的端口 5061。如果检测到任何连接失败，这些池的 VIP 必须关闭端口 80、443 和 444。

