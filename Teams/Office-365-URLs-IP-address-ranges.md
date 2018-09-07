---
title: Office 365 URL 和 IP 地址范围
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
description: 了解如何正确配置 Office 365 URL 和 IP 地址范围，在适用的情况下对与 Microsoft Teams 服务的连接不使用正向代理，以及了解网络连接和安全策略的要求。
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a21130d3e1c2e81203bb409fc2a53c77645bf0ba
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23851920"
---
<a name="office-365-urls-and-ip-address-ranges"></a>Office 365 URL 和 IP 地址范围
=====================================

有关详细和最新列表的 Url、 IP 地址、 端口和协议必须正确配置团队转到[Office 365 Url 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。 Microsoft 在不断改进 Office 365 服务，并添加新功能，这意味着所需的端口，Url 和 IP 地址可能会随时间。 建议的您[通过 RSS 订阅](https://go.microsoft.com/fwlink/p/?linkid=236301)此信息更新或更改时收到通知。

呼叫和会议的体验基于的下一个生成基于云的基础结构还使用 Skype 和 Skype for Business 的团队。 这些技术投资包括用于媒体处理和信号发送的基于 Azure 的云服务、H.264 视频编解码器、SILK 和 Opus 音频编解码器、网络复原、遥测和质量诊断。 因此，需要的 URL 和 IP 可能与 Skype 和 Skype for Business 关联。

对于所有 Office 365 工作负载，团队服务的建议的连接方法绕过转发代理，在可能的情况。 代理服务器位于客户端和 Office 365 数据中心之间，媒体可能强制 over TCP 而不是 UDP，将会影响媒体质量。 下载示例，可以用来配置[管理 Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)终结点的流量绕过代理 PAC 文件。

如果您的网络和安全策略要求 Office 365 通信都通过传输代理服务器，请确保团队部署到生产环境之前已满足上述要求 （查看[业务 online Skype 的代理服务器](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online)（英文）指南）。
