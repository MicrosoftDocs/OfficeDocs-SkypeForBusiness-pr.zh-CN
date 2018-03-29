---
title: Skype for Business Server 2015 的边缘服务器系统要求
ms.author: heidip
author: microsoftheidi
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 摘要： 了解在 Skype 的边缘服务器业务服务器的系统要求。
ms.openlocfilehash: d4d195d07b13ccfc294054a811cbd6735b2431cc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="edge-server-system-requirements-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 的边缘服务器系统要求
 
**摘要：**了解如何在 Skype 的边缘服务器业务服务器的系统要求。
  
到您 Skype 业务服务器边缘服务器部署时，这些是您需要为服务器或服务器本身，以及规划环境结构在环境中所做的事情。 有关拓扑、DNS 证书和其他基础结构问题的详细信息，请查看环境要求文档。
  
## <a name="components"></a>组件

在讨论边缘服务器环境时，我们引用，大多数情况下，部署在外围网络 （即是说它是在工作组或域之外您 Skype 业务服务器域结构） 的组件。
  
请记住，这些组件是为了成功部署边缘而需要牢记于胸的组件：
  
- [Edge Servers](system-requirements.md#EdgeServers)
    
- [Reverse proxies](system-requirements.md#ReverseProxies)
    
- [Firewalls](system-requirements.md#Firewalls)
    
- [Directors](system-requirements.md#Directors)（这类组件是可选的，如果纳入这些组件，它们将位于内部网络中）
    
- [负载平衡器](system-requirements.md#LoadBalancers)（可以有 DNS 负载平衡或硬件负载平衡器 (HLB)，但单个边缘服务器，这不需要）
    
下面我们更详细地谈论以下每个组件：
  
### <a name="edge-servers"></a>边缘服务器
<a name="EdgeServers"> </a>

这些都是业务服务器部署在外围环境的 Skype。 其作用是发送和接收业务服务器部署您内部 Skype 所提供的服务的外部用户的网络流量。 若要成功执行此操作，每个边缘服务器运行：
  
- **访问边缘服务**： 为出站和入站会话启动协议 (SIP) 通信提供单一的受信任连接点。
    
- **Web 会议边缘服务**： 使外部用户可以加入您的企业服务器环境的内部 Skype 上承载的会议。
    
- **A / V 边缘服务**： 将音频、 视频、 应用程序共享和文件传输提供给外部用户。
    
- **XMPP 代理服务**： 接受，并与配置的 XMPP 联合伙伴发送消息和状态的可扩展协议 (XMPP) 消息。
    
授权的外部用户可以使用边缘服务器连接到您内部 Skype 业务服务器部署中，但它们否则，为所有人提供其他访问您的内部网络。
  
> [!NOTE]
> 部署边缘服务器提供的业务客户端连接已启用 Skype 和其他边缘服务器 （在联合方案）。 不能从其他端点客户端或服务器节点进行连接。 XMPP 网关服务器可允许与配置的 XMPP 伙伴进行连接。 但同样，这些伙伴仅限可行的客户端和联盟类型。 
  
### <a name="reverse-proxies"></a>反向代理
<a name="ReverseProxies"> </a>

(RP) 的反向代理服务器已没有 Skype 业务服务器角色，但边缘服务器部署的重要组成部分。 反向代理服务器允许外部用户：
  
- 使用简单 URL 连接到会议或电话拨入式会议。
    
- 下载会议内容。
    
- 展开通讯组。
    
- 获取基于用户的证书，用于基于客户端证书的身份验证
    
- 从通讯簿服务器，或提交到地址簿 Web 查询服务的查询，请下载文件。
    
- 获得客户和设备软件的更新。
    
对于移动设备：
  
- 它可以让它们自动发现前端服务器提供移动服务。
    
- 它使从 Office 365 到移动设备的推式通知。
    
[对于业务的 Skype 电话基础架构](https://technet.microsoft.com/en-us/office/dn947483)页上找不到我们当前反向代理的建议。 因此您的反向代理服务器：
  
- 应能够使用通过公共证书引入环境的传输层安全性 (TLS) 连接到以下对象的已发布外部 Web 服务：
    
  - 总监或总监池
    
  - 前端服务器或前端池
    
- 需要能使用加密证书发布内部网站，或者根据需要以未加密的方式发布这些网站。
    
- 应能够使用完全限定域名 (FQDN) 在外部发布内部托管网站。
    
- 需要能发布托管网站的所有内容。 默认情况下，您可以使用**/**指令，大多数 web 服务器识别是指"发布的 web 服务器上的所有内容"。 您还可以修改指令 — — 例如， **/Uwca/\***，这意味着"发布 Ucwa 的虚拟目录下的所有内容。"
    
- 必须与从发布的网站请求内容的客户端建立 TLS 连接。
    
- 必须接受包含使用者替代名称 (SAN) 条目的证书。
    
- 需要能允许将证书绑定到将通过其解析外部 Web 服务 FQDN 的侦听器或接口。侦听器配置优于接口配置。可在一个接口上配置多个侦听器。
    
- 必须允许配置主机头处理。 通常情况下，原始主机头发送请求的客户端必须以透明的方式，传递而不是修改的反向代理服务器。
    
- 应允许将来自某个外部定义的端口（如 TCP 443）的 TLS 流量桥接至另一个定义的端口（如 TCP 4443）。 反向代理服务器可以解密数据包在收据上的，然后重新加密发送该数据包。
    
- 应将来自某个端口（如 TCP 80）的未加密 TCP 流量桥接至另一端口（如 TCP 8080）。
    
- 需要允许配置或接受“NTLM 身份验证”、“无身份验证”和“传递身份验证”。
    
如果您的反向代理服务器可以解决此列表中的所有需求，应该很好，但请记住我们的建议在上面提供的链接。
  
### <a name="firewalls"></a>防火墙
<a name="Firewalls"> </a>

需要将边缘部署放在外部防火墙后面，但是我们建议在边缘环境和内部环境之间设两个防火墙，一个外部，一个内部。我们方案的所有文档都有两个防火墙。我们之所以推荐两道防火墙是因为，这可确保从一个网络边缘到另一个网络边缘的严格路由，并对内部网络实施加倍防火墙保护。
  
### <a name="directors"></a>控制器
<a name="Directors"> </a>

这是可选角色。 它可以是一台服务器或池的运行主管角色的服务器。 它是在内部 Skype 业务服务器环境中找到一个角色。
  
控制器是内部下一个跃点服务器接收从边缘服务器发送到 Skype 业务服务器的内部服务器的入站的 SIP 通信。 它对入站请求预先进行身份验证，并将其它们重定向到用户的主池或主服务器。 此预身份验证可让您丢弃未确定身份的用户帐户的请求。
  
为什么这很重要？ 导演的重要功能是为了防止恶意通信量，如拒绝服务 (DoS) 攻击的标准版服务器和前端服务器或前端池。 如果您的网络被淹没无效的外部通信，通信停止处主任。
  
### <a name="load-balancers"></a>负载平衡器
<a name="LoadBalancers"> </a>

Skype 业务服务器 2015 缩放合并边缘拓扑优化 DNS 负载平衡的新部署，并建议这样做。 如果需要高可用性，我们建议使用一种特定情形的硬件负载平衡：
  
- 交换 UM 的远程用户使用 Exchange UM**事先**交换 2013年。
    
> [!IMPORTANT]
> 必须指出，不能混合使用负载平衡器。 在您 Skype 业务服务器环境中的所有接口必须都使用 DNS 或 HLB。 
  
> [!NOTE]
> 直接服务器返回 (DSR) NAT 不支持为 Skype 业务服务器 2015年。 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>硬件负载平衡器要求服务器边缘，边缘服务器运行 A / V 边缘服务

任何边缘服务器运行 A / V 边缘服务，这些都是要求：
  
- 对内部和外部端口 443 关闭 TCP nagling（Nagling 是将多个小数据包合并成一个大数据包以提高传输效率的过程）。
    
- 对端口范围为 50000 – 59999 的外部端口关闭 TCP nagling。
    
- 不要在内部或外部防火墙上使用 NAT。
    
- 边缘内部接口必须比您边缘服务器的外部接口，不同的网络上，并且必须禁用它们之间路由。
    
- 运行的任何边缘服务器的外部接口 / V 边缘服务必须使用公用路由的 IP 地址和没有 NAT 或端口上任何边缘外部 IP 地址的翻译。
    
#### <a name="hlb-requirements"></a>HLB 要求

使用 Lync Server 2013，业务服务器 2015年的 Skype 不会有大量的基于 cookie 的相似性要求。 因此，您不需要使用基于 cookie 持久性**除非**您将需要在您的企业服务器环境的 Skype 的 Lync Server 2010 前结束服务器或前端池。 他们将需要基于 cookie 的配置方法建议使用 Lync Server 2010 中的相似性。
  
> [!NOTE]
> 如果决定为 HLB 开启基于 Cookie 的相关性，那么即使环境不需要，这样做也没有问题。 
  
如果环境**不**需要基于 Cookie 的相关性：
  
- 在端口 443 的反向代理服务器发布规则，将设置为**True**的**前向主机标头**。 这可确保转发原始 URL。
    
对于**确实**需要基于 Cookie 的相关性的部署：
  
- 在端口 443 的反向代理服务器发布规则，将设置为**True**的**前向主机标头**。 这可确保转发原始 URL。
    
- 硬件负载平衡器 cookie**不**会标记为 httpOnly。
    
- 硬件负载平衡器 cookie**不必须**有截止时间。
    
- 硬件负载平衡器 cookie**必须**命名为**MS WSMAN** （这是所期望的 Web 服务，并且不能更改的值）。
    
- 硬件负载平衡器 cookie**必须**在传入的 HTTP 请求没有 cookie，而不考虑以前的 HTTP 响应该相同的 TCP 连接上是否有引起了 cookie 的每个 HTTP 响应中设置。 如果您的硬件负载平衡器优化 cookie 插入仅发生后该优化**必须不**使用每个 TCP 连接。
    
> [!NOTE]
> 它是典型的 HLB 配置为使用源相关性和 20 分钟 TCP 会话生存期，这是相当不错的 Skype 业务服务器 2015年和其客户端，因为通过客户端使用情况和/或应用程序交互，即可保持会话状态。 
  
如果部署移动设备，则您的 HLB 必须能对 TCP 会话中的各个请求进行负载平衡（实际上，您需要能基于目标 IP 地址对单个请求进行负载平衡）。
  
> [!IMPORTANT]
> F5 HLB 有一个名为 OneConnect 的功能。该功能确保一个 TCP 连接中的每个请求是单独进行负载平衡的。如果部署的是移动设备，请确保您的 HLB 供应商支持这同一功能。最新的 iOS 移动应用程序需要 TLS 1.2 版。如果需要了解更多，F5 提供了专门针对这一要求的设置。 
  
这里是 HLB 要求的控制器 （可选） 和 （必选） 前端池 Web 服务：
  
- 为内部的 Web 服务 Vip，设置您 HLB Source_addr 持久性 （内部端口 80、 443）。 对于业务服务器 2015年的 Skype，Source_addr 持久性意味着来自单个 IP 地址的多个连接始终发送到一台服务器，以维护会话状态。
    
- 使用 TCP 空闲超时 1800 秒。
    
- 反向代理服务器和您下一个跃点池 HLB 之间的防火墙，在创建一个规则来允许 https： 端口 4443，从您 HLB 为您反向代理服务器上的流量。 需要将 HLB 配置为侦听端口 80、443 和 4443。
    
#### <a name="summary-of-hlb-affinity-requirements"></a>HLB 相关性要求摘要

|**客户端/用户位置**|**外部 web 服务 FQDN 关联需求**|**内部 web 服务 FQSN 仿射性需求**|
|:-----|:-----|:-----|
|Skype 业务 Web 应用程序 （内部和外部用户）  <br/> 移动设备（内部和外部用户）  <br/> |无相关性  <br/> |源地址相关性  <br/> |
|Skype 业务 Web 应用程序 （仅适用于外部用户）  <br/> 移动设备（内部和外部用户）  <br/> |无相关性  <br/> |源地址相关性  <br/> |
|Skype 业务 Web 应用程序 （仅适用于内部用户）  <br/> 移动设备（未部署）  <br/> |无相关性  <br/> |源地址相关性  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>HLB 的端口监视

您定义端口监视上硬件负载平衡器以确定特定服务何时不再可用，由于硬件或通信故障。 例如，如果前端服务器服务 (RTCSRV) 停止因为前端服务器或前端池失败，HLB 监视也应该停止接收对 Web 服务进行通信。 应在 HLB 上实施端口监视来监视 HLB 外部接口的以下信息：
  
|**虚拟的 IP 端口**|**节点端口**|**节点机/监视器**|**持久性配置文件**|**说明**|
|:-----|:-----|:-----|:-----|:-----|
|\<池\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |前端  <br/> 5061  <br/> |无  <br/> |HTTPS  <br/> |
|\<池\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |前端  <br/> 5061  <br/> |无  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>硬件和软件要求

我们已经在我们总[业务服务器 2015年的 Skype 的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)文档介绍边缘服务器硬件和软件要求。
  
## <a name="collocation"></a>并置

我们已经在我们的[业务服务器 2015年的 Skype 的拓扑结构基础](../../plan-your-deployment/topology-basics/topology-basics.md)文档介绍边缘服务器配置。
  

