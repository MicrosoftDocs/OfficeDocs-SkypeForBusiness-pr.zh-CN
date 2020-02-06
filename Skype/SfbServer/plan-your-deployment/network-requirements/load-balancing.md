---
title: Skype for Business 的负载平衡要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：在实施 Skype for Business 服务器之前，请查看负载平衡注意事项。
ms.openlocfilehash: 199c93528d89786573bdac16077f1e32feb1fe6f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802042"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a>Skype for Business 的负载平衡要求
 
**摘要：** 在实施 Skype for Business 服务器之前，请查看负载平衡注意事项。
  
负载平衡在池中的服务器之间分配流量。 如果您有前端池、中介服务器池或边缘服务器池，则需要为这些池部署负载平衡。
  
Skype for Business 服务器支持客户端到服务器流量的两种类型的负载平衡解决方案：域名系统（DNS）负载平衡和硬件负载平衡（通常缩写为 HLB）。 DNS 负载平衡提供了多项优势，包括更简单的管理、更高效的故障排除以及隔离大部分 Skype for Business 服务器流量的能力，从而避免任何潜在的硬件负载平衡器问题。
  
确定你的负载平衡解决方案适合你的部署中的每个池，但请记住以下限制： 
  
- 内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。您不能在一个接口上使用 DNS 负载平衡的同时，在另一个接口上使用硬件负载平衡。
    
- 某些类型的流量需要硬件负载平衡器。例如，HTTP 流量需要硬件平衡负载器而非 DNS 负载平衡。DNS 负载平衡对客户端到服务器的 Web 流量不起作用。
    
如果选择对某个池使用 DNS 负载平衡，但仍需对流量（如 HTTP 流量）实现硬件负载平衡器，则会大大简化硬件负载平衡器的管理。例如，配置硬件负载平衡器将更简单，因为它仅管理 HTTP 和 HTTPS 流量，而所有其他协议将由 DNS 负载平衡管理。有关详细信息，请参阅 [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing)。 
  
对于服务器到服务器的流量，Skype for business 服务器使用拓扑感知负载平衡。 服务器在中央管理存储中读取已发布的拓扑，以获取拓扑中服务器的 Fqdn，并自动在服务器之间分配流量。 管理员不必设置或管理此类型的负载平衡。 
  
如果使用 DNS 负载平衡并且需要阻止至特定计算机的流量，则仅仅删除池 FQDN 中的 IP 地址条目是不够的。您还必须删除计算机的 DNS 条目。 
  
## <a name="hardware-load-balancer-requirements"></a>硬件负载平衡器要求

Skype for Business 服务器缩放的合并边缘拓扑已针对新部署优化了 DNS 负载平衡，主要与使用 Skype for Business Server 或 Lync Server 的其他组织联盟。 如果以下任何方案需要高可用性，则必须在 Edge 服务器池中使用硬件负载平衡器才能执行以下操作： 
  
- 与使用 Office 通信服务器 2007 R2 或 Office 通信服务器2007的组织进行联盟
    
- 在与 SP1 的 Exchange 2010 之前使用 Exchange UM 的远程用户的 exchange UM
    
- 与公共 IM 用户的连接
    
> [!IMPORTANT]
> 不支持对一个接口使用 DNS 负载平衡，而对另一个接口使用硬件负载平衡。必须对两个接口都使用硬件负载平衡，或者对两个接口都使用 DNS 负载平衡。 
  
> [!NOTE]
> 如果使用硬件负载平衡器，则为内部网络连接部署的负载平衡器必须配置为仅对发往运行访问边缘服务和 A/V 边缘服务的服务器的流量进行负载平衡。它不能对发往内部 Web 会议边缘服务或内部 XMPP 代理服务的流量进行负载平衡。 
  
> [!NOTE]
> Skype for Business Server 不支持直接服务器返回（DSR） NAT。 
  
