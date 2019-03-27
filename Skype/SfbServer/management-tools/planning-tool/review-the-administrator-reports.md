---
title: 在 Skype for Business Server 2015 中查看管理员报告
ms.reviewer: ''
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
description: 管理员报告是有关部署和操作的详细信息。 这些报告是基于“设计站点”中标记的选择而生成的。 设计师可以通过编辑网络图并为服务器、池和负载平衡器定义完整的 IP 地址和完全限定的域名 (FQDN)，来进一步向管理员报告中添加值。
ms.openlocfilehash: 5cab8231428ace2a0d77132481819eed304d3519
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898192"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>Review the Administrator Reports in Skype for Business Server 2015

管理员报告是有关部署和操作的详细信息。这些报告是基于“**设计站点**”中标记的选择而生成的。设计师可以通过编辑网络图并为服务器、池和负载平衡器定义完整的 IP 地址和完全限定的域名 (FQDN)，来进一步向管理员报告中添加值。

管理员报告功能允许你：

- [Review the Summary Report](review-the-administrator-reports.md#Summary_report)

- [Review the Certificates Report](review-the-administrator-reports.md#Certificates_Report)

- [Review the Firewall Report](review-the-administrator-reports.md#Firewall_report)

- [Review the DNS Report](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>查看摘要报告
<a name="Summary_report"> </a>

业务管理员报表 Skype 文档详细信息中的设计的四个有价值的报表的第一个。 此报告和其他三个相关报告中的信息对信息技术团队很有用：

![常规摘要管理报告](../../media/General_Summary_Report_Admin_Report.png)

摘要报告列出了与边缘网络关联的常规配置信息。记录了位置、完全限定域名 (FQDN) 和 IP 地址、网络类型以及特定于给定角色的注释。

要部署、管理和维护基础结构的设计师和团队的每个成员应检查摘要报告的准确性并确保将错误降到最少。

你还可以查看更详细的报告：

- 证书报告

- 防火墙报告

- DNS 报告

## <a name="review-the-certificates-report"></a>查看证书报告
<a name="Certificates_Report"> </a>

证书报告包含业务服务器 2015年部署建议 Skype 所需的所有证书。 规划工具的使用者名称和使用者替代名称的输入帐户。 未经编辑的默认文本可能会给负责请求和颁发证书的团队带来挑战。 证书信息还包含通常可以从何处颁发证书的信息。 如果基础结构中没有内部公钥基础结构 (PKI)，则可以通过公共证书提供商请求所有证书。 该报告中的“扩展密钥用法 (EKU)”和“分配给”字段非常有助于理解每个证书应有的用途和应处的位置。

![证书管理报告](../../media/Certificates_Report_Admin_Report.png)

仔细阅读并确保了解部署中每个证书的用法和用途。 如果对证书用途有疑问，请确定是何种服务器或服务在与何种对象通信。 证书中的业务服务器 2015 Skype 用于两个主要目的：

- 相互传输层安全性 (MTLS) 的每个通信中所涉及的计算机提供向另一台计算机证明其标识证书。 这称为服务器身份验证。 每台计算机信任另一台计算机标识才能开始通信。

- 加密的加密 （安全套接字层，或 SSL，和传输层安全性或 TLS） 是帮助安全通信，有助于确保隐私和创建受信任的沟通和协作系统的关键方法。

## <a name="review-the-firewall-report"></a>查看防火墙报告
<a name="Firewall_report"> </a>

Skype 的业务服务器 2015年都有一潜在的复杂的防火墙规则。 规划工具生成定义详细信息中所有的防火墙要求，基于设计器的输入条件的报告，以此降低了此复杂性。 IT 防火墙管理员将能够使用此报告配置和定义所需的规则。

从防火墙管理的角度考虑，应仔细查看此报告以确保与现有防火墙规则没有冲突，并且没有违反任何策略或过程。

![防火墙管理报告](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a>查看 DNS 报告
<a name="DNS_Report"> </a>

属于管理员报告的一部分的 DNS 报告详细记录了内部、外围和外部网络中域名系统 (DNS) 的所有推荐条目和已知条目。如果设计师已完成对网络图的编辑，并且所有 IP 地址和完全限定域名 (FQDN) 已定义为其生产值，则 DNS 报告可提供出色的配置资源。此报告还可充当可操作的疑难解答文档。

![DNS 管理报告](../../media/DNS_Report_Admin_Report.png)

您应让您的 DNS 管理团队全面检查 DNS 报告，以确保不存在可能引发部署困难的错误，也不存在可能使疑难解答会话复杂化的错误。

## <a name="see-also"></a>另请参阅
<a name="DNS_Report"> </a>

[Reviewing the Administrator Reports](https://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)
