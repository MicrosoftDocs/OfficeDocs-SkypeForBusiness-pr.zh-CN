---
title: Lync Server 2013：定义企业语音要求
TOCTitle: 定义组织的企业语音要求
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425826(v=OCS.15)
ms:contentKeyID: 49312433
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中定义企业语音要求

 

_**上一次修改主题：** 2012-08-07_

本主题概述了有关拓扑中的区域、站点和站点之间的链接方面需要了解的注意事项以及这些事项在部署 企业语音时的重要性。有关帮助您做出这些决策的详细信息，请参阅规划文档中的 [Lync Server 2013 中高级企业语音功能的网络设置](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)。

## 站点和区域

首先，确定在拓扑中要部署 企业语音的站点以及这些站点所属的网络区域。特别是，考虑如何将公用电话交换网 (PSTN) 连接到每个站点。由于可管理性和物流方面的原因，这些站点所属的区域可能是一个决定性因素。决定本地部署网关的位置、部署 Survivable Branch Appliance (SBA) 以及可将 SIP 中继（本地或位于中央站点）配置为 Internet 电话服务提供商 (ITSP) 的位置。

## 站点之间的网络链路

您还需要考虑预期在 中央站点及其 分支站点之间的网络链路上使用的带宽量。如果需要或计划部署站点之间的可恢复 WAN 链路，我们建议您在每个 分支站点上部署网关，以便为这些站点的用户提供本地外线直拨分机 (DID) 终端。如果具有可恢复 WAN 链路，但 WAN 链路上的带宽可能被限定，则需要为该链路配置呼叫允许控制。如果没有可恢复 WAN 链路，在 分支站点上承载的用户数量少于 1000，并且没有训练有素的本地 Lync Server 管理员可用，则建议您在 分支站点上部署 Survivable Branch Appliance。如果在 分支站点上承载 1000 到 5000 个用户，并缺少可恢复 WAN 连接，但具有训练有素的 Lync Server 管理员可用，则建议您在 分支站点上部署具有小型网关的 Survivable Branch Server。如果具有支持媒体旁路功能的对等网关，则也可以考虑在限定链路上启用媒体旁路功能。

## 另请参阅

#### 概念

[Lync Server 2013 中高级企业语音功能的网络设置](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)

