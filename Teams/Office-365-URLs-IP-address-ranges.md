---
title: Microsoft 365 和 Office 365 URL 和 IP 地址范围
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: 了解如何正确配置 Microsoft 365 或Office 365 URL 和 IP 地址范围，并在可能的情况下绕过前向代理，以便与 Microsoft Teams 服务建立连接。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.network.ports
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2f638b9fb29c80806082e02f2d0b09ceec619d0
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563730"
---
# <a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Microsoft 365 和 Office 365 URL 和 IP 地址范围

转到 [Microsoft 365 和Office 365 URL 和 IP 地址范围](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)，获取必须为 Teams 正确配置的 URL、IP 地址、端口和协议的详细和最新列表。 Microsoft 一直在改进 Microsoft 365 和 Office 365 服务并添加新功能，因此，所需端口、URL 和 IP 地址可能会随时间变化。 建议 [通过 RSS 订阅](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) ，以便在更新或更改此信息时接收通知。

Teams 通话和会议体验基于 Skype 和 Skype for Business 也使用的下一代基于云的基础结构构建。 这些技术投资包括用于媒体处理和信号的基于 Azure 的云服务、H.264 视频编解码器、SILK 和 Opus 音频编解码器、网络复原能力、遥测和质量诊断。 因此，需要与 Skype 和 Skype for Business 关联的 URL 和 IP。

对于所有 Microsoft 365 和Office 365工作负荷，建议的到 Teams 服务的连接方法会尽可能绕过转发代理。 当代理服务器位于客户端和Office 365数据中心之间时，媒体可能会被强制通过 TCP 而不是 UDP，这将影响媒体质量。 下载示例代理 PAC 文件，这些文件可用于从[管理 Microsoft 365 和Office 365终结点](/office365/enterprise/managing-office-365-endpoints)配置流量旁路。

如果网络和安全策略要求 Microsoft 365 或Office 365流量流经代理服务器，请确保在将 Teams 部署到生产环境中之前已满足上述要求。 有关详细信息，请阅读 [Teams 或 Skype for Business Online 的代理服务器](proxy-servers-for-skype-for-business-online.md)。