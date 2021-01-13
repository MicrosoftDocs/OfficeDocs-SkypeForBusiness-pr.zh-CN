---
title: DNS 基础
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 具有可提供 DNS 服务的内置软件，因此您可能需要查看可用的文档，如 DNS 策略方案指南。 如果需要，可以选择第三方解决方案。
ms.openlocfilehash: dc60bab84220cad306deee408a6a09fc16df5a10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825582"
---
# <a name="dns-basics"></a>DNS 基础
 
Windows Server 2016 具有可提供 DNS 服务的内置软件，因此您可能需要查看可用的文档，如 [DNS 策略方案指南](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide)。 如果需要，可以选择第三方解决方案。
  
建议最佳做法是，在你的实现中专门使用特定服务器来提供 DNS。 你可能在专用于其中一个 Skype for Business 服务器角色的服务器上设置它，但如果该服务器也是池的一部分并且因意外的 Skype for Business 停用，那么在重新建立 DNS 服务之前，Skype for Business 将发生故障。
  
## <a name="dns-records"></a>DNS 记录

名称到 IP 地址的每个 (可以是 IPv4 或 IPv6 地址) 存储在 DNS 服务器的 DNS 记录中。 该名称在 DNS 报告中专门描述为 FQDN— 一个完全限定的域名。 虽然 *contoso.com* 域名，但它是 *\* .contoso.com* 的简写，因此不明确，可能指域中的任何服务器。 引用域中的单台服务器的 FQDN 示例可能 **meeting01.contoso.com。**
  
> [!IMPORTANT]
> 默认情况下，未加入域的计算机的计算机名称是主机名，而不是 FQDN (完全限定) 。 拓扑生成器使用 FQDN，而不是主机名。 因此，您必须在要部署为域外边缘服务器的计算机的名称上配置 DNS 后缀。 向运行 Skype for Business **Server** 的服务器 (FQDN 时，请仅使用标准字符) 包括 A-Z、a-z、0-9 和连字符。 不要使用 Unicode 字符或下划线。 外部 DNS 和公共 CA（即，在 FQDN 必须分配给证书中的 SN 时）通常不支持在 FQDN 中使用非标准字符。
  
除了 IP 地址之外，FQDN 还可以映射到 **VIP—** 一个虚拟 IP 地址。 VIP 是一个与实际物理网络接口不对应的 IP 地址。 VIP 通常指向执行服务器角色的服务器池，或指向配置为冗余和容错的一对服务器。
  
有几种 DNS 记录类型，与此讨论最相关的记录有： 
  
- **A** — 地址记录或主机记录，返回 32 位 IPv4 地址。 最常用于将主机名映射到主机的 IP 地址。
    
- **AAAA** — IPv6 地址记录。 返回 128 位 IPv6 地址。 最常用于将主机名映射到主机的 IP 地址。
    
- **CNAME** — 规范名称记录。 这会将一个名称解析为另一个名称：DNS 查找将重试具有新名称的查找。
    
- **SRV** - SRV 记录 (SRV 记录) 指定在 (端口和 IP 组合上访问) 服务器上进程的服务记录。 需要服务记录的服务的名称是固定的，除了使它们成为 SIP 域的一部分之外，无法自定义它们。 某些用户服务使用简单 URL。 SRV 记录必须指向同一 SIP 域中的位置，因此，如果有多个域，则给定服务需要多个 SRV 记录。
    
## <a name="how-to-choose-a-sip-domain-name"></a>如何选择 SIP 域名
<a name="BK_NameSIP"> </a>

组织的 SIP 域名通常与向用户提供的电子邮件地址一致。 如果贵组织的用户具有类似 Brown@contoso.com 的电子邮件地址，则使用 contoso.com 域名的组织的首选只是 \<sip-domain\> contoso.com。
  
### <a name="multiple-sip-domains"></a>多个 SIP 域

 在某些情况下，您的组织可能需要多个 SIP 域。 例如，如果Fabrikam.com用户contoso.com，可能需要创建 Skype for Business Server 识别并接受其连接的新 SIP 域。 当您这样做时，您需要创建一组使用 contoso.com 的其他所有 DNS 记录，其中显示 Fabrikam 请求的发送位置的新 FQDN。
  
## <a name="dns-load-balancing"></a>DNS 负载平衡
<a name="BK_NameSIP"> </a>

您可以使用 DNS 在设置为服务器池的几个服务器之间共享流量负载。 为此，您需要为池的 FQDN 创建多个 A 记录，每条记录都指向池中节点的 IP 地址。
  
有关 [负载平衡的其他](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) 讨论，请参阅 DNS 负载平衡。
  

