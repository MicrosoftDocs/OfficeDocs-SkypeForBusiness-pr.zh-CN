---
title: Lync Server 2013：规划媒体旁路
TOCTitle: 规划媒体旁路
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398703(v=OCS.15)
ms:contentKeyID: 49313532
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中规划媒体旁路

 

_**上一次修改主题：** 2012-09-21_

媒体旁路功能是指在可能的情况下，从信号遍历中介服务器的呼叫的媒体路径中删除中介服务器。

媒体旁路功能可通过减少延迟、不必要的转换、可能的数据包丢失和潜在的故障点数来提高语音质量。由于绕过的呼叫无需媒体处理操作，这可减少中介服务器上的负载，从而提高可伸缩性。负载的减少补充了 中介服务器控制多个网关的能力。

当没有 中介服务器的分支站点通过一个或多个具有限定带宽的 WAN 链路连接到中央站点时，媒体旁路功能允许来自分支站点上的客户端的媒体直接流到其本地网关，而无需首先通过 WAN 链路流到中央站点上的 中介服务器再流回，从而降低了带宽要求。

由于无需 中介服务器处理媒体，媒体旁路功能还可以减少 企业语音基础结构所需要的 中介服务器数。

下图显示了具有和没有媒体旁路功能的拓扑中的基本媒体和信号路径。

**具有和没有媒体旁路功能的媒体和信号路径**

![语音 CAC 媒体绕过连接强制实施](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "语音 CAC 媒体绕过连接强制实施")

一般而言，应尽可能启用媒体旁路。

## 本部分内容

  - [Lync Server 2013 中的媒体旁路概述](lync-server-2013-overview-of-media-bypass.md)

  - [Lync Server 2013 中的媒体绕过模式](lync-server-2013-media-bypass-modes.md)

  - [Lync Server 2013 中的媒体绕过和呼叫允许控制](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Lync Server 2013 中媒体旁路的技术要求](lync-server-2013-technical-requirements-for-media-bypass.md)

## 相关部分

[在 Lync Server 2013 中部署高级企业语音功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

## 另请参阅

#### 任务

[在 Lync Server 2013 中配置带媒体旁路的中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)  

#### 概念

[全局媒体绕过选项](lync-server-2013-global-media-bypass-options.md)

