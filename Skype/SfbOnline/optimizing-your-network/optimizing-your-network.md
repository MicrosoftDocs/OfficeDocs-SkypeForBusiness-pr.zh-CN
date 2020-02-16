---
title: 优化网络
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: 以下要求非常重要，可以确保你要为组织设置的所有 Skype for Business Online 功能能够长期正常和成功运行。 本文档适合技术专家使用，但是有些用户并非精通技术。 如果你需要 Skype for Business Online 设置方面的帮助，请阅读本文档熟悉你需要考虑的事项。 它还将让你在使用 Microsoft FastTrack 中心、Microsoft 服务和客户团队或 Microsoft 合作伙伴了解如何满足这些要求的情况下进行讨论。
ms.openlocfilehash: 5101b59c4e911f6fbad36ff2c601428a8fa25177
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010945"
---
# <a name="optimizing-your-network-for-skype-for-business-online"></a>为 Skype for Business Online 优化网络

以下要求非常重要，可以确保你要为组织设置的所有 Skype for Business Online 功能能够长期正常和成功运行。 本文档适合技术专家使用，但是有些用户并非精通技术。 如果你需要 Skype for Business Online 设置方面的帮助，请阅读本文档熟悉你需要考虑的事项。 它还将让你在使用[Microsoft FastTrack 中心](https://fasttrack.microsoft.com/office)、Microsoft 服务和客户团队或[microsoft 合作伙伴](https://partnercenter.microsoft.com/pcv/search)了解如何满足这些要求的情况下进行讨论。

## <a name="a-quick-overview"></a>简要概述

Skype for Business 让你可与公司内或全球的同事或业务合作伙伴保持联系。

使用 Skype for Business，你可以：

- 通过即时消息、语音或视频呼叫开始交谈。

- 查看你的联系人何时在线且有空、何时在开会或演示。

- 为会议设置强大的安全性。

- 在线向大量观众广播。

- 会议期间展示你的屏幕或将控制权交给其他人。

- 在其他 Office 程序中使用 Skype for Business，只需单击一下，即可开始聊天、呼叫或加入会议。

## <a name="why-is-this-all-so-important"></a>为什么这一点如此重要？

通过 IP 的实时媒体（音频、视频和应用程序共享）的质量很大程度上受端到端网络连接质量的影响。为获得最佳的 Skype for Business Online 媒体质量，确保公司网络与 Skype for Business Online 之间的高质量连接很重要。实现这一目标的最佳做法是基于网络容量设置内部网络和云连接，以便所有连接都可以承受 Skype for Business Online 的高峰流量。

使用[Microsoft 合作伙伴](https://partnercenter.microsoft.com/pcv/search)，您可以将各种 office 365 应用程序连接到您的网络中，包括 office Online 的 skype For business Online 和 skype for business 的实时语音和视频通信功能。必须专门配置网络服务以支持这些 Office 365 实时工作负荷。 这包括具有足够带宽承载所需的流量并且能够支持服务质量 (QoS) 来为用户提供企业级体验的网络。

除了本文档中提供的信息，还有其他资源可以帮助你成功规划和部署 Skype for Business Online 服务与功能以及确保你的网络服务满足以下要求：

- [使用 ExpressRoute 的呼叫流](call-flow-using-expressroute.md)

- [Skype for Business Online 中的 ExpressRoute 和 QoS](expressroute-and-qos-in-skype-for-business-online.md)

- [Skype for Business Online 中的媒体质量和网络连接性能](media-quality-and-network-connectivity-performance.md)

## <a name="implement-quality-of-service-qos-for-skype-for-business"></a>为 Skype for Business 实施服务质量 (QoS)

在进入 Skype for Business Online 之前，应当了解一下你的网络处理音频、视频和分享会话流量的容量。正如其他 Office 365 服务一样，可从 Microsoft 下载 [Skype for Business 带宽计算器](https://www.microsoft.com/download/details.aspx?id=19011)，该计算器可用于确定每个公司站点所需的网络流量。你应该对使用情况进行建模，包括对实时通信流量媒体流和每个公司位置的 Skype for Business 流量大小进行建模、计算流量以及分析流量对整个网络的影响。完成上述操作后，此数据分析应对可从何处改进网络和队列大小提供建议，以提供卓越的最终用户体验。

Skype for Business 实时流量对于丢包率、延迟和抖动很敏感，而拥堵的网络中经常会发生这些情况。另外，还必须在受管外部 WAN、受管内部 LAN 和基于企业的 WiFi 网络上部署服务质量 (QoS)（有时称为"服务类别"）。这将有助于正确地区分 Skype for Business 实时流量的优先次序，例如音频和视频优先于本地网络上的其他非实时流量并优先于 WAN，从而为最终用户提供更佳的体验。

Skype for Business 音频必须在 EF（加速转发 - DSCP 46）队列中部署，而 Skype for Business 视频则必须在 AF41（确保转发 - DSCP 34）队列中部署。 这也适用于对等和会议流量，无论是否正在部署 Office 365 中的电话系统或其他电话功能。

用户可能已在 LAN 和 WAN 上针对其他 IP 电话产品妥善部署现有 QoS 策略，但是 Skype for Business 允许用户在使用该服务的同时进行移动，即从一个位置移动到另一个位置。因此，必须在 LAN、WAN 和无线网络上标记 QoS 策略，以确保在所有受管网络上区分所有 Skype for Business 流量的优先次序。

为帮助确定网络大小，请下载 [Skype for Business 带宽计算器](https://www.microsoft.com/download/details.aspx?id=19011)。

有关媒体质量和 QoS 的详细信息，请参阅 [Skype for Business Online 中的媒体质量和网络连接性能](media-quality-and-network-connectivity-performance.md)。

有关设置和管理 QoS 的详细信息，请参阅[管理服务质量](https://technet.microsoft.com/library/gg425841.aspx)。

## <a name="bypass-proxies-and-wan-optimization-devices"></a>绕过代理和 WAN 优化设备

包括 Skype for Business Online 在内的所有 Office 365 都经过加密，且代理设备通常无法对其进行检查。因此，我们建议，只要你的用户按照定义连接 [Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)，则对所有 Office 365 网络流量绕过代理设备。由于代理设备很可能对实时 Skype for Business Online 媒体流造成延迟，我们强烈建议至少对该流量绕过代理设备。

Microsoft 建议使用 PAC 文件将 Office 365 流量发送到防火墙，以排除 Office 365 URL。

下面的资源可能也对你有帮助：

- [使用基线和性能历史记录优化 Office 365 性能](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)

- [针对Office 365 执行网络和迁移规划](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)

- [Office 365 代理 Pac 生成器](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)

- [将 WAN 优化控制器或流量/检查设备与 Office 365 配合使用](https://aka.ms/kb2690045)

- [使用适用于 Office 365 的 ExpressRoute 进行路由](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)

## <a name="bypass-double-encryption"></a>绕过双重加密

要向用户提供最佳的音频和视频体验，必须实施可阻止 Skype for Business 媒体（音频和视频）遍历虚拟专用网络 (VPN) 隧道的解决方案。所有 Skype for Business 流量均使用传输层安全性 (TLS) 加密，媒体工作负载则使用安全实时协议 (SRTP) 加密。信号使用 TLS 加密，媒体工作负载使用 SRTP 加密。通过 VPN 隧道发送此流量将在客户端与 Office 365 之间增加一个额外的加密层和额外的网络跃点，这二者会增加抖动、丢包率和延迟，可能会导致会话降级。

阻止 Skype for Business 流量遍历 VPN 隧道的一个选项是"拆分隧道"。要实施拆分隧道，客户应当咨询其 VPN 供应商，了解在其软件中执行此操作的具体信息。

> [!NOTE]
> [!注释] 此选项仅对 Skype for Business 媒体工作负载为所需，对其他 Office 365 服务不适用。

其他资源：

- [使 Lync 媒体绕过 VPN 隧道](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)

- [有关直接访问、拆分隧道和强制隧道的更多信息](https://blogs.technet.com/b/tomshinder/archive/2010/03/30/more-on-directaccess-split-tunneling-and-force-tunneling.aspx)

- [启用直接访问](https://technet.microsoft.com/library/jj574163.aspx)

## <a name="ensure-the-right-ports-and-protocols-are-open"></a>确保打开正确的端口和协议

客户必须确保 O365 服务所需的 URL 和 IP 地址可访问。有关 Skype for Business Online 的所有 IP 地址和 URL 的完整列表，请参阅 [Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。

Skype for Business 客户端使用多个端口和协议。根据交互类型（对等与多方）和内容共享与语音/视频的使用，Skype for Business 会话网络流量的方向和流将发生变化。你必须查看并打开端口和协议列表，并且要特别注意源和目标端口。例如，音频流量在客户端仅有 20 个端口 (50000-50019 TCP/UDP) 可供使用，但目标端口可能是服务端 10,000 个端口 (50000-59999 TCP/UDP) 中的任意一个。这还包括防火墙上打开的 TCP 443 和 UDP 3478。

可能还需要其他网络配置来支持 Skype for Business Online。


## <a name="use-phones-and-devices-optimized-for-skype-for-business"></a>使用针对 Skype for Business 优化的电话和设备

在实时媒体会话中，所有参与者使用的耳机、网络摄像头等媒体设备都对音频和视频的整体质量有很大影响。 具有不正确的设备驱动程序的较低质量的设备或设备将提高音频的整体音质，降低视频的图像质量。 另一方面，经认证的设备或高品质设备有助于消除回声、过滤噪音、提高视频分辨率并减少延迟。

不同的电话和设备，会给最终用户带来迥然不同的音频和视频质量。Skype for Business 认证计划是"Lync 兼容"计划的演变，可以验证设备是否满足 Microsoft 的音频和视频标准。Microsoft 已经测试多个 IP 电话、USB 音频和视频设备、电脑和会议室设备并将其认定为合格。你应当查看针对 Skype for Business 优化的设备的列表，并提供不同的设备来满足组织中最终用户的不同需求和个人偏好。

有关受支持和经过认证的设备的详细信息，请参阅以下内容：  

- [获取适用于 Skype for Business Online 的电话](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)

- [Skype for Business 电话和设备](https://technet.microsoft.com/office/dn947482.aspx)

- [针对个人外围设备的解决方案目录](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

- [针对 Microsoft Lync 的合格电话和设备](https://technet.microsoft.com/office/dn788944.aspx)

用户会面及使用音频和视频设备的环境及周边区域是另一个影响音频和视频质量的重要因素。用户在嘈杂的环境中通话会产生回声和含混不清的音频。用户在黑暗或低光照环境中则无法生成明亮清晰的视频图像画质。在会议室设置中，麦克风和视频设备的位置对参与者接收的声音和图像质量有直接影响。

若要更清楚地了解用户的音频和视频体验，请使用 Skype for business 应用**工具** > **选项** > "**音频设备**" 或 "**视频设备**"，对设备进行更改并对其设置进行自定义。 您也可以通过单击 "**检查呼叫质量**" 来检查通话的音频质量。 If they click **Check Call Quality**, they can then report the quality and issues found with the test call.

![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)

## <a name="related-topics"></a>相关主题

[Skype for Business Online 中的 ExpressRoute 和 QoS](expressroute-and-qos-in-skype-for-business-online.md)
