---
title: Skype for Business Server 中的边缘服务器环境要求
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
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: 摘要：了解 Skype for Business Server 中的边缘服务器的环境要求。
ms.openlocfilehash: 8e2ec6d2afc53648fe50af4cd5ab02ad21d11643
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219922"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>Skype for Business Server 中的边缘服务器环境要求
 
**摘要：** 了解 Skype for Business Server 中的边缘服务器的环境要求。
  
需要在 Skype for Business Server Edge 服务器环境本身之外进行大量的规划和准备工作。 在本文中，我们将回顾需要在组织环境中进行的准备工作，如下面的列表所示：
  
- [拓扑规划](edge-environmental-requirements.md#TopoPlan)
    
- [DNS 规划](edge-environmental-requirements.md#DNSPlan)
    
- [证书规划](edge-environmental-requirements.md#CertPlan)
    
- [端口和防火墙规划](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>拓扑规划
<a name="TopoPlan"> </a>

Skype for Business Server Edge 服务器拓扑可使用：
  
- 可路由的公用 IP 地址。
    
- 不可路由的专用 IP 地址（如果使用**对称**网络地址转换（NAT））。
    
> [!TIP]
> 可以将您的边缘服务器配置为对每个服务使用具有不同端口的单个 IP 地址，也可以对每个服务使用不同的 IP 地址，但使用相同的默认端口（默认端口为 TCP 443）。 下面是 "IP 地址要求" 一节中的详细信息。 
  
如果使用 NAT 选择不可路由的专用 IP 地址，请记住以下几点：
  
- 您需要在**所有三个**外部接口上使用可路由的专用 IP 地址。
    
- 您需要为传入和传出流量配置**对称**NAT。 对称 NAT 是您可以与 Skype for Business Server Edge 服务器配合使用的唯一受支持的 NAT。
    
- 将您的 NAT 配置为不更改传入的源地址。 A/V 边缘服务需要能够接收传入的源地址以查找最佳媒体路径。
    
- 您的边缘服务器需要能够从其公共 A/V 边缘 IP 地址相互通信。 你的防火墙需要允许此流量。
    
- 如果使用 DNS 负载平衡，NAT**仅**可用于扩展的合并边缘服务器。 如果使用硬件负载平衡（HLB），则需要使用**没有**NAT 的可公开路由的 IP 地址。
    
如果路由器或防火墙后面的访问、Web 会议和 A/V 边缘接口对单个合并和扩展的合并边缘服务器拓扑执行对称 NAT （只要您不使用硬件负载平衡），则不会出现任何问题。
  
### <a name="summary-of-edge-server-topology-options"></a>边缘服务器拓扑选项摘要

对于 Skype for Business Server Edge 服务器部署，我们提供了几种拓扑选项：
  
- 具有专用 IP 地址和 NAT 的单一合并边缘
    
- 具有公用 IP 地址的单一合并边缘
    
- 使用专用 IP 地址和 NAT 的扩展合并边缘
    
- 使用公用 IP 地址的扩展合并边缘
    
- 使用硬件负载平衡器的扩展的合并边缘
    
为帮助你选择一个，我们提供了下表，其中提供了每个拓扑的哪些选项的摘要：
  
|**拓扑**|**高可用性**|**边缘池中的外部边缘服务器所需的其他 DNS 记录？**|**Skype for business Server 会话的边缘故障转移**|**Skype for business Server 联合会话的边缘故障转移**|
|:-----|:-----|:-----|:-----|:-----|
|具有专用 IP 地址和 NAT 的单一合并边缘  <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|具有公用 IP 地址的单一合并边缘  <br/> |否  <br/> |否  <br/> |否  <br/> |否  <br/> |
|使用专用 IP 地址和 NAT 的扩展合并边缘（DNS 负载平衡）  <br/> |是  <br/> |是  <br/> |是  <br/> |是&sup1;  <br/> |
|使用公用 IP 地址的扩展合并边缘（DNS 负载平衡）  <br/> |是  <br/> |是  <br/> |是  <br/> |是&sup1;  <br/> |
|使用硬件负载平衡器的扩展的合并边缘  <br/> |是  <br/> |不支持（每个 VIP 一个 DNS A 记录）  <br/> |是  <br/> |是  <br/> |
   
&sup1;Exchange 统一消息（UM）使用 DNS 负载平衡的远程用户故障转移需要 Exchange 2013 或更高版本。
  
### <a name="ip-address-requirements"></a>IP 地址要求

在基本级别，三个服务需要 IP 地址;访问边缘服务、Web 会议边缘服务和 A/V 边缘服务。 您可以选择使用三个 IP 地址（每个服务对应一个），也可以使用一个服务并选择性地将每个服务放在不同的端口上（可以查看[端口和防火墙规划](edge-environmental-requirements.md#PortFirewallPlan)部分，了解有关其中一些的详细信息）。 对于单一的合并边缘环境，这一点非常大。
  
> [!NOTE]
> 如前所述，您可以选择为所有三个服务提供一个 IP 地址，并在不同的端口上运行它们。 但为清楚，我们不建议这样做。 如果您的客户无法访问您在此方案中使用的备用端口，它们也无法访问边缘环境的全部功能。 
  
使用扩展的合并拓扑可能会稍微复杂一些，因此，我们来看看一些布局 IP 地址要求的表，请记住，拓扑选择的主要决策点是高可用性和负载平衡。 高可用性需求可能影响负载平衡选择（我们将在表后面谈论更多）。
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>扩展合并边缘的 IP 地址要求（每个角色的 IP 地址）

|**每个池的边缘服务器数量**|**DNS 负载平衡所需的 IP 地址数**|**硬件负载平衡所需的 IP 地址数量**|
|:-----|:-----|:-----|
|2   <br/> |6   <br/> |3（每个 VIP 1 个）+ 6  <br/> |
|3   <br/> |9   <br/> |3（每个 VIP 1 个）+9  <br/> |
|4   <br/> |12   <br/> |3（每个 VIP 1 个）+12  <br/> |
|5   <br/> |15   <br/> |3（每个 VIP 1 个） + 15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>扩展合并边缘的 IP 地址要求（所有角色的单个 IP 地址）

|**每个池的边缘服务器数量**|**DNS 负载平衡所需的 IP 地址数**|**硬件负载平衡所需的 IP 地址数量**|
|:-----|:-----|:-----|
|2   <br/> |2   <br/> |1（每个 VIP 1 个）2  <br/> |
|3   <br/> |3   <br/> |1（每个 VIP 1 个）+ 3  <br/> |
|4   <br/> |4   <br/> |1（每个 VIP 1 个）4  <br/> |
|5   <br/> |5  <br/> |1（每个 VIP 1 个）5  <br/> |
   
让我们来看看在规划时需要考虑的一些其他事项。
  
- **高可用性**：如果在部署中需要高可用性，应在池中部署至少两台边缘服务器。 值得注意的是，单个边缘池最长可支持12台边缘服务器（尽管拓扑生成器允许添加最高20台，这种情况未经过测试或支持，因此我们建议您不要这样做）。 如果需要多于12台边缘服务器，则应为它们创建其他边缘池。
    
- **硬件负载平衡**：我们建议在大多数情况下进行 DNS 负载平衡。 当然，还支持硬件负载平衡，但要特别注意的是，在 DNS 负载平衡的单个方案中，需要执行以下操作：
    
  - 对 Exchange 2007 或 Exchange 2010 （无 SP）统一消息（UM）的外部访问。
    
- **Dns 负载平衡**：对于 UM，EXCHANGE 2010 SP1 和更高版本可以通过 DNS 负载平衡支持。 请注意，如果您需要对早期版本的 Exchange 使用 DNS 负载平衡，它将正常运行，但此操作的所有通信都将转到池中的第一台服务器，如果不可用，则该流量随后将失败。
    
    如果要与使用以下公司的公司进行联盟，也建议使用 DNS 负载平衡：
- Skype for Business Server 2015：
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft 365 或 Office 365
- Skype for Business Server 2019：
    - Lync Server 2013
    - Skype for Business Server 2015
    - Microsoft 365 或 Office 365
    
## <a name="dns-planning"></a>DNS 规划
<a name="DNSPlan"> </a>

当涉及 Skype for business Server Edge 服务器部署时，为正确地准备 DNS 至关重要。 将适当的记录放在适当的情况下，部署将更加简单明了。 但愿您在上述部分中选择了一个拓扑，因为我们将进行概述，然后列出了一些表格，其中列出了这些方案的 DNS 记录。 如果需要，我们还将[为 Skype For Business server 提供一些高级边缘服务器 DNS 规划](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md)，以进行更深入的阅读。
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>单个合并边缘服务器方案的 DNS 记录

这些是将使用公用 Ip 或专用 Ip 和 NAT 的单个边缘服务器所需的 DNS 记录。 由于这是示例数据，因此我们将提供示例 IPs，以便您可以更轻松地使用自己的条目：
  
- 内部网络适配器：172.25.33.10 （未分配默认网关）
    
    > [!NOTE]
    > 确保从包含边缘内部接口的网络的路由到包含运行 Skype for Business Server 或 Lync Server 2013 客户端的服务器的任何网络（例如，从172.25.33.0 到192.168.10.0）。 
  
- 外部网络适配器：
    
  - 公共 Ip：
    
  - 访问边缘：131.107.155.10 （这是主网关，将默认网关设置为公用路由器，ex：131.107.155.1）
    
  - Web 会议边缘：131.107.155.20 （辅助）
    
  - A/V 边缘：131.107.155.30 （辅助）
    
  Web 会议和 A/V 边缘公共 IP 地址是 Windows Server 中的本地区域连接属性的 Internet 协议版本4（TCP/IPv4）和 Internet 协议版本6（TCP/IPv6）属性的 "高级" 部分中的其他（辅助） IP 地址。
    
  - 专用 Ip：
    
  - 访问边缘：10.45.16.10 （这是主网关，将默认网关设置为您的路由器，ex：10.45.16.1）
    
  - Web 会议边缘：10.45.16.20 （辅助）
    
  - A/V 边缘：10.45.16.30 （辅助）
    
Web 会议和 A/V 边缘公共 IP 地址是 Windows Server 中的本地区域连接属性的 Internet 协议版本4（TCP/IPv4）和 Internet 协议版本6（TCP/IPv6）属性的 "高级" 部分中的其他（辅助） IP 地址。
  
> [!TIP]
>此处有其他可能的配置：
  
- 可以在外部网络适配器上使用一个 IP 地址。 我们不建议这样做，因为接下来，你需要使用不同的端口（可以在 Skype for Business Server 中执行此操作）区分 thee 服务，但有些防火墙可能会阻止备用端口。 有关详细信息，请参阅 "[端口和防火墙规划](edge-environmental-requirements.md#PortFirewallPlan)" 一节。
    
- 您可以有三个外部网络适配器，而不是一个，并将其中一个服务 Ip 分配给每个。 为什么要这样做？ 它会将服务分开，如果出现问题，则可以更轻松地进行故障排除，并且在您解决问题时，可能会让其他服务继续正常工作。
    
|**Location**|**类型**|**Port**|**FQDN 或 DNS 记录**|**IP 地址或 FQDN**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |一条记录  <br/> |不适用  <br/> |sip.contoso.com  <br/> |**public：** 131.107.155.10 <br/> **private：** 10.45.16.10 <br/> |用于访问边缘服务的外部接口。 对于具有 Skype for Business 用户的每个 SIP 域，您都需要一个。  <br/> |
|外部 DNS  <br/> |一条记录  <br/> |不适用  <br/> |webcon.contoso.com  <br/> |**public：** 131.107.155.20 <br/> **private：** 10.45.16.20 <br/> |Web 会议边缘服务的外部接口。  <br/> |
|外部 DNS  <br/> |一条记录  <br/> |不适用  <br/> |av.contoso.com  <br/> |**public：** 131.107.155.30 <br/> **private：** 10.45.16.30 <br/> |A/V 边缘服务的外部接口。  <br/> |
|外部 DNS  <br/> |SRV record － SRV 记录  <br/> |443  <br/> |_sip _tls .com  <br/> |sip.contoso.com  <br/> |用于访问边缘服务的外部接口。 Skype for business Server、Lync Server 2013 和 Lync Server 2010 客户端需要此 SRV 记录以在外部工作。 对于具有 Skype for Business 用户的每个域，您都需要一个。  <br/> |
|外部 DNS  <br/> |SRV record － SRV 记录  <br/> |5061  <br/> |_sipfederationtls _tcp .com  <br/> |sip.contoso.com  <br/> |用于访问边缘服务的外部接口。 称为 "允许的 SIP 域" 的联盟伙伴的自动 DNS 发现需要此 SRV 记录。 对于具有 Skype for Business 用户的每个域，您都需要一个。  <br/> |
|内部 DNS  <br/> |一条记录  <br/> |不适用  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |您的合并边缘的内部接口。  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>用于扩展的 DNS 和硬件边缘服务器方案的 DNS 记录

这些是将使用公用 Ip 或专用 Ip 和 NAT 的单个边缘服务器所需的 DNS 记录。 由于这是示例数据，因此我们将提供示例 IPs，以便您可以更轻松地使用自己的条目：
  
- 内部网络适配器：
    
  - 节点1：172.25.33.10 （未分配默认网关）
    
  - 节点2：172.25.33.11 （未分配默认网关）
    
    > [!NOTE]
    > 确保从包含边缘内部接口的网络的路由到包含运行 Skype for Business Server 或 Lync Server 2013 客户端的服务器的任何网络（例如，从172.25.33.0 到192.168.10.0）。 
  
- 外部网络适配器：
    
  - 节点1
    
     - 公共 Ip：
    
        - 访问边缘：131.107.155.10 （这是主网关，将默认网关设置为公用路由器，ex：131.107.155.1）
    
        - Web 会议边缘：131.107.155.20 （辅助）
    
        - A/V 边缘：131.107.155.30 （辅助）
    
          Web 会议和 A/V 边缘公共 IP 地址是 Windows Server 中的本地区域连接属性的 Internet 协议版本4（TCP/IPv4）和 Internet 协议版本6（TCP/IPv6）属性的 "高级" 部分中的其他（辅助） IP 地址。
    
    - 专用 Ip：
    
         - 访问边缘：10.45.16.10 （这是主网关，将默认网关设置为您的路由器，ex：10.45.16.1）
    
         - Web 会议边缘：10.45.16.20 （辅助）
    
         - A/V 边缘：10.45.16.30 （辅助）
    
      Web 会议和 A/V 边缘公共 IP 地址是 Windows Server 中的本地区域连接属性的 Internet 协议版本4（TCP/IPv4）和 Internet 协议版本6（TCP/IPv6）属性的 "高级" 部分中的其他（辅助） IP 地址。
    
  - 节点2
    
    - 公共 Ip：
    
      - 访问边缘：131.107.155.11 （这是主网关，将默认网关设置为公用路由器，ex：131.107.155.1）
    
      - Web 会议边缘：131.107.155.21 （辅助）
    
      - A/V 边缘：131.107.155.31 （辅助）
    
      Web 会议和 A/V 边缘公共 IP 地址是 Windows Server 中的本地区域连接属性的 Internet 协议版本4（TCP/IPv4）和 Internet 协议版本6（TCP/IPv6）属性的 "高级" 部分中的其他（辅助） IP 地址。
    
  - 专用 Ip：
    
    - 访问边缘：10.45.16.11 （这是主网关，将默认网关设置为您的路由器，ex：10.45.16.1）
    
    - Web 会议边缘：10.45.16.21 （辅助）
    
    - A/V 边缘：10.45.16.31 （辅助）
    
      Web 会议和 A/V 边缘公共 IP 地址是 Windows Server 中的本地区域连接属性的 Internet 协议版本4（TCP/IPv4）和 Internet 协议版本6（TCP/IPv6）属性的 "高级" 部分中的其他（辅助） IP 地址。
    
此处有其他可能的配置：
  
- 可以在外部网络适配器上使用一个 IP 地址。 我们不建议这样做，因为接下来，你需要使用不同的端口（可以在 Skype for Business Server 中执行此操作）区分 thee 服务，但有些防火墙可能会阻止备用端口。 有关详细信息，请参阅 "[端口和防火墙规划](edge-environmental-requirements.md#PortFirewallPlan)" 一节。
    
- 您可以有三个外部网络适配器，而不是一个，并将其中一个服务 Ip 分配给每个。 为什么要这样做？ 它会将服务分开，如果出现问题，则可以更轻松地进行故障排除，并且在您解决问题时，可能会让其他服务继续正常工作。
    
|**Location**|**类型**|**Port**|**FQDN 或 DNS 记录**|**IP 地址或 FQDN**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |一条记录  <br/> |不适用  <br/> |sip.contoso.com  <br/> |**public：** 131.107.155.10 和131.107.155.11 <br/> **private：** 10.45.16.10 和10.45.16.11 <br/> |用于访问边缘服务的外部接口。 对于具有 Skype for Business 用户的每个 SIP 域，您都需要一个。  <br/> |
|外部 DNS  <br/> |一条记录  <br/> |不适用  <br/> |webcon.contoso.com  <br/> |**public：** 131.107.155.20 和131.107.155.21 <br/> **private：** 10.45.16.20 和10.45.16.21 <br/> |Web 会议边缘服务的外部接口。  <br/> |
|外部 DNS  <br/> |一条记录  <br/> |不适用  <br/> |av.contoso.com  <br/> |**public：** 131.107.155.30 和131.107.155.31 <br/> **private：** 10.45.16.30 和10.45.16.31 <br/> |A/V 边缘服务的外部接口。  <br/> |
|外部 DNS  <br/> |SRV record － SRV 记录  <br/> |443  <br/> |_sip _tls .com  <br/> |sip.contoso.com  <br/> |用于访问边缘服务的外部接口。 Skype for business Server、Lync Server 2013 和 Lync Server 2010 客户端需要此 SRV 记录以在外部工作。 对于每个使用 Skype for Business 的域，您都需要一个。  <br/> |
|外部 DNS  <br/> |SRV record － SRV 记录  <br/> |5061  <br/> |_sipfederationtls _tcp .com  <br/> |sip.contoso.com  <br/> |用于访问边缘服务的外部接口。 称为 "允许的 SIP 域" 的联盟伙伴的自动 DNS 发现需要此 SRV 记录。 对于每个使用 Skype for Business 的域，您都需要一个。  <br/> |
|内部 DNS  <br/> |一条记录  <br/> |不适用  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 和 172.25.33.11  <br/> |您的合并边缘的内部接口。  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>联合身份验证的 DNS 记录（所有方案）

|**Location**|**类型**|**Port**|**FQDN**|**FQDN 主机记录**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp .com  <br/> |sip.contoso.com  <br/> |自动 DNS 发现所需的 SIP 访问边缘外部接口。 由其他潜在的联合合作伙伴使用。 它也称为 "允许 SIP 域"。 你将需要针对具有 Skype for Business 用户的每个 SIP 域使用其中一种。  <br/><br/> **注意：** 对于移动性和推送通知交换所，将需要此 SRV 记录。 <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>可扩展消息传递和状态协议的 DNS 记录

|**Location**|**类型**|**Port**|**FQDN**|**IP 地址或 FQDN 主机记录**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|外部 DNS  <br/> |SRV  <br/> |5269  <br/> |_xmpp-_tcp .com  <br/> |xmpp.contoso.com  <br/> |您的访问边缘服务或边缘池上的 XMPP 代理接口。 对于启用了 Skype for Business Server 的用户的所有内部 SIP 域，您需要对其重复此操作，允许用户通过以下方式为 XMPP 联系人提供联系人：  <br/> •全局策略  <br/> •用户已启用的网站策略  <br/> •应用于启用 Skype for Business Server 的用户的用户策略  <br/> 还需要在 XMPP 联合用户策略中配置允许的 XMPP 策略。  <br/> |
|外部 DNS  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |托管您的 XMPP 代理服务的边缘服务器或边缘池上的访问边缘服务的 IP 地址  <br/> |这指向承载 XMPP 代理服务的边缘服务器或边缘池中的访问边缘服务。 通常，您创建的 SRV 记录将指向此主机（A 或 AAAA）记录。  <br/> |
   
> [!NOTE]
> XMPP 网关和代理在 Skype for business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 有关详细信息，请参阅[迁移 XMPP 联合](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。

## <a name="certificate-planning"></a>证书规划
<a name="CertPlan"> </a>

Skype for Business Server 使用证书在服务器之间和从服务器到客户端的安全、加密的通信。 正如您所期望的那样，证书需要将服务器的 DNS 记录与证书上的任何使用者名称（SN）和使用者备用名称（SAN）相匹配。 此操作现在将在规划阶段进行，以确保在 DNS 中为您的证书的 SN 和 SAN 条目注册了正确的 Fqdn。
  
我们将单独讨论外部和内部证书需求，然后查看提供这两个要求的表格。
  
### <a name="external-certificates"></a>外部证书

必须至少由公共证书颁发机构（CA）提供分配给外部边缘服务器接口的证书。 我们无法向你推荐特定的 CA，但我们确实拥有一个 CAs 和[统一通信证书合作伙伴](/SkypeForBusiness/certification/services-ssl)列表，你可以查看你的首选 CA 是否已列出。
  
何时需要向 CA 提交此公共证书的请求，以及如何执行此操作？ 有几种方法可以实现此目的：
  
- 您可以完成 Skype for Business Server 的安装，然后进行边缘服务器部署。 Skype for Business Server 部署向导将执行一步操作，以生成证书请求，然后可以将该请求发送给所选的 CA。
    
- 您还可以使用 Windows PowerShell 命令生成此请求，如果这与你的业务需求或部署策略更内联。
    
- 最后，你的 CA 可能会有自己的提交过程，这可能还涉及 Windows PowerShell 或其他方法。 在这种情况下，除了此处提供的参考信息之外，还需要依赖其文档。
    
获取证书后，您需要继续并将其分配到 Skype for Business Server 中的以下服务：
  
- 访问边缘服务接口
    
- Web 会议边缘服务接口
    
- 音频/视频身份验证服务（不要将其与 A/V 边缘服务相混淆，因为它不使用证书来加密音频和视频流）
    
> [!IMPORTANT]
> 所有边缘服务器（如果它们属于同一台边缘服务器池）都需要具有与媒体中继身份验证服务具有相同私钥的完全相同的证书。 
  
### <a name="internal-certificates"></a>内部证书

对于内部边缘服务器接口，可以使用来自公共 CA 的公共证书，也可以使用从组织的内部 CA 颁发的证书。 关于内部证书，要记住的一点是，它使用 SN 项，而不是 SAN 条目，因此您无需担心内部证书上的 SAN。
  
### <a name="required-certificates-table"></a>必需的证书表

我们在此处提供了可帮助你解决请求的表格。 此处的 FQDN 条目仅适用于示例域。 你需要根据你自己的专用域和公共域发出请求，但下面是我们使用的内容的指南：
  
- contoso <span></span> .com：公共 FQDN
    
- fabrikam <span></span> .com：第二个公共 FQDN （如果您有多个 SIP 域，则添加为要请求的内容的演示）
    
- Contoso <span></span> .net：内部域
    
#### <a name="edge-certificate-table"></a>边缘证书表

无论您是要执行单个边缘服务器还是边缘池，您的证书都需要以下内容：
  
|**组件**|**使用者名称 (SN)**|**使用者可选名称（SAN）/order**|**Notes**|
|:-----|:-----|:-----|:-----|
|外部边缘  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |这是您需要从公共 CA 请求的证书。 需要为以下项将其分配给外部边缘接口：  <br/> •访问边缘  <br/> • Web 会议边缘  <br/> •音频/视频身份验证  <br/> <br/>好消息是，San 会自动添加到您的证书请求中，因此，在提交请求后，将根据在拓扑生成器中为此部署定义的内容来提供证书。 您只需为任何其他 SIP 域或需要支持的其他条目添加 SAN 条目。 为什么 sip.contoso.com 在此实例中进行复制？ 这也会自动发生，并且在正常工作的情况下需要执行这些操作。  <br/><br/> **注意：** 此证书还可用于公共即时消息连接。 您无需对其进行任何不同的操作，但在本文档的早期版本中，它作为一个单独的表列出，现在也不会。 <br/> |
|内部边缘  <br/> |sfbedge.contoso.com  <br/> |不适用  <br/> |您可以从公共 CA 或内部 CA 获取此证书。 它需要包含服务器 EKU （增强型密钥用法），并将其分配给内部边缘接口。  <br/> |
   
如果您需要可扩展邮件和状态协议（XMPP）的证书，它看起来与上面的外部边缘表条目相同，但将包含以下两个额外的 SAN 条目：
  
- xmpp。 <span></span>contoso <span></span>
    
- \*<span></span>.com
    
请注意，当前 XMPP 仅在 Skype for Business Server for Google 谈话中受支持，如果你需要或需要将其用于其他任何内容，则需要确认涉及第三方供应商的功能。
  
## <a name="port-and-firewall-planning"></a>端口和防火墙规划
<a name="PortFirewallPlan"> </a>

为 Skype for business Server Edge 服务器部署的端口和防火墙制定规划权限，可以节省故障排除和压力的几天或几周。 因此，我们将列出几个表，它们将指出协议使用情况，以及需要对 NAT 和公共 IP 方案开放、入站和出站的端口。 我们还将单独提供用于硬件负载平衡方案（HLB）的表格，并对此进行了一些进一步指导。 为了更好地阅读，我们还[在 Skype For Business Server 中提供了一些边缘服务器方案](scenarios.md)，您可以查看您的特定部署注意事项。
  
### <a name="general-protocol-usage"></a>常规协议用法

在查看外部和内部防火墙的摘要表之前，让我们也考虑下表：
  
|**音频/视频传输**|**使用**|
|:-----|:-----|
|UDP  <br/> |音频和视频的首选传输层协议。  <br/> |
|TCP  <br/> |音频和视频的回退传输层协议。  <br/> 适用于 Skype for business Server、Lync Server 2013 和 Lync Server 2010 的应用程序共享所需的传输层协议。  <br/> 用于文件传输到 Skype for business Server、Lync Server 2013 和 Lync Server 2010 所需的传输层协议。  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>外部端口防火墙摘要表

源 IP 地址和目标 IP 地址将包含使用 NAT 的专用 IP 地址的用户的信息，以及使用公用 IP 地址的用户的信息。 这将涵盖在 " [Skype For Business server](scenarios.md) " 一节中的边缘服务器方案中的所有排列。
  
|**角色或协议**|**TCP 或 UDP**|**目标端口或端口范围**|**源 IP 地址**|**目标 IP 地址**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> 在 Skype for Business Server 2019 中不受支持 |TCP  <br/> |5269  <br/> |任意  <br/> |XMPP 代理服务（与访问边缘服务共享 IP 地址  <br/> |XMPP 代理服务接受来自定义的 XMPP 联合中的 XMPP 联系人的流量。  <br/> |
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |**使用 NAT 的专用 IP：** 边缘服务器访问边缘服务 <br/> **公用 IP：** 边缘服务器访问边缘服务公用 IP 地址 <br/> |任意  <br/> |证书吊销和 CRL 检查和检索。  <br/> |
|访问/DNS  <br/> |TCP  <br/> |53  <br/> |**使用 NAT 的专用 IP：** 边缘服务器访问边缘服务 <br/> **公用 IP：** 边缘服务器访问边缘服务公用 IP 地址 <br/> |任意  <br/> |通过 TCP 的 DNS 查询。  <br/> |
|访问/DNS  <br/> |UDP  <br/> |53  <br/> |**使用 NAT 的专用 IP：** 边缘服务器访问边缘服务 <br/> **公用 IP：** 边缘服务器访问边缘服务公用 IP 地址 <br/> |任意  <br/> |通过 UDP 的 DNS 查询。  <br/> |
|访问/SIP （TLS）  <br/> |TCP  <br/> |443  <br/> |任意  <br/> |**使用 NAT 的专用 IP：** 边缘服务器访问边缘服务 <br/> **公用 IP：** 边缘服务器访问边缘服务公用 IP 地址 <br/> |用于外部用户访问的客户端到服务器 SIP 流量。  <br/> |
|访问/SIP （MTLS）  <br/> |TCP  <br/> |5061  <br/> |任意  <br/> |**使用 NAT 的专用 IP：** 边缘服务器访问边缘服务 <br/> **公用 IP：** 边缘服务器访问边缘服务公用 IP 地址 <br/> |用于使用 SIP 的联盟和公共 IM 连接。  <br/> |
|访问/SIP （MTLS）  <br/> |TCP  <br/> |5061  <br/> |**使用 NAT 的专用 IP：** 边缘服务器访问边缘服务 <br/> **公用 IP：** 边缘服务器访问边缘服务公用 IP 地址 <br/> |任意  <br/> |用于使用 SIP 的联盟和公共 IM 连接。  <br/> |
|Web 会议/PSOM （TLS）  <br/> |TCP  <br/> |443  <br/> |任意  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 Web 会议边缘服务 <br/> **公用 IP：** 边缘服务器 Web 会议边缘服务公用 IP 地址 <br/> |Web 会议媒体。  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 A/V 边缘服务 <br/> **公用 IP：** 边缘服务器 A/V 边缘服务公共 IP 地址 <br/> |任意  <br/> |这用于中继媒体流量。  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 A/V 边缘服务 <br/> **公用 IP：** 边缘服务器 A/V 边缘服务公共 IP 地址 <br/> |任意  <br/> |这用于中继媒体流量。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP  <br/> |3478  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 A/V 边缘服务 <br/> **公用 IP：** 边缘服务器 A/V 边缘服务公共 IP 地址 <br/> |任意  <br/> |3478出站是：  <br/> •由 Skype for Business Server 用于确定与其通信的边缘服务器的版本。  <br/> •用于边缘服务器之间的媒体流量。  <br/> •使用 Lync Server 2010 进行联盟时需要。  <br/> •如果在您的组织中部署了多个边缘池，则需要。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 A/V 边缘服务 <br/> **公用 IP：** 边缘服务器 A/V 边缘服务公共 IP 地址 <br/> |在端口3478上 STUN/开启对候选人的候选人协商。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP  <br/> |443  <br/> |任意  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 A/V 边缘服务 <br/> **公用 IP：** 边缘服务器 A/V 边缘服务公共 IP 地址 <br/> |在端口443上通过 TCP STUN/TURN 的候选人协商。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP  <br/> |443  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 A/V 边缘服务 <br/> **公用 IP：** 边缘服务器 A/V 边缘服务公共 IP 地址 <br/> |任意  <br/> |在端口443上通过 TCP STUN/TURN 的候选人协商。  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>内部端口防火墙摘要表

|**协议**|**TCP 或 UDP**|**Port**|**源 IP 地址**|**目标 IP 地址**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |运行 XMPP 网关服务的以下任一项：  <br/> •前端服务器  <br/> •前端池  <br/> |边缘服务器内部接口  <br/> |来自前端服务器或前端池上运行的 XMPP 网关服务的出站 XMPP 流量。  <br/> **注意：** XMPP 网关和代理在 Skype for business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 有关详细信息，请参阅[迁移 XMPP 联合](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |各种  <br/> •控制器  <br/> •控制器池  <br/> •前端服务器  <br/> •前端池  <br/> |边缘服务器内部接口  <br/> |从控制器、控制器池、前端服务器或前端池到边缘服务器内部接口的出站 SIP 流量。  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |边缘服务器内部接口  <br/> |各种  <br/> •控制器  <br/> •控制器池  <br/> •前端服务器  <br/> •前端池  <br/> |来自边缘服务器内部接口的到控制器、控制器池、前端服务器或前端池的入站 SIP 流量。  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |各种  <br/> •前端服务器  <br/> •每台前端服务器  <br/>  在前端池中 <br/> |边缘服务器内部接口  <br/> |从前端服务器或每台前端服务器（如果有一个前端池）到边缘服务器内部接口的 Web 会议流量。  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |各种  <br/> •前端服务器  <br/> •前端池  <br/> •任何使用此边缘服务器的 Survivable 分支设备  <br/> •任何使用此边缘服务器的 Survivable 分支服务器  <br/> |边缘服务器内部接口  <br/> |您的前端服务器或前端池中的 A/V 用户身份验证，或使用边缘服务器的 Survivable 分支装置或 Survivable 分支服务器进行身份验证。  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |在内部和外部用户与 Survivable 分支机构或 Survivable 分支服务器之间传输 A/V 媒体的首选路径。  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |如果 UDP 通信不起作用，则内部和外部用户与 Survivable 分支机构或 Survivable 分支服务器之间的 A/V 媒体传输的回退路径。 然后，将 TCP 用于文件传输和桌面共享。  <br/> |
|IP-HTTPS  <br/> |TCP  <br/> |4443  <br/> |各种  <br/> •包含中央管理存储的前端服务器  <br/> •保留中央管理存储的前端池  <br/> |边缘服务器内部接口  <br/> |将您的中央管理存储中的更改复制到边缘服务器。  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |使用 Skype for Business Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志集合的集中日志记录服务控制器。  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |使用 Skype for Business Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志集合的集中日志记录服务控制器。  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |使用 Skype for Business Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志集合的集中日志记录服务控制器。  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>边缘端口表的硬件负载平衡器

我们正在为硬件负载平衡器（Hlb）和边缘端口提供其自己的部分，因为其他硬件会稍微复杂一些。 有关此特定方案的指南，请参阅下面的表格：
  
#### <a name="external-port-firewall-summary-table"></a>外部端口防火墙摘要表

源 IP 地址和目标 IP 地址将包含使用 NAT 的专用 IP 地址的用户的信息，以及使用公用 IP 地址的用户的信息。 这将涵盖在 " [Skype For Business server](scenarios.md) " 一节中的边缘服务器方案中的所有排列。
  
|**角色或协议**|**TCP 或 UDP**|**目标端口或端口范围**|**源 IP 地址**|**目标 IP 地址**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |边缘服务器访问边缘服务公用 IP 地址  <br/> |任意  <br/> |证书吊销和 CRL 检查和检索。  <br/> |
|访问/DNS  <br/> |TCP  <br/> |53  <br/> |边缘服务器访问边缘服务公用 IP 地址  <br/> |任意  <br/> |通过 TCP 的 DNS 查询。  <br/> |
|访问/DNS  <br/> |UDP  <br/> |53  <br/> |边缘服务器访问边缘服务公用 IP 地址  <br/> |任意  <br/> |通过 UDP 的 DNS 查询。  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |边缘服务器 A/V 边缘服务 IP 地址  <br/> |任意  <br/> |这用于中继媒体流量。  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |边缘服务器 A/V 边缘服务公共 IP 地址  <br/> |任意  <br/> |这用于中继媒体流量。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP  <br/> |3478  <br/> |边缘服务器 A/V 边缘服务公共 IP 地址  <br/> |任意  <br/> |3478出站是：  <br/> •由 Skype for Business Server 用于确定与其通信的边缘服务器的版本。  <br/> •用于边缘服务器之间的媒体流量。  <br/> •联合身份验证需要。  <br/> •如果在您的组织中部署了多个边缘池，则需要。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |边缘服务器 A/V 边缘服务公共 IP 地址  <br/> |在端口3478上 STUN/开启对候选人的候选人协商。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP  <br/> |443  <br/> |任意  <br/> |边缘服务器 A/V 边缘服务公共 IP 地址  <br/> |在端口443上通过 TCP STUN/TURN 的候选人协商。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP  <br/> |443  <br/> |边缘服务器 A/V 边缘服务公共 IP 地址  <br/> |任意  <br/> |在端口443上通过 TCP STUN/TURN 的候选人协商。  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>内部端口防火墙摘要表

|**协议**|**TCP 或 UDP**|**Port**|**源 IP 地址**|**目标 IP 地址**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |运行 XMPP 网关服务的以下任一项：  <br/> •前端服务器  <br/> •前端池 VIP 地址运行 XMPP 网关服务  <br/> |边缘服务器内部接口  <br/> |来自前端服务器或前端池上运行的 XMPP 网关服务的出站 XMPP 流量。  <br/><br/> **注意：** XMPP 网关和代理在 Skype for business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 有关详细信息，请参阅[迁移 XMPP 联合](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。 |
|IP-HTTPS  <br/> |TCP  <br/> |4443  <br/> |各种  <br/> •包含中央管理存储的前端服务器  <br/> •保留中央管理存储的前端池  <br/> |边缘服务器内部接口  <br/> |将您的中央管理存储中的更改复制到边缘服务器。  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |各种  <br/> •前端服务器  <br/> •前端池中的每台前端服务器  <br/> |边缘服务器内部接口  <br/> |从前端服务器或每台前端服务器（如果有一个前端池）到边缘服务器内部接口的 Web 会议流量。  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |各种  <br/> •前端服务器  <br/> •前端池中的每台前端服务器  <br/> |边缘服务器内部接口  <br/> |在内部和外部用户与 Survivable 分支机构或 Survivable 分支服务器之间传输 A/V 媒体的首选路径。  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |各种  <br/> •前端服务器  <br/> •池中的每台前端服务器  <br/> |边缘服务器内部接口  <br/> |如果 UDP 通信不起作用，则内部和外部用户与 Survivable 分支机构或 Survivable 分支服务器之间的 A/V 媒体传输的回退路径。 然后，将 TCP 用于文件传输和桌面共享。  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |使用 Skype for Business Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志集合的集中日志记录服务控制器。  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |使用 Skype for Business Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志集合的集中日志记录服务控制器。  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |使用 Skype for Business Server 命令行管理程序和集中日志记录服务 cmdlet、ClsController 命令行（ClsController）或代理（ClsAgent）命令和日志集合的集中日志记录服务控制器。  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>外部接口虚拟 Ip

|**角色或协议**|**TCP 或 UDP**|**目标端口或端口范围**|**源 IP 地址**|**目标 IP 地址**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> 在 Skype for Business Server 2019 中不受支持 |TCP  <br/> |5269  <br/> |任意  <br/> |XMPP 代理服务（与访问边缘服务共享 IP 地址）  <br/> |XMPP 代理服务接受来自定义的 XMPP 联合中的 XMPP 联系人的流量。  <br/> |
|XMPP  <br/>在 Skype for Business Server 2019 中不受支持 |TCP  <br/> |5269  <br/> |XMPP 代理服务（与访问边缘服务共享 IP 地址）  <br/> |任意  <br/> |XMPP 代理服务从定义的 XMPP 联合中的 XMPP 联系人发送流量。  <br/> |
|访问/SIP （TLS）  <br/> |TCP  <br/> |443  <br/> |任意  <br/> |**使用 NAT 的专用 IP：** 边缘服务器访问边缘服务 <br/> **公用 IP：** 边缘服务器访问边缘服务公用 IP 地址 <br/> |用于外部用户访问的客户端到服务器 SIP 流量。  <br/> |
|访问/SIP （MTLS）  <br/> |TCP  <br/> |5061  <br/> |任意  <br/> |**使用 NAT 的专用 IP：** 边缘服务器访问边缘服务 <br/> **公用 IP：** 边缘服务器访问边缘服务公用 IP 地址 <br/> |用于使用 SIP 的联盟和公共 IM 连接。  <br/> |
|访问/SIP （MTLS）  <br/> |TCP  <br/> |5061  <br/> |**使用 NAT 的专用 IP：** 边缘服务器访问边缘服务 <br/> **公用 IP：** 边缘服务器访问边缘服务公用 IP 地址 <br/> |任意  <br/> |用于使用 SIP 的联盟和公共 IM 连接。  <br/> |
|Web 会议/PSOM （TLS）  <br/> |TCP  <br/> |443  <br/> |任意  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 Web 会议边缘服务 <br/> **公用 IP：** 边缘服务器 Web 会议边缘服务公用 IP 地址 <br/> |Web 会议媒体。  <br/> |
|A/V/STUN。MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 A/V 边缘服务 <br/> **公用 IP：** 边缘服务器 A/V 边缘服务公共 IP 地址 <br/> |在端口3478上 STUN/开启对候选人的候选人协商。  <br/> |
|A/V/STUN。MSTURN  <br/> |TCP  <br/> |443  <br/> |任意  <br/> |**使用 NAT 的专用 IP：** 边缘服务器 A/V 边缘服务 <br/> **公用 IP：** 边缘服务器 A/V 边缘服务公共 IP 地址 <br/> |在端口443上通过 TCP STUN/TURN 的候选人协商。  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>内部接口虚拟 Ip

我们在此提供了一些不同的指导。 实际上，在 HLB 情况下，我们建议您仅在以下情况下通过内部 VIP 进行路由：
  
- 如果您使用的是 Exchange 2007 或 Exchange 2010 统一消息（UM）。
    
- 如果有使用边缘的旧版客户端。
    
下表提供了有关这些方案的指南，但是，您应该能够依赖于中央管理存储（CMS）将流量路由到它可以识别的单个边缘服务器（当然，这确实需要将 CMS 保持最新的边缘服务器信息）。
  
|**协议**|**TCP 或 UDP**|**Port**|**源 IP 地址**|**目标 IP 地址**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|访问/SIP （MTLS）  <br/> |TCP  <br/> |5061  <br/> |各种  <br/> •控制器  <br/> •控制器池 VIP 地址  <br/> •前端服务器  <br/> •前端池 VIP 地址  <br/> |边缘服务器内部接口  <br/> |从你的 Director、控制器池 VIP 地址、前端服务器或前端池 VIP 地址到边缘服务器内部接口的出站 SIP 流量。  <br/> |
|访问/SIP （MTLS）  <br/> |TCP  <br/> |5061  <br/> |边缘服务器内部 VIP 接口  <br/> |各种  <br/> •控制器  <br/> •控制器池 VIP 地址  <br/> •前端服务器  <br/> •前端池 VIP 地址  <br/> |来自边缘服务器内部接口的到控制器、控制器池 VIP 地址、前端服务器或前端池 VIP 地址的入站 SIP 流量。  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |各种  <br/> •前端服务器 IP 地址  <br/> •前端池 IP 地址  <br/> •任何使用此边缘服务器的 Survivable 分支设备  <br/> •任何使用此边缘服务器的 Survivable 分支服务器  <br/> |边缘服务器内部接口  <br/> |您的前端服务器或前端池中的 A/V 用户身份验证，或使用边缘服务器的 Survivable 分支装置或 Survivable 分支服务器进行身份验证。  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |任意  <br/> |边缘服务器内部接口  <br/> |您的内部和外部用户之间的 A/V 媒体传输的首选路径。  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |任意  <br/> |边缘服务器内部 VIP 接口  <br/> |如果 UDP 通信不起作用，则为内部用户与外部用户之间的 A/V 媒体传输的回退路径。 然后，将 TCP 用于文件传输和桌面共享。  <br/> |
