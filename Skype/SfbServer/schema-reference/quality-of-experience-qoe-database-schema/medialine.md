---
title: MediaLine 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: MediaLine 视图在数据库中存储有关每个媒体行的信息。 一个音频会话通常包含音频媒体一行。 一个音频和视频 (A / V) 会话通常包含音频媒体一行和视频媒体一行;但是，会话可能包含两个视频媒体行如果使用电话会议设备，或使用图片库视图。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 11905ae9ccc67bb166702f4d43f19d1b52bfbe7b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="medialine-view"></a>MediaLine 视图
 
MediaLine 视图在数据库中存储有关每个媒体行的信息。 一个音频会话通常包含音频媒体一行。 一个音频和视频 (A / V) 会话通常包含音频媒体一行和视频媒体一行;但是，会话可能包含两个视频媒体行如果使用电话会议设备，或使用图片库视图。 在 Microsoft Lync Server 2013 引入了此视图。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|SessionSeq  <br/> |int  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |交互式连接建立 (ICE) 过程中介绍有关信息位标志的调用方。 有关详细信息，请参阅质量的体验监视服务器协议规范。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |有关交互式连接建立 (ICE) 过程的信息所述位标志的被调用方。 有关详细信息，请参阅质量的体验监视服务器协议规范。  <br/> |
|安全性  <br/> |tinyint  <br/> |使用中的安全配置文件。 0 表示无、 1 是 srtp 结合、 2 是 V1。  <br/> |
|Transport  <br/> |tinyint  <br/> |传输类型。 0 是 UDP，1 是 TCP。  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |调用方的 IP 地址。 这可能是 IPv4 或 IPv6 地址。  <br/> |
|CallerPort  <br/> |int  <br/> |呼叫者使用的端口。  <br/> |
|CallerInside  <br/> |bit  <br/> |指示调用方在组织网络中。 1 表示调用方位于企业网络。 0 表示调用方是网络之外。  <br/> |
|CallerMacAddress  <br/> |varchar(256)  <br/> |由调用方使用的网络接口的 MAC 地址。  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |IP 地址的 A / V 边缘服务由调用方。 [Ip 地址表](ipaddress.md)的详细信息，请参阅。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |端口用于 A / V 边缘服务由调用方。  <br/> |
|CallerReflexiveIPAddr  <br/> |var(50)  <br/> |调用方的 IP 地址所报告的 A / V 边缘服务。 此地址可能会不同，如果客户端位于 NAT 背后，例如 CallerIPAddr。  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |调用方的捕获设备名称。  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |调用方的呈现的设备名称。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |调用方的捕获设备驱动程序的名称。  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |调用方的呈现的设备驱动程序的名称。  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar (256  <br/> |调用方的 Wifi 驱动程序说明。  <br/> |
|CallerWifiDriverVersion  <br/> |varchar(256)  <br/> |调用方的 Wifi 的驱动程序版本。  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |呼叫者的网络连接的详细信息。 [NetworkConnectionDetail 表](networkconnectiondetail.md)的详细信息，请参阅。 <br/> |
|CallerBssid  <br/> |varchar(256)  <br/> |基本服务集标识符调用方 WiFi 连接使用。  <br/> |
|CallerVPN  <br/> |bit  <br/> |指示调用方是否通过虚拟专用网络连接。 1 为虚拟专用网络 (VPN)，0 为非 VPN。  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |被调用方的 IP 地址。 这可能是 IPv4 或 IPv6 地址。  <br/> |
|CalleePort  <br/> |int  <br/> |被调用方所使用的端口。  <br/> |
|CalleeInside  <br/> |bit  <br/> |指示被调用方是否在企业网络中。 1 表示被调用方位于企业网络，0 表示被调用方位于外部网络。  <br/> |
|CalleeMacAddress  <br/> |varchar(256)  <br/> |由被调用方使用的网络接口的 MAC 地址。  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |IP 地址的 A / V 边缘服务由被调用方。 [Ip 地址表](ipaddress.md)的详细信息，请参阅。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |端口用于 A / V 边缘服务由被调用方。  <br/> |
|CalleeReflexiveIPAddr  <br/> |var(50)  <br/> |被调用方的 IP 地址所报告的 A / V 边缘服务。 此地址可能会不同，如果客户端位于 NAT 背后，例如 CalleeIPAddr。  <br/> |
|CalleeCaptureDev  <br/> |var(50)  <br/> |被调用方的捕获设备名称。  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |被调用方的呈现的设备名称。  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |被调用方的捕获设备驱动程序的名称。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |被调用方的呈现的设备驱动程序的名称。  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar(256)  <br/> |被调用方的 Wifi 驱动程序说明。  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar (256  <br/> |被调用方的 Wifi 的驱动程序版本。  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |被调用方的网络连接的详细信息。 [NetworkConnectionDetail 表](networkconnectiondetail.md)的详细信息，请参阅。 <br/> |
|CalleeBssid  <br/> |varchar(256)  <br/> |基本服务集标识符由被调用方的 WiFi 连接。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |指示被调用方是否通过虚拟专用网络连接。 1 为虚拟专用网络 (VPN)，0 为非 VPN。  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |窄带的口语 MOS （根据这两个音频流） 中的音频会话。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |这是实际的带宽应用到给定的发送端流给出各种策略设置 （启用，API，SDP、 策略服务器，等等。）。 这不应因为可以有较低的有效带宽基于带宽估计的有效带宽相混淆。 这基本上是发送流可以采取除非限制规定的带宽估计的最大带宽。  <br/> |
|AppliedBandwidthSource  <br/> |varchar(256)  <br/> |被强加带宽上限的来源。 它描述了带宽限制来自何处 （例如，"策略服务器"、"关闭服务器"或"成像设备"）。  <br/> |
|呼叫者  <br/> |bit  <br/> |指示是否已接收到从调用方的指标;1 为是，0 表示没有。  <br/> |
|被叫方  <br/> |bit  <br/> |指示是否已收到调用接收器的指标;1 为是，0 表示没有。  <br/> |
|MidCallReport  <br/> |bit  <br/> |表明报告是否为调用的部分或完整的调用。  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |指示调用是否被划分为差致电 (1) 或作为很好的呼叫 (0)。  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |指示调用方是否连接到网络使用冰协议 （Internet 连接建立）。  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |指示用户是否调用与使用冰协议 （Internet 连接建立） 的网络连接。  <br/> |
   

