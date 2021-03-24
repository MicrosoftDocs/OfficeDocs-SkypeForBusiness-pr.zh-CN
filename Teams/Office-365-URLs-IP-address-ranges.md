---
title: Microsoft 365 和 Office 365 URL 和 IP 地址范围
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: 了解如何正确配置 Microsoft 365 或 Office 365 URL 和 IP 地址范围，并尽可能绕过转发代理以与 Microsoft Teams 服务建立连接。
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
ms.openlocfilehash: 9a29984b0b389bacb50a9aa6512a9ccc8bfe07de
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094514"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Microsoft 365 和 Office 365 URL 和 IP 地址范围
=======================================================

转到 [Microsoft 365 和 Office 365](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) URL 和 IP 地址范围，获取必须为 Teams 正确配置的 URL、IP 地址、端口和协议的详细最新列表。 Microsoft 一直在改进 Microsoft 365 和 Office 365 服务并添加新功能，因此，所需端口、URL 和 IP 地址可能会随时间变化。 建议通过 [RSS 订阅](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) ，在更新或更改此信息时接收通知。

Teams 通话和会议体验基于 Skype 和 Skype for Business 也使用的下一代基于云的基础结构。 这些技术投资包括用于媒体处理和信令的基于 Azure 的云服务、H.264 视频编解码器、SILK 和 Opus 音频编解码器、网络复原、遥测和质量诊断。 因此，有些 URL 和 IP 可能需要与 Skype 和 Skype for Business 相关联。

对于所有 Microsoft 365 和 Office 365 工作负荷，建议使用 Teams 服务的连接方法尽可能绕过转发代理。 当代理服务器位于客户端和 Office 365 数据中心之间时，媒体可能会通过 TCP 而不是 UDP 强制使用，这会影响媒体质量。 下载可用于从管理 [Microsoft 365 和 Office 365](/office365/enterprise/managing-office-365-endpoints)终结点配置流量绕过的示例代理 PAC 文件。

如果网络和安全策略要求 Microsoft 365 或 Office 365 流量流经代理服务器，请确保在将 Teams 部署到生产环境之前满足上述要求。 有关详细信息，请阅读 [Teams 或 Skype for Business Online 的代理服务器](proxy-servers-for-skype-for-business-online.md)。