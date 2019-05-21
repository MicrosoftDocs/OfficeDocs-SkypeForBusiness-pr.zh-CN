---
title: Skype for Business Server 中的边缘服务器环境要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: '摘要: 了解 Skype for Business Server 中 Edge 服务器的环境要求。'
ms.openlocfilehash: a154882e6fe78faee3b020830de4049827babf89
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277172"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Skype for Business Server 中的边缘服务器环境要求
 
**摘要:** 了解 Skype for Business 服务器中的 Edge 服务器环境要求。
  
需要在 Skype for Business Server Edge 服务器环境本身之外进行许多规划和准备工作。 本文中，我们将按照下面的列表回顾需要在组织环境中进行哪些准备工作：
  
- [Topology planning](edge-environmental-requirements.md#TopoPlan)
    
- [DNS planning](edge-environmental-requirements.md#DNSPlan)
    
- [Certificate planning](edge-environmental-requirements.md#CertPlan)
    
- [Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>拓扑规划
<a name="TopoPlan"> </a>

Skype for Business 服务器边缘服务器拓扑可以使用:
  
- 可路由的公用 IP 地址。
    
- 不可路由的专用 IP 地址（如果使用**对称**网络地址转换 (NAT)）。
    
> [!TIP]
> 你的 Edge 服务器可以配置为对每个服务使用具有不同端口的单个 IP 地址, 也可以对每个服务使用不同的 IP 地址, 但使用相同的默认端口 (默认端口为 TCP 443)。 在后面的 IP 地址要求部分中，我们会介绍更多信息。 
  
如果选择结合 NAT 使用不可路由的专用 IP 地址，请记住以下几点：
  
- 需要在**所有三个**外部接口上使用可路由的专用 IP 地址。
    
- 需要为传入和传出流量配置**对称** NAT。 对称 NAT 是唯一支持的可与 Skype for Business 服务器边缘服务器配合使用的 NAT。
    
- 将 NAT 配置为不要更改传入的源地址。 A/V 边缘服务需要能够接收传入的源地址以查找最佳媒体路径。
    
- 您的边缘服务器必须能够从其公共的 A/V 边缘 IP 地址与另一个服务器进行通信。 防火墙需要允许此流量。
    
- 如果使用 DNS 负载平衡, NAT**仅**可用于缩放的合并边缘服务器。 如果使用硬件负载平衡 (HLB)，那就需要使用**无** NAT 的可公共路由的 IP 地址。
    
如果你的 Access、Web 会议和 A/V 边缘界面位于路由器或防火墙后面, 则不会对单个和缩放的合并边缘服务器拓扑执行对称 NAT (前提是你未使用硬件负载平衡)。
  
### <a name="summary-of-edge-server-topology-options"></a>边缘服务器拓扑选项摘要

对于 Skype for business 服务器 Edge 服务器部署, 我们有多种拓扑选项可供使用:
  
- 使用专用 IP 地址和 NAT 的单一合并边缘
    
- 使用公用 IP 地址的单一合并边缘
    
- 使用专用 IP 地址和 NAT 的扩展合并边缘
    
- 使用公用 IP 地址的扩展合并边缘
    
- 使用硬件负载平衡器的扩展合并边缘
    
为帮助你选择一种拓扑，我们准备了下表，该表提供了每种拓扑可选择哪些选项的摘要：
  
|**拓扑**|**高可用性**|**边缘池中的外部边缘服务器需要其他 DNS 记录？**|**Skype for business Server 会话的边缘故障转移**|**Skype for business Server 联合身份验证会话的边缘故障转移**|
|:-----|:-----|:-----|:-----|:-----|
|使用专用 IP 地址和 NAT 的单一合并边缘  <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|使用公用 IP 地址的单一合并边缘  <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|使用专用 IP 地址和 NAT 的扩展合并边缘（DNS 负载平衡）  <br/> |是  <br/> |是  <br/> |是  <br/> |Yes&sup1;  <br/> |
|使用公用 IP 地址的扩展合并边缘（DNS 负载平衡）  <br/> |是  <br/> |是  <br/> |是  <br/> |Yes&sup1;  <br/> |
|使用硬件负载平衡器的扩展合并边缘  <br/> |是  <br/> |不支持（每个 VIP 一个 DNS A 记录）  <br/> |是  <br/> |是  <br/> |
   
&sup1;Exchange 统一消息 (UM) 使用 DNS 负载平衡的远程用户故障转移需要使用 Exchange 2013 或更高版本。
  
### <a name="ip-address-requirements"></a>IP 地址要求

在基本级别上, 三个服务需要 IP 地址;Access Edge 服务、Web 会议边缘服务和 A/V 边缘服务。 可以选择使用三个 IP 地址，每种服务对应一个地址，也可以使用一个 IP 地址，并选择将每种服务置于不同的端口（有关这方面的更多信息，可查看[Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)）。 对于单一合并边缘环境，差不多就是这样。
  
> [!NOTE]
> 前面说过，你可以选择让所有三种服务使用同一个 IP 地址，但运行于不同的端口。但需要澄清的是，我们不建议这样做。如果客户无法访问你在这种情况下使用的备用端口，他们也就不能获得边缘环境的全部功能。 
  
扩展合并拓扑可能稍微复杂一点，所以我们来看一下列出 IP 地址要求的几张表，同时请牢记，拓扑选择的主要决策点是高可用性和负载平衡。高可用性需求可能影响负载平衡选择（在表的后面，我们将深入讨论）。
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>扩展合并边缘的 IP 地址要求（每个角色一个 IP 地址）

|**每个池的边缘服务器数**|**DNS 负载平衡所需的 IP 地址数量**|**硬件负载平衡所需的 IP 地址数量**|
|:-----|:-----|:-----|
|2  <br/> |6  <br/> |3（每个 VIP 1 个）6  <br/> |
|3  <br/> |db-9  <br/> |3（每个 VIP 1 个）9  <br/> |
|4  <br/> |至  <br/> |3（每个 VIP 1 个）12  <br/> |
|5  <br/> |岁  <br/> |3（每个 VIP 1 个）15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>扩展合并边缘的 IP 地址要求（所有角色一个 IP 地址）

|**每个池的边缘服务器数**|**DNS 负载平衡所需的 IP 地址数量**|**硬件负载平衡所需的 IP 地址数量**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1（每个 VIP 1 个）2  <br/> |
|3  <br/> |3  <br/> |1（每个 VIP 1 个）3  <br/> |
|4  <br/> |4  <br/> |1（每个 VIP 1 个）4  <br/> |
|5  <br/> |5  <br/> |1（每个 VIP 1 个）5  <br/> |
   
我们来看看规划时要考虑的一些其他事项。
  
- **高可用性**: 如果你需要在部署中使用高可用性, 应在池中至少部署两台边缘服务器。 值得注意的是, 单个边缘池最多支持12台边缘服务器 (虽然拓扑生成器允许添加最多20个, 但未经过测试或支持, 因此我们建议您不要这样做)。 如果需要超过12台边缘服务器, 应为它们创建其他边缘池。
    
- **硬件负载平衡**: 建议大多数情况下进行 DNS 负载平衡。 当然, 硬件负载平衡也受支持, 但要注意它是通过 DNS 负载平衡的单个方案所必需的:
    
  - 对 Exchange 2007 或 Exchange 2010 (没有 SP) 的外部访问统一消息 (UM)。
    
- **Dns 负载平衡**: 对于 UM, EXCHANGE 2010 SP1 和更高版本可由 DNS 负载平衡支持。 请注意, 如果你需要针对早期版本的 Exchange 使用 DNS 负载平衡, 它将正常工作, 但此操作的所有流量将转到池中的第一台服务器, 如果该服务器不可用, 则该流量随后将失败。
    
    如果你使用以下方式与公司进行联盟, 也建议使用 DNS 负载平衡:
- Skype for Business 服务器 2015:
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft Office O365
- Skype for Business 服务器 2019:
    - Lync Server 2013
    - Skype for Business Server 2015
    - Microsoft Office 365。
    
## <a name="dns-planning"></a>DNS 规划
<a name="DNSPlan"> </a>

当需要 Skype for business Server Edge 服务器部署时, 正确准备 DNS 非常重要。 如果正确的记录就位，部署就会容易得多。 但愿你选择了上一节中的拓扑，因为我们将作一下总结，然后列出几张表，这些表概列了适用于那些方案的 DNS 记录。 如果需要, 我们还将为[Skype for Business 服务器提供一些高级边缘服务器 DNS 规划](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md), 以便进行更深入的阅读。
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>单个统一边缘服务器方案的 DNS 记录

这些记录将是你需要用于使用 NAT 的公共 Ip 或专用 Ip 的单个边缘服务器的 DNS 记录。 因为这是示例数据，所以我们将提供示例 IP，便于你更容易地制定出自己的条目：
  
- 内部网络适配器：172.25.33.10（未分配默认网关的地址）
    
    > [!NOTE]
    > 确保有一个从网络中包含边缘内部接口的网络路由, 这些网络包含运行 Skype for business Server 或 Lync Server 2013 客户端的服务器 (例如从172.25.33.0 到 192.168.10.0)。 
  
- 外部网络适配器：
    
  - 公用 IP：
    
  - 访问边缘: 131.107.155.10 (这是主网关, 将默认网关设置为公共路由器, 例如: 131.107.155.1)
    
  - 网络会议边缘: 131.107.155.20 (辅助)
    
  - A/V 边缘: 131.107.155.30 (辅助)
    
  Web 会议和 A/V 边缘公共 IP 地址是其他 (辅助) IP 地址, 在 Internet 协议版本 4 (TCP/IPv4) 和 Internet 协议版本 6 (TCP/IPv6) 的 "Internet 协议版本 4 (TCP/IPv6)" 的 "高级" 部分中的 "本地连接" 属性Windows Server。
    
  - 专用 IP：
    
  - 访问边缘: 10.45.16.10 (这是主网关, 将默认网关设置为你的路由器, 例如: 10.45.16.1)
    
  - 网络会议边缘: 10.45.16.20 (辅助)
    
  - A/V 边缘: 10.45.16.30 (辅助)
    
Web 会议和 A/V 边缘公共 IP 地址是其他 (辅助) IP 地址, 在 Internet 协议版本 4 (TCP/IPv4) 和 Internet 协议版本 6 (TCP/IPv6) 的 "Internet 协议版本 4 (TCP/IPv6)" 的 "高级" 部分中的 "本地连接" 属性Windows Server。
  
> [!TIP]
>这里有其他可行的配置：
  
- 可以在外部网络适配器上使用一个 IP 地址。 我们不建议这样做, 因为接下来你需要使用不同的端口 (可在 Skype for Business Server 中执行) 区分了服务, 但某些防火墙可能会阻止备用端口。 有关这方面的更多内容，请参阅[Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)一节。
    
- 可以准备三个外部网络适配器，而不是一个，为每个服务分配其中一个服务 IP。为什么这样做？因为这会分隔这些服务，如果出现问题，这更便于排查故障，并可能在你解决问题时，让其他服务继续运行。
    
|**位置**|**类型**|**端口**|**FQDN 或 DNS 记录**|**IP 地址或 FQDN**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |A 记录  <br/> |NA  <br/> |sip.contoso.com  <br/> |**公共:** 131.107.155.10 <br/> **私人:** 10.45.16.10 <br/> |用于访问边缘服务的外部接口。 对于具有 Skype for Business 用户的每个 SIP 域, 你都需要一个。  <br/> |
|外部 DNS  <br/> |A 记录  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**公共:** 131.107.155.20 <br/> **私人:** 10.45.16.20 <br/> |用于 Web 会议边缘服务的外部接口。  <br/> |
|外部 DNS  <br/> |A 记录  <br/> |NA  <br/> |av.contoso.com  <br/> |**公共:** 131.107.155.30 <br/> **私人:** 10.45.16.30 <br/> |A/V 边缘服务的外部接口。  <br/> |
|外部 DNS  <br/> |SRV 记录  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |用于访问边缘服务的外部接口。 Skype for business Server、Lync Server 2013 和 Lync Server 2010 客户端需要此 SRV 记录才能在外部工作。 对于拥有 Skype for Business 用户的每个域, 您都需要一个。  <br/> |
|外部 DNS  <br/> |SRV 记录  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |用于访问边缘服务的外部接口。 称为“允许的 SIP 域”的联盟伙伴的自动 DNS 发现需要此 SRV 记录。 对于拥有 Skype for Business 用户的每个域, 您都需要一个。  <br/> |
|内部 DNS  <br/> |A 记录  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |合并边缘的内部接口。  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>用于缩放的 DNS 和硬件边缘服务器方案的 DNS 记录

这些记录将是你需要用于使用 NAT 的公共 Ip 或专用 Ip 的单个边缘服务器的 DNS 记录。 因为这是示例数据，所以我们将提供示例 IP，便于你更容易地制定出自己的条目：
  
- 内部网络适配器：
    
  - 节点 1：172.25.33.10（未分配默认网关的地址）
    
  - 节点 2：172.25.33.11（未分配默认网关的地址）
    
    > [!NOTE]
    > 确保有一个从网络中包含边缘内部接口的网络路由, 这些网络包含运行 Skype for business Server 或 Lync Server 2013 客户端的服务器 (例如从172.25.33.0 到 192.168.10.0)。 
  
- 外部网络适配器：
    
  - 节点 1
    
     - 公用 IP：
    
        - 访问边缘: 131.107.155.10 (这是主网关, 将默认网关设置为公共路由器, 例如: 131.107.155.1)
    
        - 网络会议边缘: 131.107.155.20 (辅助)
    
        - A/V 边缘: 131.107.155.30 (辅助)
    
          Web 会议和 A/V 边缘公共 IP 地址是其他 (辅助) IP 地址, 在 Internet 协议版本 4 (TCP/IPv4) 和 Internet 协议版本 6 (TCP/IPv6) 的 "Internet 协议版本 4 (TCP/IPv6)" 的 "高级" 部分中的 "本地连接" 属性Windows Server。
    
    - 专用 IP：
    
         - 访问边缘: 10.45.16.10 (这是主网关, 将默认网关设置为你的路由器, 例如: 10.45.16.1)
    
         - 网络会议边缘: 10.45.16.20 (辅助)
    
         - A/V 边缘: 10.45.16.30 (辅助)
    
      Web 会议和 A/V 边缘公共 IP 地址是其他 (辅助) IP 地址, 在 Internet 协议版本 4 (TCP/IPv4) 和 Internet 协议版本 6 (TCP/IPv6) 的 "Internet 协议版本 4 (TCP/IPv6)" 的 "高级" 部分中的 "本地连接" 属性Windows Server。
    
  - 节点 2
    
    - 公用 IP：
    
      - 访问边缘: 131.107.155.11 (这是主网关, 将默认网关设置为公共路由器, 例如: 131.107.155.1)
    
      - 网络会议边缘: 131.107.155.21 (辅助)
    
      - A/V 边缘: 131.107.155.31 (辅助)
    
      Web 会议和 A/V 边缘公共 IP 地址是其他 (辅助) IP 地址, 在 Internet 协议版本 4 (TCP/IPv4) 和 Internet 协议版本 6 (TCP/IPv6) 的 "Internet 协议版本 4 (TCP/IPv6)" 的 "高级" 部分中的 "本地连接" 属性Windows Server。
    
  - 专用 IP：
    
    - 访问边缘: 10.45.16.11 (这是主网关, 将默认网关设置为你的路由器, 例如: 10.45.16.1)
    
    - 网络会议边缘: 10.45.16.21 (辅助)
    
    - A/V 边缘: 10.45.16.31 (辅助)
    
      Web 会议和 A/V 边缘公共 IP 地址是其他 (辅助) IP 地址, 在 Internet 协议版本 4 (TCP/IPv4) 和 Internet 协议版本 6 (TCP/IPv6) 的 "Internet 协议版本 4 (TCP/IPv6)" 的 "高级" 部分中的 "本地连接" 属性Windows Server。
    
这里有其他可行的配置：
  
- 可以在外部网络适配器上使用一个 IP 地址。 我们不建议这样做, 因为接下来你需要使用不同的端口 (可在 Skype for Business Server 中执行) 区分了服务, 但某些防火墙可能会阻止备用端口。 有关这方面的更多内容，请参阅[Port and firewall planning](edge-environmental-requirements.md#PortFirewallPlan)一节。
    
- 可以准备三个外部网络适配器，而不是一个，为每个服务分配其中一个服务 IP。为什么这样做？因为这会分隔这些服务，如果出现问题，这更便于排查故障，并可能在你解决问题时，让其他服务继续运行。
    
|**位置**|**类型**|**端口**|**FQDN 或 DNS 记录**|**IP 地址或 FQDN**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |A 记录  <br/> |NA  <br/> |sip.contoso.com  <br/> |**公共:** 131.107.155.10 和131.107.155.11 <br/> **私人:** 10.45.16.10 和10.45.16.11 <br/> |用于访问边缘服务的外部接口。 对于具有 Skype for Business 用户的每个 SIP 域, 你都需要一个。  <br/> |
|外部 DNS  <br/> |A 记录  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**公共:** 131.107.155.20 和131.107.155.21 <br/> **私人:** 10.45.16.20 和10.45.16.21 <br/> |用于 Web 会议边缘服务的外部接口。  <br/> |
|外部 DNS  <br/> |A 记录  <br/> |NA  <br/> |av.contoso.com  <br/> |**公共:** 131.107.155.30 和131.107.155.31 <br/> **私人:** 10.45.16.30 和10.45.16.31 <br/> |A/V 边缘服务的外部接口。  <br/> |
|外部 DNS  <br/> |SRV 记录  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |用于访问边缘服务的外部接口。 Skype for business Server、Lync Server 2013 和 Lync Server 2010 客户端需要此 SRV 记录才能在外部工作。 对于具有 Skype for Business 的每个域, 您都需要一个。  <br/> |
|外部 DNS  <br/> |SRV 记录  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |用于访问边缘服务的外部接口。 称为“允许的 SIP 域”的联盟伙伴的自动 DNS 发现需要此 SRV 记录。 对于具有 Skype for Business 的每个域, 您都需要一个。  <br/> |
|内部 DNS  <br/> |A 记录  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 和 172.25.33.11  <br/> |合并边缘的内部接口。  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>联盟的 DNS 记录（所有方案）

|**位置**|**类型**|**端口**|**域名**|**FQDN 主机记录**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |sip.contoso.com  <br/> |自动 DNS 发现所需的 SIP 访问边缘外部接口。 由其他潜在的联盟伙伴使用。 这也称为“允许的 SIP 域”。 对于具有 Skype for Business 用户的每个 SIP 域, 您都需要其中一个。  <br/><br/> **注意:** 你将需要移动版和推送通知交换所的 SRV 记录。 <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>可扩展消息传递和状态协议的 DNS 记录

|**位置**|**类型**|**端口**|**域名**|**IP 地址或 FQDN 主机记录**|**注释**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |xmpp.contoso.com  <br/> |您的访问边缘服务或边缘池上的 XMPP 代理接口。 对于启用了 Skype for Business Server 的用户, 您需要为所有内部 SIP 域重复此步骤, 并允许用户通过以下方式为 XMPP 联系人提供联系:  <br/> •全球政策  <br/> •用户已启用的网站策略  <br/> •应用于启用 Skype for Business 服务器的用户的用户策略  <br/> 在 XMPP 联盟用户策略中，还需要配置允许的 XMPP 策略。  <br/> |
|外部 DNS  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |在托管你的 XMPP 代理服务的边缘服务器或边缘池上访问边缘服务的 IP 地址  <br/> |这指向了托管 XMPP 代理服务的边缘服务器或边缘池中的访问边缘服务。 通常，你创建的 SRV 记录将指向主机（A 或 AAAA）记录。  <br/> |
   
> [!NOTE]
> XMPP 网关和代理在 Skype for business Server 2015 中可用, 但 Skype for business Server 2019 不再支持。 有关详细信息, 请参阅[迁移 XMPP 联合身份验证](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。

## <a name="certificate-planning"></a>证书规划
<a name="CertPlan"> </a>

Skype for business 服务器在服务器之间和从服务器到客户端都使用安全的加密通信的证书。 正如你料想的那样，证书需要服务器的 DNS 记录与证书中的任何使用者名称 (SN) 和使用者替代名称 (SAN) 匹配。 在规划阶段，现在这需要花些功夫，确保在 DNS 中注册对应于证书 SN 和 SAN 条目的正确 FQDN。
  
我们将分别讨论外部和内部证书需求，然后查看提供两种需求的表。
  
### <a name="external-certificates"></a>外部证书

至少, 分配给外部边缘服务器接口的证书需要由公共证书颁发机构 (CA) 提供。 我们无法向你推荐特定的 CA, 但我们确实拥有一个 Ca、[统一通信证书合作伙伴](https://support.microsoft.com/en-us/kb/929395)列表, 你可以查看你的首选 CA 是否已列出。
  
你什么时候需要向 CA 提出申请，索要这份公共证书，如何提出申请？有几种方式可以完成申请：
  
- 您可以完成 Skype for Business 服务器的安装, 然后进行边缘服务器部署。 Skype for Business 服务器部署向导将有一个步骤来生成证书请求, 然后您可以将该请求发送到您选择的 CA。
    
- 你还可以使用 Windows PowerShell 命令生成此请求 (如果这与你的业务需求或部署策略更内联)。
    
- 最后, 你的 CA 可能会有自己的提交过程, 该过程还可能涉及 Windows PowerShell 或其他方法。 这种情况下，除了此处提供的供你参考的信息外，你还需要依靠他们的文档。
    
获得证书后, 您需要继续并在 Skype for Business Server 中将其分配到以下服务:
  
- Access Edge 服务界面
    
- 网络会议边缘服务界面
    
- 音频/视频身份验证服务 (不要将其与 A/V 边缘服务混淆, 因为它不使用加密音频和视频流的证书)
    
> [!IMPORTANT]
> 所有边缘服务器 (如果它们属于同一个 Edge 服务器池) 都需要具有与媒体中继身份验证服务具有相同私钥的完全相同的证书。 
  
### <a name="internal-certificates"></a>内部证书

对于内部边缘服务器接口, 你可以使用来自公共 CA 的公共证书, 或从你的组织的内部 CA 颁发的证书。 对于内部证书，需要记住的一点是，它使用 SN 条目，没有 SAN 条目，因此你根本不用关心内部证书的 SAN。
  
### <a name="required-certificates-table"></a>所需证书表

这里有一个表可帮助你申请证书。此处的 FQDN 条目只适用于示例域。你需要根据自己的专用域和公共域提出申请，不过这里有我们所用内容的指南：
  
- contoso<span></span>: 公共 FQDN
    
- fabrikam<span></span>: 第二公共 FQDN (已添加为要在有多个 SIP 域时请求的操作的演示)
    
- Contoso<span></span>.Net: 内部域
    
#### <a name="edge-certificate-table"></a>边缘证书表

无论你正在执行单个边缘服务器还是边缘池, 你的证书都需要执行以下操作:
  
|**组件**|**使用者名称 (SN)**|**使用者替代名称 (SAN)/顺序**|**注释**|
|:-----|:-----|:-----|:-----|
|外部边缘  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |这是需要从公共 CA 申请获得的证书。需要将其分配给以下服务的外部边缘接口：<br/> • Access Edge  <br/> •网络会议边缘  <br/> •音频/视频身份验证  <br/> <br/>好消息是, San 会自动添加到你的证书请求, 因此你提交请求后你的证书基于在拓扑生成器中为此部署定义的内容。 你只需要添加任何其他 SIP 域的 SAN 条目或需要支持的其他条目。 为什么此例中会复制 sip.contoso.com？ 这也是自动发生的，为了让系统正常工作，需要如此。  <br/><br/> **注意:** 此证书还可用于公共即时消息连接。 对此，你无需进行任何其他操作，但是在本文档以前的版本中，这作为单独的表列出，而现在不是。 <br/> |
|内部边缘  <br/> |sfbedge.contoso.com  <br/> |NA  <br/> |可以从公共 CA 或内部 CA 获得此证书。该证书需要包含服务器 EKU（增强型密钥使用），你要将其分配给内部边缘界面。  <br/> |
   
如果可扩展消息传递和状态协议 (XMPP) 需要证书，该证书看上去与上面的外部边缘表条目完全相同，但是有以下两条额外的 SAN 条目：
  
- xmpp.<span> </span>contoso<span></span>
    
- \*<span></span>.com
    
请记住, 当前 XMPP 仅在适用于 Google 的 Skype for Business 服务器中受支持, 如果你需要或需要将其用于任何其他内容, 你需要使用所涉及的第三方供应商确认该功能。
  
## <a name="port-and-firewall-planning"></a>端口和防火墙规划
<a name="PortFirewallPlan"> </a>

为 Skype for business Server Edge 的端口和防火墙准备计划您的计划可以让您节省几天或几周的故障排除和压力。 因此，我们会列出几张表，这些表指出了我们的协议用途，以及对于 NAT 和公共 IP 方案，需要开放哪些端口，包括入站和出站。 我们还针对硬件负载平衡方案 (HLB) 提供了单独的表，以及这方面的进一步指导。 为了更好地阅读, 我们还提供了[Skype For Business 服务器中的一些 Edge 服务器方案](scenarios.md), 你可以查看你的特定部署注意事项。
  
### <a name="general-protocol-usage"></a>常规协议用途

在查看外部和内部防火墙的摘要表之前，让我们同样考虑下面的表：
  
|**音频/视频传输**|**使用**|
|:-----|:-----|
|UDP  <br/> |音频和视频的首选传输层协议。  <br/> |
|TCP  <br/> |音频和视频的回退传输层协议。  <br/> 适用于 Skype for business Server、Lync Server 2013 和 Lync Server 2010 的应用程序共享所需的传输层协议。  <br/> 将文件传输到 Skype for business 服务器、Lync Server 2013 和 Lync Server 2010 所需的传输层协议。  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>外部端口防火墙摘要表

源 IP 地址和目标 IP 地址将包含相应的信息，这些信息可供结合 NAT 使用专用 IP 地址的用户，以及使用公用 IP 地址的用户使用。 这将涵盖 " [Skype For Business 服务器" 部分的 Edge 服务器方案](scenarios.md)中的所有排列。
  
|**角色或协议**|**TCP 或 UDP**|**目标端口或端口范围**|**源 IP 地址**|**目标 IP 地址**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> 在 Skype for Business Server 2019 中不受支持 |TCP  <br/> |5269  <br/> |任意  <br/> |XMPP 代理服务 (与访问边缘服务共享 IP 地址  <br/> |XMPP 代理服务接受来自定义的 XMPP 联合的 XMPP 联系人的流量。  <br/> |
|访问/HTTP  <br/> |TCP  <br/> |80  <br/> |**使用 NAT 的专用 IP:** Edge 服务器访问边缘服务 <br/> **公共 IP:** 边缘服务器访问边缘服务公共 IP 地址 <br/> |任意  <br/> |证书吊销和 CRL 检查和检索。  <br/> |
|访问/DNS  <br/> |TCP  <br/> |53  <br/> |**使用 NAT 的专用 IP:** Edge 服务器访问边缘服务 <br/> **公共 IP:** 边缘服务器访问边缘服务公共 IP 地址 <br/> |任意  <br/> |通过 TCP 的 DNS 查询。  <br/> |
|访问/DNS  <br/> |UDP  <br/> |53  <br/> |**使用 NAT 的专用 IP:** Edge 服务器访问边缘服务 <br/> **公共 IP:** 边缘服务器访问边缘服务公共 IP 地址 <br/> |任意  <br/> |通过 UDP 的 DNS 查询。  <br/> |
|访问/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |任意   <br/> |**使用 NAT 的专用 IP:** Edge 服务器访问边缘服务 <br/> **公共 IP:** 边缘服务器访问边缘服务公共 IP 地址 <br/> |外部用户访问的客户端到服务器 SIP 通信。  <br/> |
|访问/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |任意  <br/> |**使用 NAT 的专用 IP:** Edge 服务器访问边缘服务 <br/> **公共 IP:** 边缘服务器访问边缘服务公共 IP 地址 <br/> |适用于使用 SIP 的联盟和公共 IM 连接。  <br/> |
|访问/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**使用 NAT 的专用 IP:** Edge 服务器访问边缘服务 <br/> **公共 IP:** 边缘服务器访问边缘服务公共 IP 地址 <br/> |任意  <br/> |适用于使用 SIP 的联盟和公共 IM 连接。  <br/> |
|Web 会议/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |任意   <br/> |**使用 NAT 的专用 IP:** Edge 服务器 Web 会议边缘服务 <br/> **公共 IP:** Edge 服务器 Web 会议边缘服务公共 IP 地址 <br/> |网络会议媒体。  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**使用 NAT 的专用 IP:** Edge 服务器 A/V 边缘服务 <br/> **公共 IP:** Edge 服务器 A/V 边缘服务公共 IP 地址 <br/> |任意  <br/> |这可以用于中继媒体流量。  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**使用 NAT 的专用 IP:** Edge 服务器 A/V 边缘服务 <br/> **公共 IP:** Edge 服务器 A/V 边缘服务公共 IP 地址 <br/> |任意  <br/> |这可以用于中继媒体流量。  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |**使用 NAT 的专用 IP:** Edge 服务器 A/V 边缘服务 <br/> **公共 IP:** Edge 服务器 A/V 边缘服务公共 IP 地址 <br/> |任意  <br/> |3478 出站：  <br/> •由 Skype for Business 服务器使用, 用于确定与其通信的 Edge 服务器的版本。  <br/> •用于边缘服务器之间的媒体流量。  <br/> •对具有 Lync Server 2010 的联盟是必需的。  <br/> •如果你的组织中部署了多个边缘池, 则需要。  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |**使用 NAT 的专用 IP:** Edge 服务器 A/V 边缘服务 <br/> **公共 IP:** Edge 服务器 A/V 边缘服务公共 IP 地址 <br/> |在端口 3478 上通过 UDP 进行的候选项 STUN/TURN 协商。  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |任意   <br/> |**使用 NAT 的专用 IP:** Edge 服务器 A/V 边缘服务 <br/> **公共 IP:** Edge 服务器 A/V 边缘服务公共 IP 地址 <br/> |在端口 443 上通过 TCP 进行的候选项 STUN/TURN 协商。  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |**使用 NAT 的专用 IP:** Edge 服务器 A/V 边缘服务 <br/> **公共 IP:** Edge 服务器 A/V 边缘服务公共 IP 地址 <br/> |任意  <br/> |在端口 443 上通过 TCP 进行的候选项 STUN/TURN 协商。  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>内部端口防火墙摘要表

|**协议**|**TCP 或 UDP**|**端口**|**源 IP 地址**|**目标 IP 地址**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |运行 XMPP 网关服务的以下任一项：  <br/> •前端服务器  <br/> •前端池  <br/> |边缘服务器内部接口  <br/> |来自你的前端服务器或前端池运行的 XMPP 网关服务的出站 XMPP 流量。  <br/> **注意:** XMPP 网关和代理在 Skype for business Server 2015 中可用, 但 Skype for business Server 2019 不再支持。 有关详细信息, 请参阅[迁移 XMPP 联合身份验证](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |任意：  <br/> •董事  <br/> •控制器池  <br/> •前端服务器  <br/> •前端池  <br/> |边缘服务器内部接口  <br/> |从 Director、控制器池、前端服务器或前端池到边缘服务器内部接口的出站 SIP 流量。  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |边缘服务器内部接口  <br/> |任意：  <br/> •董事  <br/> •控制器池  <br/> •前端服务器  <br/> •前端池  <br/> |从边缘服务器内部接口到控制器、控制器池、前端服务器或前端池的入站 SIP 流量。  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |任意：  <br/> •前端服务器  <br/> •每个前端服务器  <br/>  在您的前端池中 <br/> |边缘服务器内部接口  <br/> |从前端服务器或每个前端服务器 (如果有一个前端池) 到边缘服务器内部接口的 Web 会议流量。  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |任意：  <br/> •前端服务器  <br/> •前端池  <br/> •任何使用此 Edge 服务器的 Survivable 分支装置  <br/> •任何使用此 Edge 服务器的 Survivable 分支服务器  <br/> |边缘服务器内部接口  <br/> |使用您的边缘服务器从您的前端服务器或前端池或 Survivable 分支装置或 Survivable 分支服务器的 A/V 用户进行身份验证。  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |在内部和外部用户与你的 Survivable 分支装置或 Survivable 分支服务器之间进行 A/V 媒体传输的首选路径。  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |任意   <br/> |边缘服务器内部接口  <br/> |内部和外部用户以及你的 Survivable 分支装置或 Survivable 分支服务器之间的 A/V 媒体传输的回退路径 (如果 UDP 通信不起作用)。 然后 TCP 用于文件传输和桌面共享。  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |任意：  <br/> •前端服务器保留中央管理存储  <br/> •保留中央管理存储的前端池  <br/> |边缘服务器内部接口  <br/> |将中央管理存储中的更改复制到 Edge 服务器。  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |使用 Skype for Business Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行 (ClsController) 或代理 (ClsAgent) 命令和日志收集的集中式日志服务控制器。  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |使用 Skype for Business Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行 (ClsController) 或代理 (ClsAgent) 命令和日志收集的集中式日志服务控制器。  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |使用 Skype for Business Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行 (ClsController) 或代理 (ClsAgent) 命令和日志收集的集中式日志服务控制器。  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>边缘的硬件负载平衡器端口表

我们在其各自的小节中提供了硬件负载平衡器 (HLB) 和边缘端口，因为额外的硬件稍微有点复杂。请参阅下面的表，获得此特定方案的指南：
  
#### <a name="external-port-firewall-summary-table"></a>外部端口防火墙摘要表

源 IP 地址和目标 IP 地址将包含相应的信息，这些信息可供结合 NAT 使用专用 IP 地址的用户，以及使用公用 IP 地址的用户使用。 这将涵盖 " [Skype For Business 服务器" 部分的 Edge 服务器方案](scenarios.md)中的所有排列。
  
|**角色或协议**|**TCP 或 UDP**|**目标端口或端口范围**|**源 IP 地址**|**目标 IP 地址**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|访问/HTTP  <br/> |TCP  <br/> |80  <br/> |边缘服务器访问边缘服务公共 IP 地址  <br/> |任意  <br/> |证书吊销和 CRL 检查和检索。  <br/> |
|访问/DNS  <br/> |TCP  <br/> |53  <br/> |边缘服务器访问边缘服务公共 IP 地址  <br/> |任意  <br/> |通过 TCP 的 DNS 查询。  <br/> |
|访问/DNS  <br/> |UDP  <br/> |53  <br/> |边缘服务器访问边缘服务公共 IP 地址  <br/> |任意  <br/> |通过 UDP 的 DNS 查询。  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |Edge 服务器 A/V 边缘服务 IP 地址  <br/> |任意  <br/> |这可以用于中继媒体流量。  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Edge 服务器 A/V 边缘服务公共 IP 地址  <br/> |任意  <br/> |这可以用于中继媒体流量。  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |Edge 服务器 A/V 边缘服务公共 IP 地址  <br/> |任意  <br/> |3478 出站：  <br/> •由 Skype for Business 服务器使用, 用于确定与其通信的 Edge 服务器的版本。  <br/> •用于边缘服务器之间的媒体流量。  <br/> •联盟需要。  <br/> •如果你的组织中部署了多个边缘池, 则需要。  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |Edge 服务器 A/V 边缘服务公共 IP 地址  <br/> |在端口 3478 上通过 UDP 进行的候选项 STUN/TURN 协商。  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |任意   <br/> |Edge 服务器 A/V 边缘服务公共 IP 地址  <br/> |在端口 443 上通过 TCP 进行的候选项 STUN/TURN 协商。  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |Edge 服务器 A/V 边缘服务公共 IP 地址  <br/> |任意  <br/> |在端口 443 上通过 TCP 进行的候选项 STUN/TURN 协商。  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>内部端口防火墙摘要表

|**协议**|**TCP 或 UDP**|**端口**|**源 IP 地址**|**目标 IP 地址**|**注释**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |运行 XMPP 网关服务的以下任一项：  <br/> •前端服务器  <br/> •前端池 VIP 地址运行 XMPP 网关服务  <br/> |边缘服务器内部接口  <br/> |来自你的前端服务器或前端池运行的 XMPP 网关服务的出站 XMPP 流量。  <br/><br/> **注意:** XMPP 网关和代理在 Skype for business Server 2015 中可用, 但 Skype for business Server 2019 不再支持。 有关详细信息, 请参阅[迁移 XMPP 联合身份验证](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。 |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |任意：  <br/> •前端服务器保留中央管理存储  <br/> •保留中央管理存储的前端池  <br/> |边缘服务器内部接口  <br/> |将中央管理存储中的更改复制到 Edge 服务器。  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |任意：  <br/> •前端服务器  <br/> •前端池中的每个前端服务器  <br/> |边缘服务器内部接口  <br/> |从前端服务器或每个前端服务器 (如果有一个前端池) 到边缘服务器内部接口的 Web 会议流量。  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意：  <br/> •前端服务器  <br/> •前端池中的每个前端服务器  <br/> |边缘服务器内部接口  <br/> |在内部和外部用户与你的 Survivable 分支装置或 Survivable 分支服务器之间进行 A/V 媒体传输的首选路径。  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |任意：  <br/> •前端服务器  <br/> •池中的每个前端服务器  <br/> |边缘服务器内部接口  <br/> |内部和外部用户以及你的 Survivable 分支装置或 Survivable 分支服务器之间的 A/V 媒体传输的回退路径 (如果 UDP 通信不起作用)。 然后 TCP 用于文件传输和桌面共享。  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |使用 Skype for Business Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行 (ClsController) 或代理 (ClsAgent) 命令和日志收集的集中式日志服务控制器。  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |使用 Skype for Business Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行 (ClsController) 或代理 (ClsAgent) 命令和日志收集的集中式日志服务控制器。  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |使用 Skype for Business Server Management Shell 和集中式日志记录服务 cmdlet、ClsController 命令行 (ClsController) 或代理 (ClsAgent) 命令和日志收集的集中式日志服务控制器。  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>外部接口虚拟 IP

|**角色或协议**|**TCP 或 UDP**|**目标端口或端口范围**|**源 IP 地址**|**目标 IP 地址**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> 在 Skype for Businesss Server 2019 中不受支持 |TCP  <br/> |5269  <br/> |任意  <br/> |XMPP 代理服务 (与访问边缘服务共享 IP 地址)  <br/> |XMPP 代理服务接受来自定义的 XMPP 联合的 XMPP 联系人的流量。  <br/> |
|XMPP  <br/>在 Skype for Businesss Server 2019 中不受支持 |TCP  <br/> |5269  <br/> |XMPP 代理服务 (与访问边缘服务共享 IP 地址)  <br/> |任意  <br/> |XMPP 代理服务从已定义的 XMPP 联合中的 XMPP 联系人发送流量。  <br/> |
|访问/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |任意   <br/> |**使用 NAT 的专用 IP:** Edge 服务器访问边缘服务 <br/> **公共 IP:** 边缘服务器访问边缘服务公共 IP 地址 <br/> |外部用户访问的客户端到服务器 SIP 通信。  <br/> |
|访问/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |任意  <br/> |**使用 NAT 的专用 IP:** Edge 服务器访问边缘服务 <br/> **公共 IP:** 边缘服务器访问边缘服务公共 IP 地址 <br/> |适用于使用 SIP 的联盟和公共 IM 连接。  <br/> |
|访问/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**使用 NAT 的专用 IP:** Edge 服务器访问边缘服务 <br/> **公共 IP:** 边缘服务器访问边缘服务公共 IP 地址 <br/> |任意  <br/> |适用于使用 SIP 的联盟和公共 IM 连接。  <br/> |
|Web 会议/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |任意   <br/> |**使用 NAT 的专用 IP:** Edge 服务器 Web 会议边缘服务 <br/> **公共 IP:** Edge 服务器 Web 会议边缘服务公共 IP 地址 <br/> |网络会议媒体。  <br/> |
|A/V/STUN.MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |**使用 NAT 的专用 IP:** Edge 服务器 A/V 边缘服务 <br/> **公共 IP:** Edge 服务器 A/V 边缘服务公共 IP 地址 <br/> |在端口 3478 上通过 UDP 进行的候选项 STUN/TURN 协商。  <br/> |
|A/V/STUN.MSTURN  <br/> |TCP  <br/> |443  <br/> |任意   <br/> |**使用 NAT 的专用 IP:** Edge 服务器 A/V 边缘服务 <br/> **公共 IP:** Edge 服务器 A/V 边缘服务公共 IP 地址 <br/> |在端口 443 上通过 TCP 进行的候选项 STUN/TURN 协商。  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>内部接口虚拟 IP

这里的指南稍有不同。实际上，在 HLB 场合中，我们现在建议在以下情况下，只要有通过内部 VIP 的路由即可：
  
- 如果您使用的是 Exchange 2007 或 Exchange 2010 统一消息 (UM)。
    
- 你有使用边缘的旧客户端。
    
下表提供了这些方案的指南, 但你应该能够依赖于中央管理应用商店 (CMS) 将流量路由到其识别的单个边缘服务器 (这需要 CMS 在 Edge 服务器上保持最新状态)信息 (当然)。
  
|**协议**|**TCP 或 UDP**|**端口**|**源 IP 地址**|**目标 IP 地址**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|访问/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |任意：  <br/> •董事  <br/> •控制器池 VIP 地址  <br/> •前端服务器  <br/> •前端池 VIP 地址  <br/> |边缘服务器内部接口  <br/> |从你的控制器、控制器池 VIP 地址、前端服务器或前端池 VIP 地址到 Edge 服务器内部接口的出站 SIP 流量。  <br/> |
|访问/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |Edge 服务器内部 VIP 接口  <br/> |任意：  <br/> •董事  <br/> •控制器池 VIP 地址  <br/> •前端服务器  <br/> •前端池 VIP 地址  <br/> |从你的边缘服务器内部接口到你的控制器、控制器池 VIP 地址、前端服务器或前端池 VIP 地址的入站 SIP 流量。  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |任意：  <br/> •前端服务器 IP 地址  <br/> •前端池 IP 地址  <br/> •任何使用此 Edge 服务器的 Survivable 分支装置  <br/> •任何使用此 Edge 服务器的 Survivable 分支服务器  <br/> |边缘服务器内部接口  <br/> |使用您的边缘服务器从您的前端服务器或前端池或 Survivable 分支装置或 Survivable 分支服务器的 A/V 用户进行身份验证。  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |用于内外部用户间的 A/V 媒体传输的首选路径。  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |任意   <br/> |Edge 服务器内部 VIP 接口  <br/> |在 UDP 通信不起作用的情况下，在内部用户与外部用户之间传输 A/V 媒体的回退路径。然后 TCP 用于文件传输和桌面共享。  <br/> |
