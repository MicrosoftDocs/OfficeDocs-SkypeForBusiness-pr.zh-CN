---
title: "优化您的网络"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "以下要求都非常重要，所有 Skype 业务联机功能为您的组织设置，确保长期的健康和成功。 我们知道有些人非常技术-本文档是为您，但也有一些你不是。 如果您需要帮助来安装 Skype 的在线业务，您应该阅读本文档以熟悉您需要考虑的事情。 它还将讨论当您正在使用 Microsoft FastTrack 中心、 Microsoft 服务和客户团队，或与 Microsoft 合作伙伴，从而算出如何能够满足这些要求的事情。"
ms.openlocfilehash: 1704ffce3a717196856833c9dff9263dde3408c9
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="optimizing-your-network-for-skype-for-business-online"></a><span data-ttu-id="3d1de-106">为 Skype for Business Online 优化网络</span><span class="sxs-lookup"><span data-stu-id="3d1de-106">Optimizing your network for Skype for Business Online</span></span>

<span data-ttu-id="3d1de-107">以下要求都非常重要，所有 Skype 业务联机功能为您的组织设置，确保长期的健康和成功。</span><span class="sxs-lookup"><span data-stu-id="3d1de-107">The following requirements are really important to ensure the long-term health and success for all Skype for Business Online features you are setting up for your organization.</span></span> <span data-ttu-id="3d1de-108">我们知道有些人非常技术-本文档是为您，但也有一些你不是。</span><span class="sxs-lookup"><span data-stu-id="3d1de-108">We know some of you are very technical - this document is for you, but there are some of you that aren't.</span></span> <span data-ttu-id="3d1de-109">如果您需要帮助来安装 Skype 的在线业务，您应该阅读本文档以熟悉您需要考虑的事情。</span><span class="sxs-lookup"><span data-stu-id="3d1de-109">If you need help setting up Skype for Business Online, you should read this document to become familiar with the things you need to consider.</span></span> <span data-ttu-id="3d1de-110">它还将讨论当您正在使用[Microsoft FastTrack 中心](https://fasttrack.microsoft.com/office)、 Microsoft 服务和客户小组或[Microsoft 合作伙伴](https://partnercenter.microsoft.com/en-us/pcv/search)，从而算出如何能够满足这些要求的事情。</span><span class="sxs-lookup"><span data-stu-id="3d1de-110">It will also give you things to talk about when you are working with the [Microsoft FastTrack Center](https://fasttrack.microsoft.com/office), your Microsoft Services and account teams, or with [Microsoft partners](https://partnercenter.microsoft.com/en-us/pcv/search) to figure out how you can meet these requirements.</span></span>
  
## <a name="a-quick-overview"></a><span data-ttu-id="3d1de-111">简要概述</span><span class="sxs-lookup"><span data-stu-id="3d1de-111">A quick overview</span></span>

<span data-ttu-id="3d1de-112">Skype for Business 让你可与公司内或全球的同事或业务合作伙伴保持联系。</span><span class="sxs-lookup"><span data-stu-id="3d1de-112">Skype for Business lets you connect with co-workers or business partners in your company or around the world.</span></span>
  
<span data-ttu-id="3d1de-113">使用 Skype for Business，你可以：</span><span class="sxs-lookup"><span data-stu-id="3d1de-113">With Skype for Business, you can:</span></span>
  
- <span data-ttu-id="3d1de-114">通过即时消息、语音或视频呼叫开始交谈。</span><span class="sxs-lookup"><span data-stu-id="3d1de-114">Start conversations with IM, voice, or video calls.</span></span>
    
- <span data-ttu-id="3d1de-115">查看你的联系人何时在线且有空、何时在开会或演示。</span><span class="sxs-lookup"><span data-stu-id="3d1de-115">See when your contacts are available online, in a meeting, or presenting.</span></span>
    
- <span data-ttu-id="3d1de-116">为会议设置强大的安全性。</span><span class="sxs-lookup"><span data-stu-id="3d1de-116">Set industrial-strength security for meetings.</span></span>
    
