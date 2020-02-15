---
title: Lync Server 2013：确定 DNS 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79f1c27f48beddd0c1fd3260193a71bb79b034bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a>确定 Lync Server 2013 的 DNS 要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-22_

使用以下流程图确定域名系统（DNS）要求。 Lync Server 2013 的累积更新的更改：二月份2013在应用的位置被记录下来。

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2013 支持使用 IPv6 寻址。 若要使用 IPv6 地址，还必须为 IPv6 DNS 提供支持并配置 DNS 主机 AAAA （称为 "quad A"）记录。 在同时使用 IPv4 和 IPv6 的部署中，最好同时配置和维护 IPv4 的主机 A 记录和 IPv6 的主机 AAAA。 即使您的部署已完全转换为 IPv6，当外部用户仍在使用 IPv4 时，仍可能需要 IPv4 DNS 主机记录。



</div>

**确定 DNS 要求流图表**

![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")

<div>


> [!IMPORTANT]  
> 默认情况下，未加入域的计算机的计算机名称是主机名，而不是完全限定的域名（FQDN）。 拓扑生成器使用 Fqdn，而不是主机名称。 因此，您必须在要部署为域外边缘服务器的计算机的名称上配置 DNS 后缀。 分配您的 Lync Server、边缘服务器和池的 FQDN 时，<STRONG>只使用标准字符</STRONG>（包括 A–Z、a–z、0–9 和连字符）。 不要使用 Unicode 字符或下划线。 外部 DNS 和公共 CA（即，在 FQDN 必须分配给证书中的 SN 时）通常不支持在 FQDN 中使用非标准字符。 有关其他详细信息，请参阅<A href="lync-server-2013-configure-dns-host-records.md">为 Lync Server 2013 配置 DNS 主机记录</A>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a>Lync 客户端如何查找服务

Microsoft Lync 2010、Lync 2013 和 Lync Mobile 类似于客户端在 Lync Server 2013 中查找和访问服务的方式。 显著的例外是使用其他服务位置进程的 Lync Windows 应用商店应用。 本节详细介绍了客户端如何查找服务的两种情况，首先是使用一系列 SRV 和主机记录的传统方法，第二种是仅使用自动发现服务记录。 对桌面客户端进行的累积更新更改了所有客户端的 Lync Server 2010 的 DNS 位置进程，DNS 查询过程将继续，直到返回成功的查询，或者可能的 DNS 记录的列表耗尽，并且最终错误将返回到客户端。

对于在 DNS 查找期间除 Lync Windows 应用商店应用**之外**的所有客户端，将按以下顺序查询 SRV 记录并将其返回到客户端：

1.  lyncdiscoverinternal..\<内部\> Web 服务上自动发现服务的域 A （主机）记录

2.  lyncdiscover..\<外部\> Web 服务上自动发现服务的域 A （主机）记录

3.  \_sipinternaltls.\_tcp。\<内部\> TLS 连接的域 SRV （服务定位器）记录

4.  \_sipinternal.\_tcp。\<内部\> TCP 连接的域 SRV （服务定位器）记录（仅在允许 TCP 时执行）

5.  \_sip.\_tls。\<外部\> TLS 连接的域 SRV （服务定位器）记录

6.  sipinternal.\<前端\>池或控制器的域 A （主机）记录，仅在内部网络上可解析

7.  sip.\<用于\>内部网络的前端池或控制器的域 A （主机）记录，或者客户端为外部客户端时的访问边缘服务

8.  sipexternal.\<当\>客户端为外部客户端时，访问边缘服务的域 A （主机）记录

Lync Windows 应用商店应用程序将完全更改该过程，因为它使用两个记录：

1.  lyncdiscoverinternal..\<内部\> Web 服务上自动发现服务的域 A （主机）记录

2.  lyncdiscover..\<外部\> Web 服务上自动发现服务的域 A （主机）记录

与其他记录类型之间没有任何回退。

与旧客户端相比，用于更新的客户端的方法之间的差异在于，自动发现服务正在成为定位所有服务的首选方法。

当连接成功时，自动发现服务将返回用户的主池的所有 Web 服务 Url，包括移动服务（称为 Mcx by 在 IIS 中为服务创建的虚拟目录）、Microsoft Lync Web App 和 Web 计划程序 Url。 但是，内部移动服务 URL 和外部移动服务 URL 均与外部 Web 服务 FQDN 相关联。 因此，无论移动设备是在网络内部还是外部，设备都会通过反向代理在外部连接到移动服务。

如果已安装 Lync Server 2013 2013 的累积更新，则自动发现服务还将返回对 Internal/UCWA、External/UCWA 和 UCWA 的引用。 这些条目引用统一通信 Web API (UCWA) Web 组件。 目前，仅使用 entry UCWA，并提供对 web 组件的 URL 的引用。 Lync 2013 移动客户端使用 UCWA，而不是 Lync 2010 移动客户端使用的 Mcx 移动服务。

<div>


> [!NOTE]  
> 创建 SRV 记录时，务必要记住，它们必须指向在其中创建 DNS SRV 记录的同一个域中的 DNS A 和 AAAA （如果使用的是 IPv6 寻址）记录。 例如，如果 SRV 记录在 contoso.com 中，则 A 和 AAAA （如果使用的是 IPv6 寻址）记录指向的是 fabrikam.com。



</div>

<div>


> [!TIP]  
> 默认配置是通过外部站点引导所有移动客户端流量。 您可以修改设置以仅返回内部 URL （如果这更适合您的要求）。 使用此配置，用户只可在其移动设备中使用 Lync 移动应用程序，而仅当它们位于企业网络内部时。 若要定义此配置，请使用<STRONG>CsMcxConfiguration</STRONG> cmdlet。



</div>

<div>


> [!NOTE]  
> 尽管移动应用程序还可以连接到其他 Lync Server 2013 服务（如通讯簿服务），但内部移动应用程序 web 请求仅针对移动服务转到外部 web FQDN。 其他服务请求（如通讯簿请求）不需要此配置。



</div>

移动设备支持手动发现服务。 在这种情况下，每个用户都必须使用完整的内部和外部自动发现服务 Uri （包括协议和路径）配置移动设备设置，如下所示：

  - https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root 用于外部访问

  - 用于\<内部\>访问的 https://IntPoolFQDN/AutoDiscover/AutoDiscover.svc/Root

我们建议使用自动发现，而不是手动发现。 但是，手动设置可用于对移动设备连接问题进行故障排除。

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a>使用 Lync Server 配置拆分的 DNS

拆分的 DNS 由多个名称（例如，拆分 DNS 或水平拆分 DNS）所熟知。 简单地说，它描述了具有相同命名空间的两个 DNS 区域的 DNS 配置，但一个 DNS 区域服务仅限内部请求，另一个 DNS 区域服务仅限外部的请求。 但是，内部 DNS 中包含的许多 DNS SRV 和 A 记录将不包含在外部 DNS 中，反之亦然也是如此。 在内部和外部 DNS 中都存在相同的 DNS 记录（例如，www.contoso.com）的情况下，返回的 IP 地址将不同，具体取决于启动查询的位置（内部或外部）。

<div>


> [!IMPORTANT]  
> 目前，移动（或更具体地说）不支持 Lyncdiscover. 和 Lyncdiscoverinternal. DNS 记录的拆分的 DNS。 必须在外部 DNS 服务器上定义 Lyncdiscover.，并且必须在内部 DNS 服务器上定义 Lyncdiscoverinternal.。



</div>

出于这些主题的目的，将使用术语 "裂脑" DNS。

如果要配置拆分大脑 DNS，以下内部和外部区域将包含每个区域中所需的 DNS 记录类型的摘要。 有关详细信息，请参阅[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)。

**内部 DNS：**

  - 包含一个名为 contoso.com 的 DNS 区域，该区域对其具有权威

  - 内部 contoso.com 区域包含：
    
      - 内部 Lync Server 2013 客户端自动配置的 DNS A 和 AAAA （如果使用的是 IPv6 寻址）和 SRV 记录（可选）
    
      - Lync Server 2013 Web 服务的自动发现的 DNS A 和 AAAA （如果使用的是 IPv6 寻址）或 CNAME 记录（可选）
    
      - 用于在企业网络中运行 Lync Server 2013 的前端池名称、控制器或控制器池名称以及所有内部服务器的 DNS A 和 AAAA （如果使用的是 IPv6 寻址）记录
    
      - 外围网络中每个 Lync Server 2013、边缘服务器的边缘内部接口的 DNS A 和 AAAA （如果使用的是 IPv6 寻址）记录
    
      - 外围网络中每个反向代理服务器的内部接口的 DNS A 和 AAAA （如果使用的是 IPv6 寻址）记录（对反向代理的管理是可选的）
    
      - 外围网络中的所有 Lync Server 2013 边缘服务器内部边缘接口使用内部 DNS 区域将查询解析为 contoso.com
    
      - 在企业网络中运行 Lync Server 2013 和运行 Lync 2013 的客户端的所有服务器指向内部 DNS 服务器，以便将查询解析为 contoso.com，或在每台边缘服务器上使用 HOSTS 文件，并列出 A 和 AAAA （如果使用 IPv6 寻址）记录。下一个跃点服务器，特别是控制器或控制器 VIP、前端池 VIP 或 Standard Edition 服务器

**外部 DNS：**

  - 包含一个名为 contoso.com 的 DNS 区域，该区域对其具有权威

  - 外部 contoso.com 区域包含：
    
      - Lync Server 2013 客户端自动配置的 DNS A 和 AAAA （如果使用的是 IPv6 寻址）和 SRV 记录（可选）
    
      - 将 DNS A 和 AAAA （如果使用 IPv6 寻址）或 CNAME 记录用于自动发现 Lync Server 2013 Web 服务，以便与移动功能一起使用
    
      - 外围网络中每个 Lync Server 2013、边缘服务器或硬件负载平衡器虚拟 IP （VIP）的边缘外部接口的 DNS A 和 AAAA （如果使用的是 IPv6 寻址）和 SRV 记录
    
      - 外围网络中的反向代理服务器或 VIP 的外部接口的 DNS A 和 AAAA （如果使用 IPv6 寻址）记录

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a>不带分裂 DNS 的自动配置

如果内部 DNS 区域包含\_sipinternaltls，则使用裂脑 DNS，在内部登录的 Lync Server 2013 用户可以利用自动配置。\_正在使用的每个 SIP 域的 tcp SRV 记录。 但是，如果不使用拆分的 DNS，则运行 Lync 的客户端的内部自动配置将不起作用，除非实现本部分后面所述的解决方法之一。 这是因为 Lync Server 2013 要求用户的 SIP URI 与为自动配置指定的前端池的域相匹配。 这也是早期版本的 Communicator 的情况。

例如，如果您有两个 SIP 域在使用中，则需要以下 DNS 服务（SRV）记录：

  - 如果用户登录为 bob@contoso.com，以下 SRV 记录将适用于自动配置，因为用户的 SIP 域（contoso.com）与自动配置前端池的域相匹配）：
    
     \_sipinternaltls.\_tcp.contoso.com。 SRV 0 0 5061 pool01.contoso.com 中的86400

  - 如果用户登录为 alice@fabrikam.com，以下 DNS SRV 记录将适用于第二个 SIP 域的自动配置。
    
     \_sipinternaltls.\_tcp.fabrikam.com。 SRV 0 0 5061 pool01.fabrikam.com 中的86400

为了进行比较，如果用户登录为 tim@litwareinc.com，以下 DNS SRV 记录将不能用于自动配置，因为客户端的 SIP 域（litwareinc.com）与池所在的域不匹配（fabrikam.com）：

 \_sipinternaltls.\_tcp.litwareinc.com。 SRV 0 0 5061 pool01.fabrikam.com 中的86400

如果运行 Lync 的客户端需要 "自动配置"，请选择下列选项之一：

  - **组策略对象**   使用组策略对象（gpo）填充正确的服务器值。
    
    <div>
    

    > [!NOTE]  
    > 此选项不启用自动配置，但它会自动执行手动配置过程，因此，如果使用此方法，则不需要与自动配置关联的 SRV 记录。

    
    </div>

  - **匹配内部区域**   在内部 dns 中创建与外部 dns 区域匹配的区域（例如，contoso.com），并创建与用于自动配置的 Lync Server 2013 池对应的 DNS a 和 AAAA （如果使用的是 IPv6 寻址）记录。 例如，如果用户驻留在 pool01.contoso.net 上，但以 bob@contoso.com 的形式登录到 Lync，请创建一个名为 contoso.com 的内部 DNS 区域并将其包含在其中，创建 pool01.contoso.com 的 DNS A 和 AAAA （如果使用的是 IPv6 寻址）记录。

  - **固定端口点内部区域**   如果在内部 DNS 中创建整个区域不是一个选项，则可以创建与自动配置所需的 SRV 记录相对应的 pin 点（即专用）区域，并使用 dnscmd 填充这些区域。 Dnscmd 是必需的，因为 DNS 用户界面不支持创建 pin 点区域。 例如，如果 SIP 域为 contoso.com，并且您有一个名为 pool01 的前端池，该池包含两台前端服务器，则您需要内部 DNS 中的以下 pin 点区域和记录：
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    如果您的环境中包含第二个 SIP 域（例如，fabrikam.com），则您需要内部 DNS 中的以下 pin 点区域和记录：
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> 前端池 FQDN 显示两次，但具有两个不同的 IP 地址。 这是因为使用了 DNS 负载平衡，但如果使用硬件负载平衡，则只会有一个前端池条目。 此外，前端池 FQDN 值在 contoso.com 示例和 fabrikam.com 示例之间发生变化，但 IP 地址保持不变。 这是因为从任意 SIP 域登录的用户都使用相同的前端池进行自动配置。



</div>

有关详细信息，请参阅 DMTF 博客文章 "Communicator Automatic Configuration and Split-大脑 DNS"，网址[http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707)为。

<div>


> [!NOTE]  
> 每个博客的内容及其 URL 如有更改，恕不另行通知。



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a>配置用于灾难恢复的域名系统（DNS）

若要将 DNS 配置为将 Lync Server 2013 Web 流量重定向到灾难恢复和故障转移站点，必须使用支持 GeoDNS 的 DNS 提供程序。 您可以设置 Web DNS 记录以支持灾难恢复，以便即使一个完整的前端池停止运行时，使用 Web 服务的功能仍将继续进行。 此灾难恢复功能支持自动发现（Lyncdiscover. URL）、满足和拨入简单 Url。

您可以在 GeoDNS 提供商处为 Web 服务的内部和外部解决方案定义和配置其他 DNS 主机（A 和 AAAA （如果使用 IPv6）记录。 以下详细信息假设您的提供程序对成对的池、地理位置和 GeoDNS 所支持的循环 DNS，或配置为使用 Pool1 作为主池，并在发生通信丢失或硬件故障时故障转移到 Pool2。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>GeoDNS 记录（示例）</th>
<th>池记录（示例）</th>
<th>CNAME 记录（示例）</th>
<th>DNS 设置（选择一个选项）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Meet-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Meet.contoso.com Pool1InternalWebFQDN.contoso.com 的别名</p>
<p>Meet.contoso.com Pool2InternalWebFQDN.contoso.com 的别名</p></td>
<td><p>池之间的循环</p>
<p>使用 primary，如果失败则连接到辅助数据库</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Meet.contoso.com Pool1ExternalWebFQDN.contoso.com 的别名</p>
<p>Meet.contoso.com Pool2ExternalWebFQDN.contoso.com 的别名</p></td>
<td><p>池之间的循环</p>
<p>使用 primary，如果失败则连接到辅助数据库</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com Pool1InternalWebFQDN.contoso.com 的别名</p>
<p>Dialin.contoso.com Pool2InternalWebFQDN.contoso.com 的别名</p></td>
<td><p>池之间的循环</p>
<p>使用 primary，如果失败则连接到辅助数据库</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com Pool1ExternalWebFQDN.contoso.com 的别名</p>
<p>Dialin.contoso.com Pool2ExternalWebFQDN.contoso.com 的别名</p></td>
<td><p>池之间的循环</p>
<p>使用 primary，如果失败则连接到辅助数据库</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscoverinternal.contoso.com Pool1InternalWebFQDN.contoso.com 的别名</p>
<p>Lyncdiscoverinternal.contoso.com Pool2InternalWebFQDN.contoso.com 的别名</p></td>
<td><p>池之间的循环</p>
<p>使用 primary，如果失败则连接到辅助数据库</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscover.contoso.com Pool1ExternalWebFQDN.contoso.com 的别名</p>
<p>Lyncdiscover.contoso.com Pool2ExternalWebFQDN.contoso.com 的别名</p></td>
<td><p>池之间的循环</p>
<p>使用 primary，如果失败则连接到辅助数据库</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com Pool1InternalWebFQDN.contoso.com 的别名</p>
<p>Scheduler.contoso.com Pool2InternalWebFQDN.contoso.com 的别名</p></td>
<td><p>池之间的循环</p>
<p>使用 primary，如果失败则连接到辅助数据库</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com Pool1ExternalWebFQDN.contoso.com 的别名</p>
<p>Scheduler.contoso.com Pool2ExternalWebFQDN.contoso.com 的别名</p></td>
<td><p>池之间的循环</p>
<p>使用 primary，如果失败则连接到辅助数据库</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a>DNS 负载平衡

DNS 负载平衡通常在应用程序级别实现。 应用程序（例如，运行 Lync 的客户端）通过连接到池完全限定的域名（FQDN）的 DNS A 和 AAAA （如果使用 IPv6 寻址）中返回的某个 IP 地址，尝试连接到池中的服务器。

例如，如果名为 pool01.contoso.com 的池中有三台前端服务器，则会发生以下情况：

  - 为 pool01.contoso.com 运行 Lync 查询 DNS 的客户端。 查询返回三个 IP 地址并将其缓存，如下所示（不一定是按此顺序）：
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92

  - 客户端尝试建立到其中一个 IP 地址的传输控制协议（TCP）连接。 如果失败，则客户端会尝试缓存中的下一个 IP 地址。

  - 如果 TCP 连接成功，则客户端将 TLS 协商为连接到 pool01.contoso.com 上的主注册器。

  - 如果客户端在未成功连接的情况下尝试所有缓存的条目，则系统会通知用户目前没有运行 Lync Server 2013 的服务器。

<div>


> [!NOTE]  
> 基于 DNS 的负载平衡不同于 DNS 循环（DNS RR），这通常是指负载平衡，具体是依靠 DNS 来提供与池中的服务器对应的 IP 地址的不同顺序。 通常，DNS RR 只启用负载分配，但不启用故障转移。 例如，如果连接到 DNS A 和 AAAA 返回的一个 IP 地址（如果使用的是 IPv6 寻址）查询失败，则连接将失败。 因此，DNS 轮循机制本身不如基于 DNS 的负载平衡可靠。 您可以将 DNS 循环与 DNS 负载平衡结合使用。



</div>

DNS 负载平衡用于以下各项：

  - 将服务器到服务器 SIP 的负载平衡到边缘服务器

  - 对统一通信应用程序服务（UCAS）应用程序（如会议自动助理、响应组和呼叫寄存）进行负载平衡

  - 阻止到 UCAS 应用程序的新连接（也称为 "排出"）

  - 负载平衡客户端和边缘服务器之间的所有客户端到服务器流量

无法将 DNS 负载平衡用于以下各项：

  - 到控制器或前端服务器的客户端到服务器 web 通信

DNS 负载平衡和联合通信：

如果 DNS SRV 查询返回了多个 DNS 记录，则访问边缘服务将始终使用最小的数值优先级和最高的数值权重来选取 DNS SRV 记录。 Internet 工程任务组文档 "用于指定服务位置的 DNS RR （DNS SRV）" <http://www.ietf.org/rfc/rfc2782.txt>指定如果定义了多个 dns SRV 记录，先使用优先级，再使用 "权重"。 例如，DNS SRV 记录 A 的权重为20，优先级为40，DNS SRV 记录 B 的权重为10，优先级为50。 将选择优先级为40的 DNS SRV 记录 A。 以下规则适用于 DNS SRV 记录选择：

  - 首先考虑优先级。 客户端必须尝试联系由 DNS SRV 记录定义的目标主机，该主机可以达到其最小编号优先级。 应按权重字段定义的顺序尝试具有相同优先级的目标。

  - "权重" 字段指定具有相同优先级的条目的相对权重。 应按按比例更高的选择概率来指定更大的权重。 当没有任何要执行的服务器选择时，DNS 管理员应使用权重0。 如果包含的权重大于0的记录存在，则权重为0的记录应具有很小的选择机会。

如果返回具有相同优先级和权重的多个 DNS SRV 记录，则访问边缘服务将选择首先从 DNS 服务器接收的 SRV 记录。

</div>

</div>

<span> </span>

</div>

</div>

</div>

