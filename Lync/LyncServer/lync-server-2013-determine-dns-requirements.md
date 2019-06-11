---
title: Lync Server 2013：确定 DNS 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e299f138a28ba4863250d2e0be1f31f705f4a173
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a>确定 Lync Server 2013 的 DNS 要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-22_

使用以下流程图确定域名系统 (DNS) 要求。 Lync Server 2013 的累积更新的更改: 2 月2013的适用位置。

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2013 支持使用 IPv6 寻址。 要使用 IPv6 地址，还必须提供 IPv6 DNS 支持和配置 DNS 主机 AAAA（称为“4 A”）记录。 在使用 IPv4 和 IPv6 的部署中，最好为 IPv4 配置和维护 A 记录，并为 IPv6 配置主机 AAAA。 即使您的部署已完全转换为 IPv6，当外部用户仍在使用 IPv4 时，也仍需要 IPv4 DNS 主机记录。



</div>

**确定 DNS 要求流程图**

![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")

<div>


> [!IMPORTANT]  
> 默认情况下, 未加入域的计算机的计算机名是主机名, 而不是完全限定的域名 (FQDN)。 拓扑生成器使用 Fqdn, 而不是主机名。 因此，您必须在要部署为域外边缘服务器的计算机的名称上配置 DNS 后缀。 分配您的 Lync Server、边缘服务器和池的 FQDN 时，<STRONG>只使用标准字符</STRONG>（包括 A–Z、a–z、0–9 和连字符）。 不要使用 Unicode 字符或下划线。 外部 DNS 和公共 CA（即，在 FQDN 必须分配给证书中的 SN 时）通常不支持在 FQDN 中使用非标准字符。 有关其他详细信息, 请参阅<A href="lync-server-2013-configure-dns-host-records.md">为 Lync Server 2013 配置 DNS 主机记录</A>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a>Lync 客户端如何查找服务

Microsoft Lync 2010、Lync 2013 和 Lync Mobile 与客户在 Lync Server 2013 中查找和访问服务的方式类似。 显著的例外是使用不同服务位置进程的 Lync Windows 应用商店应用。 本节详细介绍客户端定位服务的两种方案，第一种为传统方法，使用一系列 SRV 和 A 主机记录，第二种只使用自动发现服务记录。 对桌面客户端的累积更新从 Lync Server 2010 更改所有客户端的 DNS 位置进程, DNS 查询过程将继续, 直到返回成功的查询, 或者可能的 DNS 记录的列表已用完, 最后一个错误将返回到客户端。

对于在 DNS 查找期间除 Lync Windows 应用商店应用**之外**的所有客户端, 将按以下顺序查询和返回到客户端的 SRV 记录:

1.  lyncdiscoverinternal.\<内部\> Web 服务上的自动发现服务的域 A (主机) 记录

2.  lyncdiscover.\<外部\> Web 服务上的自动发现服务的域 A (主机) 记录

3.  \_sipinternaltls.\_tcp。\<内部\> TLS 连接的域 SRV (服务定位器) 记录

4.  \_sipinternal.\_tcp。\<内部\> TCP 连接的域 SRV (服务定位器) 记录 (仅在允许 TCP 时执行)

5.  \_sip.\_tls。\<外部\> TLS 连接的域 SRV (服务定位器) 记录

6.  sipinternal.\<前端\>池或控制器的域 A (主机) 记录, 仅在内部网络上可解析

7.  sip.\<用于\>内部网络的前端池或控制器的域 A (主机) 记录, 或者当客户端为外部客户端时的访问边缘服务

8.  sipexternal.\<当\>客户端为外部客户端时, Access Edge 服务的域 A (主机) 记录

Lync Windows 应用商店应用将完全更改该过程, 因为它使用两个记录:

1.  lyncdiscoverinternal.\<内部\> Web 服务上的自动发现服务的域 A (主机) 记录

2.  lyncdiscover.\<外部\> Web 服务上的自动发现服务的域 A (主机) 记录

不回退到其他记录类型。

用于较新客户端和较旧客户端的方法的区别在于，自动发现服务将成为定位所有服务的首选方法。

连接成功后, 自动发现服务将返回用户的主池的所有 Web 服务 Url, 包括移动服务 (称为 Mcx 由在 IIS 中为该服务创建的虚拟目录)、Microsoft Lync Web App 和 Web 计划程序 Url。 但是，内部 Mobility Service URL 和外部 Mobility Service URL 都与外部 Web 服务 FQDN 关联。 因此，不管移动设备是在网络内部还是外部，该设备都始终从外部通过反向代理连接到 Mobility Service。

如果 Lync Server 2013 的累积更新: 已安装2月 2013, 则自动发现服务还返回对 Internal/UCWA、External/UCWA 和 UCWA 的引用。 这些条目是指统一通信 Web API (UCWA) Web 组件。 目前，只使用条目 UCWA，它提供对该 Web 组件 URL 的引用。 UCWA 由 Lync 2013 移动客户端使用, 而不是 Lync 2010 移动客户端使用的 Mcx 移动服务。

<div>


> [!NOTE]  
> 创建 SRV 记录时，请务必记住，这些记录必须指向在其中创建了 DNS SRV 记录的同一域中的 DNS A 和 AAAA（如果您使用的是 IPv6 寻址）记录。 例如, 如果 SRV 记录在 contoso.com 中, 则 A 和 AAAA (如果你使用的是 IPv6 寻址) 记录指向的不能在 fabrikam.com 中。



</div>

<div>


> [!TIP]  
> 默认配置是使所有移动客户端流量通过外部网站。 您可以修改设置，以便仅返回内部 URL（如果这更符合您的需求）。 在此配置下，仅当用户位于企业网络内部时才能在其移动设备上使用 Lync 移动应用程序。 若要定义此配置，需要使用 <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet。



</div>

<div>


> [!NOTE]  
> 虽然移动应用程序也可以连接到其他 Lync Server 2013 服务 (如通讯簿服务), 但内部移动应用程序 web 请求仅转到移动服务的外部 web FQDN。 其他服务请求（如通讯簿请求）不需要此配置。



</div>

移动设备支持手动发现服务。在此情况下，每个用户必须使用整个内部和外部自动发现服务 URI（包括协议和路径）配置移动设备设置，如下所示：

  - https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root

  - https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root, 用于内部访问

建议使用自动发现而非手动发现。 但是，手动设置对解决移动设备连接问题很有用。

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a>配置与 Lync Server 的分裂的 DNS

拆分式 DNS 以名称编号得名，例如，拆分 DNS 或水平拆分 DNS。它仅仅描述其中具有相同命名空间的两个 DNS 区域（其中一个 DNS 区域仅为内部请求提供服务，而另一个 DNS 区域仅为外部请求提供服务）的 DNS 配置。但是，内部 DNS 所包含的许多 DNS SRV 和 A 记录不包含在外部 DNS 中，反之亦然。如果内部和外部 DNS 中存在相同的 DNS 记录（例如，www.contoso.com），则根据启动 DNS 查询的位置（内部或外部）不同，返回的 IP 地址也将不同。

<div>


> [!IMPORTANT]  
> 当前，移动性（或者更具体讲，LyncDiscover 和 LyncDiscoverInternal DNS 记录）不支持拆分式 DNS。必须在外部 DNS 服务器上定义 LyncDiscover，在内部 DNS 服务器上定义 LyncDiscoverInternal。



</div>

出于这些主题的目的，将使用术语“拆分式 DNS”。

如果要配置拆分式 DNS，以下内部和外部区域包含每个区域所需的 DNS 记录类型的摘要。 有关详细信息, 请参阅[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)。

**内部 DNS：**

  - 包含名为 contoso.com 且受其管辖的 DNS 区域

  - 内部 contoso.com 区域包含：
    
      - DNS A 和 AAAA (如果使用 IPv6 寻址) 和内部 Lync Server 2013 客户端自动配置的 SRV 记录 (可选)
    
      - DNS A 和 AAAA (如果使用 IPv6 寻址) 或用于自动发现 Lync Server 2013 Web 服务的 CNAME 记录 (可选)
    
      - DNS A 和 AAAA (如果使用 IPv6 寻址) 记录的前端池名称、Director 或控制器池名称, 以及在企业网络中运行 Lync Server 2013 的所有内部服务器
    
      - DNS A 和 AAAA (如果你正在使用 IPv6 寻址) 针对外围网络中每个 Lync Server 2013 和 Edge 服务器的边缘内部接口的记录
    
      - 外围网络中每台反向代理服务器的内部接口的 DNS A 和 AAAA（如果使用的是 IPv6 寻址）记录（仅对反向代理的管理是可选的）
    
      - 外围网络中的所有 Lync Server 2013 Edge 服务器内部边缘接口使用内部 DNS 区域将查询解析为 contoso.com
    
      - 在企业网络中运行 lync Server 2013 和运行 Lync 2013 的客户端的所有服务器指向内部 DNS 服务器, 以便将查询解析到 contoso.com 或在每台边缘服务器上使用 HOSTS 文件, 并列出 A 和 AAAA (如果使用 IPv6 寻址) 记录下一跃点服务器, 特别是 Director 或 Director VIP、前端池 VIP 或标准版服务器

**外部 DNS：**

  - 包含名为 contoso.com 且受其管辖的 DNS 区域

  - 外部 contoso.com 区域包含：
    
      - DNS A 和 AAAA (如果使用 IPv6 寻址) 和 Lync Server 2013 客户端自动配置的 SRV 记录 (可选)
    
      - DNS A 和 AAAA (如果使用 IPv6 寻址) 或 CNAME 记录, 用于自动发现 Lync Server 2013 Web 服务以与移动版一起使用
    
      - DNS A 和 AAAA (如果正在使用 IPv6 寻址) 和适用于外围网络中每个 Lync Server 2013、Edge 服务器或硬件负载平衡器虚拟 IP (VIP) 的边缘外部接口的 SRV 记录
    
      - 外围网络中反向代理服务器的外部接口的 DNS A 和 AAAA（如果使用的是 IPv6 寻址）记录或反向代理服务器池的 VIP

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a>没有拆分式 DNS 时的自动配置

如果内部 DNS 区域包含\_sipinternaltls, 则使用 "分裂" DNS, 登录内部的 Lync Server 2013 用户可以利用自动配置。\_正在使用的每个 SIP 域的 tcp SRV 记录。 但是, 如果您不使用分裂的 DNS, 则运行 Lync 的客户端的内部自动配置将不起作用, 除非实施本部分后面部分中所述的解决方法之一。 这是因为 Lync Server 2013 要求用户的 SIP URI 与为自动配置指定的前端池的域匹配。 这也是早期版本的 Communicator 的情况。

例如，如果正在使用两个 SIP 域，则需要以下 DNS 服务 (SRV) 记录：

  - 如果用户使用 bob@contoso.com 登录，由于用户的 SIP 域 (contoso.com) 与自动配置前端池的域相匹配，因此，以下 SRV 记录将用于自动配置：
    
     \_sipinternaltls.\_tcp.contoso.com。 86400 IN SRV 0 0 5061 pool01.contoso.com

  - 如果用户使用 alice@fabrikam.com 登录，则以下 DNS SRV 记录将用于第二个 SIP 域的自动配置。
    
     \_sipinternaltls.\_tcp.fabrikam.com。 86400 IN SRV 0 0 5061 pool01.fabrikam.com

与此相对，如果用户使用 tim@litwareinc.com 登录，则以下 DNS SRV 记录不会用于自动配置，因为客户端的 SIP 域 (litwareinc.com) 与池所在的域 (fabrikam.com) 不匹配：

 \_sipinternaltls.\_tcp.litwareinc.com。 86400 IN SRV 0 0 5061 pool01.fabrikam.com

如果运行 Lync 的客户端需要 "自动配置", 请选择下列选项之一:

  - **组策略对象**   使用组策略对象 (gpo) 填充正确的服务器值。
    
    <div>
    

    > [!NOTE]  
    > 此选项不会启用自动配置，但可以自动化手动配置的过程，因此，使用这种方法时不需要与自动配置关联的 SRV 记录。

    
    </div>

  - **匹配的内部区域**   在内部 DNS 中创建与外部 dns 区域匹配的区域 (例如 contoso.com), 并创建 DNS a 和 AAAA (如果使用 IPv6 寻址) 与用于自动的 Lync Server 2013 池对应的记录配置. 例如, 如果用户托管在 pool01.contoso.net 上, 但在 bob@contoso.com 中登录 Lync, 请创建名为 contoso.com 的内部 DNS 区域, 并在其中创建一个名为的内部 DNS 区域 (如果使用 IPv6 寻址) 记录, 请创建 pool01.contoso.com 的 DNS A 和 AAAA。

  - **固定点内部区域**   如果在内部 DNS 中创建整个区域不是一个选项, 则可以创建与自动配置所需的 SRV 记录相对应的 pin 点 (即专用) 区域, 并填充这些使用 dnscmd 的区域。 Dnscmd 是必需的, 因为 DNS 用户界面不支持创建固定点区域。 例如, 如果 SIP 域为 contoso.com, 并且你有一个名为 pool01 的前端池, 该池包含两个前端服务器, 则你需要内部 DNS 中的以下 pin 点区域和记录:
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    如果环境中包含第二个 SIP 域（例如，fabrikam.com），则内部 DNS 中需要以下精确区域和 A 记录：
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> 前端池 FQDN 出现两次，但两次的 IP 地址不同。 这是因为使用了 DNS 负载平衡，但如果使用硬件负载平衡，则只有一个前端池条目。 并且，前端池 FQDN 值因 contoso.com 示例和 fabrikam.com 示例的不同而变化，但 IP 地址保持不变。 这是因为用户从任一 SIP 域登录, 所以使用相同的前端池进行自动配置。



</div>

有关详细信息, 请参阅 DMTF 博客文章 "Communicator 自动配置和分裂的 DNS" [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707)。

<div>


> [!NOTE]  
> 每个博客的内容及其 URL 如有更改，恕不另行通知。



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a>为灾难恢复配置域名系统 (DNS)

若要将 DNS 配置为将 Lync Server 2013 Web 流量重定向到你的灾难恢复和故障转移网站, 你必须使用支持 GeoDNS 的 DNS 提供程序。 你可以设置 Web 的 DNS 记录以支持灾难恢复, 因此即使一个完整的前端池停机, 使用 Web 服务的功能仍继续。 此灾难恢复功能支持自动发现 (Lyncdiscover URL)、会议和拨入式简单 URL。

您可以在 GeoDNS 提供程序上为 Web 服务的内部和外部解决方案定义和配置其他 DNS 主机（如果使用的是 IPv6 地址，则为 A 和 AAAA）记录。以下详细信息假定池已配对，地理位置分散，且 GeoDNS 支持的提供程序使用循环 DNS 或被配置为使用 Pool1 作为主池，并且在发生通信丢失或硬件失败时故障转移到 Pool2。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>GeoDNS 记录 (示例)</th>
<th>池记录 (示例)</th>
<th>CNAME 记录 (示例)</th>
<th>DNS 设置（选择一个选项）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Meet-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com 的 Meet.contoso.com 别名</p>
<p>Pool2InternalWebFQDN.contoso.com 的 Meet.contoso.com 别名</p></td>
<td><p>在池之间启用循环</p>
<p>使用主映像, 如果失败则连接到辅助</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com 的 Meet.contoso.com 别名</p>
<p>Pool2ExternalWebFQDN.contoso.com 的 Meet.contoso.com 别名</p></td>
<td><p>在池之间启用循环</p>
<p>使用主映像, 如果失败则连接到辅助</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</p>
<p>Pool2InternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</p></td>
<td><p>在池之间启用循环</p>
<p>使用主映像, 如果失败则连接到辅助</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</p>
<p>Pool2ExternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</p></td>
<td><p>在池之间启用循环</p>
<p>使用主映像, 如果失败则连接到辅助</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com 的 Lyncdiscoverinternal.contoso.com 别名</p>
<p>Pool2InternalWebFQDN.contoso.com 的 Lyncdiscoverinternal.contoso.com 别名</p></td>
<td><p>在池之间启用循环</p>
<p>使用主映像, 如果失败则连接到辅助</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com 的 Lyncdiscover.contoso.com 别名</p>
<p>Pool2ExternalWebFQDN.contoso.com 的 Lyncdiscover.contoso.com 别名</p></td>
<td><p>在池之间启用循环</p>
<p>使用主映像, 如果失败则连接到辅助</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</p>
<p>Pool2InternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</p></td>
<td><p>在池之间启用循环</p>
<p>使用主映像, 如果失败则连接到辅助</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</p>
<p>Pool2ExternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</p></td>
<td><p>在池之间启用循环</p>
<p>使用主映像, 如果失败则连接到辅助</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a>DNS Load Balancing

DNS 负载平衡通常在应用程序级别实现。 应用程序 (例如, 运行 Lync 的客户端) 通过连接到池完全限定的域名 (FQDN) 的 DNS A 和 AAAA (如果使用 IPv6 寻址) 记录查询来连接到池中的某个服务器, 尝试连接到池中的服务器。

例如, 如果一个名为 pool01.contoso.com 的池中有三个前端服务器, 则将发生以下情况:

  - 运行 Lync 的 pool01.contoso.com 查询 DNS 的客户端。 该查询返回三个 IP 地址并将其缓存, 如下所示 (不必按此顺序):
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92

  - 客户端尝试建立与其中一个 IP 地址的传输控制协议 (TCP) 连接。 如果此操作失败, 客户端将尝试缓存中的下一个 IP 地址。

  - 如果 TCP 连接成功，则客户端与 TLS 协商连接到 pool01.contoso.com 上的主注册器。

  - 如果客户在未成功连接的情况下尝试所有缓存的条目, 则系统将通知用户目前没有运行 Lync Server 2013 的服务器。

<div>


> [!NOTE]  
> 基于 DNS 的负载平衡不同于 DNS 循环 (DNS RR), 它通常指的是负载平衡, 具体取决于 DNS 以提供与池中的服务器对应的不同 IP 地址顺序。 通常, DNS RR 仅支持负载分配, 但不支持故障转移。 例如, 如果连接到 DNS A 和 AAAA 返回的一个 IP 地址 (如果使用的是 IPv6 寻址) 查询失败, 连接将失败。 因此, DNS 循环复用本身比基于 DNS 的负载平衡的可靠性更低。 你可以将 DNS 循环与 DNS 负载平衡结合使用。



</div>

DNS 负载平衡用于以下情况:

  - 将服务器到服务器 SIP 负载平衡到边缘服务器

  - 负载平衡统一通信应用程序服务 (UCAS) 应用程序, 如会议自动助理、响应组和呼叫寄存

  - 阻止新连接 UCAS 应用程序 (也称为 "排出")

  - 负载平衡客户端和边缘服务器之间的所有客户端到服务器流量

无法将 DNS 负载平衡用于以下情况:

  - 客户端到服务器 web 流量到控制器或前端服务器

DNS 负载平衡和联合通信:

如果 DNS SRV 查询返回多个 DNS 记录, 则 Access Edge 服务始终使用最小的数值优先级和最高的数字权重来选取 DNS SRV 记录。 Internet 工程任务组文档 "用于指定服务位置的 DNS RR (DNS SRV)" <http://www.ietf.org/rfc/rfc2782.txt>指定如果定义了多个 DNS SRV 记录, 将首先使用 "优先级", 然后按 "重量"。 例如, DNS SRV 记录 A 的权重为 20, 优先级为 40, DNS SRV 记录 B 的权重为 10, 优先级为50。 将选择优先级为40的 DNS SRV 记录 A。 以下规则适用于 DNS SRV 记录选择:

  - 首先考虑优先级。 客户端必须尝试联系由 DNS SRV 记录定义的目标主机, 该目标主机可以访问的最低优先级。 应按照权重字段定义的顺序尝试具有相同优先级的目标。

  - "权重" 域为具有相同优先级的条目指定相对权重。 应按比例增加所选的概率。 当没有任何服务器选择要执行时, DNS 管理员应使用权重0。 如果记录包含的权重大于 0, 则权重为0的记录应具有非常小的选择机会。

如果返回具有相同优先级和权重的多个 DNS SRV 记录, 则 Access Edge 服务将选择首先从 DNS 服务器接收的 SRV 记录。

</div>

</div>

<span> </span>

</div>

</div>

</div>

