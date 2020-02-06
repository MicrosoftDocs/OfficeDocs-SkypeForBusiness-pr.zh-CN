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
description: 摘要：了解 Skype for Business Server 中 Edge 服务器的系统要求。
ms.openlocfilehash: 4ef2feeb2b486bc9be9f4eb59136d74ef542dd31
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803312"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Skype for Business Server 中的边缘服务器系统要求
 
**摘要：** 了解 Skype for Business Server 中 Edge 服务器的系统要求。
  
在你的 Skype for Business Server Edge 服务器部署时，这些是你需要对环境本身中的服务器或服务器进行的操作，以及规划环境结构。 有关拓扑、DNS 证书和其他基础结构问题的详细信息，请查看环境要求文档。
  
## <a name="components"></a>组件

当讨论 Edge 服务器环境时，我们将引用在外围网络中部署的大部分组件（这是指在工作组或 Skype for business Server 域结构之外的域中）。
  
请记住，这些组件是为了成功部署边缘而需要牢记于胸的组件：
  
- [Edge Servers](system-requirements.md#EdgeServers)
    
- [Reverse proxies](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directors](system-requirements.md#Directors)（这类组件是可选的，如果纳入这些组件，它们将位于内部网络中）
    
- [负载平衡](system-requirements.md#LoadBalancers)器（可以拥有 DNS 负载平衡或硬件负载平衡器（HLB），但对于单个边缘服务器，不需要这样做。
    
下面我们更详细地谈论以下每个组件：
  
### <a name="edge-servers"></a>边缘服务器
<a name="EdgeServers"> </a>

这些是您的外围环境中部署的 Skype for business 服务器。 其角色是向外部用户发送和接收网络流量，以供内部 Skype for Business 服务器部署所提供的服务。 若要成功执行此操作，每台边缘服务器都将运行：
  
- **Access Edge 服务**：为出站和入站会话初始协议（SIP）流量提供单个受信任的连接点。
    
- **网络会议边缘服务**：允许外部用户加入托管在内部 Skype For business 服务器环境中的会议。
    
- **A/V 边缘服务**：使音频、视频、应用程序共享和文件传输可供外部用户使用。
    
- **XMPP 代理服务**：接受和发送可扩展消息和状态协议（XMPP）消息，并发送到已配置的 XMPP 联盟合作伙伴。
    
已授权的外部用户可以使用你的 Edge 服务器连接到内部 Skype for Business 服务器部署，否则，它们不会为任何人提供对内部网络的其他访问权限。
  
> [!NOTE]
> 部署边缘服务器以提供适用于已启用的 Skype for Business 客户端和其他边缘服务器（在联合身份验证方案中）的连接。 不能从其他端点客户端或服务器节点进行连接。 XMPP 网关服务器可允许与配置的 XMPP 伙伴进行连接。 但同样，这些伙伴仅限可行的客户端和联盟类型。 

> [!NOTE]
> XMPP 网关和代理在 Skype for business Server 2015 中可用，但 Skype for business Server 2019 不再支持。 有关详细信息，请参阅[迁移 XMPP 联合身份验证](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。
  
### <a name="reverse-proxies"></a>反向代理
<a name="ReverseProxies"> </a>

反向代理（RP）服务器没有 Skype for business 服务器角色，但是边缘服务器部署的基本组件。 反向代理允许外部用户：
  
- 使用简单 URL 连接到会议或电话拨入式会议。
    
- 下载会议内容。
    
- 展开通讯组。
    
- 获取基于用户的证书，用于基于客户端证书的身份验证
    
- 从通讯簿服务器下载文件，或将查询提交到通讯簿 Web 查询服务。
    
- 获得客户和设备软件的更新。
    
对于移动设备：
  
- 它让他们能够自动发现提供移动服务的前端服务器。
    
- 它支持从 Office 365 到移动设备的推送通知。
    
我们可以在[Skype for business 的电话结构](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)页面上找到当前的反向代理建议。 因此，您的反向代理：
  
- 应能够使用通过公共证书引入环境的传输层安全性 (TLS) 连接到以下对象的已发布外部 Web 服务：
    
  - 导演或控制器池
    
  - 前端服务器或前端池
    
- 需要能使用加密证书发布内部网站，或者根据需要以未加密的方式发布这些网站。
    
- 应能够使用完全限定域名 (FQDN) 在外部发布内部托管网站。
    
- 需要能发布托管网站的所有内容。 默认情况下，你可以使用** / *** 指令，大多数 web 服务器可以识别该指令以表示 "发布 web 服务器上的所有内容"。 您也可以修改指令，例如 * */Uwca/\\* * *，这意味着 "在虚拟目录 Ucwa 下发布所有内容"。
    
- 必须与从发布的网站请求内容的客户端建立 TLS 连接。
    
- 必须接受包含使用者替代名称 (SAN) 条目的证书。
    
- 需要能允许将证书绑定到将通过其解析外部 Web 服务 FQDN 的侦听器或接口。侦听器配置优于接口配置。可在一个接口上配置多个侦听器。
    
- 必须允许配置主机头处理。 通常，发出请求的客户端发送的原始主机标头必须透明地传递，而不是由反向代理进行修改。
    
- 应允许将来自某个外部定义的端口（如 TCP 443）的 TLS 流量桥接至另一个定义的端口（如 TCP 4443）。 你的反向代理可能会在接收时解密数据包，然后在发送时 reencrypt 数据包。
    
- 应将来自某个端口（如 TCP 80）的未加密 TCP 流量桥接至另一端口（如 TCP 8080）。
    
- 需要允许配置或接受“NTLM 身份验证”、“无身份验证”和“传递身份验证”。
    
如果您的反向代理可以满足此列表中的所有需求，您应该可以转到，但请记住上面提供的链接的建议。
  
### <a name="firewalls"></a>防火墙
<a name="Firewalls"> </a>

需要将边缘部署放在外部防火墙后面，但是我们建议在边缘环境和内部环境之间设两个防火墙，一个外部，一个内部。我们方案的所有文档都有两个防火墙。我们之所以推荐两道防火墙是因为，这可确保从一个网络边缘到另一个网络边缘的严格路由，并对内部网络实施加倍防火墙保护。
  
### <a name="directors"></a>控制器
<a name="Directors"> </a>

这是可选角色。 它可以是单个服务器，也可以是运行 Director 角色的服务器池。 它是在内部 Skype for Business 服务器环境中找到的角色。
  
Director 是一个内部下一个跃点服务器，它从发送到 Skype for Business 服务器内部服务器的边缘服务器接收入站 SIP 流量。 它对入站请求预先进行身份验证，并将其它们重定向到用户的主池或主服务器。 此预身份验证可让您丢弃未确定身份的用户帐户的请求。
  
为什么这很重要？ Director 的一个重要功能是保护标准版服务器和前端服务器或前端池免受恶意流量的攻击，例如拒绝服务（DoS）攻击。 如果你的网络因外部流量无效而淹没，流量将在 Director 停止。
  
### <a name="load-balancers"></a>负载平衡器
<a name="LoadBalancers"> </a>

Skype for Business 服务器缩放的合并边缘拓扑针对新部署的 DNS 负载平衡进行了优化，我们建议这样做。 如果需要高可用性，建议使用硬件负载平衡器来实现一个特定情形：
  
- Exchange 2013**之前**使用 exchange um 的远程用户的 exchange um。
    
> [!IMPORTANT]
> 必须指出，不能混合使用负载平衡器。 在您的 Skype for Business 服务器环境中，所有接口都必须使用 DNS 或 HLB。 
  
> [!NOTE]
> Skype for business Server 不支持直接服务器返回（DSR） NAT。 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>运行 A/V 边缘服务的边缘服务器边缘服务器的硬件负载平衡器要求

对于运行 A/V 边缘服务的任何边缘服务器，需要满足以下要求：
  
- 对内部和外部端口 443 关闭 TCP nagling（Nagling 是将多个小数据包合并成一个大数据包以提高传输效率的过程）。
    
- 对端口范围为 50000 – 59999 的外部端口关闭 TCP nagling。
    
- 不要在内部或外部防火墙上使用 NAT。
    
- Edge 内部接口必须与 Edge 服务器外部接口位于不同的网络上，并且必须禁用它们之间的路由。
    
- 运行 A/V 边缘服务的任何边缘服务器的外部接口必须使用可公开路由的 IP 地址，并且任何边缘外部 IP 地址上都没有 NAT 或端口转换。
    
#### <a name="hlb-requirements"></a>HLB 要求

Skype for Business 服务器没有许多基于 cookie 的相关性要求。 因此，你无需使用基于 cookie 的持久性，**除非**（这是 skype For business server 2015-特定的 skype for business server），你将在 skype For business server 环境中拥有 Lync Server 2010 前端服务器或前端池。 它们在 Lync Server 2010 推荐的配置方法中需要基于 cookie 的相关性。
  
> [!NOTE]
> 如果决定为 HLB 开启基于 Cookie 的相关性，那么即使环境不需要，这样做也没有问题。 
  
如果环境**不**需要基于 Cookie 的相关性：
  
- 在端口443的反向代理发布规则上，将 "**转发主机标题**" 设置为 " **True**"。 这可确保转发原始 URL。
    
对于**确实**需要基于 Cookie 的相关性的部署：
  
- 在端口443的反向代理发布规则上，将 "**转发主机标题**" 设置为 " **True**"。 这可确保转发原始 URL。
    
- 硬件负载平衡器 cookie**不得**标记为 "httpOnly"。
    
- 硬件负载平衡器 cookie**不得**有过期时间。
    
- 硬件负载平衡器 cookie**必须**命名为**MS-WSMAN** （这是 Web 服务预期的值，并且不能更改）。
    
- 硬件负载平衡器 cookie**必须**在每个 http 响应中设置，其中传入的 HTTP 请求没有 cookie，无论同一 TCP 连接上的以前 HTTP 响应是否已获得 cookie。 如果硬件负载平衡器针对每个 TCP 连接优化 cookie 插入，则**不**能使用该优化。
    
> [!NOTE]
> 对于 Skype for business 服务器及其客户端来说，HLB 配置使用源相关性和20分钟 TCP 会话生存期很常见，因为会话状态是通过客户端使用和/或应用程序交互维护的。 
  
如果部署移动设备，则您的 HLB 必须能对 TCP 会话中的各个请求进行负载平衡（实际上，您需要能基于目标 IP 地址对单个请求进行负载平衡）。
  
> [!IMPORTANT]
> F5 HLB 有一个名为 OneConnect 的功能。该功能确保一个 TCP 连接中的每个请求是单独进行负载平衡的。如果部署的是移动设备，请确保您的 HLB 供应商支持这同一功能。最新的 iOS 移动应用程序需要 TLS 1.2 版。如果需要了解更多，F5 提供了专门针对这一要求的设置。 
  
以下是（可选）董事和（必需）前端池 Web 服务的 HLB 要求：
  
- 对于内部 Web 服务 Vip，请在 HLB 上设置 Source_addr 持久性（内部端口80、443）。 对于 Skype for Business 服务器，Source_addr 持久性意味着来自单个 IP 地址的多个连接始终发送到一台服务器，以维护会话状态。
    
- 使用 TCP 空闲超时 1800 秒。
    
- 在反向代理和下一个跃点池的 HLB 之间的防火墙上，创建规则以允许 https：从反向代理到你的 HLB 的端口4443上的流量。 需要将 HLB 配置为侦听端口 80、443 和 4443。
    
#### <a name="summary-of-hlb-affinity-requirements"></a>HLB 相关性要求摘要

|**客户端/用户位置**|**外部 Web 服务 FQDN 关联要求**|**内部 Web 服务 FQDN 相关性要求**|
|:-----|:-----|:-----|
|Skype for business Web 应用（内部和外部用户）  <br/> 移动设备（内部和外部用户）  <br/> |无相关性  <br/> |源地址相关性  <br/> |
|Skype for business Web 应用（仅限外部用户）  <br/> 移动设备（内部和外部用户）  <br/> |无相关性  <br/> |源地址相关性  <br/> |
|Skype for business Web 应用（仅限内部用户）  <br/> 移动设备（未部署）  <br/> |无相关性  <br/> |源地址相关性  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>HLB 的端口监视

在硬件负载平衡器上定义端口监视，以确定因硬件或通信故障而无法使用特定服务的时间。 例如，如果前端服务器服务（RTCSRV）因前端服务器或前端池出现故障而停止，则 HLB 监视还应停止接收 Web 服务的流量。 应在 HLB 上实施端口监视来监视 HLB 外部接口的以下信息：
  
|**虚拟 IP/端口**|**节点端口**|**节点计算机/监视器**|**持久性配置文件**|**注释**|
|:-----|:-----|:-----|:-----|:-----|
|\<池\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |前端  <br/> 5061  <br/> |无  <br/> |HTTPS  <br/> |
|\<池\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |前端  <br/> 5061  <br/> |无  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>硬件和软件要求

我们在 skype for business [server 2015 的整体服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)和[Skype for business server 2019 文档的系统要求](../../../SfBServer2019/plan/system-requirements.md)中介绍了 Edge 服务器硬件和软件要求。
  
## <a name="collocation"></a>并置

我们已在我们[的 Skype for Business server 文档的拓扑基础知识基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)中介绍了 Edge 服务器 collocation。
  

