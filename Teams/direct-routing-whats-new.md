---
title: 什么是新的直接路由
ms.reviewer: CarolynRowe
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 本文介绍直接路由中的新增功能。 请经常回头查看更新。
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 8db0f0c4d29f786166098587aafc3ec1db256e38
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271457"
---
# <a name="whats-new-for-direct-routing"></a>直接路由的新增功能

本文介绍直接路由中的新增功能。 请经常回头查看更新。

## <a name="sip-support"></a>SIP 支持

2022 年 6 月 1 日，Microsoft 将从直接路由配置中删除对 sip-all.pstnhub.microsoft.com 和 sip-all.pstnhub.gov.teams.microsoft.us FQDN 的支持。

如果在 6 月 1 日之前未执行任何操作，则用户将无法通过直接路由拨打或接收呼叫。

防止服务影响：

- 对于任何分类或 ACL 规则，请使用建议的子网： (52.112.0.0/14 和 52.120.0.0/14) 。
- 为直接路由配置会话边框控件时，请停止使用 sip-all FQDN。

有关详细信息，请参阅 [计划直接路由](direct-routing-plan.md)。

## <a name="tls-certificates"></a>TLS 证书

Microsoft 365 正在更新 Teams 和其他服务，以使用一组不同的根证书颁发机构 (CA) 。

有关详细信息和受影响服务的完整列表，请参阅 [对 Microsoft 365 服务（包括 Microsoft Teams）的 TLS 证书更改](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676)。

## <a name="certificate-authorities"></a>证书颁发机构

从 2022 年 2 月 1 日开始，直接路由 SIP 接口将仅信任证书颁发机构签署的证书 (CA) ，这些证书属于 Microsoft 受信任的根证书计划。 请执行以下步骤以避免服务影响：

- 确保 SBC 证书由属于 Microsoft 受信任根证书计划的 CA 签名。
- 验证证书的扩展密钥使用 (EKU) 扩展是否包括“服务器身份验证”。

有关 Microsoft 受信任的根证书计划的详细信息，请参阅 [计划要求 - Microsoft 受信任的根计划](/security/trusted-root/program-requirements)。

有关受信任的 CA 列表，请参阅 [Microsoft 包含的 CA 证书列表](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)。

## <a name="replace-headers"></a>替换标头

从 2022 年 4 月开始，直接路由将拒绝定义了 Replaces 标头的 SIP 请求。 Microsoft 将 Replaces 标头发送到会话边框控制器 (SBC) 的流没有更改。

检查 SBC 配置并确保未在 SIP 请求中使用 Replaces 标头。

## <a name="tls10-and-11"></a>TLS1.0 和 1.1

为了向客户提供一流的加密，Microsoft 计划弃用传输层安全性 (TLS) 版本 1.0 和 1.1。 2022 年 4 月 3 日，Microsoft 将强制使用 TLS1.2 直接路由 SIP 接口。

若要避免任何服务影响，请确保 SBC 配置为支持 TLS1.2，并且可以使用以下密码套件之一进行连接：

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384，即 ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256，即 ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384，即 ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256，即 ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>相关主题

- [直接路由 - SIP 协议](direct-routing-protocols-sip.md)
