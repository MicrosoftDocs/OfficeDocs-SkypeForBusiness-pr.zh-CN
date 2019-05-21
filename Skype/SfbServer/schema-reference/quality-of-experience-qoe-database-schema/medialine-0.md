---
title: MediaLine 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: 每条记录表示一个媒体行。 (一个音频会话通常包含一个音频媒体行。 一个音频和视频 (A/V) 会话通常包含一个音频媒体线和一个视频媒体行, 但如果使用了会议设备或使用了库视图, 则该会话可能包含两个视频媒体线。
ms.openlocfilehash: f9ededade35e5654a89b68343f44094f4319ae70
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294892"
---
# <a name="medialine-table"></a>MediaLine 表
 
每条记录表示一个媒体行。 (一个音频会话通常包含一个音频媒体行。 一个音频和视频 (A/V) 会话通常包含一个音频媒体线和一个视频媒体行, 但如果使用了会议设备或使用了库视图, 则该会话可能包含两个视频媒体线。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |从[会话表](session.md)中引用。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |从[会话表](session.md)中引用。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |0是主音频, 1 是主视频, 2 是全景视频, 3 是应用程序/桌面共享, 16 是基于视频的屏幕共享 (VbSS)。 此标签在单个会话中必须是唯一的。  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |此列存在, 但未在 Microsoft Lync Server 2013 中使用。 在 "CallerConnectivityICE" 和 "CalleeConnectivityICE" 列中捕获有关用于媒体行的连接的信息。  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |有关在 bits 标志中描述的交互式连接建立 (ICE) 流程的信息。 有关详细信息, 请参阅可供下载的*体验质量监视服务器协议规范*。 <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |与 CallerIceWarningFlags 相同, 但在被调用方。 有关详细信息, 请参阅可供下载的*体验质量监视服务器协议规范*。 <br/> |
|**安全性** <br/> |tinyint  <br/> | <br/> |正在使用的安全配置文件。 0为 NONE, 1 为 SRTP, 2 为 V1。  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |0是 UDP, 1 是 TCP。  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |外表  <br/> |呼叫方的 IP 地址。 有关详细信息, 请参阅[IPAddress 表](ipaddress.md)。 <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | 呼叫方使用的端口。 <br/> |
|**CallerSubnet** <br/> |int  <br/> | 外表 <br/> |呼叫方的子网。 有关详细信息, 请参阅[IPAddress 表](ipaddress.md)。 <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1表示呼叫方位于企业网络内, 0 表示呼叫方位于网络外部。  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |外表  <br/> |呼叫方的 mac 地址, 从[MacAddress 表](macaddress.md)引用。  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |外表  <br/> |呼叫方使用的 A/V 边缘服务的 IP 地址。 有关详细信息, 请参阅[IPAddress 表](ipaddress.md)。 <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |由呼叫者在 A/V 边缘服务上使用的端口。  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |外表  <br/> |由呼叫者使用的捕获设备。 从[设备表](device.md)中引用。  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |外表  <br/> |由呼叫者使用的渲染设备。 从[设备表](device.md)中引用。  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |外表  <br/> |调用方的捕获设备的驱动程序, 从[DeviceDriver 表](devicedriver.md)中引用。  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |外表  <br/> |调用方的呈现设备的驱动程序, 从[DeviceDriver 表](devicedriver.md)中引用。  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |外表  <br/> |指示呼叫者如何连接到网络。 从[NetworkConnectionDetail 表](networkconnectiondetail.md)中获取值。 用于 WiFi 连接的有线连接 "1" 的典型值为 0;对于以太网连接, 请使用3。  <br/> |
|**CallerBssid** <br/> |int  <br/> |外表  <br/> |呼叫者的 BSSID (如果使用无线)。 从[MacAddress 表](macaddress.md)引用。  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||呼叫者的链接。 1是虚拟专用网络 (VPN), 0 是非 VPN。  <br/> |
|**CallerLinkSpeed** <br/> |十进制 (18, 0)  <br/> ||呼叫方终结点的网络链接速度 (以 bps 为的)。  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |外表  <br/> |呼叫接收器的 IP 地址。 有关详细信息, 请参阅[IPAddress 表](ipaddress.md)。 <br/> |
|**CalleePort** <br/> |bit  <br/> ||呼叫接收器使用的端口。  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |外表  <br/> |被调用的子网。 有关详细信息, 请参阅[IPAddress 表](ipaddress.md)。 <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1表示呼叫接收器位于企业网络内, 0 表示呼叫接收器位于网络外部。  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |外表  <br/> |被呼叫方 Mac 地址。 从[MacAddress 表](macaddress.md)中引用。  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |外表  <br/> |呼叫接收器使用的 A/V 边缘服务的 IP 地址。 有关详细信息, 请参阅[IPAddress 表](ipaddress.md)。 <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |由呼叫接收器在 A/V 边缘服务上使用的端口。  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |外表  <br/> |由呼叫接收器使用的捕获设备。 从[设备表](device.md)中引用。  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |外表  <br/> |由呼叫接收器使用的呈现设备。 从[设备表](device.md)中引用。  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |外表  <br/> |呼叫接收器的捕获设备的驱动程序。 从[DeviceDriver 表](devicedriver.md)引用。  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar (256)  <br/> |外表  <br/> |呼叫接收器的呈现设备的驱动程序。 从[DeviceDriver 表](devicedriver.md)引用。  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |外表  <br/> |指明被呼叫方如何连接到网络。 从[NetworkConnectionDetail 表](networkconnectiondetail.md)中获取值。 用于 WiFi 连接的有线连接 "1" 的典型值为 0;对于以太网连接, 请使用3。  <br/> |
|**CalleeBssid** <br/> |int  <br/> |外表  <br/> |如果使用无线, 则被呼叫者的 BSSID。 从[MacAddress 表](macaddress.md)引用。  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |呼叫接收器的链接;1是虚拟专用网络 (VPN), 0 是非 VPN。  <br/> |
|**CalleeLinkSpeed** <br/> |十进制 (18, 0)  <br/> | <br/> |呼叫接收器终结点的网络链接速度 (以 bps 为 bps)。  <br/> |
|**ConversationalMOS** <br/> |十进制 (3, 2)  <br/> | <br/> |音频会话的 Narrowband 对话 MOS (基于两个音频流)。  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||这是在给定各种策略设置 (TURN、API、SDP、策略服务器等) 上应用到给定发送端流的实际带宽。 此操作不会与有效的带宽混淆, 因为根据带宽估计, 可能会有较低的有效带宽。 这基本上是发送流可以通过带宽估计限制限制的最大带宽。  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||这是所强加的带宽上限的来源。 它介绍带宽限制的来源 ("策略服务器"、"打开服务器"、"模态" 等)。 从[AppliedBandwidthSource 表](appliedbandwidthsource.md)中引用。  <br/> |
|**呼叫者** <br/> |bit  <br/> | <br/> |指示是否收到来自呼叫方的指标;1为 "是", null 值为 "否"。  <br/> |
|**被叫方** <br/> |bit  <br/> | <br/> |指示是否收到来自呼叫接收器的指标;1为 "是", null 值为 "否"。  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||指示报表是用于会话的一部分还是整个会话。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||指示呼叫是否分类为不太好的通话 (值为 1) 或正常呼叫 (0)。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||指示呼叫者是否使用 ICE 协议 (Internet 连接建立) 连接到网络。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||指示呼叫者是否使用 ICE 协议 (Internet 连接建立) 连接到网络。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |外表  <br/> |发出呼叫的用户的自身 IP 地址。 在使用 NAT (网络地址转换) 的组织中, 自身 IP 地址是代理服务器的 IP 地址。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |外表  <br/> |发出呼叫的用户所使用的 WiFi 驱动程序的设备说明。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |外表  <br/> |发出呼叫的用户所使用的 WiFi 驱动程序的版本号。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |外表  <br/> |接收呼叫的用户的自身 IP 地址。 在使用 NAT (网络地址转换) 的组织中, 自身 IP 地址是代理服务器的 IP 地址。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |外表  <br/> |接收呼叫的用户所使用的 WiFi 驱动程序的设备说明。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |外表  <br/> |接收呼叫的用户所使用的 WiFi 驱动程序的版本号。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
   

