---
title: 边缘服务器环境要求Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 摘要：了解 Skype for Business Server 中边缘服务器的环境要求。
ms.openlocfilehash: 7dbd2b3c40b60f69813edbfee29a29fb003fb703
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749961"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>边缘服务器环境要求Skype for Business Server
 
**摘要：** 了解边缘服务器在Skype for Business Server。
  
需要在边缘服务器环境本身之外进行Skype for Business Server和准备。 本文将根据下面的列表，回顾需要在组织环境中进行哪些准备工作：
  
- [拓扑规划](edge-environmental-requirements.md#TopoPlan)
    
- [DNS 规划](edge-environmental-requirements.md#DNSPlan)
    
- [证书规划](edge-environmental-requirements.md#CertPlan)
    
- [端口和防火墙规划](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>拓扑规划
<a name="TopoPlan"> </a>

Skype for Business Server边缘服务器拓扑可以使用：
  
- 可路由的公共 IP 地址。
    
- 不可路由的专用 IP 地址（如果使用对称网络地址 (NAT) NAT。
    
> [!TIP]
> 可以将边缘服务器配置为使用具有每个服务不同端口的单个 IP 地址，也可以针对每个服务使用不同的 IP 地址，但使用相同的默认端口 (默认情况下该端口将为 TCP 443) 。 我们在下面 IP 地址要求部分中提供了详细信息。 
  
如果选择使用 NAT 的不可路由专用 IP 地址，请记住以下几点：
  
- 您需要在所有三个外部接口上使用可路由 **的专用** IP 地址。
    
- 您需要为传入 **和传出** 流量配置对称 NAT。 对称 NAT 是唯一可以与边缘服务器一Skype for Business Server NAT。
    
- 配置 NAT 以不更改传入源地址。 A/V 边缘服务需要能够接收传入源地址，以查找最佳媒体路径。
    
- 边缘服务器需要能够通过公用 A/V 边缘 IP 地址相互通信。 防火墙需要允许此流量。
    
- 如果使用 DNS **负载** 平衡，NAT 只能用于扩展的合并边缘服务器。 如果使用硬件负载平衡 (HLB) ，则需要在没有 **NAT** 的情况下使用可公开路由的 IP 地址。
    
只要没有使用硬件负载平衡) ，只要访问、Web 会议和 A/V 边缘接口对单一合并边缘服务器拓扑和扩展的合并边缘服务器拓扑执行对称 (NAT 的路由器或防火墙后面将没有问题。
  
### <a name="summary-of-edge-server-topology-options"></a>边缘服务器拓扑选项摘要

我们提供了多个可用于边缘服务器Skype for Business Server拓扑选项：
  
- 使用专用 IP 地址和 NAT 的单一合并边缘
    
- 使用公用 IP 地址的单一合并边缘
    
- 使用专用 IP 地址和 NAT 的扩展合并边缘
    
- 使用公用 IP 地址的扩展合并边缘
    
- 使用硬件负载平衡器扩展的合并边缘
    
为了帮助您选择一个拓扑，我们提供了下表，其中概述了每个拓扑具有的选项：
  
|**拓扑**|**高可用性**|**边缘池中的外部边缘服务器所需的其他 DNS 记录**|**会话的边缘Skype for Business Server故障转移**|**联盟会话的边缘Skype for Business Server故障转移**|
|:-----|:-----|:-----|:-----|:-----|
|使用专用 IP 地址和 NAT 的单一合并边缘  <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|使用公用 IP 地址的单一合并边缘  <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|使用专用 IP 地址和 NAT 扩展的合并边缘 (DNS 负载平衡)   <br/> |是  <br/> |是  <br/> |是  <br/> |是&sup1;  <br/> |
|使用公用 IP 地址扩展的合并边缘 (DNS 负载平衡)   <br/> |是  <br/> |是  <br/> |是  <br/> |是&sup1;  <br/> |
|使用硬件负载平衡器扩展的合并边缘  <br/> |是  <br/> |不支持（每个 VIP 一个 DNS A 记录）  <br/> |是  <br/> |是  <br/> |
   
&sup1;Exchange统一消息 (2013) Exchange 2013 或更高版本，统一消息) 使用 DNS 负载平衡进行远程用户故障转移。
  
### <a name="ip-address-requirements"></a>IP 地址要求

在基本级别，三项服务需要 IP 地址;访问边缘服务、Web 会议边缘服务和 A/V 边缘服务。 可以选择使用三个 IP 地址（每个服务一个 IP 地址）或选择使用一个 IP 地址，选择将每个服务置于不同的端口 (请查看端口和防火墙规划[](edge-environmental-requirements.md#PortFirewallPlan)部分，了解有关其中某些 ip 地址) 。 对于单个合并边缘环境，几乎可以。
  
> [!NOTE]
> 如上所述，您可以选择为这三个服务使用一个 IP 地址，然后在不同的端口运行它们。 但很明显，我们不建议这样做。 如果你的客户无法访问你在此方案中使用的备用端口，他们无法访问边缘环境的全部功能。 
  
扩展的合并拓扑可能稍微复杂一些，因此，我们来看看一些列出了 IP 地址要求的表，请记住，拓扑选择的主要决策点是高可用性和负载平衡。 高可用性需求可能会影响负载平衡选择 (在表显示后，我们将进一) 。
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>每个角色的扩展合并边缘 (IP 地址的 IP 地址) 

|**每个池的边缘服务器数量**|**DNS 负载平衡所需的 IP 地址数**|**硬件负载平衡所需的 IP 地址数**|
|:-----|:-----|:-----|
|2  <br/> |6   <br/> |3（每个 VIP 1 个）+ 6  <br/> |
|3  <br/> |9   <br/> |3（每个 VIP 1 个）+9  <br/> |
|4   <br/> |12   <br/> |3（每个 VIP 1 个）+12  <br/> |
|5  <br/> |15   <br/> |每个 VIP (3) 1 +15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>扩展合并边缘的 IP 地址 (所有角色的单个 IP 地址) 

|**每个池的边缘服务器数量**|**DNS 负载平衡所需的 IP 地址数**|**硬件负载平衡所需的 IP 地址数**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1（每个 VIP 1 个）2  <br/> |
|3  <br/> |3  <br/> |1（每个 VIP 1 个）+ 3  <br/> |
|4   <br/> |4   <br/> |1（每个 VIP 1 个）4  <br/> |
|5  <br/> |5  <br/> |1（每个 VIP 1 个）5  <br/> |
   
让我们看一下在规划时要思考的一些其他内容。
  
- **高可用性**：如果在部署中需要高可用性，则应该在池中至少部署两台边缘服务器。 值得注意的是，单个边缘池最多支持 12 台边缘服务器 (但拓扑生成器允许您最多添加 20 台，这未经过测试或不受支持，因此我们建议您不要) 。 如果需要 12 台以上的边缘服务器，应为它们创建其他边缘池。
    
- **硬件负载平衡**：我们建议在大多数情况下使用 DNS 负载平衡。 当然，硬件负载平衡也受支持，但尤其是通过 DNS 负载平衡的单个方案需要硬件负载平衡：
    
  - 对 2007 Exchange 2010 Exchange 2010 (（没有 SP) 统一消息 (UM) ）的外部访问。
    
- **DNS 负载平衡**：对于 UM，Exchange 2010 SP1 及更高版本支持 DNS 负载平衡。 请注意，如果需要对早期版本的 Exchange 进行 DNS 负载平衡，它将正常工作，但所有流量将转到池中的第一台服务器，如果不可用，该流量随后将失败。
    
    如果与使用：
- Skype for Business Server 2015 年：
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft 365 或 Office 365
- Skype for Business Server 2019 年 10 月：
    - Lync Server 2013
    - Skype for Business Server 2015
    - Microsoft 365 或 Office 365
    
## <a name="dns-planning"></a>DNS 规划
<a name="DNSPlan"> </a>

在部署边缘Skype for Business Server时，正确准备 DNS 至关重要。 在正确的记录就位后，部署将更加简单。 希望你已选择上一节中的拓扑，因为我们将做一个概述，然后列出几个表，其中概述了这些方案的 DNS 记录。 如果需要，我们还将针对 Skype for Business Server 进行一些高级边缘服务器[DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md)规划，以进行更深入的阅读。
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>单一合并边缘服务器方案的 DNS 记录

这些将是使用公用 IP 或具有 NAT 的专用 IP 的 SINGE 边缘服务器所需的 DNS 记录。 由于这是示例数据，我们将提供示例 IP，以便更轻松地创建自己的条目：
  
- 内部网络适配器：172.25.33.10 (未分配默认) 
    
    > [!NOTE]
    > 确保存在从包含边缘内部接口的网络到包含运行 Skype for Business Server 或 Lync Server 2013 客户端 (例如，从 172.25.33.0 到 192.168.10.0) 的任何网络的路由。 
  
- 外部网络适配器：
    
  - 公共 IP：
    
  - 访问边缘：131.107.155.10 (此为主网关，默认网关设置为公共路由器，例如：131.107.155.1) 
    
  - Web 会议边缘：131.107.155.20 (辅助) 
    
  - A/V 边缘：131.107.155.30 (辅助) 
    
  Web 会议和 A/V 边缘公用 IP 地址是 Windows Server 中"本地区域连接属性"的 Internet 协议版本 4 (TCP/IPv4) 和 Internet 协议版本 6 (TCP/IPv6) 属性的高级部分中的附加 (辅助) IP 地址。
    
  - 专用 IP：
    
  - 访问边缘：10.45.16.10 (此为主网关，默认网关设置为路由器，例如：10.45.16.1) 
    
  - Web 会议边缘：10.45.16.20 (辅助) 
    
  - A/V 边缘：10.45.16.30 (辅助) 
    
Web 会议和 A/V 边缘公用 IP 地址是 Windows Server 中"本地区域连接属性"的 Internet 协议版本 4 (TCP/IPv4) 和 Internet 协议版本 6 (TCP/IPv6) 属性的高级部分中的附加 (辅助) IP 地址。
  
> [!TIP]
>此处存在其他可能的配置：
  
- 您可以在外部网络适配器上使用一个 IP 地址。 我们不建议这样做，因为你将需要区分使用不同端口 (可在 Skype for Business Server) 但有些防火墙可能会阻止备用端口。 有关详细信息，请参阅端口 [和](edge-environmental-requirements.md#PortFirewallPlan) 防火墙规划部分。
    
- 可以有三个外部网络适配器，而不是一个，并为每个适配器分配一个服务 IP。 为什么这样做？ 它会分隔这些服务，如果出现问题，更易于排查故障，并可能让其他服务在解决问题时继续工作。
    
|**位置**|**类型**|**Port**|**FQDN 或 DNS 记录**|**IP 地址或 FQDN**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |记录  <br/> |不适用  <br/> |sip.contoso.com  <br/> |**公共** ：131.107.155.10 <br/>  private：10.45.16.10 <br/> |访问边缘服务的外部接口。 对于具有特定用户的用户，每个 SIP 域Skype for Business一个。  <br/> |
|外部 DNS  <br/> |记录  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**公共** ：131.107.155.20 <br/>  private：10.45.16.20 <br/> |Web 会议边缘服务的外部接口。  <br/> |
|外部 DNS  <br/> |记录  <br/> |NA  <br/> |av.contoso.com  <br/> |**公共** ：131.107.155.30 <br/>  private：10.45.16.30 <br/> |A/V 边缘服务的外部接口。  <br/> |
|外部 DNS  <br/> |SRV record － SRV 记录  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |访问边缘服务的外部接口。 若要使 Lync Server 2013 Skype for Business Server Lync Server 2010 客户端在外部工作，需要此 SRV 记录。 对于具有特定用户的用户，每个域Skype for Business一个。  <br/> |
|外部 DNS  <br/> |SRV record － SRV 记录  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |访问边缘服务的外部接口。 名为"允许的 SIP 域"的联盟伙伴的自动 DNS 发现需要此 SRV 记录。 对于具有特定用户的用户，每个域Skype for Business一个。  <br/> |
|内部 DNS  <br/> |记录  <br/> |不适用  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |合并边缘的内部接口。  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>扩展的 DNS 和硬件边缘服务器方案的 DNS 记录

这些将是使用公用 IP 或具有 NAT 的专用 IP 的Singe Edge Server 所需的 DNS 记录。 由于这是示例数据，我们将提供示例 IP，以便更轻松地创建自己的条目：
  
- 内部网络适配器：
    
  - 节点 1：172.25.33.10 (未分配默认网关) 
    
  - 节点 2：172.25.33.11 (未分配默认网关) 
    
    > [!NOTE]
    > 确保存在从包含边缘内部接口的网络到包含运行 Skype for Business Server 或 Lync Server 2013 客户端 (例如，从 172.25.33.0 到 192.168.10.0) 的任何网络的路由。 
  
- 外部网络适配器：
    
  - 节点 1
    
     - 公共 IP：
    
        - 访问边缘：131.107.155.10 (此为主网关，默认网关设置为公共路由器，例如：131.107.155.1) 
    
        - Web 会议边缘：131.107.155.20 (辅助) 
    
        - A/V 边缘：131.107.155.30 (辅助) 
    
          Web 会议和 A/V 边缘公用 IP 地址是 Windows Server 中本地区域连接属性的 Internet 协议版本 4 (TCP/IPv4) 和 Internet 协议版本 6 (TCP/IPv6) 属性的"高级"部分中的其他 (辅助) IP 地址。
    
    - 专用 IP：
    
         - 访问边缘：10.45.16.10 (此为主网关，默认网关设置为路由器，例如：10.45.16.1) 
    
         - Web 会议边缘：10.45.16.20 (辅助) 
    
         - A/V 边缘：10.45.16.30 (辅助) 
    
      Web 会议和 A/V 边缘公用 IP 地址是 Windows Server 中本地区域连接属性的 Internet 协议版本 4 (TCP/IPv4) 和 Internet 协议版本 6 (TCP/IPv6) 属性的"高级"部分中的其他 (辅助) IP 地址。
    
  - 节点 2
    
    - 公共 IP：
    
      - 访问边缘：131.107.155.11 (此为主网关，默认网关设置为公共路由器，例如：131.107.155.1) 
    
      - Web 会议边缘：131.107.155.21 (辅助) 
    
      - A/V 边缘：131.107.155.31 (辅助) 
    
      Web 会议和 A/V 边缘公用 IP 地址是 Windows Server 中本地区域连接属性的 Internet 协议版本 4 (TCP/IPv4) 和 Internet 协议版本 6 (TCP/IPv6) 属性的"高级"部分中的其他 (辅助) IP 地址。
    
  - 专用 IP：
    
    - 访问边缘：10.45.16.11 (此为主网关，默认网关设置为路由器，例如：10.45.16.1) 
    
    - Web 会议边缘：10.45.16.21 (辅助) 
    
    - A/V 边缘：10.45.16.31 (辅助) 
    
      Web 会议和 A/V 边缘公用 IP 地址是 Windows Server 中本地区域连接属性的 Internet 协议版本 4 (TCP/IPv4) 和 Internet 协议版本 6 (TCP/IPv6) 属性的"高级"部分中的其他 (辅助) IP 地址。
    
此处存在其他可能的配置：
  
- 您可以在外部网络适配器上使用一个 IP 地址。 我们不建议这样做，因为你将需要区分使用不同端口 (可在 Skype for Business Server) 但有些防火墙可能会阻止备用端口。 有关详细信息，请参阅端口 [和](edge-environmental-requirements.md#PortFirewallPlan) 防火墙规划部分。
    
- 可以有三个外部网络适配器，而不是一个，并为每个适配器分配一个服务 IP。 为什么这样做？ 它会分隔这些服务，如果出现问题，更易于排查故障，并可能让其他服务在解决问题时继续工作。
    
|**位置**|**类型**|**Port**|**FQDN 或 DNS 记录**|**IP 地址或 FQDN**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |记录  <br/> |NA  <br/> |sip.contoso.com  <br/> |**公共** ：131.107.155.10 和 131.107.155.11 <br/>  private：10.45.16.10 和 10.45.16.11 <br/> |访问边缘服务的外部接口。 对于具有特定用户的用户，每个 SIP 域Skype for Business一个。  <br/> |
|外部 DNS  <br/> |记录  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**公共** ：131.107.155.20 和 131.107.155.21 <br/>  private：10.45.16.20 和 10.45.16.21 <br/> |Web 会议边缘服务的外部接口。  <br/> |
|外部 DNS  <br/> |记录  <br/> |NA  <br/> |av.contoso.com  <br/> | public：131.107.155.30 和 131.107.155.31 <br/>  private：10.45.16.30 和 10.45.16.31 <br/> |A/V 边缘服务的外部接口。  <br/> |
|外部 DNS  <br/> |SRV record － SRV 记录  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |访问边缘服务的外部接口。 若要使 Lync Server 2013 Skype for Business Server Lync Server 2010 客户端在外部工作，需要此 SRV 记录。 每个具有此权限的域都需要一Skype for Business。  <br/> |
|外部 DNS  <br/> |SRV record － SRV 记录  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |访问边缘服务的外部接口。 名为"允许的 SIP 域"的联盟伙伴的自动 DNS 发现需要此 SRV 记录。 每个具有此权限的域都需要一Skype for Business。  <br/> |
|内部 DNS  <br/> |记录  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 和 172.25.33.11  <br/> |合并边缘的内部接口。  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>联盟的 DNS 记录 (所有方案) 

|**位置**|**类型**|**Port**|**FQDN**|**FQDN 主机记录**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |sip.contoso.com  <br/> |自动 DNS 发现所需的 SIP 访问边缘外部接口。 由其他潜在的联盟伙伴使用。 它也称为"允许 SIP 域"。 对于具有特定用户的每个 SIP 域，都需要Skype for Business之一。  <br/><br/> **注意：** 你需要此 SRV 记录实现移动和推送通知交换所。 <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>可扩展消息传递和状态协议的 DNS 记录

|**位置**|**类型**|**Port**|**FQDN**|**IP 地址或 FQDN 主机记录**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |xmpp.contoso.com  <br/> |访问边缘服务或边缘池上的 XMPP 代理接口。 您需要根据需要对启用了 XMPP Skype for Business Server的所有内部 SIP 域重复此操作，允许通过：  <br/> • 全局策略  <br/> • 启用用户的网站策略  <br/> • 应用于启用策略的用户Skype for Business Server策略  <br/> 还需要在 XMPP 联盟用户策略中配置允许的 XMPP 策略。  <br/> |
|外部 DNS  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |承载 XMPP 代理服务的边缘服务器或边缘池中的访问边缘服务的 IP 地址  <br/> |这指向承载 XMPP 代理服务的边缘服务器或边缘池上的访问边缘服务。 通常，你创建的 SRV 记录将指向此主机 (A 或 AAAA) 记录。  <br/> |
   
> [!NOTE]
> XMPP 网关和代理在 Skype for Business Server 2015 中可用，但在 2019 年 2 月不再Skype for Business Server支持。 有关详细信息 [，请参阅迁移 XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 联盟。

## <a name="certificate-planning"></a>证书规划
<a name="CertPlan"> </a>

Skype for Business Server服务器之间以及从服务器到客户端的安全加密通信使用证书。 正如您预期，您的证书需要使服务器的 DNS 记录与证书上的任何主题名称 (SN) 和主题备用名称 (SAN) 匹配。 这现在将在规划阶段工作，以确保你在 DNS 中为证书的 SN 和 SAN 条目注册了正确的 FQDN。
  
我们将单独讨论外部和内部证书需求，然后查看提供这两项要求的表。
  
### <a name="external-certificates"></a>外部证书

分配给外部边缘服务器接口的证书至少需要由公共证书颁发机构 (CA) 。 我们不建议你使用特定 CA，但我们有 CA 列表，即统一 [通信](../../../SfbPartnerCertification/certification/services-ssl.md) 证书合作伙伴，你可以查看这些合作伙伴，看看是否列出了首选 CA。
  
何时需要向 CA 提交此公共证书的请求，如何执行？ 有两种方法可以完成此操作：
  
- 可以先完成边缘服务器的Skype for Business Server，然后再执行边缘服务器部署。 部署Skype for Business Server向导将具有生成证书请求的步骤，然后你可以将其发送给所选的 CA。
    
- 如果与业务需求或部署Windows PowerShell更内联，则您还可以使用命令生成此请求。
    
- 最后，CA 可能有其自己的提交过程，这也可能涉及Windows PowerShell或其他方法。 在这种情况下，除了此处提供的信息供你参考之外，你还需要依赖其文档。
    
获得证书后，你将需要继续，并将其分配给以下Skype for Business Server：
  
- 访问边缘服务接口
    
- Web 会议边缘服务接口
    
- 音频/视频 (身份验证服务不会将此与 A/V 边缘服务混淆，因为该服务不使用证书加密音频流和视频流) 
    
> [!IMPORTANT]
> 如果所有边缘 (属于同一边缘服务器池) 则需要具有与媒体中继身份验证服务相同的私钥完全相同的证书。 
  
### <a name="internal-certificates"></a>内部证书

对于内部边缘服务器接口，可以使用公共 CA 颁发的公共证书，或组织内部 CA 颁发的证书。 关于内部证书，要记住的一点就是它使用 SN 条目，没有 SAN 条目，因此你无需担心内部证书上的 SAN。
  
### <a name="required-certificates-table"></a>所需证书表

我们在此处提供了一个表，可帮助你提出请求。 此处的 FQDN 条目仅适用于示例域。 你将需要根据你自己的私有域和公共域提出请求，但下面是我们使用的指南：
  
- contoso <span></span> .com：公共 FQDN
    
- fabrikam .com：第二个公共 FQDN (，如果有多个 SIP 域，添加为要请求的) <span></span>
    
- Contoso <span></span> .net：内部域
    
#### <a name="edge-certificate-table"></a>边缘证书表

无论你是执行单个边缘服务器还是边缘池，证书都需要这样做：
  
|**组件**|**使用者名称 (SN)**|**SAN 或 SAN () 名称**|**备注**|
|:-----|:-----|:-----|:-----|
|外部边缘  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |这是您需要从公共 CA 请求的证书。 需要将其分配给以下项的外部边缘接口：  <br/> • 访问边缘  <br/> • Web 会议边缘  <br/> • 音频/视频身份验证  <br/> <br/>好消息是，根据在拓扑生成器中为此部署定义的定义，在提交请求后，将 PIN 自动添加到证书请求中，从而添加到证书。 你只需为任何其他 SIP 域或需要支持的其他条目添加 SAN 条目。 为什么 sip.contoso.com 复制此实例？ 这会自动发生，并且需要操作才能正常工作。  <br/><br/> **注意：** 此证书还可用于公共即时消息连接。 你无需对它执行任何不同的工作，但在本文档的早期版本中，它作为单独的表列出，现在没有。 <br/> |
|内部边缘  <br/> |sfbedge.contoso.com  <br/> |不适用  <br/> |可以从公共 CA 或内部 CA 获取此证书。 它将需要包含服务器 EKU (增强型密钥) ，并将它分配给内部边缘接口。  <br/> |
   
如果您需要用于可扩展消息传递和状态协议 (XMPP) 的证书，该证书看起来与上面的外部边缘表条目相同，但将具有以下两个附加 SAN 条目：
  
- xmpp。 <span></span>contoso <span></span> .com
    
- \*.contoso <span></span> .com
    
请记住，XMPP 当前仅在 Skype for Business Server for Google Talk 中受支持，如果你希望或需要将 XMPP 用于任何其他内容，你需要向涉及的第三方供应商确认该功能。
  
## <a name="port-and-firewall-planning"></a>端口和防火墙规划
<a name="PortFirewallPlan"> </a>

正确规划边缘服务器部署的端口和Skype for Business Server可以节省几天或几周的故障排除和压力。 因此，我们将列出几个表，这些表将指示我们的协议用法以及对于 NAT 和公共 IP 方案需要开放、入站和出站的端口。 我们还会为 HLB 解决方案中的硬件负载平衡 (表) 进一步的指导。 有关详细信息，我们还有一些边缘服务器方案，Skype for Business Server查看您的特定部署问题。 [](scenarios.md)
  
### <a name="general-protocol-usage"></a>常规协议用法

在查看外部和内部防火墙的摘要表之前，让我们也考虑下表：
  
|**音频/视频传输**|**使用情况**|
|:-----|:-----|
|UDP  <br/> |音频和视频的首选传输层协议。  <br/> |
|TCP  <br/> |音频和视频的回退传输层协议。  <br/> 应用程序共享到 Skype for Business Server Lync Server 2013 和 Lync Server 2010 所需的传输层协议。  <br/> 文件传输到 Skype for Business Server Lync Server 2013 和 Lync Server 2010 所需的传输层协议。  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>外部端口防火墙摘要表

源 IP 地址和目标 IP 地址将包含将专用 IP 地址与 NAT 一同使用的用户以及使用公用 IP 地址的用户的信息。 这将在"边缘服务器"部分介绍边缘[服务器方案中](scenarios.md)Skype for Business Server排列。
  
|**角色或协议**|**TCP 或 UDP**|**目标端口或端口范围**|**源 IP 地址**|**目标 IP 地址**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> 2019 Skype for Business Server中不受支持 |TCP  <br/> |5269  <br/> |任何  <br/> |XMPP 代理服务 (访问边缘服务共享 IP 地址  <br/> |XMPP 代理服务接受来自定义的 XMPP 联盟中的 XMPP 联系人的流量。  <br/> |
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |**使用 NAT 的专用 IP：** 边缘服务器访问边缘服务 <br/> **公用 IP：** 边缘服务器访问边缘服务公用 IP 地址 <br/> |任何  <br/> |证书吊销和 CRL 检查和检索。  <br/> |
|访问/DNS  <br/> |TCP  <br/> |53  <br/> |**使用 NAT 的专用 IP：** 边缘服务器访问边缘服务 <br/> **公用 IP：** 边缘服务器访问边缘服务公用 IP 地址 <br/> |任何  <br/> |通过 TCP 的 DNS 查询。  <br/> |
|访问/DNS  <br/> |UDP  <br/> |53  <br/> |**使用 NAT 的专用 IP：** 边缘服务器访问边缘服务 <br/> **公用 IP：** 边缘服务器访问边缘服务公用 IP 地址 <br/> |任何  <br/> |通过 UDP 的 DNS 查询。  <br/> |
|访问/SIP (TLS)   <br/> |TCP  <br/> |443  <br/> |任何  <br/> |**使用 NAT 的专用 IP：** 边缘服务器访问边缘服务 <br/> **公用 IP：** 边缘服务器访问边缘服务公用 IP 地址 <br/> |用于外部用户访问的客户端到服务器 SIP 流量。  <br/> |
|MTLS (访问/SIP)   <br/> |TCP  <br/> |5061  <br/> |任何  <br/> |**使用 NAT 的专用 IP：** 边缘服务器访问边缘服务 <br/> **公用 IP：** 边缘服务器访问边缘服务公用 IP 地址 <br/> |对于使用 SIP 的联合和公共 IM 连接。  <br/> |
|MTLS (访问/SIP)   <br/> |TCP  <br/> |5061  <br/> |**使用 NAT 的专用 IP：** 边缘服务器访问边缘服务 <br/> **公用 IP：** 边缘服务器访问边缘服务公用 IP 地址 <br/> |任何  <br/> |对于使用 SIP 的联合和公共 IM 连接。  <br/> |
|Web 会议/PSOM (TLS)   <br/> |TCP  <br/> |443  <br/> |任何  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 Web 会议边缘服务 <br/> **公用 IP：** 边缘服务器 Web 会议边缘服务公共 IP 地址 <br/> |Web 会议媒体。  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 A/V 边缘服务 <br/> **公用 IP：** 边缘服务器 A/V 边缘服务公用 IP 地址 <br/> |任何  <br/> |这用于中继媒体流量。  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 A/V 边缘服务 <br/> **公用 IP：** 边缘服务器 A/V 边缘服务公用 IP 地址 <br/> |任何  <br/> |这用于中继媒体流量。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP  <br/> |3478  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 A/V 边缘服务 <br/> **公用 IP：** 边缘服务器 A/V 边缘服务公用 IP 地址 <br/> |任何  <br/> |3478 出站为：  <br/> • 由Skype for Business Server用于确定其通信的边缘服务器的版本。  <br/> • 用于边缘服务器之间的媒体流量。  <br/> • 与 Lync Server 2010 联盟的必需项。  <br/> • 在组织中部署多个边缘池时需要。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP  <br/> |3478  <br/> |任何  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 A/V 边缘服务 <br/> **公用 IP：** 边缘服务器 A/V 边缘服务公用 IP 地址 <br/> |通过端口 3478 上的 UDP 进行候选项 STUN/TURN 协商。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP  <br/> |443  <br/> |任何  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 A/V 边缘服务 <br/> **公用 IP：** 边缘服务器 A/V 边缘服务公用 IP 地址 <br/> |端口 443 上通过 TCP 的候选项的 STUN/TURN 协商。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP  <br/> |443  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 A/V 边缘服务 <br/> **公用 IP：** 边缘服务器 A/V 边缘服务公用 IP 地址 <br/> |任何  <br/> |端口 443 上通过 TCP 的候选项的 STUN/TURN 协商。  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>内部端口防火墙摘要表

|**协议**|**TCP 或 UDP**|**Port**|**源 IP 地址**|**目标 IP 地址**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |运行 XMPP 网关服务的以下任一项：  <br/> • 前端服务器  <br/> • 前端池  <br/> |边缘服务器内部接口  <br/> |来自在前端服务器或前端池上运行的 XMPP 网关服务的出站 XMPP 流量。  <br/> **注意：** XMPP 网关和代理在 Skype for Business Server 2015 中可用，但在 2019 年 2 月不再Skype for Business Server支持。 有关详细信息 [，请参阅迁移 XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 联盟。|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |任意：  <br/> • 控制器  <br/> • 控制器池  <br/> • 前端服务器  <br/> • 前端池  <br/> |边缘服务器内部接口  <br/> |从控制器、控制器池、前端服务器或前端池到边缘服务器内部接口的出站 SIP 流量。  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |边缘服务器内部接口  <br/> |任意：  <br/> • 控制器  <br/> • 控制器池  <br/> • 前端服务器  <br/> • 前端池  <br/> |从边缘服务器内部接口到控制器、控制器池、前端服务器或前端池的入站 SIP 流量。  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |任意：  <br/> • 前端服务器  <br/> • 每台前端服务器  <br/>  在前端池中 <br/> |边缘服务器内部接口  <br/> |前端服务器或每台前端服务器的 Web 会议流量 (前端池) 边缘服务器内部接口。  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |任意：  <br/> • 前端服务器  <br/> • 前端池  <br/> • 使用此边缘服务器的任何 Survivable Branch Appliance  <br/> • 使用此边缘服务器的任何 Survivable Branch Server  <br/> |边缘服务器内部接口  <br/> |使用边缘服务器对来自前端服务器或前端池、Survivable Branch Appliance 或 Survivable Branch Server 的 A/V 用户的身份验证。  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |任何  <br/> |边缘服务器内部接口  <br/> |在内部和外部用户与 Survivable Branch Appliance 或 Survivable Branch Server 之间传输 A/V 媒体的首选路径。  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |任何  <br/> |边缘服务器内部接口  <br/> |A/V 媒体在内部和外部用户与 Survivable Branch Appliance 或 Survivable Branch Server 之间传输的回退路径（如果 UDP 通信不起作用）。 然后 TCP 用于文件传输和桌面共享。  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |任意：  <br/> • 保留中央管理存储的前端服务器  <br/> • 存放中央管理存储的前端池  <br/> |边缘服务器内部接口  <br/> |将中央管理存储中的更改复制到边缘服务器。  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |任何  <br/> |边缘服务器内部接口  <br/> |使用 Skype for Business Server 命令行管理程序和集中日志记录服务 cmdlet 的集中日志记录服务控制器、ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合。  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |任何  <br/> |边缘服务器内部接口  <br/> |使用 Skype for Business Server 命令行管理程序和集中日志记录服务 cmdlet 的集中日志记录服务控制器、ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合。  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |任何  <br/> |边缘服务器内部接口  <br/> |使用 Skype for Business Server 命令行管理程序和集中日志记录服务 cmdlet 的集中日志记录服务控制器、ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合。  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>边缘端口表的硬件负载平衡器

我们将为硬件负载平衡器提供 (HLB) 和边缘端口各自的部分，因为其他硬件会稍微复杂一些。 有关此特定方案的指南，请参阅下表：
  
#### <a name="external-port-firewall-summary-table"></a>外部端口防火墙摘要表

源 IP 地址和目标 IP 地址将包含将专用 IP 地址与 NAT 一同使用的用户以及使用公用 IP 地址的用户的信息。 这将在"边缘服务器"部分介绍边缘[服务器方案中](scenarios.md)Skype for Business Server排列。
  
|**角色或协议**|**TCP 或 UDP**|**目标端口或端口范围**|**源 IP 地址**|**目标 IP 地址**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |边缘服务器访问边缘服务公用 IP 地址  <br/> |任何  <br/> |证书吊销和 CRL 检查和检索。  <br/> |
|访问/DNS  <br/> |TCP  <br/> |53  <br/> |边缘服务器访问边缘服务公用 IP 地址  <br/> |任何  <br/> |通过 TCP 的 DNS 查询。  <br/> |
|访问/DNS  <br/> |UDP  <br/> |53  <br/> |边缘服务器访问边缘服务公用 IP 地址  <br/> |任何  <br/> |通过 UDP 的 DNS 查询。  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |边缘服务器 A/V 边缘服务 IP 地址  <br/> |任何  <br/> |这用于中继媒体流量。  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |边缘服务器 A/V 边缘服务公用 IP 地址  <br/> |任何  <br/> |这用于中继媒体流量。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP  <br/> |3478  <br/> |边缘服务器 A/V 边缘服务公用 IP 地址  <br/> |任何  <br/> |3478 出站为：  <br/> • 由 Skype for Business Server用于确定其通信的边缘服务器的版本。  <br/> • 用于边缘服务器之间的媒体流量。  <br/> • 联盟的必需项。  <br/> • 在组织中部署多个边缘池时需要。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP  <br/> |3478  <br/> |任何  <br/> |边缘服务器 A/V 边缘服务公用 IP 地址  <br/> |通过端口 3478 上的 UDP 进行候选项 STUN/TURN 协商。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP  <br/> |443  <br/> |任何  <br/> |边缘服务器 A/V 边缘服务公用 IP 地址  <br/> |端口 443 上通过 TCP 的候选项的 STUN/TURN 协商。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP  <br/> |443  <br/> |边缘服务器 A/V 边缘服务公用 IP 地址  <br/> |任何  <br/> |端口 443 上通过 TCP 的候选项的 STUN/TURN 协商。  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>内部端口防火墙摘要表

|**协议**|**TCP 或 UDP**|**Port**|**源 IP 地址**|**目标 IP 地址**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |运行 XMPP 网关服务的以下任一项：  <br/> • 前端服务器  <br/> • 运行 XMPP 网关服务的前端池 VIP 地址  <br/> |边缘服务器内部接口  <br/> |来自在前端服务器或前端池上运行的 XMPP 网关服务的出站 XMPP 流量。  <br/><br/> **注意：** XMPP 网关和代理在 Skype for Business Server 2015 中可用，但在 2019 年 2 月不再Skype for Business Server支持。 有关详细信息 [，请参阅迁移 XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 联盟。 |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |任意：  <br/> • 保留中央管理存储的前端服务器  <br/> • 存放中央管理存储的前端池  <br/> |边缘服务器内部接口  <br/> |将中央管理存储中的更改复制到边缘服务器。  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |任意：  <br/> • 前端服务器  <br/> • 前端池中的每个前端服务器  <br/> |边缘服务器内部接口  <br/> |前端服务器或每个前端服务器的 Web 会议流量 (前端池) 边缘服务器内部接口。  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意：  <br/> • 前端服务器  <br/> • 前端池中的每个前端服务器  <br/> |边缘服务器内部接口  <br/> |在内部和外部用户与 Survivable Branch Appliance 或 Survivable Branch Server 之间传输 A/V 媒体的首选路径。  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |任意：  <br/> • 前端服务器  <br/> • 池中的每台前端服务器  <br/> |边缘服务器内部接口  <br/> |A/V 媒体在内部和外部用户与 Survivable Branch Appliance 或 Survivable Branch Server 之间传输的回退路径（如果 UDP 通信不起作用）。 然后 TCP 用于文件传输和桌面共享。  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |任何  <br/> |边缘服务器内部接口  <br/> |使用 Skype for Business Server 命令行管理程序和集中日志记录服务 cmdlet 的集中日志记录服务控制器、ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合。  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |任何  <br/> |边缘服务器内部接口  <br/> |使用 Skype for Business Server 命令行管理程序和集中日志记录服务 cmdlet 的集中日志记录服务控制器、ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合。  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |任何  <br/> |边缘服务器内部接口  <br/> |使用 Skype for Business Server 命令行管理程序和集中日志记录服务 cmdlet 的集中日志记录服务控制器、ClsController 命令行 (ClsController.exe) 或代理 (ClsAgent.exe) 命令和日志集合。  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>外部接口 虚拟 IP

|**角色或协议**|**TCP 或 UDP**|**目标端口或端口范围**|**源 IP 地址**|**目标 IP 地址**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> 在 Skype for Businesss Server 2019 中不受支持 |TCP  <br/> |5269  <br/> |任何  <br/> |XMPP 代理服务 (访问边缘服务共享 IP 地址)   <br/> |XMPP 代理服务接受来自定义的 XMPP 联盟中的 XMPP 联系人的流量。  <br/> |
|XMPP  <br/>在 Skype for Businesss Server 2019 中不受支持 |TCP  <br/> |5269  <br/> |XMPP 代理服务 (访问边缘服务共享 IP 地址)   <br/> |任何  <br/> |XMPP 代理服务从定义的 XMPP 联盟中的 XMPP 联系人发送流量。  <br/> |
|访问/SIP (TLS)   <br/> |TCP  <br/> |443  <br/> |任何  <br/> |**使用 NAT 的专用 IP：** 边缘服务器访问边缘服务 <br/> **公用 IP：** 边缘服务器访问边缘服务公用 IP 地址 <br/> |用于外部用户访问的客户端到服务器 SIP 流量。  <br/> |
|MTLS (访问/SIP)   <br/> |TCP  <br/> |5061  <br/> |任何  <br/> |**使用 NAT 的专用 IP：** 边缘服务器访问边缘服务 <br/> **公用 IP：** 边缘服务器访问边缘服务公用 IP 地址 <br/> |对于使用 SIP 的联合和公共 IM 连接。  <br/> |
|MTLS (访问/SIP)   <br/> |TCP  <br/> |5061  <br/> |**使用 NAT 的专用 IP：** 边缘服务器访问边缘服务 <br/> **公用 IP：** 边缘服务器访问边缘服务公用 IP 地址 <br/> |任何  <br/> |对于使用 SIP 的联合和公共 IM 连接。  <br/> |
|Web 会议/PSOM (TLS)   <br/> |TCP  <br/> |443  <br/> |任何  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 Web 会议边缘服务 <br/> **公用 IP：** 边缘服务器 Web 会议边缘服务公共 IP 地址 <br/> |Web 会议媒体。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP  <br/> |3478  <br/> |任何  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 A/V 边缘服务 <br/> **公用 IP：** 边缘服务器 A/V 边缘服务公用 IP 地址 <br/> |通过端口 3478 上的 UDP 进行候选项 STUN/TURN 协商。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP  <br/> |443  <br/> |任何  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 A/V 边缘服务 <br/> **公用 IP：** 边缘服务器 A/V 边缘服务公用 IP 地址 <br/> |端口 443 上通过 TCP 的候选项的 STUN/TURN 协商。  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>内部接口虚拟 IP

此处的指南将有所不同。 实际上，在 HLB 情况下，我们现在建议仅在以下情况下通过内部 VIP 路由：
  
- 如果您使用的是 um Exchange 2007 或 Exchange 2010 统一 (2010) 。
    
- 如果你有使用 Edge 的旧客户端。
    
下表提供了这些方案的指导，但在其他情况下，您应该能够依赖中央管理存储 (CMS) 将流量路由到它知道 (这确实要求 CMS 在边缘服务器信息（当然) ）上保持最新。
  
|**协议**|**TCP 或 UDP**|**Port**|**源 IP 地址**|**目标 IP 地址**|**备注**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|MTLS (访问/SIP)   <br/> |TCP  <br/> |5061  <br/> |任意：  <br/> • 控制器  <br/> • 控制器池 VIP 地址  <br/> • 前端服务器  <br/> • 前端池 VIP 地址  <br/> |边缘服务器内部接口  <br/> |从控制器、控制器池 VIP 地址、前端服务器或前端池 VIP 地址到边缘服务器内部接口的出站 SIP 流量。  <br/> |
|MTLS (访问/SIP)   <br/> |TCP  <br/> |5061  <br/> |边缘服务器内部 VIP 接口  <br/> |任意：  <br/> • 控制器  <br/> • 控制器池 VIP 地址  <br/> • 前端服务器  <br/> • 前端池 VIP 地址  <br/> |从边缘服务器内部接口到控制器、控制器池 VIP 地址、前端服务器或前端池 VIP 地址的入站 SIP 流量。  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |任意：  <br/> • 前端服务器 IP 地址  <br/> • 前端池 IP 地址  <br/> • 使用此边缘服务器的任何 Survivable Branch Appliance  <br/> • 使用此边缘服务器的任何 Survivable Branch Server  <br/> |边缘服务器内部接口  <br/> |使用边缘服务器对来自前端服务器或前端池、Survivable Branch Appliance 或 Survivable Branch Server 的 A/V 用户的身份验证。  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |任何  <br/> |边缘服务器内部接口  <br/> |在内部和外部用户之间传输 A/V 媒体的首选路径。  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |任何  <br/> |边缘服务器内部 VIP 接口  <br/> |UDP 通信不起作用时，在内部和外部用户之间传输 A/V 媒体的回退路径。 然后 TCP 用于文件传输和桌面共享。  <br/> |