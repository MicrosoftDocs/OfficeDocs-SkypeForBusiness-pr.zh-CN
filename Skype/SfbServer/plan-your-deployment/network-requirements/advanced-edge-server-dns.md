---
title: 高级边缘服务器 DNS 规划为 Skype 业务服务器 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- IT_Skype16
ms.custom:
- Strat_SB_Hybrid
- Strat_SB_Hybrid
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 摘要： 查看业务服务器 2015年部署选项 Skype 的方案。 无论您想要一台服务器或更喜欢 DNS 或 HLB 的服务器池，该主题应帮助。
ms.openlocfilehash: b3c9299586856b59a8f07f7f2bcb460268c6d687
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server-2015"></a>高级边缘服务器 DNS 规划为 Skype 业务服务器 2015
 
**摘要：**回顾 Skype for Business Server 2015 部署选项的方案。无论你想要单服务器，还是偏好采用 DNS 或 HLB 的服务器池，本主题都应该有帮助。
  
说到域名系统 (DNS) 为 Skype 业务服务器 2015年计划，有可能会对您决定播放的因素很多。 如果组织的域结构已经就位，那么这可能就是考虑如何继续的问题。 我们将从下面提供的主题开始：
  
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [Split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Automatic configuration without split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Walkthrough of Skype for Business clients locating services
<a name="WalkthroughOfSkype"> </a>

业务客户端的 Skype 是类似于早期版本的 Lync 客户端如何查找和访问业务服务器 2015年在 Skype 的服务中。 本节详述服务查找过程。
  
1. lyncdiscoverinternal。\<域\>
    
     *这是内部 Web 服务上自动发现服务的 A 主机记录。* 
    
2. lyncdiscover。\<域\>
    
     *这是外部 Web 服务上自动发现服务的 A 主机记录。* 
    
3. _sipinternaltls._tcp。\<域\>
    
     *这是内部 TLS 连接的 SRV 记录。* 
    
4. _sip._tls。\<域\>
    
     *这是外部 TLS 连接的 SRV 记录。* 
    
5. sipinternal。\<域\>
    
     *这是一个前端池或控制器，可解析仅在内部网络上的主机记录。* 
    
6. sip。\<域\>
    
     *这是一个前端池或控制器，可解析仅在内部网络上的主机记录。* 
    
7. sipexternal。\<域\>
    
     *当外部客户端，这是用于访问边缘服务中，一个主机记录。* 
    
自动发现服务总是受人欢迎，因为这是服务定位的首选方法，其他方法为回退方法。
  
> [!NOTE]
> 创建 SRV 记录时，请务必记住，这些记录需要指向要在其中创建 DNS SRV 记录的同一域中的 DNS A（如果使用 IPv6 寻址，则还有 AAAA）。例如，如果 SRV 记录位于 contoso.com，则其所指向的 A（和 AAAA）记录不能在 fabrikam.com 中。 
  
如果倾向于这样做，可以设置移动设备进行手动服务发现。如果这正是你想做的，那么每个用户需要为其移动设备的设置配置内部和外部自动发现服务的完整 URI，包括协议和路径，具体如下：
  
- 允许外部访问： https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root
    
- 用于内部访问： https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root
    
我们建议使用自动发现，而不是手动发现。但是如果你要执行某种故障排除或测试，那么手动设置可能很有帮助。
  
## <a name="split-brain-dns"></a>拆分式 DNS
<a name="SplitBrainDNS"> </a>

这是一种两个 DNS 区域有相同命名空间的 DNS 配置。第一个 DNS 区域处理内部请求，而第二个 DNS 区域处理外部请求。
  
为什么公司会这样做？他们可能需要内外使用相同的命名空间，但是当然，这会导致很多 DNS SRV 和 A 记录在这个区域或那个区域是唯一的，在有重复的情况下，与这些记录关联的 IP 地址将是唯一的。
  
这带来了一些难题。 最重要的是分裂的 DNS 是**不支持**移动性。 这是因为 LyncDiscover 和 LyncDiscoverInternal DNS 记录（LyncDiscover 必须定义在外部 DNS 服务器上，而 LyncDiscoverInternal 必须定义在内部 DNS 服务器上）。
  
我们将列出的 DNS 记录的内部和外部区域，但您可以找到在边缘服务器环境要求部分的详细的示例。
  
### <a name="internal-dns"></a>内部 DNS

- 包含名为（例如）contoso.com 的 DNS 区域，内部 DNS 是该区域的权威 DNS。
    
- 这个内部 contoso.com 包含：
    
  - 前端池、 导演池或主任池的名称，和所有您的组织的网络中运行业务服务器 2015 Skype 的内部服务器，DNS A 和 （如果您使用的 IPv6 寻址） AAAA 记录。
    
  - A 和 AAAA （如果您使用的 IPv6 寻址） 的 DNS 记录您边内部接口对于每个 Skype 业务服务器 2015年边缘服务器外围网络中。
    
  - A 和 AAAA （如果您使用的 IPv6 寻址） 的 DNS 记录 （这是**可选**的反向代理服务器管理） 外围网络中的每个反向代理服务器的内部接口。
    
  - DNS A AAAA （如果您使用的 IPv6 寻址） 和内部业务服务器 2015年 （这是**可选**的） 的客户端自动配置的 Skype 的 SRV 记录。
    
  - DNS A AAAA （如果您使用的 IPv6 寻址） 或 Skype 业务服务器 2015 Web 服务 （这是**可选**的） 自动发现的 CNAME 记录。
    
- 所有您的外围网络中业务服务器 2015年内部边缘接口的 Skype 使用内部 DNS 区域到 contoso.com 解析查询。
    
- 所有服务器运行 Skype 业务服务器 2015，和客户端运行的企业网络，Skype 业务服务器 2015年都指向内部 DNS 服务器将查询解析为 contoso.com，或者 （如果使用每个边缘服务器列表 A 和 AAAA 上的主机文件您使用的 IPv6 寻址） （专门为主任或主任池 VIP、 前结束池 VIP 或标准版服务器） 的下一个跃点服务器的记录。
    
### <a name="external-dns"></a>外部 DNS

- 包含名为（例如）contoso.com 的 DNS 区域，内部 DNS 是该区域的权威 DNS。
    
- 此外部 contoso.com 包含：
    
  - DNS A 或 AAAA （如果您使用的 IPv6 寻址），CNAME 记录，Skype 的业务服务器 2015 web 服务的自动发现。 这是用于移动。
    
  - DNS A AAAA （如果您使用的 IPv6 寻址） 和 SRV 记录的边缘外部接口的每个 Skype 业务服务器 2015年边缘服务器或硬件负载平衡 (HLB) VIP 在外围网络中。
    
  - DNS A AAAA （如果您使用的 IPv6 寻址） 和 SRV 记录 (VIP 的反向代理服务器池) 的反向代理服务器的外部接口的外围网络中。
    
  - DNS A AAAA （如果您使用的 IPv6 寻址） 和 SRV 记录用于 Skype 业务服务器 2015年客户端自动配置 （**可选**）。
    
## <a name="automatic-configuration-without-split-brain-dns"></a>没有拆分式 DNS 时的自动配置
<a name="NoSplitBrainDNS"> </a>

如果您未使用 DNS 分裂，内部运行业务的 Skype 客户端自动配置不起作用，除非您使用以下解决方法之一。 为什么不进行合计？ 因为业务服务器 2015年的 Skype 要求用户的 SIP URI 匹配指定用于自动配置的前端池的域。 这还没有从 Lync Server 的早期版本进行更改。
  
所以，如果正在使用两个 SIP 域，那么需要以下 DNS SRV 记录：
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *如果用户登录为 bob@contoso.com，该记录可用于自动配置，用户的 SIP 域匹配的域中的前端池 (contoso.com)。* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *如果用户登录为 alice@fabrikam.com，此记录可用于自动配置第二个域再次由于 SIP 域匹配该域的前端池。* 
    
再举此例，下面的记录不起作用：
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *作为 tim@litwareinc.com 登录的用户对自动配置不起作用，因为该用户的 SIP 域 (litwareinc.com) 与池中的域 (fabrikam.com) 不匹配。* 
    
因此，既然我们知道了这些，如果您需要为您 Skype 业务没有分裂 DNS 的客户端的自动要求，有下列选项：
  
- **组策略对象**
    
    可使用组策略对象 (GPO) 填充正确的服务器值。
    
    > [!NOTE]
    > 此选项不会启用自动配置，但可以自动化手动配置。如果使用此方法，则不需要与自动配置关联的 SRV 记录。 
  
- **匹配内部区域**
    
    您将需要在您的内部 DNS 与外部的 DNS 区域 (如 contoso.com) 创建一个区域，然后创建 DNS A （和 AAAA 如果您使用的 IPv6 寻址） 对应于业务服务器 2015年池用于自动 Skype 的记录配置。
    
    例如，如果您有用户穴上 pool01.contoso.net，但迹象到 Skype 业务为 bob@contoso.com，创建称为 contoso.com，内部 DNS 区域，您需要在其中创建 DNS A （和 AAAA 如果使用 IPv6 寻址） 的记录pool01.contoso.com。
    
- **精确内部区域**
    
    如果在内部 DNS 中创建整个区域不适合你，你可以创建与自动配置所需要的 SRV 记录对应的精确（专用）区域，并使用 dnscmd.exe 填充这些区域。由于 DNS 用户界面不支持创建精确内部区域，因此需要 Dnscmd.exe。
    
    例如，如果您的 SIP 域 contoso.com，并且具有名为 pool01，其中包含两个前端服务器的前端池，将需要在您的内部 DNS 的针点以下区域和记录：
    
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
> 您将看到前端池的 FQDN 出现两次，但与两个不同的 IP 地址。 这是因为 DNS 负载平衡使用。 如果使用 HLB，才会单的前端池条目。 
  
> [!NOTE]
> 此外，前端池的 FQDN 值更改之间的 contoso.com 和 fabrikam.com 的示例，但 IP 地址保持不变。 这是因为从任一 SIP 域登录的用户将自动配置为使用相同的前端池。 
  
## <a name="dns-disaster-recovery"></a>DNS 灾难恢复
<a name="DNSDR"> </a>

要配置 DNS，Skype 重定向到您的灾难恢复 (DR) 和故障切换站点的业务服务器 2015 web 通信，您需要使用 DNS 支持的提供程序 GeoDNS。 您可以设置您的 DNS 记录来支持灾难恢复，这样，即使一个整个前端池出现故障，继续使用 web 服务的功能。 此 DR 功能支持自动发现、会议和拨入式简单 URL。
  
你可以在 GeoDNS 提供商处定义和配置用于 Web 服务的内部和外部解析额外的 DNS 主机 A（如果使用 IPv6，则为 AAAA）记录。以下详细信息假定池已配对，地理位置分散，且提供商支持的 GeoDNS **要么**使用循环 DNS，**要么**配置为使用 Pool1 作为主池，并且在发生通信丢失或电源故障时故障转移到 Pool2。
  
下表中的所有 DNS 记录均为示例。
  
|**GeoDNS 记录**|**池的记录**|**CNAME 记录**|**（选择一个选项） 的 DNS 设置**|
|:-----|:-----|:-----|:-----|
|符合 int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com 的 Meet.contoso.com 别名  <br/> Pool2InternalWebFQDN.contoso.com 的 Meet.contoso.com 别名  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|符合 ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com 的 Meet.contoso.com 别名  <br/> Pool2ExternalWebFQDN.contoso.com 的 Meet.contoso.com 别名  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|拨入 int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名  <br/> Pool2InternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|拨入 ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名  <br/> Pool2ExternalWebFQDN.contoso.com 的 Dialin.contoso.com 别名  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|Lyncdiscoverint int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com 的 Lyncdiscoverinternal.contoso.com 别名  <br/> Pool2InternalWebFQDN.contoso.com 的 Lyncdiscoverinternal.contoso.com 别名  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|Lyncdiscover ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com 的 Lyncdiscover.contoso.com 别名  <br/> Pool2ExternalWebFQDN.contoso.com 的 Lyncdiscover.contoso.com 别名  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|计划程序-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名  <br/> Pool2InternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
|计划程序-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名  <br/> Pool2ExternalWebFQDN.contoso.com 的 Scheduler.contoso.com 别名  <br/> |在池之间启用循环  <br/> **或者** <br/> 使用主池，发生故障时连接到副池  <br/> |
   
## <a name="dns-load-balancing"></a>DNS 负载平衡
<a name="DNSLB"> </a>

通常在应用程序级别实现 DNS 负载平衡。 应用程序 （例如，客户端运行业务的 Skype），试图通过连接到其中一个从返回的 IP 地址连接到池中的服务器的 DNS A 和 （如果使用 IPv6 寻址） AAAA 记录池的 FQDN 的查询。
  
例如，如果名为 pool01.contoso.com 的池有三个前端服务器，以下会发生这种情况：
  
- 运行业务的 Skype 客户端向 DNS 查询 pool01.contoso.com。查询返回三个 IP 地址，并将其缓存，如下所示 （按某种顺序）：
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- 客户端将尝试建立与其中一个 IP 地址的 TCP 连接。如果失败，则客户端会尝试该列表中它所缓存的下一个 IP 地址。
    
- 如果 TCP 连接成功，则客户端与 TLS 协商连接到 pool01.contoso.com 上的主注册器。
    
- 如果客户端会尝试不成功的连接的所有缓存的项，用户将收到通知，目前没有运行业务服务器 2015 Skype 的服务器都可用。
    
> [!NOTE]
> 基于 DNS 的负载平衡不同于 DNS 循环 (DNS RR)，后者通常是指依靠 DNS 来提供与池中服务器对应的不同顺序的 IP 地址来进行负载平衡。通常 DNS RR 启用负载分配，但不允许启用故障转移。例如，如果无法连接到由 DNS A 和 AAAA（如果使用 IPv6 寻址）查询返回的某个 IP 地址，则连接失败。这使得，DNS RR 的可靠性不如基于 DNS 的负载平衡。如果需要，可以将 DNS RR 与基于 DNS 的负载平衡结合使用。 
  
DNS 负载平衡可用来：
  
- 负载平衡服务器到服务器到边缘服务器的 SIP。
    
- 对统一通信应用程序服务 (UCAS) 应用程序（如会议自动助理、响应组和呼叫寄存）进行负载平衡。
    
- 阻止到 UCAS 应用程序的新连接（也称为排出）。
    
- 负载平衡客户端和边缘服务器之间的所有客户端-服务器通信。
    
DNS 负载平衡不可用于：
  
- 客户端到服务器的 web 通信到您前端服务器或导演。
    
继续更深入的 DNS SRV 记录如何选择当多个 DNS 记录返回的查询访问边缘服务始终选择数字优先级最低的记录时，决胜局时，需要最大数值的重量。 这是与[Internet 工程任务组文档](https://www.ietf.org/rfc/rfc2782.txt)保持一致。
  
例如，如果第一条 DNS SRV 记录权重为 20，优先级为 40，而第二条 DNS SRV 记录权重为 10，优先级为 50，则选择第一条记录，因为其优先级 40 更低。优先级总是最先进行比较，这是客户端首先要找的主机。优先级总是最先比较，这是首先成为客户端目标的主机。如果两个目标优先级相同该怎么办？ 
  
这种情况下，要考虑权重。优先级相同时，权重越大，被选中的可能性越大。当不作任何服务器选择时，DNS 管理员应使用权重 0。存在权重大于 0 的记录时，权重为 0 的记录被选中的机会极小。
  
那么，如果返回了优先级和权重都相同的多个 DNS SRV 记录，那又该怎么办呢？ 在此情况下访问边缘服务将选择它有 DNS 服务器从第一个的 SRV 记录。
  

