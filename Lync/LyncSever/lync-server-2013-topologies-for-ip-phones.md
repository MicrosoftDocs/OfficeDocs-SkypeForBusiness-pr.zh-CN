---
title: IP 电话的拓扑
TOCTitle: IP 电话的拓扑
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425740(v=OCS.15)
ms:contentKeyID: 49312296
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# IP 电话的拓扑

 

_**上一次修改主题：** 2012-06-21_

本节概述连接过程，并介绍 IP 电话在内部和外部网络中的连接方式之间的差异。

> [!NOTE]  
> Lync Server 对以下 IP 电话提供支持：Aastra 6721ip 公用区域电话、Aastra 6725ip 桌面电话、HP 4110 IP Phone（公用区域电话）、HP 4120 IP Phone（桌面电话）、Polycom CX600 IP 桌面电话、Polycom CX700 IP 桌面电话、Polycom CX500 IP 公用区域电话和 Polycom CX3000 IP 会议电话。在所有这些电话中，只有 Polycom CX700 可以运行 Lync Phone Edition。


下图介绍在企业环境下设备连接涉及的所有组件。

**内部拓扑**

![网络内部的设备](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "网络内部的设备")

> [!NOTE]  
> 上图采用逻辑表示形式，而非物理概述。例如，Active Directory 域服务 (AD DS) 很少与任何 Lync Server 组件位于同一计算机上。用户存储可以位于后端服务器上，也可以位于存档服务器和监控服务器上。Lync Server 命令行管理程序、Web 服务器和更新服务都是前端服务器角色的一部分。


下图概述设备位于企业网络外部时涉及的组件。

**外部拓扑**

![网络外部的设备](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "网络外部的设备")

> [!NOTE]
> 设备更新 Web 服务提供外部和内部网站，但此处仅显示外部网站。<br />
> 如果要启用外部访问，则必须在 DNS 中发布注册器的位置和组织设备更新 Web 服务的 URL。此外，还必须部署和正确配置边缘服务器，以允许从设备到企业环境的往返外部通信。上图省略了该内容，因为边缘部署并非特定于设备连接。

