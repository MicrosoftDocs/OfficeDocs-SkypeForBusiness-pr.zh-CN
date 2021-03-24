---
title: Skype for Business 的负载平衡要求
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 摘要：实施 Skype for Business Server 之前，请查看负载平衡注意事项。
ms.openlocfilehash: 7a3851b73443db6be12ef2fd1a875b034eafff74
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095006"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a>Skype for Business 的负载平衡要求
 
**摘要：** 在实施 Skype for Business Server 之前，请查看负载平衡注意事项。
  
负载平衡在池中的服务器之间分布流量。 如果您有前端池、中介服务器池或边缘服务器池，则需要为这些池部署负载平衡。
  
Skype for Business Server 支持两种类型的客户端到服务器流量负载平衡解决方案：域名系统 (DNS) 负载平衡和硬件负载平衡 (通常缩写为 HLB) 。 DNS 负载平衡具有多项优势，包括更简单的管理、更高效的故障排除，以及将大部分 Skype for Business Server 流量与任何潜在的硬件负载平衡器问题隔离在一起的能力。
  
请自己决定哪个负载平衡解决方案适用于部署中的每个池，但请记住以下限制： 
  
- 内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。您不能在一个接口上使用 DNS 负载平衡的同时，在另一个接口上使用硬件负载平衡。
    
- 某些类型的流量需要硬件负载平衡器。例如，HTTP 流量需要硬件平衡负载器而非 DNS 负载平衡。DNS 负载平衡对客户端到服务器的 Web 流量不起作用。
    
如果选择对某个池使用 DNS 负载平衡，但仍需对流量（如 HTTP 流量）使用硬件负载平衡器，则会大大简化硬件负载平衡器的管理。 例如，配置硬件负载平衡器将更简单，因为它将仅管理 HTTP 和 HTTPS 流量，而所有其他协议都将通过 DNS 负载平衡进行管理。 有关详细信息，请参阅 [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing)。 
  
对于服务器到服务器流量，Skype for Business Server 使用拓扑感知负载平衡。 服务器读取中央管理存储中的已发布拓扑以获取拓扑中服务器的 FQDN，并自动在服务器之间分发流量。 管理员无需设置或管理这种类型的负载平衡。 
  
如果使用 DNS 负载平衡，并且需要阻止到特定计算机的流量，则仅从池 FQDN 中删除 IP 地址条目是不够的。 您还必须删除计算机的 DNS 条目。 
  
## <a name="hardware-load-balancer-requirements"></a>硬件负载平衡器要求

Skype for Business Server 扩展的合并边缘拓扑已针对主要使用 Skype for Business Server 或 Lync Server 与其他组织联盟的新部署优化了 DNS 负载平衡。 如果下列任何方案要求高可用性，则必须在边缘服务器池上对以下内容使用硬件负载平衡器： 
  
- 使用 Office Communications Server 2007 R2 或 Office Communications Server 2007 与组织联盟
    
- Exchange 2010 SP1 之前使用 Exchange UM 的远程用户的 Exchange UM
    
- 与公共 IM 用户的连接
    
> [!IMPORTANT]
> 不支持对一个接口使用 DNS 负载平衡，而对另一个接口使用硬件负载平衡。必须对两个接口都使用硬件负载平衡，或者对两个接口都使用 DNS 负载平衡。 
  
> [!NOTE]
> 如果使用硬件负载平衡器，则为内部网络连接部署的负载平衡器必须配置为仅对发往运行访问边缘服务和 A/V 边缘服务的服务器的流量进行负载平衡。它不能对发往内部 Web 会议边缘服务或内部 XMPP 代理服务的流量进行负载平衡。 
  
> [!NOTE]
> Skype for Business Server 不支持 (NAT) 直接服务器返回 DSR。 
  
若要确定硬件负载平衡器是否支持 Skype for Business Server 所需的必要功能，请参阅 [Infrastructure for Skype for Business](../../../SfbPartnerCertification/certification/infra-gateways.md)。 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>运行 A/V 边缘服务的边缘服务器的硬件负载平衡器要求

以下是运行 A/V 边缘服务的边缘服务器的硬件负载平衡器要求：
  
- 对内部和外部端口 443 关闭 TCP nagling。Nagling 是将若干小数据包整合到单个大数据包以提高传输效率的过程。
    
- 关闭外部端口范围 50，000 - 59，999 的 TCP nagling。 
    
