---
title: "Lync Server 2013: 部署 Survivable Branch Appliance 或 Server - 中央站点任务"
TOCTitle: 部署 Survivable Branch Appliance 或 Survivable Branch Server - 中央站点任务
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398189(v=OCS.15)
ms:contentKeyID: 49312021
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server - 中央站点任务

 

_**上一次修改主题：** 2012-10-18_

在中央站点完成本节中的任务。如果要部署 Survivable Branch Server，请跳过第一个任务。

> [!IMPORTANT]  
> 执行本节中的任务之前，必须满足以下条件：
> <ul>
> <li><p>必须在中央站点安装 Lync Server。</p></li>
> <li><p>必须将分支站点的安装技术人员添加到 RTCUniversalSBATechnicians 组。</p></li>
> </ul>
> 此外，建议执行以下操作：
> <ul>
> <li><p>在每个分支站点部署 DHCP 服务器，以便客户端能够获取 IP 地址。</p></li>
> <li><p>作为在每个分支站点上部署 DHCP 服务器的替代方案，可以使用 Lync Server 命令行管理程序 cmdlet <strong>Set-CsRegistrarConfiguration –EnableDHCPServer $true</strong> 在 Survivable Branch Appliance 或 Survivable Branch Server 上启用 Lync Server DHCP。有关详细信息，请参阅规划文档中<a href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 的分支站点恢复能力要求</a>的“软硬件要求”部分。</p></li>
> </ul>

## 本部分内容

  - [在 Lync Server 2013 中向 Active Directory 中添加 Survivable Branch Appliance](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [在 Lync Server 2013 中向拓扑添加分支站点](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [在 Lync Server 2013 中定义 Survivable Branch Appliance 或 Survivable Branch Server](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

