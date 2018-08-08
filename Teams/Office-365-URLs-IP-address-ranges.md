---
title: Office 365 URL 和 IP 地址范围
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
description: 了解如何正确配置 Office 365 URL 和 IP 地址范围，在适用的情况下对与 Microsoft Teams 服务的连接不使用正向代理，以及了解网络连接和安全策略的要求。
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f946bc45fae230c0fd0ead9c06d0ced537bc7f92
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "18998970"
---
<a name="office-365-urls-and-ip-address-ranges"></a>Office 365 URL 和 IP 地址范围
=====================================

有关详细和最新列表的 Url、 IP 地址、 端口和协议必须正确配置团队转到[Office 365 Url 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)。 Microsoft 在不断改进 Office 365 服务，并添加新功能，这意味着所需的端口，Url 和 IP 地址可能会随时间。 建议的您[通过 RSS 订阅](https://go.microsoft.com/fwlink/p/?linkid=236301)此信息更新或更改时收到通知。

呼叫和会议的体验基于的下一个生成基于云的基础结构还使用 Skype 和 Skype for Business 的团队。 这些技术投资包括用于媒体处理和信号发送的基于 Azure 的云服务、H.264 视频编解码器、SILK 和 Opus 音频编解码器、网络复原、遥测和质量诊断。 因此，需要的 URL 和 IP 可能与 Skype 和 Skype for Business 关联。

对于所有 Office 365 工作负载，团队服务的建议的连接方法绕过转发代理，在可能的情况。 代理服务器位于客户端和 Office 365 数据中心之间，媒体可能强制 over TCP 而不是 UDP，将会影响媒体质量。 下载示例，可以用来配置[管理 Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)终结点的流量绕过代理 PAC 文件。

如果您的网络和安全策略要求 Office 365 通信都通过传输代理服务器，请确保团队部署到生产环境之前已满足上述要求 （查看[业务 online Skype 的代理服务器](https://support.office.com/article/Proxy-Servers-for-Skype-for-Business-Online-7acaf2c2-35fa-490f-84cd-822e446e0fc7?ui=en-US&rs=en-US&ad=US)（英文）指南）。
