---
title: 中的边缘服务器系统Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 摘要：了解 Skype for Business Server 中的边缘服务器的系统要求。
ms.openlocfilehash: f61412ab8246945e50af0276e46ac53ca080605c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863459"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>中的边缘服务器系统Skype for Business Server
 
**摘要：** 了解边缘服务器在 Skype for Business Server 中的系统Skype for Business Server。
  
对于边缘Skype for Business Server部署，需要针对环境本身的一个或多个服务器执行这些操作，以及规划环境结构。 有关拓扑、DNS、证书和其他基础结构问题的信息，请查看环境要求文档。
  
## <a name="components"></a>组件

讨论边缘服务器环境时，我们主要引用在外围网络 (中部署的组件，即位于工作组或 Skype for Business Server 域结构) 外部的域中。
  
请记住，这些组件是成功部署边缘时需要记住的组件：
  
- [边缘服务器](system-requirements.md#EdgeServers)
    
- [逆向代理](system-requirements.md#ReverseProxies)
    
- [防火墙](system-requirements.md#Firewalls)
    
- [控制器](system-requirements.md#Directors) (这些控制器是可选的，如果包含它们，它们将位于内部网络) 
    
- [负载平衡](system-requirements.md#LoadBalancers) 器 (HLB 服务器具有 DNS 负载平衡或硬件负载平衡器 (HLB) ，但对于单个边缘服务器，这不是) 
    
下面我们详细介绍了其中每一项：
  
### <a name="edge-servers"></a>边缘服务器
<a name="EdgeServers"> </a>

这些服务器Skype for Business部署在外围环境中。 他们的角色是向外部用户发送和接收由内部部署提供的服务的Skype for Business Server通信。 要成功执行这一操作，每台边缘服务器将运行：
  
- **访问边缘服务**：为出站和入站会话初始协议提供单一的受信任连接点 (SIP) 流量。
    
- **Web 会议边缘服务**：允许外部用户加入在内部会议环境中Skype for Business Server会议。
    
- **A/V 边缘服务**：使音频、视频、应用程序共享和文件传输对外部用户可用。
    
- **XMPP 代理** 服务：接受 XMPP 联盟伙伴 (发送) XMPP 联盟伙伴的可扩展消息传递和状态协议。
    
授权外部用户可以使用边缘服务器连接到内部Skype for Business Server部署，但在其他情况下，他们不会为任何人提供对内部网络的其他访问。
  
> [!NOTE]
> 部署边缘服务器为启用的 Skype for Business 客户端和其他边缘服务器 (联盟方案中) 。 无法从其他终端客户端或服务器类型进行连接。 XMPP 网关服务器可以允许与配置的 XMPP 合作伙伴建立连接。 但同样，这些类型是唯一能工作的客户端和联盟类型。 

> [!NOTE]
> XMPP 网关和代理在 Skype for Business Server 2015 中可用，但在 2019 年 2 月不再Skype for Business Server支持。 有关详细信息 [，请参阅迁移 XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 联盟。
  
### <a name="reverse-proxies"></a>逆向代理
<a name="ReverseProxies"> </a>

反向代理 (RP) 服务器没有Skype for Business Server角色，但是边缘服务器部署的重要组件。 反向代理允许外部用户：
  
- 使用简单 URL 连接到会议或电话拨入式会议。
    
- 下载会议内容。
    
- 展开通讯组。
    
- 为基于客户端证书的身份验证获取基于用户的证书
    
- 从通讯簿服务器下载文件，或将查询提交到通讯簿 Web 查询服务。
    
- 获取客户端和设备软件的更新。
    
对于移动设备：
  
- 它允许他们自动发现提供移动服务的前端服务器。
    
- 它支持从移动设备Microsoft 365或Office 365到移动设备的推送通知。
    
我们的当前反向代理建议可在"电话基础结构[for Skype for Business](../../../SfbPartnerCertification/certification/infra-gateways.md)页面上找到。 因此反向代理：
  
- 应该能够将传输层安全性 (TLS) 通过公共证书引入环境，以连接到以下已发布的外部 Web 服务：
    
  - 控制器或控制器池
    
  - 前端服务器或前端池
    
- 需要能够使用加密证书发布内部网站，或者根据需要通过未加密的方式发布这些网站。
    
- 应该能够使用 FQDN 中的完全限定域名在外部发布 (托管) 。
    
- 需要能够发布托管网站的所有内容。 默认情况下，您可以使用 _指令，该指令被大多数 Web 服务器识别为表示"在 Web 服务器上 **/\\** 发布所有内容"。 您还可以修改指令（例如 ，_*/Uwca/ ***，这意味着"发布虚拟目录 \\ Ucwa 下的所有内容"。
    
- 必须与从已发布网站请求内容的客户端建立 TLS 连接。
    
- 必须接受主题备用名称为 SAN (的) 证书。
    
- 需要能够允许将证书绑定到外部 Web 服务 FQDN 将通过其解析的侦听器或接口。 侦听器配置比接口更可取。 可以在单个接口上配置许多侦听器。
    
- 必须允许配置主机头处理。 通常，请求客户端发送的原始主机头必须以透明方式传递，而不是由反向代理修改。
    
- 应允许将 TLS 流量从一个外部定义的端口 (例如 TCP 443) 桥接到另一个定义的端口 (例如 TCP 4443) 。 反向代理可能在接收时解密数据包，然后在发送时重新加密数据包。
    
- 应允许将未加密的 TCP 流量从一个端口 (例如 TCP 80) 桥接到另一个端口 (例如 TCP 8080) 。
    
- 需要允许配置或接受 NTLM 身份验证、无身份验证和传递身份验证。
    
如果反向代理可以满足此列表中的所有需求，你应该可以继续操作，但请记住我们上面提供的链接中的建议。
  
### <a name="firewalls"></a>防火墙
<a name="Firewalls"> </a>

需要将边缘部署置于外部防火墙之后，但我们建议在边缘环境和内部环境之间设置两个防火墙，一个外部防火墙和一个内部防火墙。 方案的所有文档都有两个防火墙。 我们建议使用两个防火墙，因为它可确保从一个网络边缘到另一个网络边缘的严格路由，并针对内部网络将防火墙保护增加一倍。
  
### <a name="directors"></a>控制器
<a name="Directors"> </a>

这是可选角色。 它可以是单个服务器或运行控制器角色的服务器池。 它是在内部管理环境中Skype for Business Server角色。
  
控制器是内部的下一个跃点服务器，它接收来自发往内部服务器的边缘服务器的入站 SIP Skype for Business Server流量。 它会预授权入站请求，并重定向到用户主池或服务器。 此预身份验证允许你删除无法识别的用户帐户请求。
  
为什么这很重要？ 控制器的一个重要功能是Standard Edition服务器和前端服务器或前端池免受恶意流量的攻击，例如拒绝服务 (DoS) 攻击。 如果网络被无效外部流量淹没，流量将停止在控制器上。
  
### <a name="load-balancers"></a>负载均衡器
<a name="LoadBalancers"> </a>

扩展Skype for Business Server边缘拓扑已针对新部署的 DNS 负载平衡进行了优化，建议这样做。 如果您需要高可用性，我们建议针对一种特定情况使用硬件负载平衡器：
  
- Exchange2013 年 10 月Exchange UM **的** 远程Exchange UM。
    
> [!IMPORTANT]
> 值得注意的是，不能混合使用负载平衡器。 在Skype for Business Server环境中，所有接口都必须使用 DNS 或 HLB。 
  
> [!NOTE]
> 不支持直接服务器 (DSR) NAT Skype for Business Server。 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>运行 A/V 边缘服务的边缘服务器的硬件负载平衡器要求

对于运行 A/V 边缘服务的任何边缘服务器，有以下要求：
  
- 关闭内部和外部端口 443 的 TCP nagling (将多个小数据包合并到一个更大的数据包中，以更有效地传输) 。
    
- 关闭外部端口范围 50000 - 59999 的 TCP nagling。
    
- 请勿在内部或外部防火墙上使用 NAT。
    
- 边缘内部接口必须位于与边缘服务器外部接口不同的网络上，并且必须禁用它们之间的路由。
    
- 运行 A/V 边缘服务的任何边缘服务器的外部接口都必须使用可公开路由的 IP 地址，并且不能在任何边缘外部 IP 地址上进行 NAT 或端口转换。
    
#### <a name="hlb-requirements"></a>HLB 要求

Skype for Business Server没有很多基于 Cookie 的关联要求。 因此，无需使用基于 Cookie 的持久性，除非 **(** 且这是 Skype for Business Server 2015 特定的) 您将在 Skype for Business Server 环境中具有 Lync Server 2010 前端服务器或前端池。 它们将需要 Lync Server 2010 推荐的配置方法中基于 Cookie 的关联。
  
> [!NOTE]
> 如果决定为 HLB 启用基于 Cookie 的关联，则这样做不会出现问题，即使您的环境不需要它。 
  
如果你的环境 **不需要基于** Cookie 的关联：
  
- 在端口 443 的反向代理发布规则上，将 **"转发主机头"设置为****"True"。** 这将确保转发原始 URL。
    
对于需要基于 **Cookie** 的关联部署的部署：
  
- 在端口 443 的反向代理发布规则上，将 **"转发主机头"设置为****"True"。** 这将确保转发原始 URL。
    
- 硬件负载平衡器 Cookie **不得标记为** httpOnly。
    
- 硬件负载平衡器 Cookie **不得具有** 过期时间。
    
- 硬件负载平衡器 **cookie** 必须命名为 **MS-WSMAN** (这是 Web 服务期望的值，并且不能) 。
    
- 必须在传入 HTTP 请求没有 Cookie 的每一个 HTTP 响应中设置硬件负载平衡器 Cookie，无论该同一 TCP 连接上的上一个 HTTP 响应是否已获得 Cookie。 如果硬件负载平衡器将 Cookie 插入优化为每个 TCP 连接仅发生一次，则不得 **使用** 该优化。
    
> [!NOTE]
> HLB 配置通常使用源相关性和 20 分钟的 TCP 会话生存期，这适用于 Skype for Business Server 及其客户端，因为会话状态通过客户端使用和/或应用程序交互进行维护。 
  
如果要部署移动设备，则 HLB 必须能够在有效 TCP 会话 (中对单个请求进行负载平衡，您需要能够基于目标 IP 地址) 对单个请求进行负载平衡。
  
> [!IMPORTANT]
> F5 HLB 具有一个称为 OneConnect 的功能。 它确保 TCP 连接内的每个请求都单独进行负载平衡。 如果要部署移动设备，请确保您的 HLB 供应商支持相同的功能。 最新的 iOS 移动应用需要 TLS 版本 1.2。 如果需要了解更多信息，F5 会为此提供特定设置。 
  
以下是前端池 Web 服务 (可选) 控制器 (的 HLB) 要求：
  
- 对于内部 Web 服务 IP，Source_addr HLB (端口 80，443) 持久性。 例如Skype for Business Server，Source_addr持久性意味着始终向一台服务器发送来自单个 IP 地址的多个连接，以维持会话状态。
    
- 使用 TCP 空闲超时 1800 秒。
    
- 在反向代理和下一个跃点池的 HLB 之间的防火墙上，创建一个规则以允许端口 4443 上的 https：流量从反向代理到 HLB。 HLB 需要配置为侦听端口 80、443 和 4443。
    
#### <a name="summary-of-hlb-affinity-requirements"></a>HLB 相关性要求摘要

|**客户端/用户位置**|**外部 Web 服务 FQDN 关联要求**|**内部 Web 服务 FQSN 相关性要求**|
|:-----|:-----|:-----|
|Skype for Business Web应用 (内部和外部用户)   <br/> 移动设备 (内部和外部用户  <br/> |无相关性  <br/> |源地址相关性  <br/> |
|Skype for Business Web应用 (外部用户仅)   <br/> 移动设备 (内部和外部用户  <br/> |无相关性  <br/> |源地址相关性  <br/> |
|Skype for Business Web应用 (内部用户只能)   <br/> 移动设备（未部署）  <br/> |无相关性  <br/> |源地址相关性  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>HLB 的端口监控

在硬件负载平衡器上定义端口监控，以确定特定服务何时因硬件或通信故障而不再可用。 例如，如果前端服务器服务 (RTCSRV) 由于前端服务器或前端池出现故障而停止，则 HLB 监控也应停止接收 Web 服务上的流量。 应在 HLB 上实现端口监控，以监视 HLB 外部接口的以下内容：
  
|**虚拟 IP/端口**|**节点端口**|**节点计算机/监视器**|**持久性配置文件**|**注释**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |前端  <br/> 5061  <br/> |无  <br/> |HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |前端  <br/> 5061  <br/> |无  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>硬件和软件要求

我们在[2015 年 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)年的总体服务器要求和 Skype for Business Server Skype for Business Server [2019](../../../SfBServer2019/plan/system-requirements.md)的系统要求文档中介绍了边缘服务器硬件和软件要求。
  
## <a name="collocation"></a>并置

我们在[Topology Basics for Skype for Business Server文档中介绍了边缘服务器](../../plan-your-deployment/topology-basics/topology-basics.md)并置。