- 请不要对内部或外部防火墙使用 NAT。 
    
- 边缘内部接口与边缘服务器外部接口必须位于不同的网络上，且必须禁用它们之间的路由。 
    
- 运行 A/V 边缘服务的边缘服务器的外部接口必须使用可公开路由的 IP 地址，并且不能在任何边缘外部 IP 地址上进行 NAT 或端口转换。 
    
- 负载平衡器不得更改客户端的源地址。
    
### <a name="other-hardware-load-balancer-requirements"></a>其他硬件负载平衡器要求

Skype for Business Server for Web 服务中大大减少了基于 Cookie 的关联要求。 如果要部署 Skype for Business Server 并且不会保留任何 Lync Server 2010 前端服务器或前端池，则不需要基于 Cookie 的持久性。 但是，如果您暂时或永久保留任何 Lync Server 2010 前端服务器或前端池，则仍使用基于 Cookie 的持久性，因为它已针对 Lync Server 2010 进行部署和配置。 
  
> [!NOTE]
> **如果您决定使用基于 Cookie 的相关性，但您的部署不需要它**，如此做没有任何负面影响。 
  
对于 **不使用** 基于 Cookie 的相关性的部署：
  
- 在端口 4443 的反向代理发布规则上，将“转发主机头”设置为 True。这可确保转发原始 URL。
    
对于 **将使用** 基于 Cookie 的相关性的部署：
  
- 在端口 4443 的反向代理发布规则上，将“转发主机头”设置为 True。这可确保转发原始 URL。
    
- 不得将硬件负载平衡器 Cookie 标记为 httpOnly
    
- 硬件负载平衡器 Cookie 不得具有过期时间
    
- 硬件负载平衡器 Cookie 必须名为 **MS-WSMAN**（这是 Web 服务预期的值，不能更改）
    
- 必须在其传入 HTTP 请求没有 Cookie 的每个 HTTP 响应中设置硬件负载平衡器 Cookie，无论该同一 TCP 连接上的上一个 HTTP 响应是否已获得 Cookie 都是如此。如果负载平衡器将 Cookie 插入优化为每个 TCP 连接只发生一次，则不得使用该优化
    
> [!NOTE]
> 典型的硬件负载平衡器配置使用源地址相关性和 20 分钟的 TCP 会话生存期，这适用于 Lync Server 和 Lync 2013 客户端，因为会话状态通过客户端使用和/或应用程序交互进行维护。 
  
如果部署移动设备，则您的硬件负载平衡器必须能对 TCP 会话中的单个请求进行负载平衡（实际上，您必须能基于目标 IP 地址对单个请求进行负载平衡）。
  
> [!CAUTION]
> 如果要部署移动设备，则硬件负载平衡器必须能够单独对 TCP 连接内的每个请求进行负载平衡。 最新的 Apple iOS 移动应用程序要求传输层安全性 (TLS) 1.2 版。  
  
> [!CAUTION]
> 有关第三方硬件负载平衡器的详细信息，请参阅[Infrastructure for Skype for Business。](../../../SfbPartnerCertification/certification/infra-gateways.md)  
  
以下是控制器和前端池 Web 服务的硬件负载平衡器要求：
  
- 对于内部 Web 服务 VIP，在硬件负载平衡器上设置 Source_addr 持久性（内部端口 80 和 443）。 对于 Skype for Business Server，Source_addr持久性意味着始终向一台服务器发送来自单个 IP 地址的多个连接以保持会话状态。
    
- 使用 TCP 空闲超时 1800 秒。
    
- 在反向代理和下一个跃点池的硬件负载平衡器之间的防火墙上，创建一个规则以允许端口 4443 上的 https：流量从反向代理到硬件负载平衡器。 必须将硬件负载平衡器配置为侦听端口 80、443 和 4443。
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>硬件负载平衡器关联要求的摘要

|**客户端/用户位置**|**外部 Web 服务 FQDN 关联要求**|**内部 Web 服务 FQDN 关联要求**|
|:-----|:-----|:-----|
|Lync Web App (内部和外部用户)   <br/> 移动设备（内部和外部用户）  <br/> |无相关性  <br/> |源地址相关性  <br/> |
|Lync Web App (外部用户仅)   <br/> 移动设备（内部和外部用户）  <br/> |无相关性  <br/> |源地址相关性  <br/> |
|Lync Web App (内部用户)   <br/> 移动设备（未部署）  <br/> |无相关性  <br/> |源地址相关性  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a>硬件负载平衡器的端口监控

