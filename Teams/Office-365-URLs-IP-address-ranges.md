---
title: Office 365 URL 和 IP 地址范围
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
description: 了解如何正确配置 Office 365 URL 和 IP 地址范围，在适用的情况下对与 Microsoft Teams 服务的连接不使用正向代理，以及了解网络连接和安全策略的要求。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 713815836b2edcad31528abc01c74a2332ecf88a
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
<a name="office-365-urls-and-ip-address-ranges"></a>Office 365 URL 和 IP 地址范围
=====================================

有关 Url、 IP 地址、 端口和协议，必须正确配置团队的详细和最新列表，请转到[Office 365 的 Url 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)。 Microsoft 在不断改进的 Office 365 提供服务并添加新的功能，这意味着所需的端口，Url，并随着时间的推移可能会更改 IP 地址。 我们建议，您[通过 RSS 订阅](https://go.microsoft.com/fwlink/p/?linkid=236301)此信息被更新或更改时收到通知。

电话和会议的经验基于下一代基于云的基础架构，通过 Skype 和 Skype 也已用于业务的团队。 这些技术投资包括用于媒体处理和信号发送的基于 Azure 的云服务、H.264 视频编解码器、SILK 和 Opus 音频编解码器、网络复原、遥测和质量诊断。 因此，需要的 URL 和 IP 可能与 Skype 和 Skype for Business 关联。

对于所有 Office 365 提供工作负荷，为团队服务的推荐的连接方法绕过转发代理服务器，在可能的情况。 代理服务器位于客户端和 Office 365 提供数据中心之间，媒体可能会强制而不是 UDP，将影响媒体质量的 TCP 段。 下载示例代理 PAC 文件可用于配置通信量绕过从[管理 Office 365 的终结点](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)。

如果您的网络和安全策略需要 Office 365 通信量流过一个代理服务器，请确保已将上述要求满足小组部署到生产环境之前 （查看[Skype 的在线业务的代理服务器](https://support.office.com/article/Proxy-Servers-for-Skype-for-Business-Online-7acaf2c2-35fa-490f-84cd-822e446e0fc7?ui=en-US&rs=en-US&ad=US)指南）。
