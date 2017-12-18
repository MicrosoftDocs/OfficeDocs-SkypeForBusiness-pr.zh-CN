---
title: "为 Skype for Business Online 优化网络"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
description: "以下要求是真正重要，以确保长期运行状况和成功的所有 Skype for Business Online 设置为您的组织的功能。我们知道您一些非常技术-此文档仅供您，但是也存在一些您不。如果您需要帮助设置 Skype for Business Online，应阅读本文以熟悉需要考虑的事项。它还提供事项谈论当您正在使用Microsoft FastTrack 中心、 您的 Microsoft 服务和帐户团队，或与Microsoft 合作伙伴算出您可以满足这些要求。"
---

# 为 Skype for Business Online 优化网络

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
以下要求是真正重要，以确保长期运行状况和成功的所有 Skype for Business Online 设置为您的组织的功能。我们知道您一些非常技术-此文档仅供您，但是也存在一些您不。如果您需要帮助设置 Skype for Business Online，应阅读本文以熟悉需要考虑的事项。它还提供事项谈论当您正在使用[Microsoft FastTrack 中心](https://fasttrack.microsoft.com/office)、 您的 Microsoft 服务和帐户团队，或与[Microsoft 合作伙伴](https://partnercenter.microsoft.com/en-us/pcv/search)算出您可以满足这些要求。
  
## 简要概述

Skype for Business 让你可与公司内或全球的同事或业务合作伙伴保持联系。
  
使用 Skype for Business，你可以：
  
- 通过即时消息、语音或视频呼叫开始交谈。
    
- 查看你的联系人何时在线且有空、何时在开会或演示。
    
- 为会议设置强大的安全性。
    
- 在线向大量受众广播。
    
- 会议期间展示你的屏幕或将控制权交给其他人。
    
- 在其他 Office 程序中使用 Skype for Business，只需单击一下，即可开始聊天、呼叫或加入会议。
    
## 为什么这一点如此重要？

通过 IP 的实时媒体（音频、视频和应用程序共享）的质量很大程度上受端到端网络连接质量的影响。为获得最佳的 Skype for Business Online 媒体质量，确保公司网络与 Skype for Business Online 之间的高质量连接很重要。实现这一目标的最佳做法是基于网络容量设置内部网络和云连接，以便所有连接都可以承受 Skype for Business Online 的高峰流量。
  
使用[Microsoft 合作伙伴](https://partnercenter.microsoft.com/en-us/pcv/search)，您可以连接到各种包括 Skype for Business Online 云中到您的网络和实时语音和视频通信功能的 Skype for Office 365 应用程序业务要求网络服务必须专门配置为支持这些 Office 365 实时工作负荷。这其中包括具有足够带宽来执行所需的卷的通信和将能够为用户支持服务质量 (QoS) 可以提供的业务类体验的网络。
  
除了本文档中提供的信息，还有其他资源可以帮助你成功规划和部署 Skype for Business Online 服务与功能以及确保你的网络服务满足以下要求：
  
- [使用 ExpressRoute 的呼叫流](call-flow-using-expressroute.md)
    
- [Skype for Business Online 中的 ExpressRoute 和 QoS](expressroute-and-qos-in-skype-for-business-online.md)
    
- [Skype for Business Online 中的媒体质量和网络连接性能](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md)
    
## 为 Skype for Business 实施服务质量 (QoS)

移动到 Skype for Business Online 之前应采取查看您的网络容量来处理音频、 视频和共享会话流量。根据 Microsoft 具有与其他 Office 365 服务，可供下载[Skype for Business 带宽计算器](https://www.microsoft.com/en-us/download/details.aspx?id=19011)用于确定每个公司网站所需的网络流量。计算流量卷和分析该流量如何影响您的总体网络，您应执行用法建模，包括建模实时通信通信媒体流和量 Skype for Business 流量每个公司位置。您所做的之后，此数据分析应提供您的网络需要改进和建议队列大小为了提供出色的最终用户体验的建议。
  
Skype for Business 中的实时通信是对数据包丢失、 延迟和抖动，这经常出现在拥挤敏感。此外必须上托管的外部 Wan、 托管的内部 Lan 和企业基于 WiFi 网络部署服务 (QoS)-有时也称为类服务的质量。这将有助于正确确定其优先顺序 Skype for Business 实时通信，例如音频和视频对本地网络上的其他非实时通信和个 WAN，为最终用户创建更好的体验。
  
必须在 （加速转发-DSCP 46） EF 部署 Skype for Business 音频必须在 AF41 部署队列和 Skype for Business 视频 （保证转发-DSCP 34） 队列。此条件成立甚至用于对等通信和会议通信，无论是否正在部署 Office 365 中的电话系统或其他电话功能。
  
现有 QoS 策略可能在已在 LAN 和 WAN 上的其他 IP 电话产品的位置，同时 Skype for Business 允许用户为移动，然后使用该服务时移从一个位置到另一个位置。因此，QoS 策略必须 LAN、 WAN 和无线网络上标记以确保所有 Skype for Business 流量正在划分都优先级跨托管网络。
  
为帮助确定网络大小，请下载 [Skype for Business 带宽计算器](https://www.microsoft.com/en-us/download/details.aspx?id=19011)。
  
有关媒体质量和 QoS 的详细信息，请参阅 [Skype for Business Online 中的媒体质量和网络连接性能](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md)。
  
有关设置和管理 QoS 详细信息，请参阅[管理的服务的质量](https://technet.microsoft.com/en-us/library/gg425841.aspx)。
  
## 绕过代理和 WAN 优化设备

所有 Office 365 包括 Skype for Business Online 均已加密，通常不能够检查代理设备。因此，我们建议绕过代理的所有 Office 365 网络流量作为连接到[Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)使您的用户定义的设备。由于代理设备可能会引入实时 Skype for Business Online 媒体流中的延迟，强烈建议绕过代理设备至少为该通信。
  
Microsoft 建议使用 PAC 文件将 Office 365 流量发送到防火墙，以排除 Office 365 URL。
  
下面的资源可能也对你有帮助：
  
- [使用基线和性能历史记录优化 Office 365 性能](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)
    
- [针对Office 365 执行网络和迁移规划](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)
    
- [Office 365 代理 Pac 生成器](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)
    
- [将 WAN 优化控制器或流量/检查设备与 Office 365 配合使用](https://aka.ms/kb2690045)
    
- [使用适用于 Office 365 的 ExpressRoute 进行路由](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)
    
## 绕过双重加密

若要为用户提供最佳可能音频和视频体验，必须实现阻止遍历的虚拟专用网络 (VPN) 隧道 Skype for Business 媒体 （音频和视频） 的解决方案。传输层安全性 (TLS) 加密所有 Skype for Business 流量和媒体工作负载都加密安全实时协议 (SRTP)。信号使用 TLS 加密，并使用 SRTP 加密媒体工作负载。发送此流量通过 VPN 隧道添加额外的加密和客户端与 Office 365 之间的其他网络跃点，这两个可能会导致降级会话因为它会增加抖动、 数据包丢失和延迟。
  
若要防止 Skype for Business 流量遍历 VPN 隧道的一种方法是拆分隧道。若要实现拆分隧道，客户应咨询如何执行此操作在其软件的具体他们 VPN 供应商。
  
> [!NOTE]
> 此选项仅对 Skype for Business 媒体工作负载为所需，对其他 Office 365 服务不适用。 
  
其他资源：
  
- [使 Lync 媒体绕过 VPN 隧道](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)
    
- [有关直接访问、拆分隧道和强制隧道的更多信息](https://blogs.technet.com/b/tomshinder/archive/2010/03/30/more-on-directaccess-split-tunneling-and-force-tunneling.aspx)
    
- [启用直接访问](https://technet.microsoft.com/en-us/library/jj574163.aspx)
    
## 确保打开正确的端口和协议

客户必须确保 O365 服务所需的 URL 和 IP 地址可访问。有关 Skype for Business Online 的所有 IP 地址和 URL 的完整列表，请参阅 [Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。
  
Skype for Business 客户端使用多个端口和协议。根据交互类型（对等与多方）和内容共享与语音/视频的使用，Skype for Business 会话网络流量的方向和流将发生变化。你必须查看并打开端口和协议列表，并且要特别注意源和目标端口。例如，音频流量在客户端仅有 20 个端口 (50000-50019 TCP/UDP) 可供使用，但目标端口可能是服务端 10,000 个端口 (50000-59999 TCP/UDP) 中的任意一个。这还包括防火墙上打开的 TCP 443 和 UDP 3478。
  
可能还需要其他网络配置来支持 Skype for Business Online。
  
你可以从客户端计算机运行 FastTrack Cloudapp 测试，以确认设置正确：
  
- **北美：**
    
  - [Office 365 Fast Track Network Analysis（北美）](http://na1-fasttrack.cloudapp.net/)
    
  - [https://137.117.72.96](https://137.117.72.96)
    
- **欧洲、中东和非洲 (EMEA)：**
    
  - [Office 365 Fast Track Network Analysis (EMEA)](http://em1-fasttrack.cloudapp.net/)
    
  - [https://137.116.212.202](https://137.116.212.202)
    
- **亚太地区：**
    
  - [Office 365 Fast Track Network Analysis（亚太地区）](http://ap1-fasttrack.cloudapp.net)
    
  - [https://168.63.169.67](https://168.63.169.67)
    
您还可以查看，[设置 Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## 使用针对 Skype for Business 优化的电话和设备

在实时媒体会话中，所有参与者使用的耳机、网络摄像头等媒体设备都对音频和视频的整体质量有很大影响。低品质设备和错误的设备驱动程序会降低整体的音频声音质量和视频图像质量。另一方面，经认证的设备或高品质设备有助于消除回声、过滤噪音、提高视频分辨率并减少延迟。
  
电话和设备的最终用户进行音频和视频的质量庞大之差。Skype for Business 认证计划是演变"Lync 兼容"程序和验证设备满足 Microsoft 标准的音频和视频。有许多 IP 电话、 USB 音频和视频设备、 的 Pc 和会议已测试和由 Microsoft 限定聊天室设备。您应在您的组织中查看为 Skype for Business 和工作以满足不同需要提供不同的设备进行了优化的设备的列表和最终用户的个人首选项。
  
有关受支持和经过认证的设备的详细信息，请参阅以下内容：
  
- [获取适用于 Skype for Business Online 的电话](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)
    
- [Skype for Business 电话和设备](https://technet.microsoft.com/en-us/office/dn947482.aspx)
    
- [针对个人外围设备的解决方案目录](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)
    
- [针对 Microsoft Lync 的合格电话和设备](https://technet.microsoft.com/en-us/office/dn788944.aspx)
    
用户会面及使用音频和视频设备的环境及周边区域是另一个影响音频和视频质量的重要因素。用户在嘈杂的环境中通话会产生回声和含混不清的音频。用户在黑暗或低光照环境中则无法生成明亮清晰的视频图像画质。在会议室设置中，麦克风和视频设备的位置对参与者接收的声音和图像质量有直接影响。
  
若要获取清楚地了解用户的音频和视频体验使用 Skype for Business 应用 **工具**> **选项**> **音频设备**或 **视频设备**以更改中使用的设备和自定义的设置。您也可以通过单击 **检查呼叫质量**检查呼叫的音频质量。如果单击 **检查呼叫质量**时，他们可以然后报告的质量和测试呼叫发现问题。
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
## 相关主题

[Skype for Business Online 中的 ExpressRoute 和 QoS](expressroute-and-qos-in-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

