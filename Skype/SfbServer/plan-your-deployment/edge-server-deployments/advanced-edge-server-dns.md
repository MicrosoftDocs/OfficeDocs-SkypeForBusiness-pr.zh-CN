---
title: Skype for Business Server 的高级边缘服务器 DNS 规划
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 摘要：查看 Skype for business 服务器部署选项的方案。 无论您是需要单个服务器，还是希望使用 DNS 或 HLB 的服务器池，本主题都应有所帮助。
ms.openlocfilehash: c1a5cc793cde46c1334d88dfcbd430922f0b7c32
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887641"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>Skype for Business Server 的高级边缘服务器 DNS 规划
 
**摘要：** 查看 Skype for business 服务器部署选项的方案。 无论您是需要单个服务器，还是希望使用 DNS 或 HLB 的服务器池，本主题都应有所帮助。
  
当需要为 Skype for business 服务器规划域名系统（DNS）时，有许多因素可能会在你的决策中发挥作用。 如果组织的域结构已经就位，那么这可能就是考虑如何继续的问题。 我们将从下面提供的主题开始：
  
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [Split-brain DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Automatic configuration without split-brain DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS disaster recovery](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Walkthrough of Skype for Business clients locating services
<a name="WalkthroughOfSkype"> </a>

Skype for business 客户端与以前版本的 Lync 客户端类似于他们在 Skype for Business 服务器中查找和访问服务的方式。 本节详述服务查找过程。
  
1. lyncdiscoverinternal.\<域\>
    
     *这是内部 Web 服务上自动发现服务的 A 主机记录。* 
    
2. lyncdiscover.\<域\>
    
     *这是外部 Web 服务上自动发现服务的 A 主机记录。* 
    
3. _sipinternaltls _tcp。\<域\>
    
     *这是内部 TLS 连接的 SRV 记录。* 
    
4. _sip _tls。\<域\>
    
     *这是外部 TLS 连接的 SRV 记录。* 
    
5. sipinternal.\<域\>
    
     *这是前端池或控制器的主机记录，仅可在内部网络上解析。* 
    
6. sip.\<域\>
    
     *这是前端池或控制器的主机记录，仅可在内部网络上解析。* 
    
7. sipexternal.\<域\>
    
     *这是当客户端为外部客户端时，用于访问边缘服务的主机记录。* 
    
自动发现服务总是受人欢迎，因为这是服务定位的首选方法，其他方法为回退方法。
  
> [!NOTE]
> 创建 SRV 记录时，请务必记住，这些记录需要指向要在其中创建 DNS SRV 记录的同一域中的 DNS A（如果使用 IPv6 寻址，则还有 AAAA）。例如，如果 SRV 记录位于 contoso.com，则其所指向的 A（和 AAAA）记录不能在 fabrikam.com 中。 
  
如果倾向于这样做，可以设置移动设备进行手动服务发现。如果这正是你想做的，那么每个用户需要为其移动设备的设置配置内部和外部自动发现服务的完整 URI，包括协议和路径，具体如下：
  
- 对于外部访问： https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root
    
- 对于内部访问： https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root
    
我们建议使用自动发现，而不是手动发现。但是如果你要执行某种故障排除或测试，那么手动设置可能很有帮助。
  
## <a name="split-brain-dns"></a>拆分式 DNS
<a name="SplitBrainDNS"> </a>

这是一种两个 DNS 区域有相同命名空间的 DNS 配置。第一个 DNS 区域处理内部请求，而第二个 DNS 区域处理外部请求。
  
为什么公司会这样做？他们可能需要内外使用相同的命名空间，但是当然，这会导致很多 DNS SRV 和 A 记录在这个区域或那个区域是唯一的，在有重复的情况下，与这些记录关联的 IP 地址将是唯一的。
  
这带来了一些难题。 最重要的是，**不支持**移动性的分裂 DNS。 这是因为 LyncDiscover 和 LyncDiscoverInternal DNS 记录（LyncDiscover 必须定义在外部 DNS 服务器上，而 LyncDiscoverInternal 必须定义在内部 DNS 服务器上）。
  
我们将在此处列出内部和外部区域的 DNS 记录，但你可以在 "边缘服务器环境要求" 部分中找到详细示例。
  
### <a name="internal-dns"></a>内部 DNS

- 包含名为（例如）contoso.com 的 DNS 区域，内部 DNS 是该区域的权威 DNS。
    
- 这个内部 contoso.com 包含：
    
  - DNS A 和 AAAA （如果正在使用 IPv6 寻址）你的前端池、控制器池或控制器池名称的记录，以及组织网络中运行 Skype for Business 服务器的所有内部服务器。
    
  - DNS A 和 AAAA （如果你正在为外围网络中的每个 Skype for Business Server Edge 服务器使用 IPv6 寻址）记录。
    
  - DNS A 和 AAAA （如果你正在使用 IPv6 寻址）你的外围网络中每个反向代理服务器的内部接口的记录（这对于对反向代理的管理是**可选**的）。
    
  - DNS A 和 AAAA （如果正在使用 IPv6 寻址）和用于内部 Skype for Business 服务器客户端自动配置的 SRV 记录（**可选**）。
    
  - DNS A 和 AAAA （如果你使用 IPv6 寻址）或用于自动发现 Skype for business Server Web 服务的 CNAME 记录（**可选**）。
    
- 您的外围网络中的所有 Skype for Business 服务器内部边缘接口都使用此内部 DNS 区域将查询解析到 contoso.com。
    
- 运行 Skype for Business 服务器的所有服务器以及运行企业网络中 Skype for business 服务器的客户端，指向内部 DNS 服务器以将查询解析到 contoso.com，或者使用每台边缘服务器上的主机文件和列表 A 和 AAAA （如果使用的是IPv6 寻址）下一个跃点服务器（专用于 Director 或 Director pool VIP、前端池 VIP 或标准版服务器）的记录。
    
### <a name="external-dns"></a>外部 DNS

- 包含名为（例如）contoso.com 的 DNS 区域，内部 DNS 是该区域的权威 DNS。
    
- 此外部 contoso.com 包含：
    
  - DNS A 和 AAAA （如果正在使用 IPv6 寻址）或 CNAME 记录，用于自动发现 Skype for business Server web 服务。 这供移动使用。
    
  - DNS A 和 AAAA （如果正在使用 IPv6 寻址）和适用于外围网络中每个 Skype for Business 服务器边缘服务器或硬件负载平衡（HLB） VIP 的边缘外部接口的 SRV 记录。
    
  - DNS A 和 AAAA （如果你正在使用 IPv6 寻址）和针对反向代理服务器的外部接口的 SRV 记录，或者是在外围网络中（反向代理服务器的 VIP）的 SRV 记录。
    
  - DNS A 和 AAAA （如果您使用的是 IPv6 寻址）和 Skype for business 服务器客户端自动配置的 SRV 记录（**可选**）。
    
## <a name="automatic-configuration-without-split-brain-dns"></a>没有拆分式 DNS 时的自动配置
<a name="NoSplitBrainDNS"> </a>

如果不使用 "分裂大脑" DNS，则运行 Skype for Business 的客户的内部自动配置将不起作用，除非你使用我们的其中一种解决方法。 为什么会不起作用？ 由于 Skype for Business 服务器要求用户的 SIP URI 与为自动配置指定的前端池的域匹配。 此操作未从早期版本的 Lync Server 更改。
  
所以，如果正在使用两个 SIP 域，那么需要以下 DNS SRV 记录：
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *如果用户以 bob@contoso.com 的形式登录，此记录将适用于自动配置，因为用户的 SIP 域与前端池（contoso.com）的域相匹配。* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *如果用户以 alice@fabrikam.com 的形式登录，则该记录将可用于自动配置第二个域，因为 SIP 域匹配该域的前端池。* 
    
再举此例，下面的记录不起作用：
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *作为 tim@litwareinc.com 登录的用户对自动配置不起作用，因为该用户的 SIP 域 (litwareinc.com) 与池中的域 (fabrikam.com) 不匹配。* 
    
现在，我们知道，如果你需要对 Skype for Business 客户端的自动要求而不使用分裂的 DNS，则可以使用以下选项：
  
- **组策略对象**
    
    可使用组策略对象 (GPO) 填充正确的服务器值。
    
    > [!NOTE]
    > 此选项不会启用自动配置，但可以自动化手动配置。如果使用此方法，则不需要与自动配置关联的 SRV 记录。 
  
- **匹配内部区域**
    
    你需要在内部 DNS 中创建一个与你的外部 DNS 区域（例如，contoso.com）匹配的区域，然后创建 DNS A （如果使用 IPv6 寻址，则为 AAAA）与用于自动的 Skype for business 服务器池相对应的记录配置.
    
    例如，如果你有一个用户驻留在 pool01.contoso.net 上，但登录 Skype for business 的 bob@contoso.com，请创建名为 contoso.com 的内部 DNS 区域，并在其中创建一个名为 pool01.contoso.com 的 DNS A （如果使用 IPv6 寻址的 AAAA）记录。
    
- **精确内部区域**
    
    如果在内部 DNS 中创建整个区域不适合你，你可以创建与自动配置所需要的 SRV 记录对应的精确（专用）区域，并使用 dnscmd.exe 填充这些区域。由于 DNS 用户界面不支持创建精确内部区域，因此需要 Dnscmd.exe。
    
    例如，如果你的 SIP 域是 contoso.com，而你有一个名为 pool01 的前端池，其中包含两个前端服务器，则你需要在内部 DNS 中具有以下 pin 点区域和记录：
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    环境中可能还有第二个 SIP 域。这种情况下，内部 DNS 中需要以下精确区域和 A 记录：
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> 你将看到前端池 FQDN 出现两次，但具有两个不同的 IP 地址。 这是因为使用了 DNS 负载平衡。 如果使用 HLB，则只能有一个前端池条目。 
  
> [!NOTE]
> 此外，前端池 FQDN 值在 contoso.com 和 fabrikam.com 示例之间更改，但 IP 地址保持不变。 这是因为从任一 SIP 域登录的用户都将使用相同的前端池进行自动配置。 
  
## <a name="dns-disaster-recovery"></a>DNS 灾难恢复
<a name="DNSDR"> </a>

若要将 DNS 配置为将 Skype for Business 服务器 web 流量重定向到灾难恢复（DR）和故障转移站点，需要使用支持 GeoDNS 的 DNS 提供程序。 你可以将 DNS 记录设置为支持灾难恢复，以便使用 web 服务的功能即使在一个完整的前端池停止时也会继续。 此 DR 功能支持自动发现、会议和拨入式简单 URL。
  
你可以在 GeoDNS 提供商处定义和配置用于 Web 服务的内部和外部解析额外的 DNS 主机 A（如果使用 IPv6，则为 AAAA）记录。以下详细信息假定池已配对，地理位置分散，且提供商支持的 GeoDNS **要么**使用循环 DNS，**要么**配置为使用 Pool1 作为主池，并且在发生通信丢失或电源故障时故障转移到 Pool2。
  
下表中的所有 DNS 记录均为示例。
  
|**GeoDNS 记录**|**池记录**|**CNAME 记录**|**DNS 设置（选择一个选项）**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com 至 Meet-int.geolb.contoso.com  <br/>   <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com 至 Meet-ext.geolb.contoso.com  <br/>   <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com 至 Meet-int.geolb.contoso.com   <br/>  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com 至 Meet-ext.geolb.contoso.com  <br/>  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com 至 Meet-int.geolb.contoso.com   <br/>   <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com 至 Meet-ext.geolb.contoso.com  <br/>  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com 至 Meet-int.geolb.contoso.com   <br/>  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com 至 Meet-ext.geolb.contoso.com   <br/>  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
   
## <a name="dns-load-balancing"></a>DNS 负载平衡
<a name="DNSLB"> </a>

通常在应用程序级别实现 DNS 负载平衡。 应用程序（例如，运行 Skype for Business 的客户端）通过连接到池 FQDN 的 DNS A 和 AAAA （如果使用 IPv6 寻址）记录查询来连接到池中的某个 IP 地址，尝试连接到池中的服务器。
  
例如，如果一个名为 pool01.contoso.com 的池中有三个前端服务器，则会发生以下情况：
  
- 运行 Skype for business 的 pool01.contoso.com 的客户端查询 DNS。 此查询将返回三个 IP 地址并如下方式缓存它们（按某种顺序）：
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- 客户端将尝试建立与其中一个 IP 地址的 TCP 连接。如果失败，则客户端会尝试该列表中它所缓存的下一个 IP 地址。
    
- 如果 TCP 连接成功，则客户端与 TLS 协商连接到 pool01.contoso.com 上的主注册器。
    
- 如果客户在未成功连接的情况下尝试所有缓存的条目，用户此时将收到一条通知，表明当前没有运行 Skype for business 服务器的服务器可用。
    
> [!NOTE]
> 基于 DNS 的负载平衡不同于 DNS 循环 (DNS RR)，后者通常是指依靠 DNS 来提供与池中服务器对应的不同顺序的 IP 地址来进行负载平衡。通常 DNS RR 启用负载分配，但不允许启用故障转移。例如，如果无法连接到由 DNS A 和 AAAA（如果使用 IPv6 寻址）查询返回的某个 IP 地址，则连接失败。这使得，DNS RR 的可靠性不如基于 DNS 的负载平衡。如果需要，可以将 DNS RR 与基于 DNS 的负载平衡结合使用。 
  
DNS 负载平衡可用来：
  
- 将服务器到服务器 SIP 的负载平衡到边缘服务器。
    
- 对统一通信应用程序服务 (UCAS) 应用程序（如会议自动助理、响应组和呼叫寄存）进行负载平衡。
    
- 阻止到 UCAS 应用程序的新连接（也称为排出）。
    
- 在客户端和边缘服务器之间对所有客户端到服务器的通信进行负载平衡。
    
DNS 负载平衡不可用于：
  
- 与您的前端服务器或 Director 的客户端到服务器 web 流量。
    
若要更深入地了解查询返回 mutiple DNS 记录时如何选择 DNS SRV 记录，Access Edge 服务始终使用最低的数值优先级选择记录，并且如果需要断字符，则使用最高的数字权重。 这与[Internet 工程任务组文档](https://www.ietf.org/rfc/rfc2782.txt)一致。
  
例如，如果第一条 DNS SRV 记录权重为 20，优先级为 40，而第二条 DNS SRV 记录权重为 10，优先级为 50，则选择第一条记录，因为其优先级 40 更低。优先级总是最先进行比较，这是客户端首先要找的主机。优先级总是最先比较，这是首先成为客户端目标的主机。如果两个目标优先级相同该怎么办？ 
  
这种情况下，要考虑权重。优先级相同时，权重越大，被选中的可能性越大。当不作任何服务器选择时，DNS 管理员应使用权重 0。存在权重大于 0 的记录时，权重为 0 的记录被选中的机会极小。
  
那么，如果返回了优先级和权重都相同的多个 DNS SRV 记录，那又该怎么办呢？ 在这种情况下，Access Edge 服务将选择它首先从 DNS 服务器获取的 SRV 记录。
  

