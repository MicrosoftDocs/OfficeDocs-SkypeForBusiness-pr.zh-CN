---
title: Lync Server 2013：确定 DNS 要求
TOCTitle: 确定 DNS 要求
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398758(v=OCS.15)
ms:contentKeyID: 49313639
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 确定 Lync Server 2013 的 DNS 要求

 

_**上一次修改主题：** 2016-12-08_

使用以下流程图确定域名系统 (DNS) 要求。对于 2013 年 2 月版的 Lync Server 2013 累积更新，如有变化会在应用处注明。

> [!IMPORTANT]
> Microsoft Lync Server 2013 支持使用 IPv6 寻址。要使用 IPv6 地址，还必须提供 IPv6 DNS 支持和配置 DNS 主机 AAAA（称为“4 A”）记录。在使用 IPv4 和 IPv6 的部署中，最好为 IPv4 配置和维护 A 记录，并为 IPv6 配置主机 AAAA。即使您的部署已完全转换为 IPv6，当外部用户仍在使用 IPv4 时，也仍需要 IPv4 DNS 主机记录。


**确定 DNS 要求流程图**

![DNS 要求流程图](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "DNS 要求流程图")

> [!IMPORTANT]
> 默认情况下，未加入域的计算机的计算机名称是主机名称，而不是完全限定域名 (FQDN)。拓扑生成器使用 FQDN，而非主机名称。因此，必须在要部署为未加入域的边缘服务器的计算机名称上配置 DNS 后缀。在分配 Lync Server、边缘服务器和池的 FQDN 时，<strong>仅使用标准字符</strong>（包括 A–Z、a–z、0–9 和连字符）。不要使用 Unicode 字符或下划线字符。外部 DNS 和公共 CA 通常不支持在 FQDN 中使用非标准字符（当必须向证书中的 SN 分配 FQDN 时）。有关其他详细信息，请参阅<a href="lync-server-2013-configure-dns-host-records.md">配置 Lync Server 2013 的 DNS 主机记录</a>


## Lync 客户端如何定位服务

在 Microsoft Lync 2010、 Lync 2013 和 Lync Mobile 客户端从 Lync Server 2013 查找和访问服务方面，这些客户端是类似的。明显的例外是 Lync Windows 应用商店应用，它使用不同的服务定位过程。本节详细介绍客户端定位服务的两种方案，第一种为传统方法，使用一系列 SRV 和 A 主机记录，第二种只使用自动发现服务记录。对桌面客户端的累积更新改变了 Lync Server 2010 中的 DNS 定位过程。对于所有客户端，DNS 查询过程会一直持续到返回成功查询或者可能的 DNS 记录列表用尽为止，而最终错误将返回到客户端。

对于 **除**Lync Windows 应用商店应用外的所有客户端 在 DNS 查找期间，按以下顺序查询 SRV 记录并将其返回到客户端：

1.  lyncdiscoverinternal.*\<domain\>*   内部 Web 服务上自动发现服务的 A（主机）记录

2.  lyncdiscover.*\<domain\>*   外部 Web 服务上自动发现服务的 A（主机）记录

3.  \_sipinternaltls.\_tcp.*\<domain\>*   内部 TLS 连接的 SRV（服务定位器）记录

4.  \_sipinternal.\_tcp.*\<domain\>*   内部 TCP 连接的 SRV（服务定位器）记录（仅当允许 TCP 时才执行）

5.  \_sip.\_tls.*\<domain\>*   外部 TLS 连接的 SRV（服务定位器）记录

6.  sipinternal.*\<domain\>*   前端池或 控制器的 A（主机）记录，只能在内部网络上解析

7.  sip.*\<domain\>*   内部网络上 前端池或 控制器或者当客户端为外部客户端时 访问边缘服务的 A（主机）记录

8.  sipexternal.*\<domain\>*   当客户端为外部客户端时 访问边缘服务的 A（主机）记录

Lync Windows 应用商店应用使用以下两个记录，因此完全改变了这一过程：

