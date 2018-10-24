---
title: Lync Server 2013：MPLS 网络上的呼叫允许控制
TOCTitle: MPLS 网络上的呼叫允许控制
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398168(v=OCS.15)
ms:contentKeyID: 49311972
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 具有 Lync Server 2013 的 MPLS 网络上的呼叫允许控制

 

_**上一次修改主题：** 2012-09-22_

在多协议标签交换 (MPLS) 网络中，所有站点均以全连通的方式连接。也就是说，所有站点都直接连接到 Internet 服务提供商的 MPLS 主干线，并且每个站点都设置了带宽，以用于通过 WAN 链路连接到 MPLS 云。没有控制 IP 路由的网络集线器或中心站点。下图显示了基于 MPLS 技术的简单网络。

**MPLS 网络示例**

![使用 MPLS 的 CAC](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "使用 MPLS 的 CAC")

要在 MPLS 网络中部署呼叫允许控制 (CAC)，需创建代表 MPLS 云的网络区域，以及代表每个 MPLS 分支站点的网络站点。下图说明如何配置代表上图中的示例 MPLS 网络的网络区域和网络站点。之后，总体带宽限制和带宽会话限制将取决于从每个网络站点连接到代表 MPLS 云的网络区域的 WAN 链路容量。

**MPLS 网络的网络区域和网络站点**

![使用 MPLS 的呼叫允许控制 (CAC) 图](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "使用 MPLS 的呼叫允许控制 (CAC) 图")