在硬件负载平衡器上定义端口监控来确定特定服务何时由于硬件或通信故障而不再可用。 例如，如果前端服务器服务 (RTCSRV) 由于前端服务器或前端池出现故障而停止，则 HLB 监控也应停止接收 Web 服务上的流量。 可在 HLB 上实施端口监控来监控以下各项：
  
**前端服务器用户池 - HLB 内部接口**

|**虚拟 IP/端口**|**节点端口**|**节点计算机/监视器**|**持久性配置文件**|**备注**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web-int_mco_443_vs  <br/> 443  <br/> |443  <br/> |前端  <br/> 5061  <br/> |Source  <br/> |HTTPS  <br/> |
|\<pool\>web-int_mco_80_vs  <br/> 80  <br/> |80  <br/> |前端  <br/> 5061  <br/> |Source  <br/> |HTTP  <br/> |
   
**前端服务器用户池 - HLB 外部接口**

|**虚拟 IP/端口**|**节点端口**|**节点计算机/监视器**|**持久性配置文件**|**备注**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |前端  <br/> 5061  <br/> |无  <br/> |HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |前端  <br/> 5061  <br/> |无  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>DNS 负载平衡
<a name="BKMK_DNSLoadBalancing"> </a>

Skype for Business Server 支持 DNS 负载平衡，这是一种可大大减少网络上负载平衡的管理开销的软件解决方案。 DNS 负载平衡可平衡 Skype for Business Server 特有的网络流量，如 SIP 流量和媒体流量。
  
如果部署 DNS 负载平衡，则组织的硬件负载平衡器管理开销将降至最低。 此外，还可以免除解决 SIP 流量负载平衡器配置错误相关问题的复杂过程。 您还可以阻止服务器连接以使服务器脱机。 同时，DNS 负载平衡还可确保硬件负载平衡器问题不会影响 SIP 流量的元素，例如基本呼叫路由。

下图显示了包括内部和外部 DNS 负载平衡的示例： 
  
**使用公用 IPv4 地址的边缘网络图**

![DNS 网络图示例](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
与为所有类型的流量使用硬件负载平衡器相比，使用 DNS 负载平衡还可以降低您购买硬件负载平衡器的成本。 你应该使用已通过与 Skype for Business Server 的互操作性资格测试的负载平衡器。 有关负载平衡器互操作性测试的详细信息，请参阅 [Lync Server 2010 Load Balancer Partners](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)。 内容适用于 Skype for Business Server。
  
前端池、边缘服务器池、控制器池和独立的中介服务器池都支持 DNS 负载平衡。
  
DNS 负载平衡通常在应用程序级别实现。 应用程序 (例如，运行 Skype for Business) 的客户端，如果对池完全限定域名 (FQDN) 使用) 记录查询，则通过连接到从 DNS A 和 AAAA (返回的 IP 地址之一来尝试连接到池中的服务器。 
  
例如，如果名为 pool01.contoso.com 的池中有三个前端服务器，将发生以下情况：
  
- 运行 Skype for Business 的客户端查询 DNS pool01.contoso.com。 查询返回三个 IP 地址，并按如下 (，但不一定按照以下顺序) ：
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92
    
- 客户端尝试建立传输控制协议 (TCP) IP 地址之一。 如果失败，客户端将尝试缓存中的下一个 IP 地址。
    
- 如果 TCP 连接成功，客户端将协商 TLS 以连接到 pool01.contoso.com。
    
- 如果客户端在未成功连接的情况下尝试所有缓存的条目，则通知用户当前没有运行 Skype for Business Server 的服务器可用。
    
> [!NOTE]
> 基于 DNS 的负载平衡不同于 DNS 轮循机制 (DNS RR) 它通常是指通过依赖 DNS 来提供与池中服务器对应的不同顺序的 IP 地址的负载平衡。 通常，DNS RR 仅启用负载分布，但不启用故障转移。 例如，如果与 DNS A 和 AAAA 返回的一个 IP 地址的连接 (如果使用 IPv6 寻址，则查询) 失败。 因此，DNS 轮循机制本身不如基于 DNS 的负载平衡可靠。 可以将 DNS 轮循机制与 DNS 负载平衡结合使用。 
  
DNS 负载平衡用于以下项：
  
- 对边缘服务器的服务器到服务器 SIP 进行负载平衡
    
- 负载平衡 统一通信应用程序服务 (一) 应用程序，如会议自动助理、响应组和呼叫呼叫呼叫
    
- 阻止与 UCAS 应用程序的新 (也称为"排出") 
    
- 负载平衡客户端和边缘服务器之间的所有客户端到服务器通信
    
DNS 负载平衡不能用于以下项：
  
- 到控制器或前端服务器的客户端到服务器 Web 流量
    
DNS 负载平衡和联盟流量：
  
如果 DNS SRV 查询返回了多个 DNS 记录，则访问边缘服务始终选取具有最低数字优先级和最高数字权重的 DNS SRV 记录。 Internet 工程任务组文档"用于指定服务位置的 DNS RR (DNS SRV [) "RFC 2782，DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt) 指定如果定义了多个 DNS SRV 记录，则首先使用优先级，然后是权重。 例如，DNS SRV 记录 A 的权重为 20，优先级为 40，DNS SRV 记录 B 的权重为 10，优先级为 50。 将选择优先级为 40 的 DNS SRV 记录 A。 以下规则适用于 DNS SRV 记录选择：
  
