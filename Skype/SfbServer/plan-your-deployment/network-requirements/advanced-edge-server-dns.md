---
title: 高级边缘服务器 DNS 规划Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
audience: ITPro
manager: serdars
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 查看部署选项Skype for Business Server方案。 无论是希望使用单个服务器，还是首选具有 DNS 或 HLB 的服务器池，本主题都应有所帮助。
ms.openlocfilehash: 2c9ea99ae8f5ae7c6151dc337bd5571d739ff549
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844105"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>高级边缘服务器 DNS 规划Skype for Business Server
 
**摘要：** 查看部署选项Skype for Business Server方案。 无论是希望使用单个服务器，还是首选具有 DNS 或 HLB 的服务器池，本主题都应有所帮助。
  
对于域名系统 (DNS) 规划Skype for Business Server，你的决策可能涉及许多因素。 如果组织的域结构已就位，这可能就是查看如何继续的问题。 我们将从以下主题开始：
  
- [客户端定位Skype for Business的演练](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [拆分式 DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [无拆分式 DNS 的自动配置](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS 灾难恢复](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing － DNS 负载平衡](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>客户端定位Skype for Business的演练
<a name="WalkthroughOfSkype"> </a>

Skype for Business客户端在客户端中查找和访问服务的方式与以前版本的 Lync 客户端Skype for Business Server。 本节详细介绍服务器位置过程。
  
1. lyncdiscoverinternal。\<domain\>
    
     *这是内部 Web 服务上的自动发现服务的 A 主机记录。* 
    
2. lyncdiscover。\<domain\>
    
     *这是外部 Web 服务上的自动发现服务的 A 主机记录。* 
    
3. _sipinternaltls._tcp。\<domain\>
    
     *这是内部 TLS 连接的 SRV 记录。* 
    
4. _sip._tls。\<domain\>
    
     *这是外部 TLS 连接的 SRV 记录。* 
    
5. sipinternal。\<domain\>
    
     *这是前端池或控制器的 A 主机记录，只能在内部网络上进行解决。* 
    
6. sip。\<domain\>
    
     *这是前端池或控制器的 A 主机记录，只能在内部网络上进行解决。* 
    
7. sipexternal。\<domain\>
    
     *当客户端位于外部时，这是访问边缘服务的 A 主机记录。* 
    
自动发现服务始终受支持，因为这是服务位置的首选方法，其他方法为回退方法。
  
> [!NOTE]
> 在创建 SRV 记录时，必须记住，如果使用创建 DNS SRV 记录的同一域中的 IPv6 寻址) ，需要指向 DNS A (和 AAAA。 例如，如果 SRV 记录在 contoso.com 中，则它指向的 A (和 AAAA) 记录不能 fabrikam.com。 
  
如果你倾向于这样做，你可以将移动设备设置为手动发现服务。 如果你希望这样做，每个用户都需要使用完整的内部和外部自动发现服务 URI（包括协议和路径）配置其移动设备设置，如下所示：
  
- 对于外部访问：https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root
    
- 对于内部访问：https:// \<IntPoolFQDN\> /AutoDiscover/AutoDiscover.svc/Root
    
我们建议你使用自动发现，而不是手动发现。 但是，如果你要执行一些疑难解答或测试，手动设置可能会很有帮助。
  
## <a name="split-brain-dns"></a>拆分式 DNS
<a name="SplitBrainDNS"> </a>

这是一个 DNS 配置，其中两个 DNS 区域具有相同的命名空间。 第一个 DNS 区域处理内部请求，第二个 DNS 区域处理外部请求。
  
为什么公司会这样做？ 他们可能需要在内部和外部使用相同的命名空间，但当然，这可能会导致许多 DNS SRV 和 A 记录对一个区域或另一个区域是唯一的，如果重复，则与这些记录关联的 IP 地址将是唯一的。
  
这种情况带来了一些挑战。 最重要的是，移动功能不支持 **拆分式** DNS。 这是因为 LyncDiscover 和 LyncDiscoverInternal DNS 记录 (LyncDiscover 必须定义在外部 DNS 服务器上，而 LyncDiscoverInternal 必须定义在内部 DNS) 。
  
我们将在此处列出内部和外部区域 DNS 记录，但您可以在边缘服务器环境要求部分找到详细示例。
  
### <a name="internal-dns"></a>内部 DNS

- 包含名为 dns 区域 (例如) contoso.com，它的权威 DNS 区域。
    
- 此内部 contoso.com 包含：
    
  - 如果对前端池、控制器池或控制器池名称以及组织网络中运行 Skype for Business Server 的所有内部服务器使用 IPv6 寻址) 记录，则 DNS A 和 AAA (A 为 DNS A 和 AAAA。
    
  - 如果为外围网络中 (边缘服务器的边缘内部接口使用 IPv6 寻址) 记录，则 DNS A 和 AAAA Skype for Business Server。
    
  - DNS A 和 AAAA (如果你为外围网络 (中每台反向代理服务器的内部接口使用 IPv6 寻址) 记录 (则对于反向代理服务的管理是可选的) 。
    
  - 如果使用 IPv6 寻址) 和 SRV 记录进行内部 Skype for Business Server 客户端自动配置 (则使用 DNS A 和 AAA (A (（可选) ）。
    
  - DNS A 和 AAAA (如果使用 IPv6 寻址) 或 CNAME 记录自动发现 Skype for Business Server Web 服务 (可选 **) 。**
    
- 外围Skype for Business Server中所有内部边缘接口均使用此内部 DNS 区域解析 contoso.com。
    
- 所有运行 Skype for Business Server 的服务器和在企业网络中运行 Skype for Business Server 的客户端指向内部 DNS 服务器以解析对 contoso.com 的查询，或者，如果使用 IPv6 寻址下一跃点服务器 (（专门针对控制器或目录）使用 IPv6 寻址) 记录，则它们在每个边缘服务器上使用主机文件并列出 A 和 AAAA (ctor 池 VIP、前端池 VIP 或 Standard Edition 服务器) 。
    
### <a name="external-dns"></a>外部 DNS

- 包含名为 dns 区域 (例如) contoso.com，它的权威 DNS 区域。
    
- 此外部 contoso.com 包含：
    
  - DNS A 和 AAAA (如果使用 IPv6 寻址) 或 CNAME 记录，则用于自动发现 Skype for Business Server Web 服务。 这适用于移动性。
    
  - 如果对外围网络中每台 Skype for Business Server 边缘服务器的边缘外部接口或硬件负载平衡 (HLB) VIP 使用 IPv6 寻址) 和 SRV 记录，则 DNS A 和 AAAA (。
    
  - DNS A 和 AAAA (如果使用 IPv6 寻址) 和 SRV 记录用于外围网络中反向代理服务器) 池的反向代理服务器的外部接口或 (VIP。
    
  - DNS A 和 AAAA (如果使用 IPv6 寻址) 和 SRV 记录进行 Skype for Business Server 客户端自动配置 (**可选) 。**
    
## <a name="automatic-configuration-without-split-brain-dns"></a>无拆分式 DNS 的自动配置
<a name="NoSplitBrainDNS"> </a>

如果不使用拆分式 DNS，则运行 Skype for Business 的客户端的内部自动配置将不起作用，除非你使用的是我们在此处使用的解决方法之一。 这是为什么？ 由于Skype for Business Server要求用户的 SIP URI 与为自动配置指定的前端池的域相匹配。 这一点与早期版本的 Lync Server 没有变化。
  
因此，如果您有两个 SIP 域在使用中，则需要以下 DNS SRV 记录：
  
- _sipinternaltls._tcp.contoso.com。 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *如果用户以 bob@contoso.com 登录，则此记录适用于自动配置，因为用户的 SIP 域与前端池的域 (contoso.com) 。* 
    
- _sipinternaltls._tcp.fabrikam.com。 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *如果用户以用户 alice@fabrikam.com 登录，此记录适用于第二个域的自动配置，同样，因为 SIP 域与该域的前端池匹配。* 
    
若要进一步说明示例，此操作将不起作用：
  
- _sipinternaltls._tcp.litwareinc.com。 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *用户以 tim@litwareinc.com 登录对自动配置不起作用，因为他们的 SIP (litwareinc.com) 与池中的域不匹配 (fabrikam.com) 。* 
    
现在，我们已经了解所有这些信息，如果需要自动要求无拆分式 DNS 的 Skype for Business 客户端，则有以下选项：
  
- **组策略对象**
    
    可以使用组策略对象 (GPO) 填充正确的服务器值。
    
    > [!NOTE]
    > 此选项不会启用自动配置，但它确实可以自动执行手动配置。 如果使用此方法，则不需要与自动配置关联的 SRV 记录。 
  
- **匹配内部区域**
    
    您需要在内部 DNS 中创建一个与外部 DNS 区域 (（例如 contoso.com) ）相匹配的区域，然后使用与用于自动配置的 Skype for Business Server 池相对应的 IPv6 寻址) 记录，然后创建 DNS A (和 AAAA。
    
    例如，如果你的用户托管在 pool01.contoso.net 上，但以 bob@contoso.com 登录 Skype for Business，请创建名为 contoso.com 的内部 DNS 区域，如果在 pool01.contoso.com 使用 IPv6 寻址的) 记录，则需要在内部创建 DNS A (和 AAAA。
    
- **固定点内部区域**
    
    如果无法选择在内部 DNS 中创建整个区域，可以创建与自动配置所需的 SRV 记录对应的 pin-point (专用) 区域，并使用 dnscmd.exe 填充这些区域。 Dnscmd.exe，因为 DNS 用户界面不支持创建 pin-point 区域。
    
    例如，如果您的 SIP 域是 contoso.com，并且您的前端池名为 pool01，其中包含两台前端服务器，则需要在内部 DNS 中具有以下 pin-point 区域和 A 记录：
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    环境中可能有第二个 SIP 域。 在这种情况下，内部 DNS 中需要以下 pin-point 区域和 A 记录：
    
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
> 你将看到前端池 FQDN 出现两次，但显示两个不同的 IP 地址。 这是因为使用了 DNS 负载平衡。 如果使用 HLB，则只有一个前端池条目。 
  
> [!NOTE]
> 此外，前端池 FQDN 值在 contoso.com 和 fabrikam.com 示例中更改，但 IP 地址保持不变。 这是因为从任一 SIP 域登录的用户将使用相同的前端池进行自动配置。 
  
## <a name="dns-disaster-recovery"></a>DNS 灾难恢复
<a name="DNSDR"> </a>

若要将 DNS 配置为Skype for Business Server Web 流量重定向到灾难恢复 (DR) 和故障转移网站，您需要使用支持 GeoDNS 的 DNS 提供程序。 您可以将 DNS 记录设置为支持灾难恢复，以便即使整个前端池关闭，使用 Web 服务的功能也将继续。 此 DR 功能支持自动发现、会议和拨入简单 URL。
  
如果在 GeoDNS 提供程序上为 Web 服务的内部和外部解析) IPv6 记录，则定义和配置其他 DNS 主机 (A 或 AAAA。 以下详细信息假定池已配对，地理位置分散，且您的提供商支持的 GeoDNS 要么具有循环 **DNS，** 要么配置为使用 Pool1 作为主池，并且在任何通信丢失或电源故障时将故障转网到 Pool2。
  
此表中的所有 DNS 记录都是示例。
  
|**GeoDNS 记录**|**池记录**|**CNAME 记录**|**DNS 设置 (选择一个选项)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com 别名 Pool1InternalWebFQDN.contoso.com  <br/> Meet.contoso.com 别名 Pool2InternalWebFQDN.contoso.com  <br/> |池之间的循环  <br/> **OR** <br/> 使用主服务器，如果发生故障，请连接到辅助服务器  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com 别名 Pool1ExternalWebFQDN.contoso.com  <br/> Meet.contoso.com 别名 Pool2ExternalWebFQDN.contoso.com  <br/> |池之间的循环  <br/> **OR** <br/> 使用主服务器，如果发生故障，请连接到辅助服务器  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com 别名 Pool1InternalWebFQDN.contoso.com  <br/> Dialin.contoso.com 别名 Pool2InternalWebFQDN.contoso.com  <br/> |池之间的循环  <br/> **OR** <br/> 使用主服务器，如果发生故障，请连接到辅助服务器  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com 别名 Pool1ExternalWebFQDN.contoso.com  <br/> Dialin.contoso.com 别名 Pool2ExternalWebFQDN.contoso.com  <br/> |池之间的循环  <br/> **OR** <br/> 使用主服务器，如果发生故障，请连接到辅助服务器  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Lyncdiscoverinternal.contoso.com 别名 Pool1InternalWebFQDN.contoso.com  <br/> Lyncdiscoverinternal.contoso.com 别名 Pool2InternalWebFQDN.contoso.com  <br/> |池之间的循环  <br/> **OR** <br/> 使用主服务器，如果发生故障，请连接到辅助服务器  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Lyncdiscover.contoso.com 别名 Pool1ExternalWebFQDN.contoso.com  <br/> Lyncdiscover.contoso.com 别名 Pool2ExternalWebFQDN.contoso.com  <br/> |池之间的循环  <br/> **OR** <br/> 使用主服务器，如果发生故障，请连接到辅助服务器  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com 别名 Pool1InternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com 别名 Pool2InternalWebFQDN.contoso.com  <br/> |池之间的循环  <br/> **OR** <br/> 使用主服务器，如果发生故障，请连接到辅助服务器  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com 别名 Pool1ExternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com 别名 Pool2ExternalWebFQDN.contoso.com  <br/> |池之间的循环  <br/> **OR** <br/> 使用主服务器，如果发生故障，请连接到辅助服务器  <br/> |
   
## <a name="dns-load-balancing"></a>DNS load balancing － DNS 负载平衡
<a name="DNSLB"> </a>

DNS 负载平衡通常在应用程序级别实现。 应用程序 (例如，运行 Skype for Business) 的客户端，如果对池 FQDN 使用) 记录查询，则通过连接到从 DNS A 和 AAAA (返回的 IP 地址之一来尝试连接到池中的服务器。
  
例如，如果名为 pool01.contoso.com 的池中有三台前端服务器，则会发生以下情况：
  
- 运行 dns 的Skype for Business查询 DNS pool01.contoso.com。 查询返回三个 IP 地址，并按以下 (以某种顺序缓存它们) ：
    
   |&nbsp;|&nbsp;|
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- 客户端尝试建立到其中一个 IP 地址的 TCP 连接。 如果失败，它将尝试从该列表缓存的下一个 IP 地址。
    
- 如果 TCP 连接成功，客户端将协商 TLS 以连接到 pool01.contoso.com。
    
- 如果客户端在未成功连接的情况下尝试所有缓存的条目，则用户将收到一条通知，Skype for Business Server当前没有可用的服务器。
    
> [!NOTE]
> 基于 DNS 的负载平衡不同于 DNS 轮循机制 (DNS RR) ，DNS RR) 通常是指通过依赖 DNS 为池中的服务器提供不同的 IP 地址顺序来实现负载平衡。 通常，DNS RR 会启用负载分布，但不允许您启用故障转移。 例如，如果与 DNS A 或 AAAA 在 IPv6 方案中返回的一个 IP 地址 (或 AAAA 的连接) 查询失败，该连接将失败。 这使得 DNS RR 的可靠性低于基于 DNS 的负载平衡。 如果需要，您仍可以将 DNS RR 与基于 DNS 的负载平衡结合使用。 
  
DNS 负载平衡用于：
  
- 负载平衡服务器到服务器 SIP 到边缘服务器。
    
- 负载平衡 统一通信应用程序服务 (一) 应用程序，如会议自动助理、响应组和呼叫应答。
    
- 阻止与 一些 一 (一起的新连接，也称为排出) 。
    
- 负载平衡客户端和边缘服务器之间的所有客户端到服务器流量。
    
DNS 负载平衡不能用于：
  
- 到前端服务器或控制器的客户端到服务器 Web 流量。
    
为了进一步深入探讨当查询返回多个 DNS 记录时如何选择 DNS SRV 记录，访问边缘服务始终选取数字优先级最低的记录，如果需要分线，则选择数字权重最高的记录。 这一点与 [Internet 工程任务组文档一致](https://www.ietf.org/rfc/rfc2782.txt)。
  
例如，如果第一条 DNS SRV 记录的权重为 20，优先级为 40，第二条 DNS SRV 记录的权重为 10，优先级为 50，则选择第一条记录，因为它的优先级为 40。 优先级始终优先，这是客户端首先面向的主机。 如果存在两个优先级相同的目标，该做什么？ 
  
在这种情况下，需要考虑权重。 在这种情况下，权重越大，被选中的可能性越大。 当没有任何服务器选择时，DNS 管理员应使用权重 0。 当存在权重大于 0 的记录时，权重为 0 的记录被选中的可能性很小。
  
那么，如果返回多个优先级和权重相同的 DNS SRV 记录，会发生什么情况？ 在这种情况下，访问边缘服务将选择它首先从 DNS 服务器获取的 SRV 记录。
  

