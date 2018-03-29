---
title: 在 Skype for Business Server 2015 中查看管理员报告
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: 管理员报告是有关部署和操作的详细信息。 根据标记在设计网站的选择生成报表。 设计师可以通过编辑网络图并为服务器、池和负载平衡器定义完整的 IP 地址和完全限定的域名 (FQDN)，来进一步向管理员报告中添加值。
ms.openlocfilehash: 989623fe8966a7f26f43bae0470da2cc57c3ddc7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中查看管理员报告
 
管理员报告是有关部署和操作的详细信息。这些报告是基于“**设计站点**”中标记的选择而生成的。设计师可以通过编辑网络图并为服务器、池和负载平衡器定义完整的 IP 地址和完全限定的域名 (FQDN)，来进一步向管理员报告中添加值。
  
管理员报告功能允许你：
  
- [Review the Summary Report](review-the-administrator-reports.md#Summary_report)
    
- [Review the Certificates Report](review-the-administrator-reports.md#Certificates_Report)
    
- [Review the Firewall Report](review-the-administrator-reports.md#Firewall_report)
    
- [Review the DNS Report](review-the-administrator-reports.md#DNS_Report)
    
## <a name="review-the-summary-report"></a>查看摘要报告
<a name="Summary_report"> </a>

业务管理员报告 Skype 是第一个的文档中详细设计的四个重要的报告。 此报告和其他三个相关报告中的信息对信息技术团队很有用：
  
![常规摘要管理报告](../../media/General_Summary_Report_Admin_Report.png)
  
摘要报告列出了与边缘网络关联的常规配置信息。记录了位置、完全限定域名 (FQDN) 和 IP 地址、网络类型以及特定于给定角色的注释。
  
要部署、管理和维护基础结构的设计师和团队的每个成员应检查摘要报告的准确性并确保将错误降到最少。
  
你还可以查看更详细的报告：
  
- 证书报告
    
- 防火墙报告
    
- DNS 报告
    
## <a name="review-the-certificates-report"></a>查看证书报告
<a name="Certificates_Report"> </a>

该证书报告包含中建议使用 Skype 业务服务器 2015年部署所需的所有证书。 规划工具的主题名称以及主题备用名称输入帐户。 未经编辑的默认文本可能会给负责请求和颁发证书的团队带来挑战。 证书信息还包含通常可以从何处颁发证书的信息。 如果基础结构中没有内部公钥基础结构 (PKI)，则可以通过公共证书提供商请求所有证书。 该报告中的“扩展密钥用法 (EKU)”和“分配给”字段非常有助于理解每个证书应有的用途和应处的位置。 
  
![证书管理报告](../../media/Certificates_Report_Admin_Report.png)
  
仔细阅读并确保了解部署中每个证书的用法和用途。 如果对证书用途有疑问，请确定是何种服务器或服务在与何种对象通信。 在业务服务器 2015年的 Skype 的证书用于两个主要目的：
  
- 相互传输层安全性 (MTLS)-在每个通信中涉及的计算机提供证书来证明自己的身份，到另一台计算机。 这称为服务器身份验证。 直到每个计算机信任另一台计算机的身份不能通信。
    
- 加密的安全套接字层，或 SSL，和传输层安全性 （TLS） 加密是以帮助安全的通信，有助于确保隐私，和创建一个受信任的通信和协作系统的重要方法。
    
## <a name="review-the-firewall-report"></a>查看防火墙报告
<a name="Firewall_report"> </a>

Skype 的业务服务器 2015年具有一组潜在复杂的防火墙规则。 规划工具生成一个报表，详细定义了基于设计器的输入条件的所有防火墙需求来降低这种复杂性。 IT 防火墙管理员将能够使用此报告配置和定义所需的规则。
  
从防火墙管理的角度考虑，应仔细查看此报告以确保与现有防火墙规则没有冲突，并且没有违反任何策略或过程。
  
![防火墙管理报告](../../media/Firewall_Report_Admin_Report.png)
  
## <a name="review-the-dns-report"></a>查看 DNS 报告
<a name="DNS_Report"> </a>

属于管理员报告的一部分的 DNS 报告详细记录了内部、外围和外部网络中域名系统 (DNS) 的所有推荐条目和已知条目。如果设计师已完成对网络图的编辑，并且所有 IP 地址和完全限定域名 (FQDN) 已定义为其生产值，则 DNS 报告可提供出色的配置资源。此报告还可充当可操作的疑难解答文档。
  
![DNS 管理报告](../../media/DNS_Report_Admin_Report.png)
  
您应让您的 DNS 管理团队全面检查 DNS 报告，以确保不存在可能引发部署困难的错误，也不存在可能使疑难解答会话复杂化的错误。
  
## <a name="see-also"></a>另请参阅
<a name="DNS_Report"> </a>

#### 

[查看管理员报告](http://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)

