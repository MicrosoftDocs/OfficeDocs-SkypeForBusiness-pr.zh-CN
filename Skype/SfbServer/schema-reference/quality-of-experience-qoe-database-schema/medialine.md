---
title: MediaLine 视图
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: MediaLine 视图在数据库中存储有关每个媒体行的信息。 一个音频会话通常包含一个音频媒体行。 一个音频和视频 (A / V) 会话通常包含一个音频媒体行和视频媒体一行;但是，会话可能包含两个视频媒体行，如果使用一种会议设备，或使用库视图。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 04037bae4b2f04058667d42205a2e0b33abacb4f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894214"
---
# <a name="medialine-view"></a>MediaLine 视图
 
MediaLine 视图在数据库中存储有关每个媒体行的信息。 一个音频会话通常包含一个音频媒体行。 一个音频和视频 (A / V) 会话通常包含一个音频媒体行和视频媒体一行;但是，会话可能包含两个视频媒体行，如果使用一种会议设备，或使用库视图。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|SessionSeq  <br/> |int  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |有关互动式连接建立 (ICE) 过程中介绍信息位标志为呼叫者。 有关详细信息，请参阅质量的体验监控服务器协议规范。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |有关互动式连接建立 (ICE) 过程的信息中所述位标志为被叫方。 有关详细信息，请参阅质量的体验监控服务器协议规范。  <br/> |
|安全性  <br/> |tinyint  <br/> |正在使用的安全配置文件。 0 为 NONE，1 是 SRTP，2 是 V1。  <br/> |
|Transport  <br/> |tinyint  <br/> |传输类型。 UDP 0，1 是 TCP。  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |呼叫者的 IP 地址。 这可以是 IPv4 或 IPv6 地址。  <br/> |
|CallerPort  <br/> |int  <br/> |呼叫者使用的端口。  <br/> |
|CallerInside  <br/> |bit  <br/> |指示呼叫者位于组织网络内。 1 表示呼叫者位于企业网络内部。 0 表示呼叫者位于网络外部。  <br/> |
|CallerMacAddress  <br/> |varchar(256)  <br/> |呼叫者使用的网络接口的 MAC 地址。  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |IP 地址的 A / V 边缘服务使用的呼叫者。 请参阅[IPAddress 表](ipaddress.md)的详细信息。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |端口在 a / V 边缘服务使用的呼叫者。  <br/> |
|CallerReflexiveIPAddr  <br/> |var(50)  <br/> |呼叫者的 IP 地址报告的 A / V 边缘服务。 此地址可能会有所不同，如果客户端位于 NAT 后面，例如 CallerIPAddr。  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |呼叫者的捕获设备名称。  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |呼叫者呈现设备名称。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |呼叫者的捕获设备驱动程序名称。  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |呼叫者的呈现设备驱动程序名称。  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar (256  <br/> |呼叫者的 Wifi 驱动程序描述。  <br/> |
|CallerWifiDriverVersion  <br/> |varchar(256)  <br/> |呼叫者的 Wifi 驱动程序版本。  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |呼叫者的网络连接的详细信息。 请参阅[NetworkConnectionDetail 表](networkconnectiondetail.md)的详细信息。 <br/> |
|CallerBssid  <br/> |varchar(256)  <br/> |基本服务集标识符呼叫者 WiFi 连接使用。  <br/> |
|CallerVPN  <br/> |bit  <br/> |指示呼叫者是否通过虚拟专用网络连接。 1 是虚拟专用网络 (VPN)，0 为非 VPN。  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |被叫方的 IP 地址。 这可以是 IPv4 或 IPv6 地址。  <br/> |
|CalleePort  <br/> |int  <br/> |被叫方所使用的端口。  <br/> |
|CalleeInside  <br/> |bit  <br/> |指示被叫方是否位于企业网络内部。 1 表示被叫方位于企业网络内部，0 表示被叫方位于网络外部。  <br/> |
|CalleeMacAddress  <br/> |varchar(256)  <br/> |被叫方使用的网络接口的 MAC 地址。  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |IP 地址的 A / V 边缘服务由被叫方。 请参阅[IPAddress 表](ipaddress.md)的详细信息。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |端口在 a / V 边缘服务由被叫方。  <br/> |
|CalleeReflexiveIPAddr  <br/> |var(50)  <br/> |被叫方的 IP 地址报告的 A / V 边缘服务。 此地址可能会有所不同，如果客户端位于 NAT 后面，例如 CalleeIPAddr。  <br/> |
|CalleeCaptureDev  <br/> |var(50)  <br/> |被叫方的捕获设备名称。  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |被叫方的呈现设备名称。  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |被叫方的捕获设备驱动程序名称。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |被叫方的呈现设备驱动程序名称。  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar(256)  <br/> |被叫方的 Wifi 驱动程序描述。  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar (256  <br/> |被叫方的 Wifi 驱动程序版本。  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |被叫方的网络连接的详细信息。 请参阅[NetworkConnectionDetail 表](networkconnectiondetail.md)的详细信息。 <br/> |
|CalleeBssid  <br/> |varchar(256)  <br/> |基本服务集标识符被叫方的 WiFi 连接使用。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |指示被叫方是否通过虚拟专用网络连接。 1 是虚拟专用网络 (VPN)，0 为非 VPN。  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |窄带交谈 MOS （基于两个音频流） 的音频会话。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |这是实际的带宽应用到给定的发送端流给定 （打开，API、 SDP、 策略服务器等。） 的各种策略设置。 这不应与有效带宽混淆，因为可能有基于带宽估计较低的有效带宽。 这是一种基本上发送流花费除非按带宽估计施加限制的最大带宽。  <br/> |
|AppliedBandwidthSource  <br/> |varchar(256)  <br/> |带宽帽正在施加的源。 它介绍了其中的带宽限制来自 （例如，"策略服务器"、"打开服务器"或"形式"）。  <br/> |
|呼叫者  <br/> |bit  <br/> |指示是否已收到来自呼叫者的度量;1 为是，0 为无。  <br/> |
|被叫方  <br/> |bit  <br/> |指示是否已收到来自呼叫接收者的度量;1 为是，0 为无。  <br/> |
|MidCallReport  <br/> |bit  <br/> |指示报表是呼叫的一部分还是用于整个呼叫。  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |指示呼叫是否被分类为质量欠佳呼叫 (1) 还是质量良好的呼叫 (0)。  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |指示呼叫者是否连接到使用 ICE 协议 （Internet 连接建立） 的网络。  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |指示用户是否调用连接到使用 ICE 协议 （Internet 连接建立） 的网络。  <br/> |
   

