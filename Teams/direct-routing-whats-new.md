---
title: 新增直接路由
ms.reviewer: CarolynRowe
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 本文介绍直接路由中的新增功能。 请经常返回查看更新。
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6f2ec21ec3e7f4278443d6bcab4b4220db3619f
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556734"
---
# <a name="whats-new-for-direct-routing"></a>直接路由的新增功能

本文介绍直接路由中的新增功能。 请经常返回查看更新。

## <a name="sip-support"></a>SIP 支持

2022 年 6 月 1 日，Microsoft 将删除对直接路由 sip-all.pstnhub.microsoft.com FQNS sip-all.pstnhub.gov.teams.microsoft.us FQNS 的支持。

如果在 6 月 1 日之前未采取任何操作，用户将无法通过直接路由拨打或接听呼叫。

防止服务影响：

- 对于任何分类或 ACL 规则，请使用建议的子网： (52.112.0.0/14 和 52.120.0.0/14) 。
- 为直接路由配置会话边界控件时，停止使用 sip-all FQDN。

有关详细信息，请参阅 [规划直接路由](direct-routing-plan.md)。

## <a name="tls-certificates"></a>TLS 证书

Microsoft 365更新 Teams 和其他服务，以使用一组不同的根证书颁发机构 (CA) 。

有关详细信息和受影响服务的完整列表，请参阅 [TLS 证书对 Microsoft 365 服务（包括 Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676)）。

## <a name="certificate-authorities"></a>证书颁发机构

从 2022 年 2 月 1 日起，直接路由 SIP 接口将仅信任由证书颁发机构 (CA) 签名的证书，这些证书是 Microsoft 受信任的根证书计划的一部分。 请执行以下步骤以避免服务影响：

- 确保 SBC 证书由 Microsoft 受信任的根证书计划的 CA 签名。
- 验证证书的 EKU 扩展 (密钥) 包括"服务器身份验证"。

有关 Microsoft 受信任的根证书计划的信息，请参阅计划 [要求 - Microsoft 受信任的根程序](/security/trusted-root/program-requirements)。

有关受信任的 CA 列表，请参阅 [Microsoft 包含的 CA 证书列表](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)。

## <a name="replace-headers"></a>替换标头

从 2022 年 4 月开始，直接路由将拒绝定义了 Replaces 标头的 SIP 请求。 对于 Microsoft 将 Replaces 标头发送到 SBC (会话边界控制器的流) 。

检查 SBC 配置，并确保未在 SIP 请求中使用 Replaces 标头。

## <a name="tls10-and-10"></a>TLS1.0 和 1.0

为了为客户提供一流加密，Microsoft 计划弃用 1.0 和 1.1 (TLS) 层安全性。 2022 年 4 月 3 日，Microsoft 将强制将 TLS1.2 用于直接路由 SIP 接口。

为了避免任何服务影响，请确保将 SDC 配置为支持 TLS1.2，并可以使用以下密码套件之一进行连接：

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384例如 ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256例如 ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384例如 ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256例如 ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>相关主题

- [直接路由 - SIP 协议](direct-routing-protocols-sip.md)