1.  lyncdiscoverinternal.*\<domain\>*   内部 Web 服务上自动发现服务的 A（主机）记录

2.  lyncdiscover.*\<domain\>*   外部 Web 服务上自动发现服务的 A（主机）记录

不回退到其他记录类型。

用于较新客户端和较旧客户端的方法的区别在于，自动发现服务将成为定位所有服务的首选方法。

当成功连接时，自动发现服务返回用户主池的所有 Web 服务 URL，包括 Mobility Service（被在 IIS 中为该服务创建的虚拟目录称为 Mcx）、 Microsoft Lync Web App 和 Web 计划程序 URL。但是，内部 Mobility Service URL 和外部 Mobility Service URL 都与外部 Web 服务 FQDN 关联。因此，不管移动设备是在网络内部还是外部，该设备都始终从外部通过反向代理连接到 Mobility Service。

如果已安装 2013 年 2 月版的 Lync Server 2013 累积更新，则自动发现服务还将返回对内部/UCWA、外部/UCWA 和 UCWA 的引用。这些条目是指统一通信 Web API (UCWA) Web 组件。目前，只使用条目 UCWA，它提供对该 Web 组件 URL 的引用。UCWA 由 Lync 2013 Mobile 客户端使用，而不是由 Lync 2010 Mobile 客户端所用的 Mcx Mobility Service 使用。

> [!NOTE]  
> 创建 SRV 记录时，请务必记住，这些记录必须指向在其中创建了 DNS SRV 记录的同一域中的 DNS A 和 AAAA（如果您使用的是 IPv6 寻址）记录。例如，如果 SRV 记录位于 contoso.com，则它所指向的 A 和 AAAA（如果您使用的是 IPv6 寻址）记录不能位于 fabrikam.com 中。



> [!TIP]
> 默认配置是使所有移动客户端流量通过外部网站。您可以修改设置，以便仅返回内部 URL（如果这更符合您的需求）。在此配置下，仅当用户位于企业网络内部时才能在其移动设备上使用 Lync 移动应用程序。若要定义此配置，需要使用 <strong>Set-CsMcxConfiguration</strong> cmdlet。


> [!NOTE]  
> 虽然移动应用程序还可以连接到其他 Lync Server 2013 服务（如通讯簿服务），但仅为 Mobility Service 将内部移动应用程序 Web 请求转到外部 Web FQDN。其他服务请求（如通讯簿请求）不需要此配置。



移动设备支持手动发现服务。在此情况下，每个用户必须使用整个内部和外部自动发现服务 URI（包括协议和路径）配置移动设备设置，如下所示：

  - htt<span></span>ps://<span></span>*\<ExtPoolFQDN\>*/Autodiscover/autodiscoverservice.svc/Root（用于外部访问）

  - h<span></span>ttps://<span></span>*\<IntPoolFQDN\>*/AutoDiscover/AutoDiscover.svc/Root（用于内部访问）

建议使用自动发现而非手动发现。但是，手动设置对解决移动设备连接问题很有用。

## 通过 Lync Server 配置拆分式 DNS

拆分式 DNS 以名称编号得名，例如，拆分 DNS 或水平拆分 DNS。它仅仅描述其中具有相同命名空间的两个 DNS 区域（其中一个 DNS 区域仅为内部请求提供服务，而另一个 DNS 区域仅为外部请求提供服务）的 DNS 配置。但是，内部 DNS 所包含的许多 DNS SRV 和 A 记录不包含在外部 DNS 中，反之亦然。如果内部和外部 DNS 中存在相同的 DNS 记录（例如，www.contoso.com），则根据启动 DNS 查询的位置（内部或外部）不同，返回的 IP 地址也将不同。

> [!IMPORTANT]
> 当前，移动性（或者更具体讲，LyncDiscover 和 LyncDiscoverInternal DNS 记录）不支持拆分式 DNS。必须在外部 DNS 服务器上定义 LyncDiscover，在内部 DNS 服务器上定义 LyncDiscoverInternal。


出于这些主题的目的，将使用术语“拆分式 DNS”。

