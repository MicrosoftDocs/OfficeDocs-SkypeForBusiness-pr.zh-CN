---
title: Office 365 URL 和 IP 地址范围
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
description: 了解如何正确配置 Office 365 URL 和 IP 地址范围，在适用的情况下对与 Microsoft Teams 服务的连接不使用正向代理，以及了解网络连接和安全策略的要求。
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.network.ports
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06079ccb801cb73c8fc4851beab8694f772bb59b
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "30493510"
---
<a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="d11b2-103">Office 365 URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="d11b2-103">Office 365 URLs and IP address ranges</span></span>
=====================================

<span data-ttu-id="d11b2-104">有关详细和最新列表的 Url、 IP 地址、 端口和协议必须正确配置团队转到[Office 365 Url 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="d11b2-104">Go to [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="d11b2-105">Microsoft 一直在改进 Office 365 服务并添加新功能，因此，所需端口、URL 和 IP 地址可能会随时间变化。</span><span class="sxs-lookup"><span data-stu-id="d11b2-105">Microsoft is continuously improving the Office 365 service and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="d11b2-106">建议的您[通过 RSS 订阅](https://go.microsoft.com/fwlink/p/?linkid=236301)此信息更新或更改时收到通知。</span><span class="sxs-lookup"><span data-stu-id="d11b2-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="d11b2-107">呼叫和会议的体验基于的下一个生成基于云的基础结构还使用 Skype 和 Skype for Business 的团队。</span><span class="sxs-lookup"><span data-stu-id="d11b2-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="d11b2-108">这些技术投资包括对媒体处理和信号、 H.264 视频编解码器、 绞丝和作品音频编解码器、 网络恢复能力、 遥测、 和质量诊断的基于 Azure 云服务。</span><span class="sxs-lookup"><span data-stu-id="d11b2-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="d11b2-109">因此，需要的 URL 和 IP 可能与 Skype 和 Skype for Business 关联。</span><span class="sxs-lookup"><span data-stu-id="d11b2-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="d11b2-110">对于所有 Office 365 工作负载，团队服务的建议的连接方法绕过转发代理，在可能的情况。</span><span class="sxs-lookup"><span data-stu-id="d11b2-110">For all Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="d11b2-111">代理服务器位于客户端和 Office 365 数据中心之间，媒体可能强制 over TCP 而不是 UDP，将会影响媒体质量。</span><span class="sxs-lookup"><span data-stu-id="d11b2-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="d11b2-112">下载示例，可以用来配置[管理 Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)终结点的流量绕过代理 PAC 文件。</span><span class="sxs-lookup"><span data-stu-id="d11b2-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span></span>

<span data-ttu-id="d11b2-113">如果您的网络和安全策略要求 Office 365 通信都通过传输代理服务器，请确保已部署到生产环境 （回顾[工作组或业务 online Skype 的代理服务器](proxy-servers-for-skype-for-business-online.md)的团队之前满足上述要求有关指南）。</span><span class="sxs-lookup"><span data-stu-id="d11b2-113">If your networking and security policies require Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production (review [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md) for guidance).</span></span>
