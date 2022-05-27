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
description: 了解如何正确配置Microsoft 365或Office 365 URL 和 IP 地址范围，并在可能的情况下绕过前向代理，以便与Microsoft Teams服务建立连接。
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
ms.openlocfilehash: 1ebcf7c6595da3e1774571be4c65a796838115b3
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675714"
---
# <a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Microsoft 365和Office 365 URL 和 IP 地址范围

转到[Microsoft 365和Office 365 URL 和 IP 地址范围](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)，以获取必须为Teams正确配置的 URL、IP 地址、端口和协议的详细和最新列表。 Microsoft 一直在改进 Microsoft 365 和 Office 365 服务并添加新功能，因此，所需端口、URL 和 IP 地址可能会随时间变化。 建议 [通过 RSS 订阅](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) ，以便在更新或更改此信息时接收通知。

Teams通话和会议体验建立在基于云的下一代基础结构之上，Skype和Skype for Business也使用这些基础结构。 这些技术投资包括用于媒体处理和信号的基于 Azure 的云服务、H.264 视频编解码器、SILK 和 Opus 音频编解码器、网络复原能力、遥测和质量诊断。 因此，需要与Skype和Skype for Business关联的 URL 和 IP。

对于所有Microsoft 365和Office 365工作负荷，建议Teams服务的连接方法会尽可能绕过转发代理。 当代理服务器位于客户端和Office 365数据中心之间时，媒体可能会被强制通过 TCP 而不是 UDP，这将影响媒体质量。 下载示例代理 PAC 文件，这些文件可用于从[管理Microsoft 365和Office 365终结点](/office365/enterprise/managing-office-365-endpoints)配置流量旁路。

如果网络和安全策略要求Microsoft 365或Office 365流量流经代理服务器，请确保在将Teams部署到生产环境之前已满足上述要求。 有关详细信息，请阅读[用于Teams或联机Skype for Business代理服务器](proxy-servers-for-skype-for-business-online.md)。