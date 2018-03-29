---
title: DNS 基础知识
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows 服务器 2016年有内置软件，可以提供 DNS 服务，因此您可能想要查看可用的文档，如 DNS 策略方案指南。 如果您愿意，您可以选择第三方解决方案。
ms.openlocfilehash: df6a693c50b3ca8b61baf0e47e0d019478f3cbf9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="dns-basics"></a>DNS 基础知识
 
Windows 服务器 2016年有内置软件，可以提供 DNS 服务，因此您可能想要查看可用的文档，如[DNS 策略方案指南](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/dns-policy-scenario-guide)。 如果您愿意，您可以选择第三方解决方案。
  
我们建议最好将专用特定服务器以提供 DNS 实现中。 您可能有可能将其设置一个专用于一个业务服务器角色，但如果该服务器也是池的一部分，对于业务将出现故障之前 DNS 服务已重新建立了退役无意 Skype Skype 的服务器上。
  
## <a name="dns-records"></a>DNS 记录

每个映射到 IP 地址的名称 （和可能就在 IPv4 或 IPv6 地址） 存储在 DNS 服务器上的 DNS 记录。 名称所述专门作为 FQDN 的 DNS 报表 — — 完全限定域名。 虽然*contoso.com*是一个有效的域名，但它是简写形式*\*。 contoso.com* ，因此，它不明确，可能就可以查阅到域中的任何服务器。 将参考您域中的单个服务器的 FQDN 的示例可能是**meeting01.contoso.com**。
  
> [!IMPORTANT]
> 默认情况下，未加入域的计算机的计算机名称是主机名称，而不是完全限定域名 (FQDN)。 拓扑生成器使用 Fqdn，而不是主机名。 因此，必须在要部署为未加入域的边缘服务器的计算机名称上配置 DNS 后缀。 **使用仅标准字符**（包括 A-Z、 a-z、 0-9 和连字符） 时分配给运行 Skype 业务服务器的服务器的 Fqdn。 不要使用 Unicode 字符或下划线字符。 外部 DNS 和公共 CA 通常不支持在 FQDN 中使用非标准字符（当必须向证书中的 SN 分配 FQDN 时）。
  
除了 IP 地址，FQDN 可以映射到**VIP** — — 一个虚拟 IP 地址。 VIP 是不对应于实际物理网络接口的 IP 地址。 VIP 通常点到池中的服务器执行服务器角色，或对服务器配置的冗余和容错能力。
  
有几种类型的 DNS 记录，在此讨论最相关的那些： 
  
- **A** — 地址记录或主机记录返回 32 位 IPv4 地址。 通常用于将主机名映射到 IP 地址的主机。
    
- **AAAA** — IPv6 地址记录。 返回一个 128 位的 IPv6 地址。 通常用于将主机名映射到 IP 地址的主机。
    
- **CNAME** — 规范名称记录。 这到另一个解析一个名称： DNS 查找将重试以新名称查找。
    
- **SRV** — 服务记录 （SRV 记录） 指定访问特定的端口和 IP 组合的服务 （在服务器上的进程）。 要求服务记录的服务的名称固定的并不能自定义之外，使它们成为您的 SIP 域的一部分。 一些用户服务使用简单的 Url。 因此，如果您有多个域需要多个 SRV 记录给定服务的 SRV 记录必须指向相同的 SIP 域中的某个位置。
    
## <a name="how-to-choose-a-sip-domain-name"></a>如何选择一个 SIP 域的名称
<a name="BK_NameSIP"> </a>

组织的 SIP 域的名称通常与提供给其用户的电子邮件地址相符。 如果您的组织中的用户将具有类似 Brown@contoso.com，首选电子邮件地址\<sip 域\>contoso.com 域的组织名称是简单 contoso.com。
  
### <a name="multiple-sip-domains"></a>多个 SIP 域

 您的组织在某些情况下可能需要多个 SIP 域。 举一个例子，如果 Fabrikam.com 获取 contoso.com，您可能需要创建一个新的 SIP 域，Skype 业务服务器识别并将接受连接。 当您执行此操作时，您需要创建一组额外的 contoso.com，使用显示的发送请求的位置的新 Fqdn 的 DNS 记录。
  
## <a name="dns-load-balancing"></a>DNS 负载平衡
<a name="BK_NameSIP"> </a>

您可以使用 DNS 来共享设置为服务器池的多个服务器之间的通信负载。 为了做到这一点，您需要创建几个 A 记录为该池的 FQDN，其中的每个点到池中的节点的 IP 地址。
  
有关负载平衡的详细讨论，请参阅[DNS 负载平衡](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)。
  

