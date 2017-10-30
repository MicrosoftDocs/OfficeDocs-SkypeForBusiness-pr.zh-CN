---
title: "Office 365 URL 和 IP 地址范围 | Microsoft 支持"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解如何正确配置 Office 365 URL 和 IP 地址范围，在适用的情况下对与 Microsoft Teams 服务的连接不使用正向代理，以及了解网络连接和安全策略的要求。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: a226a2d541119c61a3538c86f3502defb739147d
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2017
---
<a name="office-365-urls-and-ip-address-ranges"></a>Office 365 URL 和 IP 地址范围
=====================================

请查看以下链接，了解必须正确配置的确切 IP 和端口的最新详细列表：[Office 365 URL 和 IP 地址范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US) Microsoft 一直在改进 Office 365 服务并添加新功能，因此，所需端口、URL 和 IP 地址可能会随时间变化。 请参阅 [Office 365 URL 和 IP 地址范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)指南，了解最新版本的端口和协议。 此外，强烈建议[通过 RSS 订阅](https://go.microsoft.com/fwlink/p/?linkid=236301)以在终结点更新或更改时接收通知。

如前所述，Microsoft Teams 通话和会议体验建立在下一代基于云的基础结构之上，而 Skype 和 Skype for Business 也使用该基础结构。 这些技术投资包括用于媒体处理和信号发送的基于 Azure 的云服务、H.264 视频编解码器、SILK 和 Opus 音频编解码器、网络复原、遥测和质量诊断。 因此，需要的 URL 和 IP 可能与 Skype 和 Skype for Business 关联。

对于所有 Office 365 工作负荷，建议的 Microsoft Teams 服务连接方法是尽可能不使用正向代理。 客户端与 Office 365 数据中心之间存在代理服务器时，可能会强制采用 TCP 而非 UDP 传输媒体，这可能会影响媒体质量。 可以从[管理 Office 365 终结点](https://support.office.com/article/managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a)指南下载可用于配置流量旁路的示例代理 PAC 文件。

如果你的网络连接和安全策略要求 Office 365 通信通过代理服务器传输，则请确保先满足上述要求，然后再将 Microsoft Teams 部署到生产中（请查看 [Skype for Business Online 的代理服务器](https://support.office.com/en-us/article/Proxy-Servers-for-Skype-for-Business-Online-7acaf2c2-35fa-490f-84cd-822e446e0fc7?ui=en-US&rs=en-US&ad=US)了解相关指导）。