- 首先考虑优先级。 客户端必须尝试与 DNS SRV 记录定义的目标主机联系，该目标主机的编号优先级可以达到最低。 应按权重字段定义的顺序尝试具有相同优先级的目标。
    
- 权重字段指定优先级相同的条目的相对权重。 较大权重的选定概率应成比例地提高。 当没有任何服务器选择时，DNS 管理员应使用 Weight 0。 当存在权重大于 0 的记录时，选择权重为 0 的记录的可能性应该很小。
    
如果返回多个优先级和权重相同的 DNS SRV 记录，访问边缘服务将选择首先从 DNS 服务器收到的 SRV 记录。
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>前端池和控制器池中的 DNS 负载平衡

您可以使用 DNS 负载平衡来平衡前端池和控制器池中的 SIP 流量。部署 DNS 负载平衡后，仍需要对这些池使用硬件负载平衡器，但仅用于客户端到服务器的 HTTPS 流量。硬件负载平衡器用于通过端口 443 和 80 从客户端传入的 HTTPS 流量。 
  
尽管这些池中仍需要硬件负载平衡器，但这些负载平衡器的安装和管理主要用于硬件负载平衡器管理员熟悉的 HTTPS 流量。
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>支持旧客户端和服务器并对其进行 DNS 负载平衡

DNS 负载平衡仅支持运行 Skype for Business Server 或 Lync Server 2010 的服务器以及 Lync 2013 和 Skype for Business 客户端的自动故障转移。 早期版本的客户端和 Office Communications Server 仍可连接到运行 DNS 负载平衡的池，但如果它们无法连接到 DNS 负载平衡引用的第一台服务器，则它们无法故障转移到池中的另一台服务器。 
  
此外，如果使用 Exchange UM，则必须至少使用 Exchange 2010 SP1 才能获得对 Skype for Business Server DNS 负载平衡的支持。 如果使用早期版本的 Exchange，您的用户将没有针对这些 Exchange UM 方案的故障转移功能：
  
- 在电话上播放企业语音邮件
    
- 转接来自 Exchange UM 自动助理的呼叫
    
其他所有 Exchange UM 方案将正常工作。
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>在前端池和控制器池中部署 DNS 负载平衡
<a name="BK_FE_Dir"> </a>

在前端池和控制器池中部署 DNS 负载平衡时，需要使用 FQDN 和 DNS 记录执行一些额外步骤。
  
- 使用 DNS 负载平衡的池必须具有两个 FQDN：DNS 负载平衡 (（如 pool01.contoso.com) ）使用的常规池 FQDN，解析为池中服务器的物理 IP;池的 Web 服务 (如 web01.contoso.com) 的另一个 FQDN，解析为池的虚拟 IP 地址。 
    
    在拓扑生成器中，如果要为池部署 DNS 负载平衡，若要为池的 Web 服务创建此额外的 FQDN，必须选中"覆盖内部 Web 服务池 **FQDN"** 复选框，并键入"指定此池的 **Web** 服务 URL"页中的 FQDN。
    
