---
title: 高级边缘服务器的 DNS 规划 Skype 业务服务器
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 摘要： 查看的 Skype 方案的业务服务器部署选项。 是否希望一台服务器或首选 DNS 或 HLB 的服务器池，应帮助本主题。
ms.openlocfilehash: 88f3da6a006c74393b487a55e85a16aa56bd968b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893067"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>高级边缘服务器的 DNS 规划 Skype 业务服务器
 
**摘要：** 为业务服务器部署选项的 Skype 查看方案。 是否希望一台服务器或首选 DNS 或 HLB 的服务器池，应帮助本主题。
  
当谈到域名系统 (DNS) 规划 Skype 业务服务器时，有大量的可能播放到您的决定因素。 如果组织的域结构已经就位，那么这可能就是考虑如何继续的问题。 我们将从下面提供的主题开始：
  
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [Split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Automatic configuration without split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Walkthrough of Skype for Business clients locating services
<a name="WalkthroughOfSkype"> </a>

Skype 业务客户端在类似于早期版本的 Lync 客户端如何查找和访问业务服务器 Skype 中的服务。 本节详述服务查找过程。
  
1. lyncdiscoverinternal。\<域\>
    
     *这是内部 Web 服务上自动发现服务的 A 主机记录。* 
    
2. lyncdiscover。\<域\>
    
     *这是外部 Web 服务上自动发现服务的 A 主机记录。* 
    
3. _sipinternaltls._tcp。\<域\>
    
     *这是内部 TLS 连接的 SRV 记录。* 
    
4. _sip._tls。\<域\>
    
     *这是外部 TLS 连接的 SRV 记录。* 
    
5. sipinternal。\<域\>
    
     *这是前端池或控制器，仅在内部网络上进行解析 A 主机记录。* 
    
6. sip。\<域\>
    
     *这是前端池或控制器，仅在内部网络上进行解析 A 主机记录。* 
    
7. sipexternal。\<域\>
    
     *外部客户端时，这是访问边缘服务中，A 主机记录。* 
    
自动发现服务总是受人欢迎，因为这是服务定位的首选方法，其他方法为回退方法。
  
> [!NOTE]
> 创建 SRV 记录时，请务必记住，这些记录需要指向要在其中创建 DNS SRV 记录的同一域中的 DNS A（如果使用 IPv6 寻址，则还有 AAAA）。例如，如果 SRV 记录位于 contoso.com，则其所指向的 A（和 AAAA）记录不能在 fabrikam.com 中。 
  
如果倾向于这样做，可以设置移动设备进行手动服务发现。如果这正是你想做的，那么每个用户需要为其移动设备的设置配置内部和外部自动发现服务的完整 URI，包括协议和路径，具体如下：
  
- 用于外部访问： https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root
    
- 用于内部访问： https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root
    
我们建议使用自动发现，而不是手动发现。但是如果你要执行某种故障排除或测试，那么手动设置可能很有帮助。
  
## <a name="split-brain-dns"></a>拆分式 DNS
<a name="SplitBrainDNS"> </a>

这是一种两个 DNS 区域有相同命名空间的 DNS 配置。第一个 DNS 区域处理内部请求，而第二个 DNS 区域处理外部请求。
  
为什么公司会这样做？他们可能需要内外使用相同的命名空间，但是当然，这会导致很多 DNS SRV 和 A 记录在这个区域或那个区域是唯一的，在有重复的情况下，与这些记录关联的 IP 地址将是唯一的。
  
这带来了一些难题。 最重要的是拆分式 DNS 是**不支持**移动。 这是因为 LyncDiscover 和 LyncDiscoverInternal DNS 记录（LyncDiscover 必须定义在外部 DNS 服务器上，而 LyncDiscoverInternal 必须定义在内部 DNS 服务器上）。
  
我们将列表的内部和外部区域此处的 DNS 记录，但您可以找到详细的示例的边缘服务器环境的要求一节。
  
### <a name="internal-dns"></a>内部 DNS

- 包含名为（例如）contoso.com 的 DNS 区域，内部 DNS 是该区域的权威 DNS。
    
- 这个内部 contoso.com 包含：
    
  - DNS A 和 AAAA （如果您正在使用 IPv6 寻址） 记录前端池、 控制器池或控制器池名称和业务服务器运行 Skype，贵组织的网络中的所有内部服务器。
    
  - DNS A 和 AAAA （如果您正在使用 IPv6 寻址） 记录您边缘内部接口的每个 Skype 业务 Server 边缘服务器在外围网络中。
    
  - （这是**可选**的反向代理的管理） 外围网络中每台反向代理服务器的内部接口的 DNS A 和 AAAA （如果您正在使用 IPv6 寻址） 记录。
    
  - DNS A 和 AAAA （如果您正在使用 IPv6 寻址） 和 SRV 记录内部 Skype Business Server 客户端自动配置 （它是**可选**的）。
    
  - DNS A 和 AAAA （如果您正在使用 IPv6 寻址） 或 CNAME 记录的自动发现的 Skype Business Server Web services （这是**可选**的）。
    
- 您的业务服务器内部边缘接口外围网络中的所有 Skype 可都用于解决对 contoso.com 的查询此内部 DNS 区域。
    
- 业务提供，和企业网络中运行业务服务器 Skype 的客户端运行 Skype 的所有服务器都指向内部 DNS 服务器，以解决对 contoso.com 的查询或他们使用主机文件上每个边缘服务器和列表 A 和 AAAA （如果您正在使用（特别是对于控制器或控制器池 VIP、 Front End 池 VIP 或 Standard Edition server） 的下一个跃点服务器 IPv6 寻址） 记录。
    
### <a name="external-dns"></a>外部 DNS

- 包含名为（例如）contoso.com 的 DNS 区域，内部 DNS 是该区域的权威 DNS。
    
- 此外部 contoso.com 包含：
    
  - DNS A 和 AAAA （如果您正在使用 IPv6 寻址） 或 CNAME 记录的自动发现的 Skype 业务服务器 web 服务。 这是用于移动。
    
  - DNS A 和 AAAA （如果您正在使用 IPv6 寻址） 和 SRV 记录的边缘外部接口的每个 Skype 业务 Server 边缘服务器或硬件负载平衡 (HLB) VIP 外围网络中。
    
  - DNS A 和 AAAA （如果您正在使用 IPv6 寻址） 和 SRV 记录的外部接口 (VIP 的反向代理服务器池)，反向代理服务器的外围网络中。
    
  - DNS A 和 AAAA （如果您正在使用 IPv6 寻址） 和 SRV 记录的 Skype Business Server 客户端自动配置 （**可选**）。
    
## <a name="automatic-configuration-without-split-brain-dns"></a>没有拆分式 DNS 时的自动配置
<a name="NoSplitBrainDNS"> </a>

如果不使用拆分式 DNS，内部自动配置运行 for Business 的 Skype 的客户端不会起作用，除非您使用我们在这里有解决方法之一。 为什么会不起作用？ 因为 Skype 业务服务器需要用户的 SIP URI 匹配指定用于自动配置的前端池的域。 此尚未更改从早期版本的 Lync Server。
  
所以，如果正在使用两个 SIP 域，那么需要以下 DNS SRV 记录：
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *如果一个用户登录为 bob@contoso.com，此记录将适合自动配置，如前端池 (contoso.com) 的域用户的 SIP 域匹配。* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *如果用户为 alice@fabrikam.com 登录，此记录将自动配置的第二个域，再次中工作，这因为的 SIP 域匹配该域的前端池。* 
    
再举此例，下面的记录不起作用：
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *作为 tim@litwareinc.com 登录的用户对自动配置不起作用，因为该用户的 SIP 域 (litwareinc.com) 与池中的域 (fabrikam.com) 不匹配。* 
    
因此，既然我们知道所有，如果您需要为您 Skype 业务没有拆分式 DNS 的客户端的自动要求，必须这些选项：
  
- **组策略对象**
    
    可使用组策略对象 (GPO) 填充正确的服务器值。
    
    > [!NOTE]
    > 此选项不会启用自动配置，但可以自动化手动配置。如果使用此方法，则不需要与自动配置关联的 SRV 记录。 
  
- **匹配内部区域**
    
    您需要创建匹配外部 DNS 区域 (例如，contoso.com)，在内部 dns 区域，然后创建 DNS A （和 AAAA 如果您使用的 IPv6 寻址） 对应的业务服务器池用于自动 Skype 的记录配置。
    
    例如，如果您有用户驻留在 pool01.contoso.net，但迹象到 Skype 的业务作为 bob@contoso.com，创建名为 contoso.com，内部 DNS 区域，您需要在其中创建 DNS A （和 AAAA 如果正在使用 IPv6 寻址） 记录pool01.contoso.com。
    
- **精确内部区域**
    
    如果在内部 DNS 中创建整个区域不适合你，你可以创建与自动配置所需要的 SRV 记录对应的精确（专用）区域，并使用 dnscmd.exe 填充这些区域。由于 DNS 用户界面不支持创建精确内部区域，因此需要 Dnscmd.exe。
    
    例如，如果您的 SIP 域是 contoso.com，并且必须调用包含两个前端服务器的 pool01 前端池，将需要在您的内部 DNS 中的以下精确区域和 A 记录：
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    环境中可能还有第二个 SIP 域。这种情况下，内部 DNS 中需要以下精确区域和 A 记录：
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> 您将看到前端池 FQDN 出现两次，但有两个不同的 IP 地址。 这是因为使用 DNS 负载平衡。 如果使用 HLB 时，才会一个前端池项。 
  
> [!NOTE]
> 此外，前端池 FQDN 值之间 contoso.com 和 fabrikam.com 示例中，更改但的 IP 地址保持不变。 这是因为正在登录从任一 SIP 域的用户将自动配置为使用相同的前端池。 
  
## <a name="dns-disaster-recovery"></a>DNS 灾难恢复
<a name="DNSDR"> </a>

若要配置 DNS 以将 Skype 重定向到您的灾难恢复 （灾难恢复） 和故障转移网站的企业服务器的 web 通信，您需要使用支持 GeoDNS DNS 提供程序。 您可以设置 DNS 记录以支持灾难恢复，以便使用 web 服务的功能继续即使一个整个前端池不可用。 此 DR 功能支持自动发现、会议和拨入式简单 URL。
  
你可以在 GeoDNS 提供商处定义和配置用于 Web 服务的内部和外部解析额外的 DNS 主机 A（如果使用 IPv6，则为 AAAA）记录。以下详细信息假定池已配对，地理位置分散，且提供商支持的 GeoDNS **要么**使用循环 DNS，**要么**配置为使用 Pool1 作为主池，并且在发生通信丢失或电源故障时故障转移到 Pool2。
  
下表中的所有 DNS 记录均为示例。
  
|**GeoDNS 记录**|**池记录**|**CNAME 记录**|**DNS 设置（选择一个选项）**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com 的 Meet.contoso.com 别名  <br/> Pool2InternalWebFQDN.contoso.com 的 Meet.contoso.com 别名  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com 的 Meet.contoso.com 别名  <br/> Pool2ExternalWebFQDN.contoso.com 的 Meet.contoso.com 别名  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名  <br/> Pool2InternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名  <br/> Pool2ExternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com 的 Lyncdiscoverinternal.contoso.com 别名  <br/> Pool2InternalWebFQDN.contoso.com 的 Lyncdiscoverinternal.contoso.com 别名  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com 的 Lyncdiscover.contoso.com 别名  <br/> Pool2ExternalWebFQDN.contoso.com 的 Lyncdiscover.contoso.com 别名  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名  <br/> Pool2InternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名  <br/> Pool2ExternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
   
## <a name="dns-load-balancing"></a>DNS 负载平衡
<a name="DNSLB"> </a>

通常在应用程序级别实现 DNS 负载平衡。 应用程序 （例如，客户端运行 for Business 的 Skype），尝试连接到一个从返回的 IP 地址连接到池中的服务器的 DNS A 和 AAAA （如果使用 IPv6 寻址） 记录的池 FQDN 的查询。
  
例如，如果名为 pool01.contoso.com 的池中有三个前端服务器，以下会发生：
  
- 运行 for Business 的 Skype 的客户端 DNS 查询 pool01.contoso.com。 此查询将返回三个 IP 地址并如下方式缓存它们（按某种顺序）：
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- 客户端将尝试建立与其中一个 IP 地址的 TCP 连接。如果失败，则客户端会尝试该列表中它所缓存的下一个 IP 地址。
    
- 如果 TCP 连接成功，则客户端与 TLS 协商连接到 pool01.contoso.com 上的主注册器。
    
- 如果客户端尝试了所有缓存的条目不成功连接的情况下，用户将收到通知，任何服务器运行 Business Server Skype 此时都已可用。
    
> [!NOTE]
> 基于 DNS 的负载平衡不同于 DNS 循环 (DNS RR)，后者通常是指依靠 DNS 来提供与池中服务器对应的不同顺序的 IP 地址来进行负载平衡。通常 DNS RR 启用负载分配，但不允许启用故障转移。例如，如果无法连接到由 DNS A 和 AAAA（如果使用 IPv6 寻址）查询返回的某个 IP 地址，则连接失败。这使得，DNS RR 的可靠性不如基于 DNS 的负载平衡。如果需要，可以将 DNS RR 与基于 DNS 的负载平衡结合使用。 
  
DNS 负载平衡可用来：
  
- 负载平衡服务器到服务器到边缘服务器的 SIP。
    
- 对统一通信应用程序服务 (UCAS) 应用程序（如会议自动助理、响应组和呼叫寄存）进行负载平衡。
    
- 阻止到 UCAS 应用程序的新连接（也称为排出）。
    
- 负载平衡客户端和边缘服务器之间的所有客户端到服务器通信。
    
DNS 负载平衡不可用于：
  
- 客户端到服务器的 web 前端服务器或控制器的流量。
    
继续更深入的 DNS SRV 记录如何选择当多 DNS 记录返回查询，访问边缘服务始终选择数字优先级最低记录时，断开裁判是否需要，可使用的最大数字权重。 这是与[Internet 工程任务组文档](https://www.ietf.org/rfc/rfc2782.txt)一致。
  
例如，如果第一条 DNS SRV 记录权重为 20，优先级为 40，而第二条 DNS SRV 记录权重为 10，优先级为 50，则选择第一条记录，因为其优先级 40 更低。优先级总是最先进行比较，这是客户端首先要找的主机。优先级总是最先比较，这是首先成为客户端目标的主机。如果两个目标优先级相同该怎么办？ 
  
这种情况下，要考虑权重。优先级相同时，权重越大，被选中的可能性越大。当不作任何服务器选择时，DNS 管理员应使用权重 0。存在权重大于 0 的记录时，权重为 0 的记录被选中的机会极小。
  
那么，如果返回了优先级和权重都相同的多个 DNS SRV 记录，那又该怎么办呢？ 在这种情况下在访问边缘服务将选择它获得 DNS 服务器从第一个 SRV 记录。
  