如果要配置拆分式 DNS，以下内部和外部区域包含每个区域所需的 DNS 记录类型的摘要。有关详细信息，请参阅 [Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)。

**内部 DNS：**

  - 包含名为 contoso.com 且受其管辖的 DNS 区域

  - 内部 contoso.com 区域包含：
    
      - 内部 Lync Server 2013 客户端自动配置的 DNS A 和 AAAA（如果使用的是 IPv6 寻址）和 SRV 记录（可选）
    
      - Lync Server 2013 Web 服务的自动发现的 DNS A 和 AAAA（如果使用的是 IPv6 寻址）或 CNAME 记录（可选）
    
      - 前端池名称、控制器或控制器池名称和企业网络中运行 Lync Server 2013 的所有内部服务器的 DNS A 和 AAAA 记录（如果使用的是 IPv6 寻址）
    
      - 外围网络中每台 Lync Server 2013 边缘服务器的边缘内部接口的 DNS A 和 AAAA（如果使用的是 IPv6 寻址）
    
      - 外围网络中每台反向代理服务器的内部接口的 DNS A 和 AAAA（如果使用的是 IPv6 寻址）记录（仅对反向代理的管理是可选的）
    
      - 外围网络中用于解决对 contoso.com 的查询的所有 Lync Server 2013  边缘服务器内部边缘接口
    
      - 企业网络中所有运行 Lync Server 2013 的服务器和运行 Lync 2013 的客户端均指向内部 DNS 服务器，以解决对 contoso.com 的查询，或在每台边缘服务器上使用 HOSTS 文件并列出下一个跃点服务器（尤其是控制器或控制器 VIP、前端池 VIP 或 Standard Edition Server）的 A 和 AAAA（如果使用的是 IPv6 寻址）记录。

**外部 DNS：**

  - 包含名为 contoso.com 且受其管辖的 DNS 区域

  - 外部 contoso.com 区域包含：
    
      - Lync Server 2013 客户端自动配置的 DNS A 和 AAAA（如果使用的是 IPv6 寻址）和 SRV 记录（可选）
    
      - Lync Server 2013 Web 服务的自动发现的 DNS A 和 AAAA（如果使用的是 IPv6 寻址）或 CNAME 记录以便用于移动性
    
      - 外围网络中每台 Lync Server 2013 边缘服务器的边缘外部接口或硬件负载平衡器虚拟 IP (VIP) 的 DNS A 和 AAAA（如果使用的是 IPv6 寻址）和 SRV 记录
    
      - 外围网络中反向代理服务器的外部接口的 DNS A 和 AAAA（如果使用的是 IPv6 寻址）记录或反向代理服务器池的 VIP

## 没有拆分式 DNS 时的自动配置

如果使用拆分式 DNS，则当内部 DNS 区域包含每个使用中的 SIP 域的 \_sipinternaltls.\_tcp SRV 记录时，从内部登录的 Lync Server 2013 用户可以利用自动配置。但是，如果不使用拆分式 DNS，则除非执行本节后面所述的解决办法之一，否则运行 Lync 的客户端的内部自动配置将不起作用。这是因为 Lync Server 2013 要求用户的 SIP URI 与为自动配置指定的前端池的域相匹配。 Communicator 早期版本亦是如此。

例如，如果正在使用两个 SIP 域，则需要以下 DNS 服务 (SRV) 记录：

  - 如果用户使用 bob@contoso.com 登录，由于用户的 SIP 域 (contoso.com) 与自动配置前端池的域相匹配，因此，以下 SRV 记录将用于自动配置：
    
     \_sipinternaltls.\_tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com

  - 如果用户使用 alice@fabrikam.com 登录，则以下 DNS SRV 记录将用于第二个 SIP 域的自动配置。
    
     \_sipinternaltls.\_tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

与此相对，如果用户使用 tim@litwareinc.com 登录，则以下 DNS SRV 记录不会用于自动配置，因为客户端的 SIP 域 (litwareinc.com) 与池所在的域 (fabrikam.com) 不匹配：

 \_sipinternaltls.\_tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com

