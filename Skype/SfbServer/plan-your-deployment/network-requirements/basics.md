---
title: DNS 基础知识
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 具有内置可以提供 DNS 服务，因此您可能想要查看可用的文档，如 DNS 策略方案指南的软件。 如果您愿意，您可以选择第三方解决方案。
ms.openlocfilehash: 297dc905a308806aec9228a9514f8e1bd65a245b
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839053"
---
# <a name="dns-basics"></a>DNS 基础知识
 
Windows Server 2016 具有内置可以提供 DNS 服务，因此您可能想要查看可用的文档，如[DNS 策略方案指南](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide)的软件。 如果您愿意，您可以选择第三方解决方案。
  
建议的最佳做法是将专用特定服务器实现提供 DNS 中。 您无法可能将其设置在一台服务器专用于业务服务器角色，但如果该服务器也是池的一部分，并获得停用无意 Skype 的业务会出现故障，直到 DNS 服务已重新建立 Skype 之一。
  
## <a name="dns-records"></a>DNS 记录

每个映射的 IP 地址的名称 （和可能的 IPv4 或 IPv6 地址） 存储在 DNS 服务器上的 DNS 记录。 名称所述明确标注为 FQDN DNS 报告 — 完全限定域名。 一个有效域名*contoso.com*时，它是简写*\*。 contoso.com* ，因此它不明确而无法可能引用域中的任何服务器。 将引用您的域中的单个服务器的 FQDN 的示例可能**meeting01.contoso.com**。
  
> [!IMPORTANT]
> 默认情况下，未加入域的计算机的计算机名称是主机名称，而不是完全限定域名 (FQDN)。 拓扑生成器使用 Fqdn，而不是主机名称。 因此，您必须在要部署为域外边缘服务器的计算机的名称上配置 DNS 后缀。 **使用仅标准字符**（包括 A-Z、 a-z、 0-9 和连字符） 时分配到您的业务服务器运行 Skype 的服务器的 Fqdn。 不要使用 Unicode 字符或下划线。 外部 DNS 和公共 CA（即，在 FQDN 必须分配给证书中的 SN 时）通常不支持在 FQDN 中使用非标准字符。
  
除了 IP 地址、 FQDN 可以映射到**VIP** — 一个虚拟 IP 地址。 VIP 是不对应于实际的物理网络接口的 IP 地址。 VIP 通常指向池服务器执行服务器角色，或指向一对的服务器配置为冗余和容错能力。
  
有几种类型的 DNS 记录，此次讨论中与最相关的那些是： 
  
- **A** -地址记录或主机记录返回 32 位 IPv4 地址。 最常用于映射到主机的 IP 地址的主机名。
    
- **AAAA** — IPv6 地址记录。 返回一个 128 位 IPv6 地址。 最常用于映射到主机的 IP 地址的主机名。
    
- **CNAME** — 规范名称记录。 这解析到另一个名称： DNS 查找将重试查找使用新名称。
    
- **SRV** -服务记录 （SRV 记录） 指定访问特定端口和 IP 组合的服务 （此过程的服务器上）。 需要服务记录的服务的名称固定的而且不能超出进行自定义您的 SIP 域的一部分。 某些用户服务使用简单 Url。 如果您有多个域的给定的服务，您将需要多个 SRV 记录以便 SRV 记录必须指向中的相同的 SIP 域的位置。
    
## <a name="how-to-choose-a-sip-domain-name"></a>如何选择 SIP 域名称
<a name="BK_NameSIP"> </a>

组织的 SIP 域名通常与分配给用户的电子邮件地址。 如果您的组织中用户应具有类似 Brown@contoso.com，首选的电子邮件地址\<sip 域\>具有 contoso.com 域的组织的名称是只需 contoso.com。
  
### <a name="multiple-sip-domains"></a>多个 SIP 域

 您的组织在某些情况下可能需要多个 SIP 域。 例如，如果 Fabrikam.com 被收购的 contoso.com，您可能需要创建一个新的 SIP 域的业务服务器 Skype 识别和将接受来自连接。 执行此操作，您将需要创建一组额外的 contoso.com，使用新的显示位置以将请求发送的 Fabrikam 的 Fqdn 的 DNS 记录。
  
## <a name="dns-load-balancing"></a>DNS 负载平衡
<a name="BK_NameSIP"> </a>

您可以使用 DNS 共享为服务器池设置的多个服务器之间的流量负载。 若要执行此操作，您将创建几个 A 记录的池的 FQDN，其中每个指向池中的节点的 IP 地址。
  
有关负载平衡的详细讨论，请参阅[DNS 负载平衡](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)。
  

