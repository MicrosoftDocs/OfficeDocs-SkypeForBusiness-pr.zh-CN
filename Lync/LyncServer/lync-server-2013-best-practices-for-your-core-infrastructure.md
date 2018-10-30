---
title: 适用于 Lync Server 2013 中核心基础结构的最佳做法
TOCTitle: 适用于 Lync Server 2013 中核心基础结构的最佳做法
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn518328(v=OCS.15)
ms:contentKeyID: 60505964
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 适用于 Lync Server 2013 中核心基础结构的最佳做法

 

_**上一次修改主题：** 2016-12-08_

您可能已经着手设计系统容错能力了，做法有：确保硬件冗余，防止断电，例行安装安全更新和防病毒措施，以及监控服务器活动等。这些做法不仅对 Microsoft Lync Server 2013 基础结构有益，而且对整个网络有益。如果您还未实施这些做法，建议您在部署 Lync Server 2013 之前先实施这些做法。

为帮助防止 Lync Server 2013 部署中的服务器受到无意或故意的可能导致停机的破坏，请采取以下防范措施：

  - 使用安全更新使服务器保持最新状态。订阅 Microsoft 安全性通知服务来帮助您确保收到关于任何 Microsoft 产品的安全公告发布的最新通知。要订阅此服务，请转至 Microsoft 技术安全性通知网站，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202)。

  - 确保正确设置访问权限。

  - 将服务器部署在可阻止未经授权访问的物理环境中。确保在所有服务器上安装适当的防病毒软件。使用最新的病毒特征文件使软件保持最新。使用防病毒应用程序的自动更新功能使病毒特征保持最新。

  - 建议您在安装 Lync Server 2013 的计算机上禁用不需要的 Windows Server 操作系统服务。

  - 除非可以确保实现连续完整的服务器控制、完全物理隔离以及正确安全地停用更换的或有故障的磁盘驱动器，否则使用全卷加密系统对操作系统和存储数据的磁盘驱动器加密。

  - 除非可以确保严格控制对服务器的物理访问，否则禁用服务器的所有外部直接内存访问 (DMA) 端口。很容易就能发起的基于 DMA 的攻击可能会公开非常敏感的信息，例如加密私钥。

