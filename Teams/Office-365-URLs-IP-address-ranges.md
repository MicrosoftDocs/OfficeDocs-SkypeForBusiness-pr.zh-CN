---
title: Office 365 URL 和 IP 地址范围
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: 了解如何正确配置 Office 365 URL 和 IP 地址范围，在适用的情况下对与 Microsoft Teams 服务的连接不使用正向代理，以及了解网络连接和安全策略的要求。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.meetingsettings.network.ports
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1258138ce6f57dfb0284e030f7a813acf8b94a62
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862792"
---
<a name="office-365-urls-and-ip-address-ranges"></a>Office 365 URL 和 IP 地址范围
=====================================

有关必须为 Teams 正确配置的 URL、IP 地址、端口和协议的最新详细列表，请参阅 [Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。 Microsoft 一直在改进 Office 365 服务并添加新功能，因此，所需端口、URL 和 IP 地址可能会随时间变化。 建议你[通过 RSS 订阅](https://go.microsoft.com/fwlink/p/?linkid=236301)以在此信息更新或更改时收到通知。

Teams 通话和会议体验建立在下一代基于云的基础结构之上，而 Skype 和 Skype for Business 也使用该基础结构。 这些技术投资包括基于 Azure 的云服务，用于媒体处理和信号传输、H-p 视频编解码器、绞 Opus 音频编解码器、网络复原、遥测和质量诊断。 因此，需要的 URL 和 IP 可能与 Skype 和 Skype for Business 关联。

对于所有 Office 365 工作负荷，建议的 Teams 服务连接方法是尽可能不使用正向代理。 客户端与 Office 365 数据中心之间存在代理服务器时，可能会强制采用 TCP 而非 UDP 传输媒体，这可能会影响媒体质量。 可以从[管理 Office 365 终结点](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)下载可用于配置流量旁路的示例代理 PAC 文件。

如果你的网络和安全策略需要 Office 365 流量以流过代理服务器，请确保在将团队部署到生产之前已满足上述要求。 有关详细信息，请阅读[团队或 Skype for Business Online 的代理服务器](proxy-servers-for-skype-for-business-online.md)。
