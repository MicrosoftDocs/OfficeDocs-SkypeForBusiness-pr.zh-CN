---
title: 在 Skype for Business Server 2015 中查看管理员报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: 管理员报告是有关部署和操作的详细信息。 这些报告是基于“设计站点”中标记的选择而生成的。 设计师可以通过编辑网络图并为服务器、池和负载平衡器定义完整的 IP 地址和完全限定的域名 (FQDN)，来进一步向管理员报告中添加值。
ms.openlocfilehash: 22b3628c5c2a499d57a6bfdd1d90fe3b79b90e85
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288983"
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

Skype for Business 管理员报告是记录你的设计详细信息的四个有价值的报表中的第一个。 此报告和其他三个相关报告中的信息对信息技术团队很有用：

![常规摘要管理报告](../../media/General_Summary_Report_Admin_Report.png)

摘要报告列出了与边缘网络关联的常规配置信息。记录了位置、完全限定域名 (FQDN) 和 IP 地址、网络类型以及特定于给定角色的注释。

要部署、管理和维护基础结构的设计师和团队的每个成员应检查摘要报告的准确性并确保将错误降到最少。

你还可以查看更详细的报告：

- 证书报告

- 防火墙报告

- DNS 报告

## <a name="review-the-certificates-report"></a>查看证书报告
<a name="Certificates_Report"> </a>

"证书" 报告包含建议的 Skype for Business Server 2015 部署中所需的所有证书。 适用于所输入的主题名称和主题备用名称的规划工具帐户。 未经编辑的默认文本可能会给负责请求和颁发证书的团队带来挑战。 证书信息还包含通常可以从何处颁发证书的信息。 如果基础结构中没有内部公钥基础结构 (PKI)，则可以通过公共证书提供商请求所有证书。 该报告中的“扩展密钥用法 (EKU)”和“分配给”字段非常有助于理解每个证书应有的用途和应处的位置。

![证书管理报告](../../media/Certificates_Report_Admin_Report.png)

仔细阅读并确保了解部署中每个证书的用法和用途。 如果对证书用途有疑问，请确定是何种服务器或服务在与何种对象通信。 Skype for Business Server 2015 中的证书用于两个主要用途:

- 相互传输层安全性 (MTLS)-通信中涉及的计算机都提供了向其他计算机证明其身份的证书。 这称为服务器身份验证。 通信无法开始, 直到每台计算机都信任另一台计算机的标识。

- 加密加密 (安全套接字层或 SSL, 以及传输层安全性或 TLS) 是一种有助于确保通信安全、帮助确保隐私以及创建受信任的通信和协作系统的关键方法。

## <a name="review-the-firewall-report"></a>查看防火墙报告
<a name="Firewall_report"> </a>

Skype for Business 服务器2015具有一组可能复杂的防火墙规则。 计划工具通过生成基于设计器的输入条件来详细定义所有防火墙要求的报表, 降低了这种复杂性。 IT 防火墙管理员将能够使用此报告配置和定义所需的规则。

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
