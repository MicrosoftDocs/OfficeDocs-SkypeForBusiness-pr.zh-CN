---
title: MediaLine 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: 每个记录表示媒体一行。 （通常一个音频会话包含音频媒体一行。 一个音频和视频 (A / V) 会话通常包含音频媒体一行和视频媒体一行，虽然该会话可能包含两个视频媒体行如果使用电话会议设备，或使用图片库视图。
ms.openlocfilehash: 03da40b97c6a067f13a9855cd51b1bbb4780f2ad
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="medialine-table"></a>MediaLine 表
 
每个记录表示媒体一行。 （通常一个音频会话包含音频媒体一行。 一个音频和视频 (A / V) 会话通常包含音频媒体一行和视频媒体一行，虽然该会话可能包含两个视频媒体行如果使用电话会议设备，或使用图片库视图。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |从[会话表](session.md)引用。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |从[会话表](session.md)引用。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |0 是主要的音频，1 是主视频，2 是全景视频，3 是应用程序/桌面共享。 此标签在一个会话中必须是唯一的。  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |此列是存在，但不是用于 Microsoft Lync Server 2013。 CallerConnectivityICE 和 CalleeConnectivityICE 列中捕获有关媒体行所使用的连接的信息。  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |述位标志的交互式连接建立 (ICE) 进程的信息。 有关详细信息，请参阅*质量的体验监视服务器协议规范*，可供下载。 <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |同为 CallerIceWarningFlags，但在被调用方。 有关详细信息，请参阅*质量的体验监视服务器协议规范*，可供下载。 <br/> |
|**安全** <br/> |tinyint  <br/> | <br/> |使用安全配置文件。 0 表示无、 1 是 srtp 结合、 2 是 V1。  <br/> |
|**运输** <br/> |tinyint  <br/> | <br/> |0 是 UDP，1 是 TCP。  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |外  <br/> |调用方的 IP 地址。 [Ip 地址表](ipaddress.md)的详细信息，请参阅。 <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | 呼叫者使用的端口。 <br/> |
|**CallerSubnet** <br/> |int  <br/> | 外 <br/> |调用方的子网。 [Ip 地址表](ipaddress.md)的详细信息，请参阅。 <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 表示调用方位于企业网络，0 表示调用方是网络之外。  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |外  <br/> |调用方的 mac 地址，从[MacAddress 表](macaddress.md)引用。  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |外  <br/> |IP 地址的 A / V 边缘服务由调用方。 [Ip 地址表](ipaddress.md)的详细信息，请参阅。 <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |端口用于 A / V 边缘服务调用方。  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |外  <br/> |捕获设备由调用方。 从[设备表](device.md)引用。  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |外  <br/> |导致调用方所使用的设备。 从[设备表](device.md)引用。  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |外  <br/> |用于从[DeviceDriver 表](devicedriver.md)中引用的调用方的捕获设备驱动程序。  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |外  <br/> |设备驱动程序调用方的呈现，从[DeviceDriver 表](devicedriver.md)引用。  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |外  <br/> |指示调用方的连接到网络。 从[NetworkConnectionDetail 表](networkconnectiondetail.md)获取值。 典型值为 0 表示有线连接 1 WiFi 连接;和 3 个以太网连接。  <br/> |
|**CallerBssid** <br/> |int  <br/> |外  <br/> |如果使用无线，则调用方的 BSSID。 从[MacAddress 表](macaddress.md)引用。  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||调用方的链接。 1 为虚拟专用网络 (VPN)，0 为非 VPN。  <br/> |
|**CallerLinkSpeed** <br/> |decimal(18,0)  <br/> ||网络链接速度，以 bps，为调用方的端点。  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |外  <br/> |调用接收方的 IP 地址。 [Ip 地址表](ipaddress.md)的详细信息，请参阅。 <br/> |
|**CalleePort** <br/> |bit  <br/> ||通过调用接收器使用的端口。  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |外  <br/> |被调用方的子网。 [Ip 地址表](ipaddress.md)的详细信息，请参阅。 <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 表示调用接收器位于企业网络，0 表示调用接收器是网络之外。  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |外  <br/> |被调用方的 Mac 地址。 从[MacAddress 表](macaddress.md)引用。  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |外  <br/> |IP 地址的 A / V 边缘服务由调用接收器。 [Ip 地址表](ipaddress.md)的详细信息，请参阅。 <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |端口用于 A / V 边缘服务的调用接收器。  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |外  <br/> |捕获设备由调用接收器。 从[设备表](device.md)引用。  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |外  <br/> |导致调用接收器所使用的设备。 从[设备表](device.md)引用。  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |外  <br/> |用于调用接收器捕获设备驱动程序。 从[DeviceDriver 表](devicedriver.md)引用。  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar(256)  <br/> |外  <br/> |用于调用接收器的呈现的设备驱动程序。 从[DeviceDriver 表](devicedriver.md)引用。  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |外  <br/> |指示被调用方的连接到网络。 从[NetworkConnectionDetail 表](networkconnectiondetail.md)获取值。 典型值为 0 表示有线连接 1 WiFi 连接;和 3 个以太网连接。  <br/> |
|**CalleeBssid** <br/> |int  <br/> |外  <br/> |如果使用无线，则被调用方的 BSSID。 从[MacAddress 表](macaddress.md)引用。  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |调用接收方的链接;1 为虚拟专用网络 (VPN)，0 为非 VPN。  <br/> |
|**CalleeLinkSpeed** <br/> |decimal(18,0)  <br/> | <br/> |网络链接速度，以 bps，调用接收器的终结点。  <br/> |
|**ConversationalMOS** <br/> |decimal(3,2)  <br/> | <br/> |窄带的口语 MOS （根据这两个音频流） 中的音频会话。  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||这是实际的带宽应用到给定的发送端流给出各种策略设置 （启用、 API、 SDP、 策略服务器等等）。 这并不是因为可以有较低的有效带宽基于带宽估计能有效带宽与混淆。 这基本上是发送流可以采取除非限制规定的带宽估计的最大带宽。  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||这是被强加的带宽帽的来源。 它描述了其中的带宽限制来自 （"策略服务器"、"关闭服务器"、"成像设备"，等等）。 从[AppliedBandwidthSource 表](appliedbandwidthsource.md)引用。  <br/> |
|**呼叫者** <br/> |bit  <br/> | <br/> |指示是否已接收到从调用方的指标;1 为是，null 值是没有。  <br/> |
|**被叫方** <br/> |bit  <br/> | <br/> |指示是否已收到调用接收器的指标;1 为是，null 值是没有。  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||表明报告是否为会话的部分或完整会话。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||指示是否调用已划分为较差的调用 （值为 1） 或作为很好的呼叫 (0)。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||指示调用方是否连接到网络使用冰协议 （Internet 连接建立）。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||指示调用方是否连接到网络使用冰协议 （Internet 连接建立）。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |外  <br/> |身发出调用的用户的 IP 地址。 在使用 NAT （网络地址转换） 的单位，自反的 IP 地址是代理服务器的 IP 地址。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |外  <br/> |由发出调用的用户 WiFi 驱动程序的设备说明。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |外  <br/> |由发出调用的用户 WiFi 驱动程序的版本号。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |外  <br/> |接收呼叫的用户的 IP 地址反身。 在使用 NAT （网络地址转换） 的单位，自反的 IP 地址是代理服务器的 IP 地址。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |外  <br/> |所采用的接收呼叫的用户的 WiFi 驱动程序的设备说明。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |外  <br/> |所采用的接收呼叫的用户的 WiFi 驱动程序的版本号。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
   