如果运行 Lync 的客户端需要自动配置，请选择以下选项之一：

  - **组策略对象** 使用组策略对象 (GPO) 填充正确的服务器值。
    
    > [!NOTE]  
    > 此选项不会启用自动配置，但可以自动化手动配置的过程，因此，使用这种方法时不需要与自动配置关联的 SRV 记录。
    


  - **匹配内部区域** 在内部 DNS 中创建一个与外部 DNS 区域匹配的区域（例如，contoso.com），并创建与用于自动配置的 Lync Server 2013 池对应的 DNS A 和 AAAA（如果使用的是 IPv6 寻址）记录。例如，如果用户驻留在 pool01.contoso.net 上，却使用 bob@contoso.com 登录 Lync，则创建一个名为 contoso.com 的内部 DNS 区域，并在其内部为 pool01.contoso.com 创建 DNS A 和 AAAA（如果使用的是 IPv6 寻址）记录。

  - **精确内部区域** 如果不能选择在内部 DNS 中创建整个区域，则可以创建与自动配置需要的 SRV 记录对应的精确（即专用的）区域，并使用 dnscmd.exe 填充这些区域。需要 Dnscmd.exe 是因为 DNS 用户界面不支持创建精确区域。例如，如果 SIP 域为 contoso.com，并且名为 pool01 的前端池包含两台前端服务器，则内部 DNS 中需要以下精确区域和 A 记录：
    
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

> [!NOTE]  
> 前端池 FQDN 出现两次，但两次的 IP 地址不同。这是因为使用了 DNS 负载平衡，但如果使用硬件负载平衡，则只有一个前端池条目。并且，前端池 FQDN 值因 contoso.com 示例和 fabrikam.com 示例的不同而变化，但 IP 地址保持不变。这是因为从任一 SIP 域登录的用户都对自动配置使用相同的前端池。



有关详细信息，请参阅 DMTF 博客文章“Communicator 自动配置和拆分式 DNS”，网址为 <http://go.microsoft.com/fwlink/?linkid=200707>。

> [!NOTE]  
> 每个博客的内容及其 URL 如有更改，恕不另行通知。



## 为灾难恢复配置域名系统 (DNS)

若要配置 DNS 以将 Lync Server 2013 Web 流量重定向到灾难恢复和故障转移网站，则必须使用支持 GeoDNS 的 DNS 提供程序。可以将针对 Web 的 DNS 记录设置为支持灾难恢复，以便让使用 Web 服务的功能在 前端池关闭的情况下也能继续运行。此灾难恢复功能支持自动发现 (Lyncdiscover URL)、会议和拨入式简单 URL。

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
<td><p>Pool1InternalWebFQDN.contoso.com 的 Meet.contoso.com 别名</p>
<p>Pool2InternalWebFQDN.contoso.com 的 Meet.contoso.com 别名</p></td>
<td><p>在池之间启用循环</p>
<p>使用主池，发生故障时连接到副池</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com 的 Meet.contoso.com 别名</p>
<p>Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>在池之间启用循环</p>
<p>使用主池，发生故障时连接到副池</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</p>
<p>Pool2InternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</p></td>
<td><p>在池之间启用循环</p>
<p>使用主池，发生故障时连接到副池</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</p>
<p>Pool2ExternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名</p></td>
<td><p>在池之间启用循环</p>
<p>使用主池，发生故障时连接到副池</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com 的 Lyncdiscoverinternal.contoso.com 别名</p>
<p>Pool2InternalWebFQDN.contoso.com 的 Lyncdiscoverinternal.contoso.com 别名</p></td>
<td><p>在池之间启用循环</p>
<p>使用主池，发生故障时连接到副池</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com 的 Lyncdiscover.contoso.com 别名</p>
<p>Pool2ExternalWebFQDN.contoso.com 的 Lyncdiscover.contoso.com 别名</p></td>
<td><p>在池之间启用循环</p>
<p>使用主池，发生故障时连接到副池</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</p>
<p>Pool2InternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</p></td>
<td><p>在池之间启用循环</p>
<p>使用主池，发生故障时连接到副池</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</p>
<p>Pool2ExternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名</p></td>
<td><p>在池之间启用循环</p>
<p>使用主池，发生故障时连接到副池</p></td>
</tr>
</tbody>
</table>


