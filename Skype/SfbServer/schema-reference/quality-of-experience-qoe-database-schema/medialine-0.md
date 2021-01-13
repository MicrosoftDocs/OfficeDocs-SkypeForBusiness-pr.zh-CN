---
title: MediaLine 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: 每条记录代表一个媒体行。  (一个音频会话通常包含一个音频媒体行。 A/V) 会话的一个音频和视频 (通常包含一个音频媒体行和一个视频媒体行，但如果使用会议设备或使用库视图，该会话可能包含两个视频媒体行。
ms.openlocfilehash: 99a54fe7a4ee4e91506069873c98d423b9069f06
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802762"
---
# <a name="medialine-table"></a>MediaLine 表
 
每条记录代表一个媒体行。  (一个音频会话通常包含一个音频媒体行。 A/V) 会话的一个音频和视频 (通常包含一个音频媒体行和一个视频媒体行，但如果使用会议设备或使用库视图，该会话可能包含两个视频媒体行。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主  <br/> |从会话表 [引用](session.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主  <br/> |从会话表 [引用](session.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |主  <br/> |0 是主音频，1 是主视频，2 是全景视频，3 是应用程序/桌面共享，16 是基于视频的屏幕共享 (VbSS) 。 此标签在单个会话中必须是唯一的。  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |此列存在，但在 Microsoft Lync Server 2013 中未使用。 有关用于媒体线路的连接的信息将捕获到 CallerConnectivityICE 和 CalleeConnectivityICE 列中。  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |有关位标志中描述的 ICE (建立) 连接建立过程的信息。 有关详细信息，请参阅用户体验  *质量监控服务器协议规范*  （可供下载）。 <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |与 CallerIceWarningFlags 相同，但在被叫方端。 有关详细信息，请参阅用户体验  *质量监控服务器协议规范*  （可供下载）。 <br/> |
|**安全性** <br/> |tinyint  <br/> | <br/> |使用的安全配置文件。 0 为无，1 为 SRTP，2 为 V1。  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |0 为 UDP，1 为 TCP。  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Foreign  <br/> |呼叫者的 IP 地址。 有关详细信息， [请参阅 IPAddress](ipaddress.md) 表。 <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | 呼叫者使用的端口。 <br/> |
|**CallerSubnet** <br/> |int  <br/> | Foreign <br/> |呼叫者的子网。 有关详细信息， [请参阅 IPAddress](ipaddress.md) 表。 <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 表示呼叫者位于企业网络内部，0 表示呼叫者位于该网络外部。  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Foreign  <br/> |呼叫者的 mac 地址，从 [MacAddress](macaddress.md)表引用。  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Foreign  <br/> |呼叫者所使用的 A/V 边缘服务的 IP 地址。 有关详细信息， [请参阅 IPAddress](ipaddress.md) 表。 <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |呼叫者在 A/V 边缘服务中使用的端口。  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Foreign  <br/> |捕获调用方使用的设备。 从 Device 表 [引用](device.md)。  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Foreign  <br/> |呈现调用方使用的设备。 从 Device 表 [引用](device.md)。  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Foreign  <br/> |呼叫者的捕获设备的驱动程序，从 [DeviceDriver 表引用](devicedriver.md)。  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Foreign  <br/> |呼叫者的呈现设备的驱动程序，从 [DeviceDriver 表引用](devicedriver.md)。  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |Foreign  <br/> |指示呼叫者如何连接到网络。 值从 [NetworkConnectionDetail 表获取](networkconnectiondetail.md)。 对于 WiFi 连接的有线连接，典型值为 0;3 表示以太网连接。  <br/> |
|**CallerBssid** <br/> |int  <br/> |Foreign  <br/> |呼叫者的 BSSID（如果使用无线）。 从 [MacAddress 表引用](macaddress.md)。  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||呼叫者链接。 1 是虚拟专用网 (VPN)，0 是非 VPN。  <br/> |
|**CallerLinkSpeed** <br/> |decimal (18，0)   <br/> ||呼叫者的终结点的网络链接速度（以 bps 表示）。  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Foreign  <br/> |呼叫接收器的 IP 地址。 有关详细信息， [请参阅 IPAddress](ipaddress.md) 表。 <br/> |
|**CalleePort** <br/> |bit  <br/> ||呼叫接收器使用的端口。  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Foreign  <br/> |被叫方子网。 有关详细信息， [请参阅 IPAddress](ipaddress.md) 表。 <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 表示呼叫接收器位于企业网络内部，0 表示呼叫接收器位于网络外部。  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Foreign  <br/> |被叫方 Mac 地址。 从 [MacAddress 表引用](macaddress.md)。  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Foreign  <br/> |呼叫接收器使用的 A/V 边缘服务的 IP 地址。 有关详细信息， [请参阅 IPAddress](ipaddress.md) 表。 <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |呼叫接收器在 A/V 边缘服务中使用的端口。  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |foreign  <br/> |呼叫接收器使用的捕获设备。 从 Device 表 [引用](device.md)。  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Foreign  <br/> |呈现呼叫接收器使用的设备。 从 Device 表 [引用](device.md)。  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Foreign  <br/> |呼叫接收器的捕获设备的驱动程序。 从 [DeviceDriver 表引用](devicedriver.md)。  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar (256)   <br/> |Foreign  <br/> |呼叫接收器呈现设备的驱动程序。 从 [DeviceDriver 表引用](devicedriver.md)。  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |Foreign  <br/> |指示被叫方如何连接到网络。 值从 [NetworkConnectionDetail 表获取](networkconnectiondetail.md)。 对于 WiFi 连接的有线连接，典型值为 0;3 表示以太网连接。  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Foreign  <br/> |被叫方 BSSID（如果使用无线）。 从 [MacAddress 表引用](macaddress.md)。  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |呼叫接收器的链接;1 是 VPN (VPN) ，0 是非 VPN。  <br/> |
|**CalleeLinkSpeed** <br/> |decimal (18，0)   <br/> | <br/> |呼叫接收器终结点的网络链接速度（以 bps 表示）。  <br/> |
|**ConversationalMOS** <br/> |decimal (3，2)   <br/> | <br/> |音频会话的窄带交谈 MOS（基于两个音频流）。  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||这是应用于给定发送端流的实际带宽，给定了各种策略 (TURN、API、SDP、Policy Server 等) 。 不要将其与有效带宽混淆，因为根据带宽预估的不同，可能会降低带宽的有效性。 这基本上是发送流可禁止带宽预估设定的限制的最大带宽。  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||这是所设定的带宽限制的来源。 它描述带宽限制来自 (策略服务器"、"TURN Server"、"形式"等) 。 从 [AppliedBandwidthSource 表引用](appliedbandwidthsource.md)。  <br/> |
|**Caller** <br/> |bit  <br/> | <br/> |指示是否收到来自调用方的指标;1 是，空值是否。  <br/> |
|**被叫方** <br/> |bit  <br/> | <br/> |指示是否收到来自呼叫接收器的指标;1 是，空值是否。  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||指示报告是用于会话的一部分还是整个会话。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||指示呼叫被分类为质量欠佳的 (值为 1) 或 0 (质量) 。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||指示呼叫者是否使用 ICE 协议（Internet 连接建立）连接至网络。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||指示呼叫者是否使用 ICE 协议（Internet 连接建立）连接至网络。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**CallerReiveiveLocalIPAddr** <br/> |int  <br/> |Foreign  <br/> |拨打呼叫的用户的具有反应性的 IP 地址。 在使用 NAT (网络地址转换) ，响应 IP 地址是代理服务器的 IP 地址。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Foreign  <br/> |拨打呼叫的用户所使用 WiFi 驱动程序的设备说明。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Foreign  <br/> |拨打呼叫的用户所使用 WiFi 驱动程序的版本号。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**CalleReiveiveLocalIPAddr** <br/> |int  <br/> |Foreign  <br/> |收到呼叫的用户的具有反应性的 IP 地址。 在使用 NAT (网络地址转换) ，响应 IP 地址是代理服务器的 IP 地址。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Foreign  <br/> |接收呼叫的用户所使用 WiFi 驱动程序的设备说明。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Foreign  <br/> |接收呼叫的用户所使用 WiFi 驱动程序的版本号。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
   

