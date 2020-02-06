---
title: DNS 基础知识
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 具有可提供 DNS 服务的内置软件，因此你可能需要查看 "DNS 策略方案指南" 等可用文档。 如果愿意，您可以选择第三方解决方案。
ms.openlocfilehash: 5438ee6ccedda6e840ca706cf285af49326a3bf4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815790"
---
# <a name="dns-basics"></a>DNS 基础知识
 
Windows Server 2016 具有可提供 DNS 服务的内置软件，因此你可能需要查看 " [Dns 策略方案指南](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide)" 等可用文档。 如果愿意，您可以选择第三方解决方案。
  
我们建议，最佳做法是在你的实现中专用特定服务器以提供 DNS。 您可能会在专用于其中一个 Skype for Business 服务器角色的服务器之一上设置它，但如果该服务器也是某个池的一部分，而在重新建立 DNS 服务之前，您的 Skype for business 取消授权将无法正常工作。
  
## <a name="dns-records"></a>DNS 记录

每个名称到 IP 地址（也可以是 IPv4 或 IPv6 地址）的映射都存储在 DNS 服务器上的 DNS 记录中。 该名称在 DNS 报告中描述为 FQDN （完全限定的域名）。 虽然*contoso.com*是有效的* \** 域名，但它是 contoso.com 的简写，因此它不明确，并且可能会引用域中的任何服务器。 在您的域中引用单个服务器的 FQDN 的示例可能是**meeting01.contoso.com**。
  
> [!IMPORTANT]
> 默认情况下，未加入域的计算机的计算机名称是主机名称，而不是完全限定域名 (FQDN)。 拓扑生成器使用 Fqdn，而不是主机名。 因此，您必须在要部署为域外边缘服务器的计算机的名称上配置 DNS 后缀。 将 Fqdn 分配给运行 Skype for Business Server 的服务器时，**请仅使用标准字符**（包括 a-z、A-z、0-9 和连字符）。 不要使用 Unicode 字符或下划线。 外部 DNS 和公共 CA（即，在 FQDN 必须分配给证书中的 SN 时）通常不支持在 FQDN 中使用非标准字符。
  
除了 IP 地址，FQDN 还可以映射到**VIP** （虚拟 IP 地址）。 VIP 是不对应于实际物理网络接口的 IP 地址。 VIP 通常指向执行服务器角色的服务器池，或者指向配置为冗余和容错的一对服务器。
  
有多种类型的 DNS 记录，与本讨论最相关的 DNS 记录包括： 
  
- **A** -地址记录或主机记录返回32位的 IPv4 地址。 最常用于将主机名映射到主机的 IP 地址。
    
- **AAAA** -IPv6 地址记录。 返回128位 IPv6 地址。 最常用于将主机名映射到主机的 IP 地址。
    
- **CNAME** -规范名称记录。 这会将一个名称解析为另一个名称： DNS 查找将重试具有新名称的查找。
    
- **SRV** —服务记录（srv 记录）指定在特定端口和 IP 组合上访问的服务（服务器上的进程）。 需要服务记录的服务的名称是固定的，并且不能进行自定义，而不是使其成为您的 SIP 域的一部分。 某些用户服务使用简单的 Url。 SRV 记录必须指向同一 SIP 域中的某个位置，因此如果你有多个域，则给定服务需要多个 SRV 记录。
    
## <a name="how-to-choose-a-sip-domain-name"></a>如何选择 SIP 域名
<a name="BK_NameSIP"> </a>

组织的 SIP 域名通常与为其用户提供的电子邮件地址对齐。 如果组织中的用户具有类似 Brown@contoso.com 的电子邮件地址，则具有 contoso.com \<域名的组织\>的首选 sip 域只是 contoso.com。
  
### <a name="multiple-sip-domains"></a>多个 SIP 域

 在某些情况下，您的组织可能需要多个 SIP 域。 例如，如果 contoso.com 获取了 Fabrikam.com，你可能需要创建一个新的 SIP 域，以便 Skype for Business 服务器识别并将接受来自的连接。 执行此操作时，你需要创建一个使用 contoso.com 的所有 DNS 记录的附加集，其中显示了在何处发送 Fabrikam 请求的新 Fqdn。
  
## <a name="dns-load-balancing"></a>DNS Load Balancing
<a name="BK_NameSIP"> </a>

可以使用 DNS 在设置为服务器池的多个服务器之间共享流量负载。 为此，你将为池的 FQDN 创建几条记录，每个记录指向池中的一个节点的 IP 地址。
  
有关负载平衡的其他讨论，请参阅[DNS 负载平衡](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)。
  

