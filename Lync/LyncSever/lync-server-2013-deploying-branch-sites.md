---
title: Lync Server 2013：部署分支站点
TOCTitle: 部署分支站点
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398217(v=OCS.15)
ms:contentKeyID: 49312092
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中部署分支站点

 

_**上一次修改主题：** 2012-09-21_

分支站点用户从与该分支站点关联的中央站点的服务器获取大部分 Lync Server 2013 功能。每个分支站点都只与一个中央站点关联。要提供来往于公用电话交换网 (PSTN) 的呼叫，分支站点可以包含以下任一项：

  - PSTN 网关和可选的中介服务器

  - SIP 中继

  - 具有专用交换机 (PBX) 的现有语音基础结构

  - Survivable Branch Appliance

  - Survivable Branch Server

广域网或中央站点出现故障时，具有 Survivable Branch Appliance 或 Survivable Branch Server 的分支站点的复原能力比没有这些解决方案的分支站点更强。例如，在部署了 Survivable Branch Appliance 或 Survivable Branch Server 的站点中，如果将分支站点连接到中央站点的网络出现故障，用户仍然可以拨打和接收 PSTN 呼叫。获得分支站点复原能力的另一方法是使用 PSTN 网关或 SIP 中继，同时在分支站点上全面部署 Lync Server。

有关确定适用于组织的分支站点部署的详细信息，包括先决条件和其他规划注意事项，请参阅规划文档中的 [在 Lync Server 2013 中规划 PSTN 连接](lync-server-2013-planning-for-pstn-connectivity.md)和 [在 Lync Server 2013 中规划分支站点语音恢复能力](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。

## 本部分内容

  - [在 Lync Server 2013 中在分支站点提供 PSTN 连接](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

