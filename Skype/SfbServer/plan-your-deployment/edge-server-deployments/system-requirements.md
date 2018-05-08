---
title: Skype for Business Server 2015 的边缘服务器系统要求
ms.author: heidip
author: microsoftheidi
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 摘要： 了解如何为业务服务器 Skype 中的边缘服务器的系统要求。
ms.openlocfilehash: aaf8e45c005ff6295e1c0927d6a29abade383bfb
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="edge-server-system-requirements-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 的边缘服务器系统要求
 
**摘要：**了解业务服务器 Skype 中的边缘服务器的系统要求。
  
当谈您 Skype 业务 Server 边缘服务器部署时，这些是您需要为服务器或服务器的环境中本身，以及规划环境结构实现的内容。 有关拓扑、DNS 证书和其他基础结构问题的详细信息，请查看环境要求文档。
  
## <a name="components"></a>组件

在讨论边缘服务器环境时，我们引用，大多数情况下，部署在外围网络 （即可以说工作组或之外的业务服务器域结构您 Skype 域） 的组件。
  
请记住，这些组件是为了成功部署边缘而需要牢记于胸的组件：
  
- [Edge Servers](system-requirements.md#EdgeServers)
    
- [Reverse proxies](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directors](system-requirements.md#Directors)（这类组件是可选的，如果纳入这些组件，它们将位于内部网络中）
    
- [负载平衡器](system-requirements.md#LoadBalancers)（您可以 DNS 负载平衡或硬件负载平衡器 (HLB)，但对于单个边缘服务器，这不需要）
    
下面我们更详细地谈论以下每个组件：
  
### <a name="edge-servers"></a>边缘服务器
<a name="EdgeServers"> </a>

这些是业务服务器在外围环境中部署的 Skype。 他们的角色是发送和接收由业务服务器部署在内部 Skype 提供的服务的外部用户的网络流量。 若要成功执行此操作，每台边缘服务器运行：
  
- **访问边缘服务**： 为出站和入站会话初始协议 (SIP) 流量提供单一的受信任连接点。
    
- **Web 会议边缘服务**： 允许外部用户可以加入您的业务服务器环境的内部 Skype 上承载的会议。
    
- **A / V 边缘服务**： 使音频、 视频、 应用程序共享和文件传输供外部用户。
    
- **XMPP 代理服务**： 接受和可扩展消息和状态协议 (XMPP) 将消息发送到和从配置 XMPP 联盟伙伴。
    
授权的外部用户可以使用边缘服务器连接到业务服务器部署在内部 Skype 但否则，将它们提供的任何人都到内部网络的任何其他访问。
  
> [!NOTE]
> 部署了边缘服务器提供连接启用 Skype 业务客户端和其他边缘服务器 （在联盟方案）。 不能从其他端点客户端或服务器节点进行连接。 XMPP 网关服务器可允许与配置的 XMPP 伙伴进行连接。 但同样，这些伙伴仅限可行的客户端和联盟类型。 
  
### <a name="reverse-proxies"></a>反向代理
<a name="ReverseProxies"> </a>

反向代理 (RP) 服务器已没有 Skype 对于业务服务器角色，但边缘服务器部署的基本组件。 反向代理允许外部用户：
  
- 使用简单 URL 连接到会议或电话拨入式会议。
    
- 下载会议内容。
    
- 展开通讯组。
    
- 获取基于用户的证书，用于基于客户端证书的身份验证
    
- 从通讯簿服务器，或者向通讯簿 Web 查询服务提交查询，请下载文件。
    
- 获得客户和设备软件的更新。
    
对于移动设备：
  
- 这会让其自动发现前端服务器提供 mobility service。
    
- 使移动设备从 Office 365 的推送通知。
    
可以在[for Business 的 Skype 的电话基础结构](https://technet.microsoft.com/en-us/office/dn947483)上找到我们当前的反向代理建议。 因此，反向代理：
  
- 应能够使用通过公共证书引入环境的传输层安全性 (TLS) 连接到以下对象的已发布外部 Web 服务：
    
  - 控制器或控制器池
    
  - 前端服务器或前端池
    
- 需要能使用加密证书发布内部网站，或者根据需要以未加密的方式发布这些网站。
    
- 应能够使用完全限定域名 (FQDN) 在外部发布内部托管网站。
    
- 需要能发布托管网站的所有内容。 默认情况下，您可以使用**/** 指令，大多数 web 服务器识别为表示"发布 web 服务器上的所有内容"。 您还可以修改指令 — 例如， **/Uwca/\***，这意味着"发布虚拟目录 Ucwa 下的所有内容。"
    
- 必须与从发布的网站请求内容的客户端建立 TLS 连接。
    
- 必须接受包含使用者替代名称 (SAN) 条目的证书。
    
- 需要能允许将证书绑定到将通过其解析外部 Web 服务 FQDN 的侦听器或接口。侦听器配置优于接口配置。可在一个接口上配置多个侦听器。
    
- 必须允许配置主机头处理。 通常，发送请求客户端的原始主机头必须以透明方式，传递而不是由反向代理进行修改。
    
- 应允许将来自某个外部定义的端口（如 TCP 443）的 TLS 流量桥接至另一个定义的端口（如 TCP 4443）。 反向代理可以解密收据上的数据包，然后重新加密上发送的数据包。
    
- 应将来自某个端口（如 TCP 80）的未加密 TCP 流量桥接至另一端口（如 TCP 8080）。
    
- 需要允许配置或接受“NTLM 身份验证”、“无身份验证”和“传递身份验证”。
    
如果反向代理可以解决此列表中的所有需求，您应为良好的发展，但请记住我们建议在上面提供的链接。
  
### <a name="firewalls"></a>防火墙
<a name="Firewalls"> </a>

需要将边缘部署放在外部防火墙后面，但是我们建议在边缘环境和内部环境之间设两个防火墙，一个外部，一个内部。我们方案的所有文档都有两个防火墙。我们之所以推荐两道防火墙是因为，这可确保从一个网络边缘到另一个网络边缘的严格路由，并对内部网络实施加倍防火墙保护。
  
### <a name="directors"></a>控制器
<a name="Directors"> </a>

这是可选角色。 它可以是单台服务器或池的运行控制器角色的服务器。 它是业务服务器环境内部的 Skype 上找到的一个角色。
  
控制器是接收的 Skype 发送 Business Server 内部服务器到边缘服务器的入站的 SIP 流量内部下一个跃点服务器。 它对入站请求预先进行身份验证，并将其它们重定向到用户的主池或主服务器。 此预身份验证可让您丢弃未确定身份的用户帐户的请求。
  
为什么这很重要？ 控制器的重要功能是 Standard Edition 服务器和前端服务器或前端池防止恶意流量，如拒绝服务 (DoS) 攻击。 如果您的网络淹没无效的外部流量，在控制器将停止流量。
  
### <a name="load-balancers"></a>负载平衡器
<a name="LoadBalancers"> </a>

Skype 的业务服务器 2015 扩展的合并边缘拓扑被优化 DNS 负载平衡新部署中，并建议这样做。 如果您需要高可用性，建议使用硬件负载平衡器的一个特定的情况：
  
- Exchange UM 使用 Exchange UM**早期**到 Exchange 2013 的远程用户。
    
> [!IMPORTANT]
> 必须指出，不能混合使用负载平衡器。 在您 Skype 业务服务器环境中所有接口必须都使用 DNS 或 HLB。 
  
> [!NOTE]
> 直接服务器返回 (DSR) NAT 不受支持的 Skype 业务服务器 2015年。 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>硬件负载平衡器要求边缘服务器的边缘服务器运行 A / V 边缘服务

任何边缘服务器运行 A / V 边缘服务，这些要求：
  
- 对内部和外部端口 443 关闭 TCP nagling（Nagling 是将多个小数据包合并成一个大数据包以提高传输效率的过程）。
    
- 对端口范围为 50000 – 59999 的外部端口关闭 TCP nagling。
    
- 不要在内部或外部防火墙上使用 NAT。
    
- 边缘内部接口必须位于不同网络您边缘服务器外部接口，且必须禁用它们之间的路由。
    
- 外部接口的任何边缘服务器运行 A / V 边缘服务必须使用公开可路由 IP 地址和 NAT 或端口上的任何边缘外部 IP 地址的转换。
    
#### <a name="hlb-requirements"></a>HLB 要求

与 Lync Server 2013 的业务服务器 2015 Skype 不具有大量的基于 cookie 的相关性要求。 因此您无需使用基于 cookie 的持久性**除非**您将能够在您 Skype 业务服务器环境中的 Lync Server 2010 前端服务器或前端池。 他们将需要在配置方法中建议的 Lync Server 2010 基于 cookie 的相关性。
  
> [!NOTE]
> 如果决定为 HLB 开启基于 Cookie 的相关性，那么即使环境不需要，这样做也没有问题。 
  
如果环境**不**需要基于 Cookie 的相关性：
  
- 在端口 443 的反向代理发布规则，将设置为**True**的**正向主机标头**。 这可确保转发原始 URL。
    
对于**确实**需要基于 Cookie 的相关性的部署：
  
- 在端口 443 的反向代理发布规则，将设置为**True**的**正向主机标头**。 这可确保转发原始 URL。
    
- 硬件负载平衡器 cookie**不得**标记为 httpOnly。
    
- 硬件负载平衡器 cookie**不得**具有过期时间。
    
- 硬件负载平衡器 cookie**必须**命名**为 MS-WSMAN** （这是 Web 服务预期的并且不能更改的值）。
    
- 硬件负载平衡器 cookie**必须**设置为其传入的 HTTP 请求没有 cookie 中，无论该相同的 TCP 连接上以前 HTTP 响应是否具有变得 cookie 每个 HTTP 响应。 如果您的硬件负载平衡器优化 cookie 插入只发生后该优化**不必须**使用每个 TCP 连接。
    
> [!NOTE]
> 它是 HLB 配置使用源相关性和 20 分钟 TCP 会话生存期，这对于 Skype 业务服务器 2015年和其客户端，因为会话状态维护通过客户端使用情况和/或应用程序交互的典型。 
  
如果部署移动设备，则您的 HLB 必须能对 TCP 会话中的各个请求进行负载平衡（实际上，您需要能基于目标 IP 地址对单个请求进行负载平衡）。
  
> [!IMPORTANT]
> F5 HLB 有一个名为 OneConnect 的功能。该功能确保一个 TCP 连接中的每个请求是单独进行负载平衡的。如果部署的是移动设备，请确保您的 HLB 供应商支持这同一功能。最新的 iOS 移动应用程序需要 TLS 1.2 版。如果需要了解更多，F5 提供了专门针对这一要求的设置。 
  
以下是控制器 （可选） 和 （必需） 的前端池 Web 服务的 HLB 要求：
  
- 为内部的 Web 服务 Vip，设置您 HLB Source_addr 持久性 （内部端口 80、 443）。 对于业务服务器 2015年的 Skype，Source_addr 持久性意味着，来自单个 IP 地址的多个连接始终发送到一台服务器，以维护会话状态。
    
- 使用 TCP 空闲超时 1800 秒。
    
- 在您下一跃点池 HLB 之间反向代理防火墙中，创建一个规则来允许 https： 端口 4443，从您 HLB 您反向代理上的流量。 需要将 HLB 配置为侦听端口 80、443 和 4443。
    
#### <a name="summary-of-hlb-affinity-requirements"></a>HLB 相关性要求摘要

|**客户端/用户位置**|**外部 web 服务 FQDN 关联要求**|**内部 web 服务 FQSN 关联要求**|
|:-----|:-----|:-----|
|Skype 业务 Web app （内部和外部用户）  <br/> 移动设备（内部和外部用户）  <br/> |无相关性  <br/> |源地址相关性  <br/> |
|Skype 业务 Web 应用程序 （仅外部用户）  <br/> 移动设备（内部和外部用户）  <br/> |无相关性  <br/> |源地址相关性  <br/> |
|Skype 业务 Web 应用程序 （仅内部用户）  <br/> 移动设备（未部署）  <br/> |无相关性  <br/> |源地址相关性  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>HLB 的端口监视

您可以定义端口监视您的硬件负载平衡器来确定何时特定服务不再可用，由于硬件或通信失败而导致上。 例如，如果前端服务器服务 (RTCSRV) 停止因为前端服务器或前端池失败，HLB 监控还应该停止接收通信，在 Web 服务。 应在 HLB 上实施端口监视来监视 HLB 外部接口的以下信息：
  
|**虚拟 IP/端口**|**节点端口**|**节点计算机/监视器**|**持久性配置文件**|**说明**|
|:-----|:-----|:-----|:-----|:-----|
|\<池\>web_mco_443_vs  <br/> 443  <br/> |端口 4443  <br/> |前端  <br/> 5061  <br/> |无  <br/> |HTTPS  <br/> |
|\<池\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |前端  <br/> 5061  <br/> |无  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>硬件和软件要求

我们已经我们总体[服务器要求的业务服务器 2015 Skype](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)文档中介绍边缘服务器的硬件和软件要求。
  
## <a name="collocation"></a>并置

我们已经我们[拓扑的业务服务器 2015年的 Skype 的基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)文档中介绍的边缘服务器并置。
  

