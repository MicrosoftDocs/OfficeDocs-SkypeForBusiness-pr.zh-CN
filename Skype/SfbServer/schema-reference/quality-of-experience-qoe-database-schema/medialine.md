---
title: MediaLine 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: MediaLine 视图存储有关数据库中每个媒体行的信息。 一个音频会话通常包含一个音频媒体行。 一个音频和视频（A/V）会话通常包含一个音频媒体线和一个视频媒体行;但是，如果使用了会议设备或使用了库视图，则会话可能包含两个视频媒体线。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: b22408ddc40f1df6452895327e8a67800ef24eb9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41808190"
---
# <a name="medialine-view"></a>MediaLine 视图
 
MediaLine 视图存储有关数据库中每个媒体行的信息。 一个音频会话通常包含一个音频媒体行。 一个音频和视频（A/V）会话通常包含一个音频媒体线和一个视频媒体行;但是，如果使用了会议设备或使用了库视图，则会话可能包含两个视频媒体线。 此视图已在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**更多信息**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|SessionSeq  <br/> |int  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |有关在呼叫者的位标志中描述的交互式连接建立（ICE）流程的信息。 有关详细信息，请参阅体验质量监视服务器协议规范。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |有关被调用方的位标志中所述的交互式连接建立（ICE）流程的信息。 有关详细信息，请参阅体验质量监视服务器协议规范。  <br/> |
|安全性  <br/> |tinyint  <br/> |安全配置文件正在使用。 0为 NONE，1为 SRTP，2为 V1。  <br/> |
|Transport  <br/> |tinyint  <br/> |传输类型。 0是 UDP，1是 TCP。  <br/> |
|CallerIPAddr  <br/> |var （50）  <br/> |呼叫方的 IP 地址。 这可以是 IPv4 地址或 IPv6 地址。  <br/> |
|CallerPort  <br/> |int  <br/> |呼叫方使用的端口。  <br/> |
|CallerInside  <br/> |bit  <br/> |指示呼叫者是否在组织网络内。 1表示呼叫方位于企业网络内。 0表示呼叫方位于网络外部。  <br/> |
|CallerMacAddress  <br/> |varchar （256）  <br/> |呼叫方使用的网络接口的 MAC 地址。  <br/> |
|CallerRelayIPAddr  <br/> |var （50）  <br/> |呼叫方使用的 A/V 边缘服务的 IP 地址。 有关详细信息，请参阅[IPAddress 表](ipaddress.md)。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |由呼叫方使用的 A/V 边缘服务使用的端口。  <br/> |
|CallerReflexiveIPAddr  <br/> |var （50）  <br/> |由 A/V 边缘服务报告的呼叫者的 IP 地址。 如果客户端位于 NAT 后面，则该地址可能与 CallerIPAddr 不同，例如。  <br/> |
|CallerCaptureDev  <br/> |varchar （256）  <br/> |呼叫方的捕获设备名称。  <br/> |
|CallerRenderDev  <br/> |varchar （256）  <br/> |调用方的呈现设备名称。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar （256）  <br/> |呼叫方的捕获设备驱动程序名称。  <br/> |
|CallerRenderDevDriver  <br/> |varchar （256）  <br/> |呼叫方的呈现设备驱动程序名称。  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar （256  <br/> |呼叫方的 Wifi 驱动程序说明。  <br/> |
|CallerWifiDriverVersion  <br/> |varchar （256）  <br/> |呼叫方的 Wifi 驱动程序版本。  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar （256）  <br/> |呼叫方网络连接的详细信息。 有关详细信息，请参阅[NetworkConnectionDetail 表](networkconnectiondetail.md)。 <br/> |
|CallerBssid  <br/> |varchar （256）  <br/> |呼叫方 WiFi 连接使用的基本服务设置标识符。  <br/> |
|CallerVPN  <br/> |bit  <br/> |指示呼叫者是否通过虚拟专用网络连接。 1是虚拟专用网络（VPN），0是非 VPN。  <br/> |
|CalleeIPAddr  <br/> |var （50）  <br/> |被呼叫方的 IP 地址。 这可以是 IPv4 地址或 IPv6 地址。  <br/> |
|CalleePort  <br/> |int  <br/> |被呼叫方使用的端口。  <br/> |
|CalleeInside  <br/> |bit  <br/> |指示被调用方是否位于企业网络内。 1表示被呼叫方位于企业网络内，0表示被呼叫方位于网络外部。  <br/> |
|CalleeMacAddress  <br/> |varchar （256）  <br/> |被呼叫方使用的网络接口的 MAC 地址。  <br/> |
|CalleeRelayIPAddr  <br/> |var （50）  <br/> |被呼叫方使用的 A/V 边缘服务的 IP 地址。 有关详细信息，请参阅[IPAddress 表](ipaddress.md)。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |用于由被呼叫方使用的 A/V 边缘服务的端口。  <br/> |
|CalleeReflexiveIPAddr  <br/> |var （50）  <br/> |由 A/V 边缘服务报告的被呼叫方的 IP 地址。 如果客户端位于 NAT 后面，则该地址可能与 CalleeIPAddr 不同，例如。  <br/> |
|CalleeCaptureDev  <br/> |var （50）  <br/> |被调用方的捕获设备名称。  <br/> |
|CalleeRenderDev  <br/> |varchar （256）  <br/> |被调用方的呈现设备名称。  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar （256）  <br/> |被调用方的捕获设备驱动程序名称。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar （256）  <br/> |被调用方的呈现设备驱动程序名称。  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar （256）  <br/> |被呼叫方的 Wifi 驱动程序说明。  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar （256  <br/> |被呼叫方的 Wifi 驱动程序版本。  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar （256）  <br/> |被呼叫方的网络连接的详细信息。 有关详细信息，请参阅[NetworkConnectionDetail 表](networkconnectiondetail.md)。 <br/> |
|CalleeBssid  <br/> |varchar （256）  <br/> |被呼叫方的 WiFi 连接使用的基本服务设置标识符。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |指示被调用方是否通过虚拟专用网络进行连接。 1是虚拟专用网络（VPN），0是非 VPN。  <br/> |
|ConversationalMOS  <br/> |十进制（3，2）  <br/> |音频会话的 Narrowband 对话 MOS （基于两个音频流）。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |这是在给定各种策略设置（TURN、API、SDP、策略服务器等）上应用到给定发送端流的实际带宽。 不要将这一点与有效的带宽混淆，因为它可以根据带宽估计值降低较低的有效带宽。 这基本上是发送流可以通过带宽估计限制限制的最大带宽。  <br/> |
|AppliedBandwidthSource  <br/> |varchar （256）  <br/> |所强加带宽上限的来源。 它介绍带宽限制的来源（例如，"策略服务器"、"转换服务器" 或 "模态"）。  <br/> |
|呼叫者  <br/> |bit  <br/> |指示是否收到来自呼叫方的指标;1为 "是"，0为 "否"。  <br/> |
|被叫方  <br/> |bit  <br/> |指示是否收到来自呼叫接收器的指标;1为 "是"，0为 "否"。  <br/> |
|MidCallReport  <br/> |bit  <br/> |指示报表是用于部分通话还是完整通话。  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |指示呼叫是否分类为差通话（1）或正常呼叫（0）。  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |指示呼叫者是否使用 ICE 协议（Internet 连接建立）连接到网络。  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |指示用户是否使用 ICE 协议（Internet 连接建立）连接到网络。  <br/> |
   

