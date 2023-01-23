---
title: 直接路由的新增功能
ms.reviewer: CarolynRowe
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 本文介绍直接路由中的新增功能。 请经常回来查看更新。
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 85a700faf37044c97c432707b07b6d6699c6692b
ms.sourcegitcommit: 1f4a0b7cf03f63438bb37668d053853494c92168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2023
ms.locfileid: "69948579"
---
# <a name="whats-new-for-direct-routing"></a>直接路由的新增功能

本文介绍直接路由中的新增功能。 请经常回来查看更新。

## <a name="new-direct-routing-sip-endpoints"></a>新的直接路由 SIP 终结点 

Microsoft 将向 Teams 直接路由 SIP 终结点引入新的信号 IP。 若要确保此更改不会影响服务可用性，请确保会话边界控制器和防火墙配置为使用建议的子网 52.112.0.0/14 和 52.120.0.0/14 作为分类和 ACL 规则。 有关详细信息，请参阅 [Microsoft 365、Office 365 和 Office 365 GCC 环境](direct-routing-plan.md#microsoft-365-office-365-and-office-365-gcc-environments)。  

## <a name="trunk-demoting-logic-based-on-sip-options"></a>基于 SIP 选项的中继降级逻辑

针对中继运行状况引入了基于 SIP 选项的新功能。 在网关配置中启用 (看到 Set-CsOnlinePSTNGateway cmdlet 和 SendSipOptions 参数) 时，出站呼叫的路由逻辑会降级不定期发送 SIP 选项的中继， (预期时间段是 SBC 每分钟发送一个 SIP 选项，) 到 Microsoft 后端。 这些降级的中继将放在可用于出站呼叫的中继列表的末尾，并作为最后一个进行尝试：因此，可能会减少呼叫设置时间。
为该功能启用的任何中继在五分钟内未将至少一个 SIP 选项发送到任何 Microsoft 区域 (NOAM、EMEA、APAC、OCEA) SIP 代理都被视为降级。 如果中继仅将 SIP 选项发送到 Microsoft 区域 SIP 代理的子集，则首先尝试这些路由，其余路由将降级。


## <a name="sip-support"></a>SIP 支持

2022 年 6 月 1 日，Microsoft 将从直接路由配置中删除对 sip-all.pstnhub.microsoft.com 和 sip-all.pstnhub.gov.teams.microsoft.us FQDN 的支持。

如果在 6 月 1 日之前未执行任何操作，用户将无法通过直接路由拨打或接听呼叫。

防止服务影响：

- 对于任何分类或 ACL 规则，请使用建议的子网： (52.112.0.0/14 和 52.120.0.0/14) 。
- 为直接路由配置会话边界控件时，停止使用 sip-all FQDN。

有关详细信息，请参阅 [计划直接路由](direct-routing-plan.md)。

## <a name="tls-certificates"></a>TLS 证书

Microsoft 365 正在更新 Teams 和其他服务，以使用一组不同的根证书颁发机构 (CA) 。

有关详细信息和受影响服务的完整列表，请参阅 [对 Microsoft 365 服务（包括 Microsoft Teams）的 TLS 证书更改](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676)。

## <a name="certificate-authorities"></a>证书颁发机构

从 2022 年 2 月 1 日起，直接路由 SIP 接口将仅信任证书颁发机构 (CA) 签名的证书，这些证书属于 Microsoft 受信任的根证书计划。 执行以下步骤以避免对服务造成影响：

- 确保 SBC 证书由属于 Microsoft 受信任的根证书计划的 CA 签名。
- 验证证书的扩展密钥用法 (EKU) 扩展是否包括“服务器身份验证”。

有关 Microsoft 受信任的根证书计划的详细信息，请参阅 [计划要求 - Microsoft 受信任的根计划](/security/trusted-root/program-requirements)。

有关受信任的 CA 列表，请参阅 [Microsoft 包含的 CA 证书列表](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)。

## <a name="replace-headers"></a>替换标头

从 2022 年 4 月开始，直接路由将拒绝定义了 Replaces 标头的 SIP 请求。 Microsoft 将 Replaces 标头发送到会话边界控制器 (SBC) 的流没有变化。

检查 SBC 配置，并确保未在 SIP 请求中使用替换标头。

## <a name="tls10-and-11"></a>TLS1.0 和 1.1

为了为客户提供一流的加密，Microsoft 计划弃用传输层安全性 (TLS) 版本 1.0 和 1.1。 2022 年 4 月 3 日，Microsoft 将强制使用直接路由 SIP 接口的 TLS1.2。

若要避免任何服务影响，请确保 SBC 配置为支持 TLS1.2，并且可以使用以下密码套件之一进行连接：

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 i.e. ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 i.e. ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 i.e. ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 i.e. ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>相关主题

- [直接路由 - SIP 协议](direct-routing-protocols-sip.md)
