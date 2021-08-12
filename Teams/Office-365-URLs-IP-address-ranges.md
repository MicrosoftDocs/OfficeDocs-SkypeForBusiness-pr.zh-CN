---
title: Microsoft 365和Office 365 URL 和 IP 地址范围
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: 了解如何正确配置Microsoft 365或Office 365 URL 和 IP 地址范围，并尽可能绕过转发代理以Microsoft Teams连接。
localization_priority: Normal
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
ms.openlocfilehash: f6b42865666538c6af431ab8f6e69ef495f3d5daf89c673a118eb4a2dd429564
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2021
ms.locfileid: "57850157"
---
# <a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Microsoft 365和Office 365 URL 和 IP 地址范围

转到Microsoft 365和 Office 365 URL 和[IP](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)地址范围，获取必须正确为 Teams 正确配置的 URL、IP 地址、端口和协议的详细最新列表。 Microsoft 一直在改进 Microsoft 365 和 Office 365 服务并添加新功能，因此，所需端口、URL 和 IP 地址可能会随时间变化。 建议通过 [RSS 订阅](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) ，在更新或更改此信息时接收通知。

呼叫Teams会议体验基于下一代基于云的基础结构，Skype和Skype for Business。 这些技术投资包括用于媒体处理和信令的基于 Azure 的云服务、H.264 视频编解码器、SILK 和 Opus 音频编解码器、网络复原、遥测和质量诊断。 因此，可能需要将 URL 和 IP 与 Skype 和 Skype for Business。

对于所有Microsoft 365 Office 365工作负荷，建议用于Teams连接方法是尽可能绕过转发代理。 当代理服务器位于客户端和数据中心Office 365之间时，媒体可能会通过 TCP 而不是 UDP 强制使用，这会影响媒体质量。 下载示例代理 PAC 文件，这些文件可用于从管理终结点和终结点[配置Microsoft 365 Office 365绕过。](/office365/enterprise/managing-office-365-endpoints)

如果网络和安全策略要求Microsoft 365或Office 365流量流经代理服务器，请确保在将 Teams 部署到生产环境之前满足上述要求。 有关详细信息，请阅读适用于 Teams[或 Skype for Business Online 的代理服务器](proxy-servers-for-skype-for-business-online.md)。