## DNS 负载平衡

通常在应用程序级别实现 DNS 负载平衡。应用程序（如运行 Lync 的客户端）通过连接到由池的完全限定域名 (FQDN) 的 DNS A 和 AAAA（如果使用的是 IPv6 寻址）记录查询返回的 IP 地址之一来尝试连接到池中的服务器。

例如，如果名为 pool01.contoso.com 的池中有三台前端服务器，则会发生以下情形：

  - 运行 Lync 的客户端将向 DNS 查询 pool01.contoso.com。此查询将返回三个 IP 地址并将其按如下方式进行缓存（不需要按此顺序）：
    
    pool01.contoso.com      192.168.10.90
    
    pool01.contoso.com      192.168.10.91
    
    pool01.contoso.com      192.168.10.92

  - 客户端将尝试建立到其中一个 IP 地址的传输控制协议 (TCP) 连接。如果失败，则客户端会尝试缓存中的下一个 IP 地址。

  - 如果 TCP 连接成功，则客户端与 TLS 协商连接到 pool01.contoso.com 上的主注册器。

  - 如果客户端尝试了所有缓存的条目，但连接仍未成功，则通知用户当前没有可用的运行 Lync Server 2013 的服务器。

> [!NOTE]  
> 基于 DNS 的负载平衡不同于 DNS 循环 (DNS RR)，后者通常是指依靠 DNS 提供与池中服务器对应的不同顺序的 IP 地址来进行负载平衡。通常 DNS RR 只启用负载分配，而不启用故障转移。例如，如果到由 DNS A 和 AAAA（如果使用的是 IPv6 寻址）查询返回的一个 IP 地址的连接失败，则连接失败。因此，DNS 循环自身的可靠性低于基于 DNS 的负载平衡。您可以将 DNS 循环与 DNS 负载平衡结合使用。



DNS 负载平衡用于以下方面：

  - 对至边缘服务器的服务器到服务器 SIP 进行负载平衡

  - 对统一通信应用程序服务 (UCAS) 应用程序（如会议自动助理、响应组和呼叫寄存）进行负载平衡

  - 阻止到 UCAS 应用程序的新连接（也称为“排出”）

  - 对客户端和边缘服务器之间的所有客户端到服务器的流量进行负载平衡

DNS 负载平衡不能用于以下方面：

  - 客户端到服务器至控制器或前端服务器的 Web 流量

DNS 负载平衡和联盟流量：

如果一个 DNS SRV 查询返回了多个 DNS 记录，则访问边缘服务始终以最低数值优先级与最高数值权重拾取 DNS SRV 记录。Internet 工程任务组文档“用于指定服务位置的一个 DNS RR (DNS SRV)”（见于 <http://www.ietf.org/rfc/rfc2782.txt>）指定，如果有多个定义的 DNS SRV 记录，则首先使用优先级，其次使用权重。例如 DNS SRV 记录 A 权重为 20，优先级为 40，而 DNS SRV 记录 B 权重为 10，优先级为 50。优先级为 40 的 DNS SRV 记录 A 将被选中。下列规则适用于 DNS SRV 记录选择：

  - 首先考虑优先级。客户端必须尝试联系它可访问的由具有最低编号优先级的 DNS SRV 记录定义的目标主机。应按权重字段定义的顺序尝试具有相同优先级的目标。

  - 权重字段指定具有相同优先级的条目的相对权重。权重越大，应赋予的被选中可能性相应越高。当不作任何服务器选择时，DNS 管理员应使用权重 0。相对于包含大于 0 的权重的记录，权重为 0 的记录应具有非常小的被选中机会。

如果返回了优先级和权重都相同的多个 DNS SRV 记录，则访问边缘服务将选择首先从 DNS 服务器收到的 SRV 记录。

