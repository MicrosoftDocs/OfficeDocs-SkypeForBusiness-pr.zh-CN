---
title: MediaLine 视图
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: 媒体行视图存储有关数据库中每个媒体行的信息。 一个音频会话通常包含一个音频媒体行。 一个音频与视频 (A/V) 会话通常包含一个音频媒体行和一个视频媒体行；但是，如果使用了会议设备或库视图，则会话可能包含两个视频媒体行。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: c31fe1c5b8f6ed97d49c695986ad14fd890ae26f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802742"
---
# <a name="medialine-view"></a>MediaLine 视图
 
媒体行视图存储有关数据库中每个媒体行的信息。 一个音频会话通常包含一个音频媒体行。 一个音频与视频 (A/V) 会话通常包含一个音频媒体行和一个视频媒体行；但是，如果使用了会议设备或库视图，则会话可能包含两个视频媒体行。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**details**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|SessionSeq  <br/> |int  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |关于呼叫者的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |关于被叫方的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。  <br/> |
|安全性  <br/> |tinyint  <br/> |正在使用的安全配置文件。0 为无，1 为 SRTP，2 为 V1。  <br/> |
|Transport  <br/> |tinyint  <br/> |传输类型。0 为 UDP，1 为 TCP。  <br/> |
|CallerIPAddr  <br/> |var (50)   <br/> |呼叫者的 IP 地址。可为 IPv4 或 IPv6 地址。  <br/> |
|CallerPort  <br/> |int  <br/> |呼叫者使用的端口。  <br/> |
|CallerInside  <br/> |bit  <br/> |指示呼叫者是否在组织网络内。1 表示呼叫者在企业网络内。0 表示呼叫者在网络外。  <br/> |
|CallerMacAddress  <br/> |varchar (256)   <br/> |呼叫者使用的网络接口的 MAC 地址。  <br/> |
|CallerRelayIPAddr  <br/> |var (50)   <br/> |呼叫者所使用的 A/V 边缘服务的 IP 地址。 有关详细信息， [请参阅 IPAddress](ipaddress.md) 表。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |呼叫者在 A/V 边缘服务中使用的端口。  <br/> |
|CallerReiveiveIPAddr  <br/> |var (50)   <br/> |A/V 边缘服务报告的呼叫者的 IP 地址。 如果客户端位于 NAT 之后，则此地址可能与 CallerIPAddr 不同。  <br/> |
|CallerCaptureDev  <br/> |varchar (256)   <br/> |呼叫者的捕获设备名称。  <br/> |
|CallerRenderDev  <br/> |varchar (256)   <br/> |呼叫者的呈现设备名称。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)   <br/> |呼叫者的捕获设备驱动程序名称。  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)   <br/> |呼叫者的呈现设备驱动程序名称。  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar (256  <br/> |呼叫者的 Wifi 驱动程序说明。  <br/> |
|CallerWifiDriverVersion  <br/> |varchar (256)   <br/> |呼叫者的 Wifi 驱动程序版本。  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar (256)   <br/> |呼叫者的网络连接的详细信息。 有关详细信息， [请参阅 NetworkConnectionDetail](networkconnectiondetail.md) 表。 <br/> |
|CallerBssid  <br/> |varchar (256)   <br/> |呼叫者 WiFi 连接使用的基本服务集标识符。  <br/> |
|CallerVPN  <br/> |bit  <br/> |指示呼叫者是否通过虚拟专用网连接。1 是虚拟专用网 (VPN)，0 是非 VPN。  <br/> |
|CalleeIPAddr  <br/> |var (50)   <br/> |被叫方的 IP 地址。 可为 IPv4 或 IPv6 地址。  <br/> |
|CalleePort  <br/> |int  <br/> |被叫方所使用的端口。  <br/> |
|CalleeInside  <br/> |bit  <br/> |指示被叫方是否在企业网络内。1 表示被叫方在企业网络内，0 表示被叫方在该网络外。  <br/> |
|CalleeMacAddress  <br/> |varchar (256)   <br/> |被叫方使用的网络接口的 MAC 地址。  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)   <br/> |被叫方使用的 A/V 边缘服务的 IP 地址。 有关详细信息， [请参阅 IPAddress](ipaddress.md) 表。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |被叫方在 A/V 边缘服务中使用的端口。  <br/> |
|CalleeReiveiveIPAddr  <br/> |var (50)   <br/> |A/V 边缘服务报告的被叫方 IP 地址。 如果客户端位于 NAT 之后，则此地址可能与 CalleeIPAddr 不同。  <br/> |
|CalleeCaptureDev  <br/> |var (50)   <br/> |被叫方捕获设备名称。  <br/> |
|CalleeRenderDev  <br/> |varchar (256)   <br/> |被叫方呈现设备名称。  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar (256)   <br/> |被叫方捕获设备驱动程序名称。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)   <br/> |被叫方呈现设备驱动程序名称。  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar (256)   <br/> |被叫方 Wifi 驱动程序说明。  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar (256  <br/> |被叫方 Wifi 驱动程序版本。  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar (256)   <br/> |被叫方网络连接的详细信息。 有关详细信息， [请参阅 NetworkConnectionDetail](networkconnectiondetail.md) 表。 <br/> |
|CalleeBssid  <br/> |varchar (256)   <br/> |被叫方 WiFi 连接使用的基本服务集标识符。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |指示被叫方是否通过虚拟专用网连接。1 是虚拟专用网 (VPN)，0 是非 VPN。  <br/> |
|ConversationalMOS  <br/> |decimal (3，2)   <br/> |音频会话的窄带交谈 MOS（基于两个音频流）。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |这是应用于指定发送端流指定的多种策略设置（TURN、API、SDP、策略服务器等）的实际带宽。不应将其与有效带宽混淆，因为根据带宽预估的不同，有效带宽可能会减少。这基本上是发送流可禁止带宽预估设定的限制的最大带宽。  <br/> |
|AppliedBandwidthSource  <br/> |varchar (256)   <br/> |所设定的带宽限制的来源。 它描述带宽限制来自何处 (例如，"Policy Server"、"TURN Server"或"Modality") 。  <br/> |
|Caller  <br/> |bit  <br/> |指示是否已收到来自呼叫者的度量；1 为是，0 为否。  <br/> |
|被叫方  <br/> |bit  <br/> |指示是否已收到来自呼叫接收者的度量；1 为是，0 为否。  <br/> |
|MidCallReport  <br/> |bit  <br/> |指示报告用于呼叫的一部分还是用于整个呼叫。  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |指示呼叫被分类为质量欠佳的呼叫 (1) 还是质量良好的呼叫 (0)。  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |指示呼叫者是否使用 ICE 协议（Internet 连接建立）连接至网络。  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |指示被呼叫的用户是否使用 ICE 协议（Internet 连接建立）连接至网络。  <br/> |
   

