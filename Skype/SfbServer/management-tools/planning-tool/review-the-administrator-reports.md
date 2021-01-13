---
title: 查看 Skype for Business Server 2015 中的管理员报告
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: 管理员报告是有关部署和操作的详细信息。 报告基于设计网站中标记的选择生成。 设计师可通过编辑网络图，并为服务器、池和负载平衡器定义完整的 IP 地址和完全限定域名 (FQDN)，来进一步向管理报告中添加值。
ms.openlocfilehash: b8c18dcfef28ac93e8c2036fee7f7b105f5c69bd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823342"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>查看 Skype for Business Server 2015 中的管理员报告

管理员报告是有关部署和操作的详细信息。 报告基于设计网站中标记 **的选择生成**。 设计师可通过编辑网络图，并为服务器、池和负载平衡器定义完整的 IP 地址和完全限定域名 (FQDN)，来进一步向管理报告中添加值。

管理员报告功能允许您：

- [查看摘要报告](review-the-administrator-reports.md#Summary_report)

- [查看证书报告](review-the-administrator-reports.md#Certificates_Report)

- [查看防火墙报告](review-the-administrator-reports.md#Firewall_report)

- [查看 DNS 报告](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>查看摘要报告
<a name="Summary_report"> </a>

Skype for Business 管理员报告是详细记录设计的四个有价值的报告中的第一个报告。 此报告和其他三个相关报告中的信息对信息技术团队很有用：

![一般摘要管理报告](../../media/General_Summary_Report_Admin_Report.png)

摘要报告列出了与边缘网络关联的常规配置信息。 记录了位置、完全限定域名 (FQDN) IP 地址、网络类型和特定于给定角色的注释。

将部署、管理和维护基础结构的设计人员和每个团队应检查摘要报告的准确性并确保错误最少。

还可以查看更详细的报告：

- 证书报告

- 防火墙报告

- DNS 报告

## <a name="review-the-certificates-report"></a>查看证书报告
<a name="Certificates_Report"> </a>

证书报告包含建议的 Skype for Business Server 2015 部署中所需的所有证书。 规划工具会考虑输入的主题名称和主题替代名称。 对于负责请求和颁发证书的团队来说，未编辑的默认文本可能会带来挑战。 证书信息还包含通常可以从何处颁发证书的信息。 如果基础结构中没有内部公钥基础结构 (PKI)，则可以通过公共证书提供商请求所有证书。 该报告中的“扩展密钥用法 (EKU)”和“分配给”字段非常有助于理解每个证书应有的用途和应处的位置。

![证书管理员报告](../../media/Certificates_Report_Admin_Report.png)

仔细检查部署中每个证书的用途和用途，并确保了解。 如果对证书执行哪些操作存在疑问，请确定与哪些服务器或服务通信。 Skype for Business Server 2015 中的证书主要用于两个目的：

- 相互传输层安全性 (MTLS) - 通信中涉及的每台计算机都提供一个向另一台计算机证明其身份的证书。 这称为服务器身份验证。 在每个计算机信任另一台计算机的标识之前，通信无法开始。

- 加密 - 加密 (安全套接字层、SSL、传输层安全性或 TLS) 是帮助保护通信、帮助确保隐私以及创建受信任的通信和协作系统的关键方法。

## <a name="review-the-firewall-report"></a>查看防火墙报告
<a name="Firewall_report"> </a>

Skype for Business Server 2015 具有一组可能复杂的防火墙规则。 规划工具通过生成报告来基于设计器的输入条件详细定义所有防火墙要求，从而降低此复杂性。 IT 防火墙管理员将可以使用此报告配置和定义所需的规则。

从防火墙管理的角度来看，应仔细审阅报告，以确保与退出防火墙规则没有冲突，并且没有违反的策略或过程。

![防火墙管理员报告](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a>查看 DNS 报告
<a name="DNS_Report"> </a>

DNS 报告是管理员报告的一部分，它详细说明了内部、外围和外部网络中域名系统 (DNS) 的所有推荐条目和已知条目。 如果设计器已完成对网络图的编辑，并且所有 IP 地址和完全限定域名 (FQDN) 都定义为其生产值，则 DNS 报告将提供出色的配置资源。 此报告还可以作为操作疑难解答文档。

![DNS 管理员报告](../../media/DNS_Report_Admin_Report.png)

您应该让 DNS 管理团队全面查看 DNS 报告，以确保在部署过程中没有可能导致问题的错误，或可能导致疑难解答会话复杂化的错误。

## <a name="see-also"></a>另请参阅
<a name="DNS_Report"> </a>

[查看管理员报告](https://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)
