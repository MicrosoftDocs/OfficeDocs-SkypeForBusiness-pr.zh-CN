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
description: 了解如何正确配置Microsoft 365或Office 365 URL 和 IP 地址范围，并尽可能绕过转发代理以Microsoft Teams服务。
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
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="45135-103">Microsoft 365和Office 365 URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="45135-103">Microsoft 365 and Office 365 URLs and IP address ranges</span></span>
=======================================================

<span data-ttu-id="45135-104">转到Microsoft 365和 Office 365 URL 和[IP](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)地址范围，获取必须正确为 Teams 正确配置的 URL、IP 地址、端口和协议的详细最新列表。</span><span class="sxs-lookup"><span data-stu-id="45135-104">Go to [Microsoft 365 and Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="45135-105">Microsoft 一直在改进 Microsoft 365 和 Office 365 服务并添加新功能，因此，所需端口、URL 和 IP 地址可能会随时间变化。</span><span class="sxs-lookup"><span data-stu-id="45135-105">Microsoft is continuously improving the Microsoft 365 and Office 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="45135-106">建议通过 [RSS 订阅](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) ，在更新或更改此信息时接收通知。</span><span class="sxs-lookup"><span data-stu-id="45135-106">We recommend that you [subscribe via RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="45135-107">呼叫Teams会议体验构建在下一代基于云的基础结构上，Skype Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="45135-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="45135-108">这些技术投资包括用于媒体处理和信令的基于 Azure 的云服务、H.264 视频编解码器、SILK 和 Opus 音频编解码器、网络复原、遥测和质量诊断。</span><span class="sxs-lookup"><span data-stu-id="45135-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="45135-109">因此，可能需要将 URL 和 IP 与 Skype 和 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="45135-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="45135-110">对于所有Microsoft 365 Office 365工作负荷，建议Teams连接方法尽可能绕过转发代理。</span><span class="sxs-lookup"><span data-stu-id="45135-110">For all Microsoft 365 and Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="45135-111">当代理服务器位于客户端与Office 365之间时，媒体可能会通过 TCP 而不是 UDP 强制使用，这会影响媒体质量。</span><span class="sxs-lookup"><span data-stu-id="45135-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="45135-112">下载示例代理 PAC 文件，这些文件可用于从管理终结点和终结点[配置Microsoft 365 Office 365绕过。](/office365/enterprise/managing-office-365-endpoints)</span><span class="sxs-lookup"><span data-stu-id="45135-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Microsoft 365 and Office 365 endpoints](/office365/enterprise/managing-office-365-endpoints).</span></span>

<span data-ttu-id="45135-113">如果网络和安全策略要求Microsoft 365 Office 365流量流经代理服务器，请确保在将 Teams 部署到生产环境之前满足上述要求。</span><span class="sxs-lookup"><span data-stu-id="45135-113">If your networking and security policies require Microsoft 365 or Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production.</span></span> <span data-ttu-id="45135-114">有关详细信息，请阅读适用于 Teams[或 Skype for Business Online 的代理服务器](proxy-servers-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="45135-114">For more information, read [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span></span>