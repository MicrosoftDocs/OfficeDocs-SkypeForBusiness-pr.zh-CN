---
title: MediaLine 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: 每条记录代表一个媒体行。 （一个音频会话通常包含一个音频媒体行。 一个音频和视频 (A / V) 会话通常包含一个音频媒体行和视频媒体一行，尽管会话可能包含两个视频媒体行，如果使用一种会议设备，或使用库视图。
ms.openlocfilehash: 42c770486c3b2b457e1715dfa5c5a5b028022f26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920143"
---
# <a name="medialine-table"></a>MediaLine 表
 
每条记录代表一个媒体行。 （一个音频会话通常包含一个音频媒体行。 一个音频和视频 (A / V) 会话通常包含一个音频媒体行和视频媒体一行，尽管会话可能包含两个视频媒体行，如果使用一种会议设备，或使用库视图。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |引用自[Session table](session.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |引用自[Session table](session.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |0 是主音频，1 是主视频，并且 2 是全景视频、 3 应用程序/桌面共享，16 是视频基于屏幕共享 (VbSS)。 此标签单个会话中必须是唯一的。  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |此列是存在但未在 Microsoft Lync Server 2013 中使用。 CallerConnectivityICE 和 CalleeConnectivityICE 列捕获有关用于媒体行的连接信息。  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |有关位标志中所述的互动式连接建立 (ICE) 过程的信息。 有关详细信息，请参阅*质量的体验监控服务器协议规范*，可供下载。 <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |相同 CallerIceWarningFlags，但被叫方侧。 有关详细信息，请参阅*质量的体验监控服务器协议规范*，可供下载。 <br/> |
|**安全性** <br/> |tinyint  <br/> | <br/> |使用中的安全配置文件。 0 为 NONE，1 是 SRTP，2 是 V1。  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |UDP 0，1 是 TCP。  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |外  <br/> |呼叫者的 IP 地址。 请参阅[IPAddress 表](ipaddress.md)的详细信息。 <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | 呼叫者使用的端口。 <br/> |
|**CallerSubnet** <br/> |int  <br/> | 外 <br/> |呼叫者的子网。 请参阅[IPAddress 表](ipaddress.md)的详细信息。 <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 表示呼叫者位于企业网络内部，0 表示呼叫者位于网络外部。  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |外  <br/> |呼叫者的 mac 地址，引用[自 MacAddress table](macaddress.md)。  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |外  <br/> |IP 地址的 A / V 边缘服务使用的呼叫者。 请参阅[IPAddress 表](ipaddress.md)的详细信息。 <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |端口在 a / V 边缘服务呼叫者。  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |外  <br/> |捕获呼叫者使用的设备。 从[设备表](device.md)引用。  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |外  <br/> |呈现呼叫者使用的设备。 从[设备表](device.md)引用。  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |外  <br/> |用于引用自[DeviceDriver table](devicedriver.md)的呼叫者的捕获设备驱动程序。  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |外  <br/> |用于引用自[DeviceDriver table](devicedriver.md)的呼叫者的呈现设备驱动程序。  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |外  <br/> |指示呼叫者如何连接到网络。 [NetworkConnectionDetail 表](networkconnectiondetail.md)中获取值。 典型的值为 0 是有线连接 WiFi 连接; 1和以太网连接 3。  <br/> |
|**CallerBssid** <br/> |int  <br/> |外  <br/> |如果使用无线，呼叫者的 BSSID。 引用[自 MacAddress table](macaddress.md)。  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||呼叫者的链接。 1 是虚拟专用网络 (VPN)，0 为非 VPN。  <br/> |
|**CallerLinkSpeed** <br/> |decimal(18,0)  <br/> ||网络链接速度，以 bps，呼叫者的终结点。  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |外  <br/> |呼叫接收者的 IP 地址。 请参阅[IPAddress 表](ipaddress.md)的详细信息。 <br/> |
|**CalleePort** <br/> |bit  <br/> ||呼叫接收者使用的端口。  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |外  <br/> |被叫方的子网。 请参阅[IPAddress 表](ipaddress.md)的详细信息。 <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 表示呼叫接收者位于企业网络内部，0 表示呼叫接收者位于该网络。  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |外  <br/> |被叫方的 Mac 地址。 引用自[MacAddress 表](macaddress.md)。  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |外  <br/> |IP 地址的 A / V 边缘服务使用的呼叫接收者。 请参阅[IPAddress 表](ipaddress.md)的详细信息。 <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |端口在 a / V 边缘服务的呼叫接收者。  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |外  <br/> |捕获呼叫接收者使用的设备。 从[设备表](device.md)引用。  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |外  <br/> |呈现呼叫接收者使用的设备。 从[设备表](device.md)引用。  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |外  <br/> |呼叫接收者的捕获设备驱动程序。 引用自[DeviceDriver table](devicedriver.md)。  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar(256)  <br/> |外  <br/> |呼叫接收者的呈现设备驱动程序。 引用自[DeviceDriver table](devicedriver.md)。  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |外  <br/> |指示被叫方如何连接到网络。 [NetworkConnectionDetail 表](networkconnectiondetail.md)中获取值。 典型的值为 0 是有线连接 WiFi 连接; 1和以太网连接 3。  <br/> |
|**CalleeBssid** <br/> |int  <br/> |外  <br/> |被叫方的 BSSID，如果使用无线。 引用[自 MacAddress table](macaddress.md)。  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |呼叫接收者的链接;1 是虚拟专用网络 (VPN)，0 为非 VPN。  <br/> |
|**CalleeLinkSpeed** <br/> |decimal(18,0)  <br/> | <br/> |网络链接速度，以 bps，呼叫接收者的终结点。  <br/> |
|**ConversationalMOS** <br/> |decimal(3,2)  <br/> | <br/> |窄带交谈 MOS （基于两个音频流） 的音频会话。  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||这是实际的带宽应用到给定的发送端流给定的各种策略设置 （打开、 API、 SDP、 策略服务器等）。 这是不是有效的带宽与混淆，因为可以基于带宽估计较低的有效带宽。 这是一种基本上发送流花费除非按带宽估计施加限制的最大带宽。  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||这是带宽帽正在施加的源。 它介绍了其中的带宽限制来自 （《 策略服务器 》、 《 打开服务器"、"形式"等）。 从[AppliedBandwidthSource 表](appliedbandwidthsource.md)引用。  <br/> |
|**呼叫者** <br/> |bit  <br/> | <br/> |指示是否已收到来自呼叫者的度量;1 为是，null 值为无。  <br/> |
|**被叫方** <br/> |bit  <br/> | <br/> |指示是否已收到来自呼叫接收者的度量;1 为是，null 值为无。  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||指示报告是会话的一部分还是整个会话。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||指示呼叫是否被分类为质量欠佳的呼叫 （值 1） 或质量良好的呼叫 (0)。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||指示呼叫者是否连接到使用 ICE 协议 （Internet 连接建立） 的网络。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||指示呼叫者是否连接到使用 ICE 协议 （Internet 连接建立） 的网络。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |外  <br/> |发出呼叫的用户的身 IP 地址。 在组织中使用 NAT （网络地址转换），身的 IP 地址是代理服务器的 IP 地址。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |外  <br/> |发出呼叫的用户所使用的 WiFi 驱动程序的设备描述。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |外  <br/> |发出呼叫的用户所使用的 WiFi 驱动程序的版本号。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |外  <br/> |接收呼叫的用户的身 IP 地址。 在组织中使用 NAT （网络地址转换），身的 IP 地址是代理服务器的 IP 地址。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |外  <br/> |接收呼叫的用户所使用的 WiFi 驱动程序的设备描述。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |外  <br/> |接收呼叫的用户所使用的 WiFi 驱动程序的版本号。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
   