若要确定硬件负载平衡器是否支持 Skype for business 服务器所需的功能，请参阅[skype for Business 基础结构](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>运行 A/V 边缘服务的边缘服务器的硬件负载平衡器要求

以下是运行 A/V 边缘服务的边缘服务器的硬件负载平衡器要求：
  
- 对内部和外部端口 443 关闭 TCP nagling。Nagling 是将若干小数据包整合到单个大数据包以提高传输效率的过程。
    
- 对于外部端口范围 50000-59999，请关闭 TCP nagling。 
    
- 请不要对内部或外部防火墙使用 NAT。 
    
- Edge 内部接口必须位于不同的网络上，而不是边缘服务器外部接口和必须禁用它们之间的路由。 
    
- 运行 A/V 边缘服务的边缘服务器的外部接口必须使用可公开路由的 IP 地址，并且任何边缘外部 IP 地址上没有 NAT 或端口转换。 
    
- 负载平衡器不得更改客户端的源地址。
    
### <a name="other-hardware-load-balancer-requirements"></a>其他硬件负载平衡器要求

在 Web 服务的 Skype for business 服务器中，基于 Cookie 的相关性要求大大减少。 如果你要部署 Skype for Business 服务器，并且不会保留任何 Lync Server 2010 前端服务器或前端池，则不需要基于 cookie 的持久性。 但是，如果你将临时或永久保留任何 Lync Server 2010 前端服务器或前端池，你仍然使用基于 cookie 的持久性，因为它是为 Lync Server 2010 部署和配置的。 
  
> [!NOTE]
> **如果您决定使用基于 Cookie 的相关性，但您的部署不需要它**，如此做没有任何负面影响。 
  
对于 **不使用**基于 Cookie 的相关性的部署：
  
- 在端口 4443 的反向代理发布规则上，将“**转发主机头**”设置为 True。 这可确保转发原始 URL。
    
对于**将使用**基于 Cookie 的相关性的部署：
  
- 在端口 4443 的反向代理发布规则上，将“**转发主机头**”设置为 True。这可确保转发原始 URL。
    
- 不得将硬件负载平衡器 Cookie 标记为 httpOnly
    
- 硬件负载平衡器 Cookie 不得具有过期时间
    
- 硬件负载平衡器 Cookie 必须名为 **MS-WSMAN**（这是 Web 服务预期的值，不能更改）
    
- 必须在其传入 HTTP 请求没有 Cookie 的每个 HTTP 响应中设置硬件负载平衡器 Cookie，无论该同一 TCP 连接上的上一个 HTTP 响应是否已获得 Cookie 都是如此。如果负载平衡器将 Cookie 插入优化为每个 TCP 连接只发生一次，则不得使用该优化
    
> [!NOTE]
> 典型的硬件负载平衡器配置使用源地址相关性和20分钟 TCP 会话生存期，这对于 Lync Server 和 Lync 2013 客户端来说非常合适，因为会话状态是通过客户端使用和/或应用程序交互维护的。 
  
如果部署移动设备，则您的硬件负载平衡器必须能对 TCP 会话中的单个请求进行负载平衡（实际上，您必须能基于目标 IP 地址对单个请求进行负载平衡）。
  
> [!CAUTION]
> 如果你要部署移动设备，你的硬件负载平衡器必须能够在 TCP 连接内单独对每个请求进行负载平衡。 最新的 Apple iOS 移动应用程序要求传输层安全性 (TLS) 1.2 版。  
  
> [!CAUTION]
> 有关第三方硬件负载平衡器的详细信息，请参阅[Skype for Business 基础结构](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。  
  
以下是控制器和前端池 Web 服务的硬件负载平衡器要求：
  
- 对于内部 Web 服务 VIP，在硬件负载平衡器上设置 Source_addr 持久性（内部端口 80 和 443）。 对于 Skype for Business 服务器，Source_addr 持久性意味着来自单个 IP 地址的多个连接始终发送到一台服务器，以维护会话状态。
    
- 使用 TCP 空闲超时 1800 秒。
    
- 在反向代理和下一个跃点池的硬件负载平衡器之间的防火墙上，创建规则以允许 https：从反向代理到硬件负载平衡器的端口4443上的流量。 必须将硬件负载平衡器配置为侦听端口 80、443 和 4443。
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>硬件负载平衡器关联要求的摘要

|**客户端/用户位置**|**外部 Web 服务 FQDN 关联要求**|**内部 Web 服务 FQDN 关联要求**|
|:-----|:-----|:-----|
|Lync Web App （内部和外部用户）  <br/> 移动设备（内部和外部用户）  <br/> |无相关性  <br/> |源地址相关性  <br/> |
|Lync Web App （仅限外部用户）  <br/> 移动设备（内部和外部用户）  <br/> |无相关性  <br/> |源地址相关性  <br/> |
|Lync Web App （仅限内部用户）  <br/> 移动设备（未部署）  <br/> |无相关性  <br/> |源地址相关性  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a>硬件负载平衡器的端口监控

在硬件负载平衡器上定义端口监控来确定特定服务何时由于硬件或通信故障而不再可用。 例如，如果前端服务器服务（RTCSRV）因前端服务器或前端池出现故障而停止，则 HLB 监视还应停止接收 Web 服务的流量。 可在 HLB 上实施端口监控来监控以下各项：
  
**前端服务器用户池-HLB 内部接口**

|**虚拟 IP/端口**|**节点端口**|**节点计算机/监视器**|**持久性配置文件**|**注释**|
|:-----|:-----|:-----|:-----|:-----|
|\<池\>web-int_mco_443_vs  <br/> 443  <br/> |443  <br/> |前端  <br/> 5061  <br/> |源  <br/> |HTTPS  <br/> |
|\<池\>web-int_mco_80_vs  <br/> 80  <br/> |80  <br/> |前端  <br/> 5061  <br/> |源  <br/> |HTTP  <br/> |
   
**前端服务器用户池-HLB 外部接口**

|**虚拟 IP/端口**|**节点端口**|**节点计算机/监视器**|**持久性配置文件**|**注释**|
|:-----|:-----|:-----|:-----|:-----|
|\<池\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |前端  <br/> 5061  <br/> |无  <br/> |HTTPS  <br/> |
|\<池\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |前端  <br/> 5061  <br/> |无  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>DNS Load Balancing
<a name="BKMK_DNSLoadBalancing"> </a>

Skype for Business 服务器支持 DNS 负载平衡，这种软件解决方案可以大大降低网络上负载平衡的管理开销。 DNS 负载平衡平衡 Skype for Business 服务器特有的网络流量，如 SIP 流量和媒体流量。
  
如果你部署 DNS 负载平衡，你的组织的硬件负载平衡器的管理开销将会最小化。 此外，对 SIP 流量的负载平衡器配置错误相关的问题的复杂疑难解答将会被消除。 您也可以阻止服务器连接，以便您可以使服务器脱机。 DNS 负载平衡还可确保硬件负载平衡器问题不会影响 SIP 流量（如基本呼叫路由）的元素。

下图显示了包括内部和外部 DNS 负载平衡的示例： 
  
**使用公用 IPv4 地址的 Edge 网络图**

![DNS 网络图表示例](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
如果使用 DNS 负载平衡，您还可以购买成本较低的硬件负载平衡器，而不是对所有类型的流量使用硬件负载平衡器。 你应该使用与 Skype for Business 服务器已通过互操作性鉴定测试的负载平衡器。 有关负载平衡器互操作性测试的详细信息，请参阅[Lync Server 2010 负载平衡器合作伙伴](https://go.microsoft.com/fwlink/p/?linkId=202452)。 此处的内容适用于 Skype for Business 服务器。
  
对于前端池、边缘服务器池、控制器池和独立的中介服务器池，DNS 负载平衡受支持。
  
DNS 负载平衡通常在应用程序级别实现。 应用程序（例如，运行 Skype for Business 的客户端）通过连接到池完全限定的域名（FQDN）的 DNS A 和 AAAA （如果使用 IPv6 寻址）记录查询来连接到池中的某个服务器，尝试连接到池中的服务器。 
  
例如，如果一个名为 pool01.contoso.com 的池中有三个前端服务器，则将发生以下情况：
  
- 运行 Skype for business 的 pool01.contoso.com 的客户端查询 DNS。 该查询返回三个 IP 地址并将其缓存，如下所示（不必按此顺序）：
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92
    
- 客户端尝试建立与其中一个 IP 地址的传输控制协议（TCP）连接。 如果此操作失败，客户端将尝试缓存中的下一个 IP 地址。
    
- 如果 TCP 连接成功，则客户端与 TLS 协商连接到 pool01.contoso.com 上的主注册器。
    
- 如果客户在未成功连接的情况下尝试所有缓存的条目，则系统将通知用户目前没有运行 Skype for business 服务器的服务器可用。
    
> [!NOTE]
> 基于 DNS 的负载平衡不同于 DNS 循环（DNS RR），它通常指的是负载平衡，具体取决于 DNS 以提供与池中的服务器对应的不同 IP 地址顺序。 通常，DNS RR 仅支持负载分配，但不支持故障转移。 例如，如果连接到 DNS A 和 AAAA 返回的一个 IP 地址（如果使用的是 IPv6 寻址）查询失败，连接将失败。 因此，DNS 循环复用本身比基于 DNS 的负载平衡的可靠性更低。 你可以将 DNS 循环与 DNS 负载平衡结合使用。 
  
DNS 负载平衡用于以下情况：
  
- 将服务器到服务器 SIP 负载平衡到边缘服务器
    
- 负载平衡统一通信应用程序服务（UCAS）应用程序，如会议自动助理、响应组和呼叫寄存
    
- 阻止新连接 UCAS 应用程序（也称为 "排出"）
    
- 负载平衡客户端和边缘服务器之间的所有客户端到服务器流量
    
无法将 DNS 负载平衡用于以下情况：
  
- 客户端到服务器 web 流量到控制器或前端服务器
    
DNS 负载平衡和联合通信：
  
如果 DNS SRV 查询返回多个 DNS 记录，则 Access Edge 服务始终使用最小的数值优先级和最高的数字权重来选取 DNS SRV 记录。 Internet 工程任务强制文档 "用于指定服务位置的 DNS RR （DNS SRV）" [RFC 2782，DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt)指定如果已定义多个 DNS srv 记录，将首先使用 "优先级"，然后按 "重量"。 例如，DNS SRV 记录 A 的权重为20，优先级为40，DNS SRV 记录 B 的权重为10，优先级为50。 将选择优先级为40的 DNS SRV 记录 A。 以下规则适用于 DNS SRV 记录选择：
  
- 首先考虑优先级。 客户端必须尝试联系由 DNS SRV 记录定义的目标主机，该目标主机可以访问的最低优先级。 应按照权重字段定义的顺序尝试具有相同优先级的目标。
    
- "权重" 域为具有相同优先级的条目指定相对权重。 应按比例增加所选的概率。 当没有任何服务器选择要执行时，DNS 管理员应使用权重0。 如果记录包含的权重大于0，则权重为0的记录应具有非常小的选择机会。
    
如果返回具有相同优先级和权重的多个 DNS SRV 记录，则 Access Edge 服务将选择首先从 DNS 服务器接收的 SRV 记录。
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>前端池和控制器池上的 DNS 负载平衡

你可以对前端池和控制器池上的 SIP 流量使用 DNS 负载平衡。 在部署了 "DNS 负载平衡" 的情况下，你还需要对这些池使用硬件负载平衡器，但仅需要客户端到服务器的 HTTPS 流量。 硬件负载平衡器用于来自端口443和80的客户端的 HTTPS 流量。 
  
尽管你仍需要这些池的硬件负载平衡器，但其设置和管理主要用于 HTTPS 流量，这些通信是硬件负载平衡器的管理员习惯的。
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>DNS 负载平衡和支持较旧的客户端和服务器

仅对于运行 Skype for Business Server 或 Lync Server 2010 的服务器以及 Lync 2013 和 Skype for business 客户端，DNS 负载平衡才支持自动故障转移。 早期版本的客户端和 Office 通信服务器仍然可以连接到运行 DNS 负载平衡的池，但如果它们无法连接到 DNS 负载平衡所引用的第一台服务器，则它们无法故障转移到池中的另一台服务器. 
  
此外，如果您使用的是 Exchange UM，则必须至少使用 Exchange 2010 SP1，才能获取 Skype for business 服务器 DNS 负载平衡的支持。 如果你使用的是早期版本的 Exchange，你的用户将不具有以下 Exchange UM 方案的故障转移功能：
  
- 在手机上播放企业语音邮件
    
- 转移来自 Exchange UM 自动助理的呼叫
    
所有其他 Exchange UM 方案都将正常工作。
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>在前端池和控制器池上部署 DNS 负载平衡
<a name="BK_FE_Dir"> </a>

在前端池和控制器池上部署 DNS 负载平衡需要使用 Fqdn 和 DNS 记录执行一些额外步骤。
  
- 使用 DNS 负载平衡的池必须具有两个 Fqdn：由 DNS 负载平衡使用的常规池 FQDN （如 pool01.contoso.com），并解析为池中服务器的物理 Ip 以及该池的 Web 服务的其他 FQDN （如web01.contoso.com），它解析为池的虚拟 IP 地址。 
    
    在拓扑生成器中，如果要为池部署 DNS 负载平衡，若要为池的 Web 服务创建此额外的 FQDN，必须选中 "**替代内部 Web 服务池 FQDN** " 复选框，然后在 "**指定此池的 Web 服务 url** " 页面中键入 FQDN。
    
- 若要支持 DNS 负载平衡使用的 FQDN，必须预配 DNS 以将池 FQDN （如 pool01.contoso.com）解析为池中所有服务器的 IP 地址（例如192.168.1.1、192.168.1.2 等）。 应仅包含当前已部署的服务器的 IP 地址。
    
    > [!CAUTION]
    > 如果您有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。 例如，如果你将前端服务器的外部 Web 服务 FQDN 定义为**pool01.contoso.com**，则不能将**Pool01.contoso.com**用于其他前端池或前端服务器。 如果你还部署控制器，则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须是任何其他 Director 或控制器池以及任何前端池或前端服务器的唯一。 如果决定使用自定义的 FQDN 替代内部 web 服务，则每个 FQDN 都必须与任何其他前端池、Director 或控制器池唯一。
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>边缘服务器池中的 DNS 负载平衡
<a name="BK_Edge"> </a>

你可以在 Edge 服务器池上部署 DNS 负载平衡。 如果执行此操作，则必须注意一些事项。
  
在边缘服务器上使用 DNS 负载平衡会导致在以下情况下丢失故障转移能力：
  
- 与运行在 Lync Server 2010 之前发布的 Skype for business Server 版本的组织进行联盟。
    
- 与公共即时消息（IM）服务 AOL 和 Yahoo！的用户进行即时消息交换，除了基于 XMPP 的提供商和服务器（如 Google 通话），当前仅支持 XMPP 合作伙伴。
    
只要池中的所有边缘服务器都已启动并正在运行，这些方案就会正常运行，但如果一台边缘服务器不可用，则对发送给它的这些方案的任何请求都将失败，而不是路由到另一台边缘服务器。
  
 如果您使用的是 Exchange UM，则必须至少使用 Exchange 2013，才能获取有关 Edge 的 Skype for business 服务器 DNS 负载平衡的支持。 如果您使用的是早期版本的 Exchange，则您的远程用户将不具有以下 Exchange UM 方案的故障转移功能：
  
- 在手机上播放企业语音邮件
    
- 转移来自 Exchange UM 自动助理的呼叫
    
所有其他 Exchange UM 方案都将正常工作。
  
内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。 您不能在一个边缘接口上使用 DNS 负载平衡的同时，在另一个边缘接口上使用硬件负载平衡。
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>在 Edge 服务器池上部署 DNS 负载平衡

若要在 Edge 服务器池的外部接口上部署 DNS 负载平衡，需要以下 DNS 条目：
  
- 对于访问边缘服务，池中的每个服务器都需要一个条目。 每个条目都必须将访问边缘服务的 FQDN （例如，sip.contoso.com）解析为池中某个边缘服务器上的访问边缘服务的 IP 地址。
    
- 对于 Web 会议 Edge 服务，池中的每台服务器都需要一个条目。 每个条目都必须将 Web 会议 Edge 服务（例如，webconf.contoso.com）的 FQDN 解析为池中的一个边缘服务器上的 Web 会议边缘服务的 IP 地址。
    
- 对于音频/视频边缘服务，池中的每台服务器都需要一个条目。 每个条目都必须将音频/视频边缘服务（例如，av.contoso.com）的 FQDN 解析为池中的一个边缘服务器上的 A/V 边缘服务的 IP 地址。
    
若要在 Edge 服务器池的内部接口上部署 DNS 负载平衡，必须添加一个 DNS A 记录，该记录将 Edge 服务器池的内部 FQDN 解析为池中每个服务器的 IP 地址。
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>在中介服务器池中使用 DNS 负载平衡
<a name="BK_Mediation"> </a>

可以在独立的中介服务器池上使用 "DNS 负载平衡"。 所有 SIP 和媒体流量通过 "DNS 负载平衡" 平衡。
  
若要在中介服务器池中部署 DNS 负载平衡，必须预配 DNS 以将池 FQDN （例如，mediationpool1.contoso.com）解析为池中所有服务器的 IP 地址（例如192.168.1.1、192.168.1.2 等）。
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>使用 DNS 负载平衡阻止到服务器的通信
<a name="BK_Mediation"> </a>

如果使用 DNS 负载平衡并且需要阻止至特定计算机的流量，则仅仅删除池 FQDN 中的 IP 地址条目是不够的。您还必须删除计算机的 DNS 条目。 
  
请注意，对于服务器到服务器的流量，Skype for Business 服务器使用拓扑感知负载平衡。 服务器在中央管理存储中读取已发布的拓扑，以获取拓扑中服务器的 Fqdn，并自动在服务器之间分配流量。 若要阻止服务器接收服务器到服务器的流量，必须从拓扑结构中删除该服务器。 
  