- 要支持 DNS 负载平衡使用的 FQDN，必须设置 DNS，以便将池 FQDN（例如 pool01.contoso.com）解析为该池中所有服务器的 IP 地址（例如，192.168.1.1、192.168.1.2 等）。您应该仅包含当前部署的服务器的 IP 地址。
    
    > [!CAUTION]
    > 如果您具有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。 例如，如果将前端服务器的外部 Web 服务 FQDN 定义为 **pool01.contoso.com，** 则不能将 **pool01.contoso.com** 用于另一个前端池或前端服务器。 如果还要部署控制器，则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须与任何其他控制器或控制器池以及任何前端池或前端服务器是唯一的。 如果决定使用自定义的 FQDN 覆盖内部 Web 服务，则每个 FQDN 都必须与任何其他前端池、控制器或控制器池是唯一的。
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>边缘服务器池中的 DNS 负载平衡
<a name="BK_Edge"> </a>

您可以在边缘服务器池中部署 DNS 负载平衡。如果要进行部署，则必须了解以下注意事项。
  
在边缘服务器中使用 DNS 负载平衡会导致以下方案中丧失故障转移功能：
  
- 与运行 Lync Server 2010 之前发布的 Skype for Business Server 版本的组织联盟。
    
- 即时消息交换与公共即时消息 (IM) 服务 AOL 和 Yahoo！的用户，以及基于 XMPP 的提供商和服务器（如 Google Talk）目前是唯一受支持的 XMPP 合作伙伴。
    
只要池中的所有边缘服务器都在运行，这些方案就会正常工作；但是如果某台边缘服务器不可用，则发送到该服务器的对这些方案的所有请求都将失败，而不会路由到其他边缘服务器。
  
 如果使用 Exchange UM，则必须至少使用 Exchange 2013 才能在边缘上获取对 Skype for Business Server DNS 负载平衡的支持。 如果使用早期版本的 Exchange，则远程用户将不会具有这些 Exchange UM 方案的故障转移功能：
  
- 在电话上播放企业语音邮件
    
- 转接来自 Exchange UM 自动助理的呼叫
    
其他所有 Exchange UM 方案将正常工作。
  
内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。您不能对一个边缘接口使用 DNS 负载平衡，而对另一个边缘接口使用硬件负载平衡。
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>在边缘服务器池中部署 DNS 负载平衡

要在边缘服务器池的外部接口上部署 DNS 负载平衡，需要具有以下 DNS 条目：
  
- 对于访问边缘服务，池内每台服务器都需要一个条目。 每个条目必须将访问边缘服务的 FQDN (例如，sip.contoso.com) 解析为池中其中一台边缘服务器上访问边缘服务的 IP 地址。
    
- 对于 Web 会议边缘服务，池中每台服务器都需要一个条目。 每个条目必须将 Web 会议边缘服务的 FQDN (例如，webconf.contoso.com) 解析为池中某一台边缘服务器的 Web 会议边缘服务的 IP 地址。
    
- 对于音频/视频边缘服务，池内每台服务器都需要一个条目。 每个条目必须将音频/视频边缘服务的 FQDN (例如，av.contoso.com) 解析为池中某台边缘服务器的 A/V 边缘服务的 IP 地址。
    
要在边缘服务器池的内部接口上部署 DNS 负载平衡，必须添加一条将此边缘服务器池的内部 FQDN 解析为该池中每台服务器的 IP 地址的 DNS A 记录。
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>在中介服务器池中使用 DNS 负载平衡
<a name="BK_Mediation"> </a>

可以在独立的中介服务器池上使用 DNS 负载平衡。所有 SIP 和媒体流量都通过 DNS 负载平衡进行平衡。
  
要在中介服务器池中部署 DNS 负载平衡，必须设置 DNS，以便将池 FQDN（例如 mediationpool1.contoso.com）解析为该池中所有服务器的 IP 地址（例如，192.168.1.1、192.168.1.2 等）。
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>使用 DNS 负载平衡阻止到服务器的流量
<a name="BK_Mediation"> </a>

如果使用 DNS 负载平衡，并且需要阻止到特定计算机的流量，则仅从池 FQDN 中删除 IP 地址条目是不够的。 您还必须删除计算机的 DNS 条目。 
  
请注意，对于服务器到服务器的流量，Skype for Business Server 使用拓扑感知负载平衡。 服务器读取中央管理存储中的已发布拓扑以获取拓扑中服务器的 FQDN，并自动在服务器之间分发流量。 若要阻止服务器接收服务器到服务器通信，必须从拓扑中删除服务器。 