- <span data-ttu-id="3d1de-117">在线向大量观众广播。</span><span class="sxs-lookup"><span data-stu-id="3d1de-117">Broadcast online to a large audience.</span></span>
    
- <span data-ttu-id="3d1de-118">会议期间展示你的屏幕或将控制权交给其他人。</span><span class="sxs-lookup"><span data-stu-id="3d1de-118">Present your screen during meetings or give control to others.</span></span>
    
- <span data-ttu-id="3d1de-119">在其他 Office 程序中使用 Skype for Business，只需单击一下，即可开始聊天、呼叫或加入会议。</span><span class="sxs-lookup"><span data-stu-id="3d1de-119">Use Skype for Business in other Office programs to chat, call, or join a meeting with a click.</span></span>
    
## <a name="why-is-this-all-so-important"></a><span data-ttu-id="3d1de-120">为什么这一点如此重要？</span><span class="sxs-lookup"><span data-stu-id="3d1de-120">Why is this all so important?</span></span>

<span data-ttu-id="3d1de-p103">通过 IP 的实时媒体（音频、视频和应用程序共享）的质量很大程度上受端到端网络连接质量的影响。为获得最佳的 Skype for Business Online 媒体质量，确保公司网络与 Skype for Business Online 之间的高质量连接很重要。实现这一目标的最佳做法是基于网络容量设置内部网络和云连接，以便所有连接都可以承受 Skype for Business Online 的高峰流量。</span><span class="sxs-lookup"><span data-stu-id="3d1de-p103">The quality of real-time media (audio, video, and application sharing) over IP is greatly impacted by the quality of end-to-end network connectivity. For optimal Skype for Business Online media quality, it is important for you to make sure there is a high-quality connection between your company network and Skype for Business Online. The best way to accomplish this is to set up your internal network and cloud connectivity based on the capacity of your network to accommodate for peak traffic volume for Skype for Business Online across all connections.</span></span>
  
