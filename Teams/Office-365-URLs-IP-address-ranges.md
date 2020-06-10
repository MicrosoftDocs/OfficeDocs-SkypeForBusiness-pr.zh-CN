---
title: Microsoft 365 和 Office 365 Url 和 IP 地址范围
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: 了解如何正确配置 Microsoft 365 或 Office 365 Url 和 IP 地址范围，以及如何在可能的连接与 Microsoft 团队服务连接时绕过转发代理。
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
ms.openlocfilehash: 30736a347f447d265059de1a26ded5ef690e53dc
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665685"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Microsoft 365 和 Office 365 Url 和 IP 地址范围
=======================================================

转到[Microsoft 365 和 Office 365 url 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)，了解必须为团队正确配置的 URL、IP 地址、端口和协议的详细信息和最新列表。 Microsoft 不断改进 Microsoft 365 和 Office 365 服务并添加新功能，这意味着所需的端口、Url 和 IP 地址可能会随着时间的推移而更改。 建议你[通过 RSS 订阅](https://go.microsoft.com/fwlink/p/?linkid=236301)以在此信息更新或更改时收到通知。

Teams 通话和会议体验建立在下一代基于云的基础结构之上，而 Skype 和 Skype for Business 也使用该基础结构。 这些技术投资包括基于 Azure 的云服务，用于媒体处理和信号传输、H-p 视频编解码器、绞 Opus 音频编解码器、网络复原、遥测和质量诊断。 因此，需要的 URL 和 IP 可能与 Skype 和 Skype for Business 关联。

对于所有 Microsoft 365 和 Office 365 工作负荷，建议使用的团队服务的连接方法是在可能的情况下绕过转发代理。 客户端与 Office 365 数据中心之间存在代理服务器时，可能会强制采用 TCP 而非 UDP 传输媒体，这可能会影响媒体质量。 下载可用于配置绕过[管理 Microsoft 365 和 Office 365 终结点](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)的流量的示例代理 PAC 文件。

如果你的网络和安全策略需要 Microsoft 365 或 Office 365 通信流通过代理服务器，请确保在将团队部署到生产之前已满足上述要求。 有关详细信息，请阅读[团队或 Skype for Business Online 的代理服务器](proxy-servers-for-skype-for-business-online.md)。
