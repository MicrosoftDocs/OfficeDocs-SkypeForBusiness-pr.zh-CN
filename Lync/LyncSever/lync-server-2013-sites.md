---
title: Lync Server 2013 网站
TOCTitle: 网站
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398076(v=OCS.15)
ms:contentKeyID: 49311813
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的 Lync Server 网站

 

_**上一次修改主题：** 2012-10-16_

在 Lync Server 中，可以在网络上定义包含 Lync Server 组件的 *站点* 。站点是一组由高速度、低延迟网络（例如，单个局域网 (LAN) 或由高速光纤网络连接的两个网络）完美连接的计算机。请注意， Lync Server 站点的概念不同于 Active Directory 域服务 站点和 Microsoft Exchange Server 站点。 Lync Server 站点不必与 Active Directory 站点对应。

## 站点类型

每个站点可以是至少包含一个 前端池或 Standard Edition Server的 *中央站点* ，也可以是 *分支站点* 。每个分支站点只与一个中央站点相关联，分支站点的用户可以从关联的中央站点的服务器上获取大部分 Lync Server 功能。

每个分支站点包含以下设备之一：

  - 一个 *Survivable Branch Appliance (SBA)* ，这是行业标准的刀片式服务器，其中包含在 Windows Server 上运行的 Lync Server 注册器和中介服务器。 Survivable Branch Appliance 还包含公用电话交换网 (PSTN) 网关。 Survivable Branch Appliance 是为具有 25 至 1000 个用户的分支站点而设计的。

  - 一个 *Survivable Branch Server (SBS)* ，这是运行 Windows Server 的服务器，它满足指定的硬件要求并已安装 Lync Server 注册器和中介服务器软件。它必须连接到 PSTN 网关或电话服务提供商的 SIP 中继。Survivable Branch Server 是为具有 1000 至 5000 个用户的分支站点而设计的。

  - PSTN 网关和可选的 *中介服务器* 。有关此角色和其他服务器角色的详细信息，请参阅 [Lync Server 2013 中的服务器角色](lync-server-2013-server-roles.md)。

具有指向中央站点的可恢复广域网 (WAN) 链接的分支机构可以使用第三个选项，即 PSTN 网关和可选的中介服务器。具有较低复原能力链接的分支机构站点应使用可在广域网出现故障时恢复运行的 Survivable Branch Appliance 或 Survivable Branch Server。例如，在部署了 Survivable Branch Appliance 或 Survivable Branch Server 的站点中，如果将分支站点连接到中央站点的 WAN 出现故障，用户仍然可以拨打和接收企业语音呼叫。有关 Survivable Branch Appliance、Survivable Branch Server 和复原的详细信息，请参阅规划文档中的[在 Lync Server 2013 中规划企业语音恢复能力](lync-server-2013-planning-for-enterprise-voice-resiliency.md)。

## 站点拓扑

部署中必须至少包含一个中央站点，可以包含多个分支站点，也可以不包含分支站点。每个分支站点都与一个中央站点关联。中央站点会为分支站点提供不在分支站点本地承载的 Lync Server 服务，如状态和会议。

如果有多个站点，则可以将不同站点的前端池配对，以实现灾难恢复能力。有关详细信息，请参阅 [Lync Server 2013 中的高可用性和灾难恢复支持](lync-server-2013-high-availability-and-disaster-recovery-support.md)。

## 另请参阅

#### 概念

[Lync Server 2013 中的服务器角色](lync-server-2013-server-roles.md)  
[Lync Server 2013 中的高可用性和灾难恢复支持](lync-server-2013-high-availability-and-disaster-recovery-support.md)  

#### 其他资源

[在 Lync Server 2013 中规划企业语音恢复能力](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