<span data-ttu-id="3d1de-124">与[Microsoft 合作伙伴](https://partnercenter.microsoft.com/en-us/pcv/search)合作，您可以连接各种 Office 365 应用到您的网络和实时语音云中在线业务包括 Skype 和业务的 Skype 的视频通信功能需要的网络必须专门配置服务以支持这些 Office 365 的实时工作负载。</span><span class="sxs-lookup"><span data-stu-id="3d1de-124">Working with a [Microsoft partner](https://partnercenter.microsoft.com/en-us/pcv/search), you can connect a variety of Office 365 applications including Skype for Business Online in the cloud to your network and real-time voice and video communications capabilities for Skype for Business require network services must be specifically configured to support these Office 365 real-time workloads.</span></span> <span data-ttu-id="3d1de-125">这包括有足够的带宽来携带的通信所需的卷，并能够支持用户的服务质量 (QoS) 用于提供业务类经验的网络。</span><span class="sxs-lookup"><span data-stu-id="3d1de-125">This includes a network that has sufficient bandwidth to carry the required volume of traffic and be capable of supporting Quality of Service (QoS) to deliver a business class experience for your users.</span></span>
  
<span data-ttu-id="3d1de-126">除了本文档中提供的信息，还有其他资源可以帮助你成功规划和部署 Skype for Business Online 服务与功能以及确保你的网络服务满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="3d1de-126">Along with the information here, there are other resources that can help you successfully plan and deploy Skype for Business Online services and features and to ensure that your network services meet those requirements:</span></span>
  
- [<span data-ttu-id="3d1de-127">使用 ExpressRoute 的呼叫流</span><span class="sxs-lookup"><span data-stu-id="3d1de-127">Call flow using ExpressRoute</span></span>](call-flow-using-expressroute.md)
    
- [<span data-ttu-id="3d1de-128">Skype for Business Online 中的 ExpressRoute 和 QoS</span><span class="sxs-lookup"><span data-stu-id="3d1de-128">ExpressRoute and QoS in Skype for Business Online</span></span>](expressroute-and-qos-in-skype-for-business-online.md)
    
- [<span data-ttu-id="3d1de-129">Skype for Business Online 中的媒体质量和网络连接性能</span><span class="sxs-lookup"><span data-stu-id="3d1de-129">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](media-quality-and-network-connectivity-performance.md)
    
## <a name="implement-quality-of-service-qos-for-skype-for-business"></a><span data-ttu-id="3d1de-130">为 Skype for Business 实施服务质量 (QoS)</span><span class="sxs-lookup"><span data-stu-id="3d1de-130">Implement Quality of Service (QoS) for Skype for Business</span></span>

<span data-ttu-id="3d1de-p105">在进入 Skype for Business Online 之前，应当了解一下你的网络处理音频、视频和分享会话流量的容量。正如其他 Office 365 服务一样，可从 Microsoft 下载 [Skype for Business 带宽计算器](https://www.microsoft.com/en-us/download/details.aspx?id=19011)，该计算器可用于确定每个公司站点所需的网络流量。你应该对使用情况进行建模，包括对实时通信流量媒体流和每个公司位置的 Skype for Business 流量大小进行建模、计算流量以及分析流量对整个网络的影响。完成上述操作后，此数据分析应对可从何处改进网络和队列大小提供建议，以提供卓越的最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="3d1de-p105">Before moving to Skype for Business Online, you should take a look at your network's capacity to handle audio, video and sharing session traffic. As with other Office 365 services, Microsoft has available for download the [Skype for Business Bandwidth Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=19011) that's used to determine the required network traffic for each of your company sites. You should perform usage modeling, including modeling real-time communication traffic media flows and the amount of Skype for Business traffic per company location, calculating traffic volume, and analyzing how that traffic impacts your overall network. After you've done that, analysis of this data should provide recommendations of where your network needs to be improved and recommend queue sizes in order to provide an excellent end user experience.</span></span>
  
<span data-ttu-id="3d1de-p106">Skype for Business 实时流量对于丢包率、延迟和抖动很敏感，而拥堵的网络中经常会发生这些情况。另外，还必须在受管外部 WAN、受管内部 LAN 和基于企业的 WiFi 网络上部署服务质量 (QoS)（有时称为"服务类别"）。这将有助于正确地区分 Skype for Business 实时流量的优先次序，例如音频和视频优先于本地网络上的其他非实时流量并优先于 WAN，从而为最终用户提供更佳的体验。</span><span class="sxs-lookup"><span data-stu-id="3d1de-p106">Skype for Business real-time traffic is sensitive to packet loss, delay and jitter, which occur frequently in congested networks. Quality of Service (QoS) - sometimes called Class of Service - must also be deployed on managed external WANs, managed internal LANs, and enterprise-based WiFi networks. This will help to properly prioritize Skype for Business real-time traffic such as audio and video over other non-real time traffic on local networks and over WAN, creating a better experience for end users.</span></span>
  
<span data-ttu-id="3d1de-138">Skype 业务音频必须部署在 EF （加急转发的 DSCP 46） 队列和 Skype 的视频业务必须部署在 AF41 （保证转发的 DSCP 34） 队列。</span><span class="sxs-lookup"><span data-stu-id="3d1de-138">Skype for Business audio must be deployed in the EF (Expedited Forwarding - DSCP 46) queue and Skype for Business video must be deployed in the AF41 (Assured Forwarding - DSCP 34) queue.</span></span> <span data-ttu-id="3d1de-139">这是也适用对等和会议通信，而不管是否正在部署 Office 365 中的电话系统或其他电话功能。</span><span class="sxs-lookup"><span data-stu-id="3d1de-139">This is true even for peer-to-peer and conferencing traffic, regardless of whether Phone System in Office 365 or other telephony features are being deployed.</span></span>
  
<span data-ttu-id="3d1de-p108">用户可能已在 LAN 和 WAN 上针对其他 IP 电话产品妥善部署现有 QoS 策略，但是 Skype for Business 允许用户在使用该服务的同时进行移动，即从一个位置移动到另一个位置。因此，必须在 LAN、WAN 和无线网络上标记 QoS 策略，以确保在所有受管网络上区分所有 Skype for Business 流量的优先次序。</span><span class="sxs-lookup"><span data-stu-id="3d1de-p108">While existing QoS policies might be in place already on the LAN and WAN for other IP telephony products, Skype for Business allows users to be mobile and to move from location to location while using the service. Because of this, QoS policies must be marked on the LAN, WAN and wireless networks in order to be sure that all Skype for Business traffic is being prioritized across managed networks.</span></span>
  
<span data-ttu-id="3d1de-142">为帮助确定网络大小，请下载 [Skype for Business 带宽计算器](https://www.microsoft.com/en-us/download/details.aspx?id=19011)。</span><span class="sxs-lookup"><span data-stu-id="3d1de-142">To help you will sizing your network, download the [Skype for Business Bandwidth Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=19011).</span></span>
  
<span data-ttu-id="3d1de-143">有关媒体质量和 QoS 的详细信息，请参阅 [Skype for Business Online 中的媒体质量和网络连接性能](media-quality-and-network-connectivity-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="3d1de-143">For more about media quality and QoS, see [Media Quality and Network Connectivity Performance in Skype for Business Online](media-quality-and-network-connectivity-performance.md).</span></span>
  
<span data-ttu-id="3d1de-144">有关如何设置和管理 QoS 的详细信息，请参阅[管理高质量的服务](https://technet.microsoft.com/en-us/library/gg425841.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3d1de-144">For more about setting up and managing QoS, see [Managing Quality of Service](https://technet.microsoft.com/en-us/library/gg425841.aspx).</span></span>
  
## <a name="bypass-proxies-and-wan-optimization-devices"></a><span data-ttu-id="3d1de-145">绕过代理和 WAN 优化设备</span><span class="sxs-lookup"><span data-stu-id="3d1de-145">Bypass proxies and WAN optimization devices</span></span>

<span data-ttu-id="3d1de-p109">包括 Skype for Business Online 在内的所有 Office 365 都经过加密，且代理设备通常无法对其进行检查。因此，我们建议，只要你的用户按照定义连接 [Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)，则对所有 Office 365 网络流量绕过代理设备。由于代理设备很可能对实时 Skype for Business Online 媒体流造成延迟，我们强烈建议至少对该流量绕过代理设备。</span><span class="sxs-lookup"><span data-stu-id="3d1de-p109">All Office 365 including Skype for Business Online is encrypted and is typically not able to be inspected by proxy devices. For these reasons we recommend bypassing proxy devices for all Office 365 network traffic as defined as connections your users make to [Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). Since proxy devices will likely introduce delay in real-time Skype for Business Online media streams we strongly recommend bypassing proxy devices at a minimum for that traffic.</span></span>
  
<span data-ttu-id="3d1de-149">Microsoft 建议使用 PAC 文件将 Office 365 流量发送到防火墙，以排除 Office 365 URL。</span><span class="sxs-lookup"><span data-stu-id="3d1de-149">Microsoft recommends excluding Office 365 URLs using PAC files to send Office 365 traffic to a firewall.</span></span>
  
<span data-ttu-id="3d1de-150">下面的资源可能也对你有帮助：</span><span class="sxs-lookup"><span data-stu-id="3d1de-150">Here are some available resources that can help too:</span></span>
  
- [<span data-ttu-id="3d1de-151">使用基线和性能历史记录优化 Office 365 性能</span><span class="sxs-lookup"><span data-stu-id="3d1de-151">Office 365 performance tuning using baselines and performance history</span></span>](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)
    
- [<span data-ttu-id="3d1de-152">针对Office 365 执行网络和迁移规划</span><span class="sxs-lookup"><span data-stu-id="3d1de-152">Network and migration planning for Office 365</span></span>](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)
    
- [<span data-ttu-id="3d1de-153">Office 365 代理 Pac 生成器</span><span class="sxs-lookup"><span data-stu-id="3d1de-153">Office 365 Proxy Pac generator</span></span>](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)
    
- [<span data-ttu-id="3d1de-154">将 WAN 优化控制器或流量/检查设备与 Office 365 配合使用</span><span class="sxs-lookup"><span data-stu-id="3d1de-154">Using WAN Optimization Controller or Traffic/Inspection devices with Office 365</span></span>](https://aka.ms/kb2690045)
    
- [<span data-ttu-id="3d1de-155">使用适用于 Office 365 的 ExpressRoute 进行路由</span><span class="sxs-lookup"><span data-stu-id="3d1de-155">Routing with ExpressRoute for Office 365</span></span>](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)
    
## <a name="bypass-double-encryption"></a><span data-ttu-id="3d1de-156">绕过双重加密</span><span class="sxs-lookup"><span data-stu-id="3d1de-156">Bypass double encryption</span></span>

<span data-ttu-id="3d1de-p110">要向用户提供最佳的音频和视频体验，必须实施可阻止 Skype for Business 媒体（音频和视频）遍历虚拟专用网络 (VPN) 隧道的解决方案。所有 Skype for Business 流量均使用传输层安全性 (TLS) 加密，媒体工作负载则使用安全实时协议 (SRTP) 加密。信号使用 TLS 加密，媒体工作负载使用 SRTP 加密。通过 VPN 隧道发送此流量将在客户端与 Office 365 之间增加一个额外的加密层和额外的网络跃点，这二者会增加抖动、丢包率和延迟，可能会导致会话降级。</span><span class="sxs-lookup"><span data-stu-id="3d1de-p110">To provide users the best possible audio and video experience, you must implement a solution that prevents Skype for Business media (audio and video) from traversing a Virtual Private Network (VPN) tunnel. All Skype for Business traffic is encrypted with Transport Layer Security (TLS) and the media workloads are encrypted with Secure Real Time Protocol (SRTP). Signaling is encrypted with TLS and the media workloads are encrypted with SRTP. Sending this traffic over the VPN tunnel adds an extra layer of encryption, and additional network hops between the client and Office 365, both of which can result in a degraded session because it increases jitter, packet loss and latency.</span></span>
  
<span data-ttu-id="3d1de-p111">阻止 Skype for Business 流量遍历 VPN 隧道的一个选项是"拆分隧道"。要实施拆分隧道，客户应当咨询其 VPN 供应商，了解在其软件中执行此操作的具体信息。</span><span class="sxs-lookup"><span data-stu-id="3d1de-p111">One option to prevent Skype for Business traffic from traversing the VPN tunnel is Split Tunneling. To implement split-tunneling, customers should consult with their VPN vendor on the specifics of how to do this in their software.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3d1de-163">[!注释] 此选项仅对 Skype for Business 媒体工作负载为所需，对其他 Office 365 服务不适用。</span><span class="sxs-lookup"><span data-stu-id="3d1de-163">This is only required for the Skype for Business media workloads and isn't applicable to other Office 365 services.</span></span> 
  
<span data-ttu-id="3d1de-164">其他资源：</span><span class="sxs-lookup"><span data-stu-id="3d1de-164">Additional resources:</span></span>
  
- [<span data-ttu-id="3d1de-165">使 Lync 媒体绕过 VPN 隧道</span><span class="sxs-lookup"><span data-stu-id="3d1de-165">Enabling Lync Media to Bypass a VPN Tunnel</span></span>](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)
    
- [<span data-ttu-id="3d1de-166">有关直接访问、拆分隧道和强制隧道的更多信息</span><span class="sxs-lookup"><span data-stu-id="3d1de-166">More on Direct Access, Split Tunneling and Force Tunneling</span></span>](https://blogs.technet.com/b/tomshinder/archive/2010/03/30/more-on-directaccess-split-tunneling-and-force-tunneling.aspx)
    
- [<span data-ttu-id="3d1de-167">启用直接访问</span><span class="sxs-lookup"><span data-stu-id="3d1de-167">Enable Direct Access</span></span>](https://technet.microsoft.com/en-us/library/jj574163.aspx)
    
## <a name="ensure-the-right-ports-and-protocols-are-open"></a><span data-ttu-id="3d1de-168">确保打开正确的端口和协议</span><span class="sxs-lookup"><span data-stu-id="3d1de-168">Ensure the right ports and protocols are open</span></span>

<span data-ttu-id="3d1de-p112">客户必须确保 O365 服务所需的 URL 和 IP 地址可访问。有关 Skype for Business Online 的所有 IP 地址和 URL 的完整列表，请参阅 [Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。</span><span class="sxs-lookup"><span data-stu-id="3d1de-p112">Customers must ensure reachability of the URLs and IP addresses that are required for the O365 service. For a complete listing of all IP addresses and URLs for Skype for Business Online, see [Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span>
  
<span data-ttu-id="3d1de-p113">Skype for Business 客户端使用多个端口和协议。根据交互类型（对等与多方）和内容共享与语音/视频的使用，Skype for Business 会话网络流量的方向和流将发生变化。你必须查看并打开端口和协议列表，并且要特别注意源和目标端口。例如，音频流量在客户端仅有 20 个端口 (50000-50019 TCP/UDP) 可供使用，但目标端口可能是服务端 10,000 个端口 (50000-59999 TCP/UDP) 中的任意一个。这还包括防火墙上打开的 TCP 443 和 UDP 3478。</span><span class="sxs-lookup"><span data-stu-id="3d1de-p113">Skype for Business clients use a variety of ports and protocols. The direction and flow of network traffic for a Skype for Business session will vary depending on the type of interactions (peer-to-peer vs multiparty) and depending on the use of content sharing and voice/video. You must review and open the list of ports and protocols, paying special attention to the source and destination ports. For example, audio traffic uses just 20 ports (50000-50019 TCP/UDP) at the client side, but the destination port could be anywhere in a 10K port range (50000-59999 TCP/UDP) at the service side. This also includes opening TCP 443 and UDP 3478 on the firewall.</span></span>
  
<span data-ttu-id="3d1de-176">可能还需要其他网络配置来支持 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="3d1de-176">Additional network configuration might also be required to support Skype for Business Online.</span></span>
  
  
## <a name="use-phones-and-devices-optimized-for-skype-for-business"></a><span data-ttu-id="3d1de-177">使用针对 Skype for Business 优化的电话和设备</span><span class="sxs-lookup"><span data-stu-id="3d1de-177">Use Phones and Devices Optimized for Skype for Business</span></span>

<span data-ttu-id="3d1de-178">在实时媒体会话中，所使用的耳机和摄像头等所有参与者的媒体设备有整体的音频和视频质量很大的影响。</span><span class="sxs-lookup"><span data-stu-id="3d1de-178">In a real-time media session, media devices that are used by all participants such as headsets and web cams have a great impact on the overall audio and video quality.</span></span> <span data-ttu-id="3d1de-179">低质量的设备或具有不正确的设备驱动程序的设备将会产生的视频音频和较低的图像质量整体声音品质较低。</span><span class="sxs-lookup"><span data-stu-id="3d1de-179">Lower-quality devices or devices with incorrect device drivers will produce lower overall sound quality for audio and lower image quality for video.</span></span> <span data-ttu-id="3d1de-180">认证的设备的好质量，另一方面，帮助回声抵消、 噪音过滤、 视频分辨率，并减少延迟。</span><span class="sxs-lookup"><span data-stu-id="3d1de-180">Certified devices or good quality devices, on the other hand, help with echo cancellation, noise filtering, video resolution and reduce latency.</span></span>
  
<span data-ttu-id="3d1de-p115">不同的电话和设备，会给最终用户带来迥然不同的音频和视频质量。Skype for Business 认证计划是"Lync 兼容"计划的演变，可以验证设备是否满足 Microsoft 的音频和视频标准。Microsoft 已经测试多个 IP 电话、USB 音频和视频设备、电脑和会议室设备并将其认定为合格。你应当查看针对 Skype for Business 优化的设备的列表，并提供不同的设备来满足组织中最终用户的不同需求和个人偏好。</span><span class="sxs-lookup"><span data-stu-id="3d1de-p115">Phones and devices make a huge difference in the quality of audio and video for end users. The Skype for Business certification program is an evolution of the "Lync Compatible" program and validates that the device meets Microsoft standards for audio and video. There are a number of IP Phones, USB audio and video devices, PCs and meeting room devices that have been tested and qualified by Microsoft. You should review the list of devices that are optimized for Skype for Business, and work to provide different devices in order to meet the various needs and personal preferences of your end users in your organization.</span></span>
  
<span data-ttu-id="3d1de-185">有关受支持和经过认证的设备的详细信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="3d1de-185">See the following for more information on supported and certified devices:</span></span>  
  
- [<span data-ttu-id="3d1de-186">获取适用于 Skype for Business Online 的电话</span><span class="sxs-lookup"><span data-stu-id="3d1de-186">Getting phones for Skype for Business Online</span></span>](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)
    
- [<span data-ttu-id="3d1de-187">Skype for Business 电话和设备</span><span class="sxs-lookup"><span data-stu-id="3d1de-187">Phones and Devices for Skype for Business</span></span>](https://technet.microsoft.com/en-us/office/dn947482.aspx)
    
- [<span data-ttu-id="3d1de-188">针对个人外围设备的解决方案目录</span><span class="sxs-lookup"><span data-stu-id="3d1de-188">Solutions Catalog for Personal Peripherals</span></span>](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)
    
- [<span data-ttu-id="3d1de-189">针对 Microsoft Lync 的合格电话和设备</span><span class="sxs-lookup"><span data-stu-id="3d1de-189">Phones and devices qualified for Microsoft Lync</span></span>](https://technet.microsoft.com/en-us/office/dn788944.aspx)
    
<span data-ttu-id="3d1de-p116">用户会面及使用音频和视频设备的环境及周边区域是另一个影响音频和视频质量的重要因素。用户在嘈杂的环境中通话会产生回声和含混不清的音频。用户在黑暗或低光照环境中则无法生成明亮清晰的视频图像画质。在会议室设置中，麦克风和视频设备的位置对参与者接收的声音和图像质量有直接影响。</span><span class="sxs-lookup"><span data-stu-id="3d1de-p116">The environment and surrounding area where users are meeting and using audio and video devices is another big factor for audio and video quality. Users calling from a noisy environment will have echoed, muffled and unclear audio. Users in a dark or low light environment won't be able to produce bright, clear image quality for video. In a conference room setting, the location of the microphone and video device have a direct impact on the sound and image quality that participants will receive.</span></span>
  
<span data-ttu-id="3d1de-194">能够清楚地了解用户的音频和视频体验使用 Skype 为业务应用程序**工具** > **选项** > **音频设备**或**视频设备**中使用的设备中进行更改和自定义的设置。</span><span class="sxs-lookup"><span data-stu-id="3d1de-194">To get a clearer picture of a user's audio and video experience use the Skype for Business app **Tools** > **Options** > **Audio Device** or **Video Device** to make changes to the device in use and customize it's settings.</span></span> <span data-ttu-id="3d1de-195">您还可以通过单击**检查调用质量**检查呼叫的音频质量。</span><span class="sxs-lookup"><span data-stu-id="3d1de-195">You can also check the audio quality of a call by clicking **Check Call Quality**.</span></span> <span data-ttu-id="3d1de-196">如果单击**检查调用质量**时，它们能够报告的质量和测试调用与发现的问题。</span><span class="sxs-lookup"><span data-stu-id="3d1de-196">If they click **Check Call Quality**, they can then report the quality and issues found with the test call.</span></span>
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
## <a name="related-topics"></a><span data-ttu-id="3d1de-198">相关主题</span><span class="sxs-lookup"><span data-stu-id="3d1de-198">Related topics</span></span> 

[<span data-ttu-id="3d1de-199">Skype for Business Online 中的 ExpressRoute 和 QoS</span><span class="sxs-lookup"><span data-stu-id="3d1de-199">ExpressRoute and QoS in Skype for Business Online</span></span>](expressroute-and-qos-in-skype-for-business-online.md)
  

