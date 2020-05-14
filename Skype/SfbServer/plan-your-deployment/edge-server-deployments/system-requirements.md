---
title: Skype for Business Server 中的边缘服务器系统要求
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
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 摘要：了解 Skype for Business Server 中的边缘服务器的系统要求。
ms.openlocfilehash: ce68475ffc2534f686b39bbcdbcd46b7cdee735a
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221022"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Skype for Business Server 中的边缘服务器系统要求
 
**摘要：** 了解 Skype for Business Server 中的边缘服务器的系统要求。
  
在你的 Skype for Business Server Edge 服务器部署时，需要执行这些操作，才能针对环境本身中的服务器或服务器，以及规划环境结构。 有关拓扑、DNS、证书和其他基础结构问题的详细信息，请参阅环境要求文档。
  
## <a name="components"></a>组件

在讨论边缘服务器环境时，我们正在引用大多数在外围网络中部署的组件（这是指在工作组或位于 Skype for business Server 域之外的域中）。
  
请记住，以下是您在成功部署 Edge 时需要记住的组件：
  
- [边缘服务器](system-requirements.md#EdgeServers)
    
- [反向代理](system-requirements.md#ReverseProxies)
    
- [道](system-requirements.md#Firewalls)
    
- [控制器](system-requirements.md#Directors)（这些是可选的，如果包含，它们将位于内部网络中）
    
- [负载平衡](system-requirements.md#LoadBalancers)器（可以具有 DNS 负载平衡或硬件负载平衡器（HLB），但对于单个边缘服务器，不需要这样做。
    
下面详细介绍了每个选项：
  
### <a name="edge-servers"></a>边缘服务器
<a name="EdgeServers"> </a>

这些是部署在你的外围环境中的 Skype for Business 服务器。 其角色是向外部用户发送和接收由内部 Skype for Business Server 部署提供的服务的网络通信。 若要成功执行此操作，每台边缘服务器都将运行：
  
- **访问边缘服务**：为出站和入站会话初始协议（SIP）流量提供单个受信任的连接点。
    
- **Web 会议边缘服务**：允许外部用户加入托管在内部 Skype For business Server 环境中的会议。
    
- **A/V 边缘服务**：使音频、视频、应用程序共享和文件传输可供外部用户使用。
    
- **XMPP 代理服务**：接受并发送来自已配置的 XMPP 联盟伙伴的可扩展消息和状态协议（XMPP）消息。
    
已授权的外部用户可以使用边缘服务器连接到内部 Skype for Business Server 部署，否则，不会为任何人提供对内部网络的其他访问权限。
  
> [!NOTE]
> 部署边缘服务器以提供启用的 Skype for Business 客户端和其他边缘服务器（在联合身份验证方案中）的连接。 无法从其他终结点客户端或服务器类型进行连接。 XMPP 网关服务器可以允许与已配置的 XMPP 合作伙伴的连接。 但同样，这些是唯一可以使用的客户端和联合类型。 

> [!NOTE]
> XMPP 网关和代理在 Skype for business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 有关详细信息，请参阅[迁移 XMPP 联合](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。
  
### <a name="reverse-proxies"></a>反向代理
<a name="ReverseProxies"> </a>

反向代理（RP）服务器没有 Skype for Business Server 角色，但它是边缘服务器部署的基本组件。 反向代理允许外部用户执行以下操作：
  
- 使用简单 Url 连接到会议或电话拨入式会议。
    
- 下载会议内容。
    
- 展开 "通讯组"。
    
- 获取基于用户的证书以用于基于客户端证书的身份验证
    
- 从通讯簿服务器下载文件，或将查询提交到通讯簿 Web 查询服务。
    
- 获取客户端和设备软件的更新。
    
对于移动设备：
  
- 它让他们能够自动发现提供移动服务的前端服务器。
    
- 它支持从 Microsoft 365 或 Office 365 推送到移动设备的推送通知。
    
我们可以在[Skype for business 的电话基础结构](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)页上找到我们当前的反向代理建议。 因此，你的反向代理：
  
- 应能够使用通过公共证书引入的环境中引入的传输层安全性（TLS），以连接到的发布的外部 Web 服务：
    
  - 控制器或控制器池
    
  - 前端服务器或前端池
    
- 需要能够使用证书进行加密来发布内部网站，或在需要时通过未加密的方式发布这些网站。
    
- 应能够使用完全限定的域名（FQDN）在外部发布内部托管的网站。
    
- 需要能够发布托管网站的所有内容。 默认情况下，可以使用 **/\\** * 指令，大多数 web 服务器都可以识别该指令，以表示 "发布 web 服务器上的所有内容"。 您还可以修改指令（例如，* */Uwca/ \\ * * *），这意味着 "在虚拟目录 Ucwa 下发布所有内容"。
    
- 必须需要与从已发布网站请求内容的客户端进行 TLS 连接。
    
- 必须接受具有使用者可选名称（SAN）项的证书。
    
- 需要能够允许将证书绑定到外部 web 服务 FQDN 将解析的侦听器或接口。 侦听器配置优于接口。 可以在单个接口上配置多个侦听器。
    
- 必须允许配置主机标头处理。 通常，发出请求的客户端发送的原始主机标头必须透明地传递，而不是由反向代理进行修改。
    
- 应允许将 TLS 流量从一个外部定义的端口（例如，TCP 443）桥接到另一个定义的端口（例如，TCP 4443）。 反向代理可能会在接收时对数据包进行解密，然后在发送时重新加密数据包。
    
- 应允许将未加密的 TCP 流量从一个端口桥接（例如，TCP 80）到另一个端口（例如，TCP 8080）。
    
- 需要允许配置或接受 NTLM 身份验证、无身份验证和传递身份验证。
    
如果反向代理可以满足此列表中的所有需求，则应转到，但请记住上面提供的链接中的建议。
  
### <a name="firewalls"></a>道
<a name="Firewalls"> </a>

您需要将边缘部署置于外部防火墙后面，但我们建议在边缘环境和内部环境之间使用两个防火墙（一个外部）和一个内部防火墙。 我们的应用场景中的所有文档都有两个防火墙。 我们建议采用两个防火墙，因为它可确保严格地从一个网络边缘路由到另一个，并将内部网络的防火墙保护加倍。
  
### <a name="directors"></a>控制器
<a name="Directors"> </a>

这是可选角色。 它可以是单个服务器，也可以是运行控制器角色的服务器池。 它是内置 Skype for Business Server 环境中的角色。
  
Director 是一个内部的下一个跃点服务器，它接收来自发往 Skype for Business Server 内部服务器的边缘服务器的入站 SIP 通信。 它对入站请求，并将其重定向到用户的主池或服务器。 此预身份验证允许您删除未识别的用户帐户请求。
  
为什么要这么做呢？ Director 的一个重要功能是保护 Standard Edition 服务器和前端服务器或前端池免遭恶意流量（如拒绝服务（DoS）攻击）。 如果你的网络充斥了无效的外部流量，则流量将在控制器处停止。
  
### <a name="load-balancers"></a>负载平衡器
<a name="LoadBalancers"> </a>

Skype for Business Server 扩展的合并边缘拓扑已针对新部署的 DNS 负载平衡进行了优化，我们建议这样做。 如果需要高可用性，建议使用硬件负载平衡器来实现一种特定情况：
  
- Exchange 2013**之前**使用 exchange um 的远程用户的 exchange um。
    
> [!IMPORTANT]
> 需要注意的重要一点是，不能混合使用负载平衡器。 在 Skype for Business Server 环境中，所有接口都必须使用 DNS 或 HLB。 
  
> [!NOTE]
> Skype for business Server 不支持直接服务器返回（DSR） NAT。 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>边缘服务器的硬件负载平衡器要求运行 A/V 边缘服务的边缘服务器

对于运行 A/V 边缘服务的任何边缘服务器，需要满足以下要求：
  
- 对内部和外部端口443关闭 TCP nagling （nagling 是将几个小型数据包合并成一个较大的数据包以提高传输效率的过程）。
    
- 对于外部端口范围 50000-59999，请关闭 TCP nagling。
    
- 请勿在内部或外部防火墙上使用 NAT。
    
- 您的边缘内部接口必须位于与边缘服务器外部接口不同的网络上，并且必须禁用它们之间的路由。
    
- 运行 A/V 边缘服务的任何边缘服务器的外部接口都必须使用可公开路由的 IP 地址，并且不会在任何边缘外部 IP 地址上进行 NAT 或端口转换。
    
#### <a name="hlb-requirements"></a>HLB 要求

Skype for Business Server 不具有很多基于 cookie 的相关性要求。 因此，您不需要使用基于 cookie 的持久性，**除非**（且这是 skype For business server 2015 专用的）您的 skype For business server 环境中将包含 Lync Server 2010 前端服务器或前端池。 在为 Lync Server 2010 推荐的配置方法中，它们需要基于 cookie 的相关性。
  
> [!NOTE]
> 如果您决定为您的 HLB 启用基于 cookie 的相关性，则即使您的环境不需要，也不会出现问题。 
  
如果您的环境**不**需要基于 cookie 的相关性：
  
- 在端口443的反向代理发布规则上，将 "**转发主机头**" 设置为**True**。 这将确保转发原始 URL。
    
对于**确实**需要基于 cookie 的相关性的部署：
  
- 在端口443的反向代理发布规则上，将 "**转发主机头**" 设置为**True**。 这将确保转发原始 URL。
    
- 硬件负载平衡器 cookie**不得**标记为 "httpOnly"。
    
- 硬件负载平衡器 cookie**不得**具有过期时间。
    
- 硬件负载平衡器 cookie**必须**命名为**MS-WSMAN** （这是 Web 服务预期的值，并且不能更改）。
    
- 必须在传入的 HTTP 请求没有 cookie 的每个 HTTP 响应中设置硬件负载平衡器 cookie，而**不**考虑该 TCP 连接上以前的 http 响应是否已获得 cookie。 如果您的硬件负载平衡器将 cookie 插入优化为每个 TCP 连接只发生一次，则**不得**使用该优化。
    
> [!NOTE]
> 通常情况下，HLB 配置使用源相关性和20分钟 TCP 会话生存期（适用于 Skype for business Server 及其客户端），因为会话状态是通过客户端使用和/或应用程序交互来维护的。 
  
如果要部署移动设备，HLB 必须能够在 TCP 会话中对单个请求进行负载平衡（实际上，您需要能够根据目标 IP 地址对单个请求进行负载平衡）。
  
> [!IMPORTANT]
> F5 Hlb 具有称为 "OneConnect" 的功能。 它确保 TCP 连接中的每个请求都单独进行负载平衡。 如果要部署移动设备，请确保您的 HLB 供应商支持相同的功能。 最新的 iOS 移动应用需要 TLS 版本1.2。 如果需要了解详细信息，按 F5 可为此提供特定的设置。 
  
以下是（可选） Director 和（必需）前端池 Web 服务的 HLB 要求：
  
- 对于内部 Web 服务 Vip，请在 HLB 上设置 Source_addr 持久性（内部端口80、443）。 对于 Skype for Business Server，Source_addr 暂留意味着来自单个 IP 地址的多个连接将始终发送到一台服务器，以维护会话状态。
    
- 使用1800秒的 TCP 空闲超时。
    
- 在反向代理与下一个跃点池的 HLB 之间的防火墙上，创建一个规则，以允许从您的反向代理到您的 HLB 的端口4443上的 https：流量。 您的 HLB 需要配置为侦听端口80、443和4443。
    
#### <a name="summary-of-hlb-affinity-requirements"></a>HLB 相关性要求摘要

|**客户端/用户位置**|**外部 Web 服务 FQDN 关联要求**|**内部 web 服务 FQDN 相关性要求**|
|:-----|:-----|:-----|
|Skype for Business Web 应用程序（内部和外部用户）  <br/> 移动设备（内部和外部用户  <br/> |无相关性  <br/> |源地址相关性  <br/> |
|Skype for Business Web 应用程序（仅限外部用户）  <br/> 移动设备（内部和外部用户  <br/> |无相关性  <br/> |源地址相关性  <br/> |
|Skype for Business Web 应用程序（仅限内部用户）  <br/> 移动设备（未部署）  <br/> |无相关性  <br/> |源地址相关性  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Hlb 的端口监视

您可以在硬件负载平衡器上定义端口监控，以确定特定服务何时不再可用，因为硬件或通信故障。 例如，如果前端服务器服务（RTCSRV）因前端服务器或前端池出现故障而停止，则 HLB 监视还应停止接收 Web 服务上的流量。 应在 HLB 上实现端口监控，以监视 HLB 外部接口的以下内容：
  
|**虚拟 IP/端口**|**节点端口**|**节点计算机/监视器**|**持久性配置文件**|**Notes**|
|:-----|:-----|:-----|:-----|:-----|
|\<池 \> web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |前端  <br/> 5061  <br/> |无  <br/> |IP-HTTPS  <br/> |
|\<池 \> web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |前端  <br/> 5061  <br/> |无  <br/> |HTTP.SYS  <br/> |
   
## <a name="hardware-and-software-requirements"></a>硬件和软件要求

我们在 Skype for business [server 2015 的总体服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)和[Skype for business server 2019 文档的系统要求](../../../SfBServer2019/plan/system-requirements.md)中介绍了边缘服务器硬件和软件要求。
  
## <a name="collocation"></a>并置

我们在[拓扑基础知识 For Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md)文档中介绍了边缘服务器并置。
  

