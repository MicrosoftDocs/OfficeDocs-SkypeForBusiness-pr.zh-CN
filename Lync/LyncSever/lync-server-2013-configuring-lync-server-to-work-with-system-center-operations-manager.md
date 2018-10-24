---
title: 配置 Lync Server 以使用 System Center Operations Manager
TOCTitle: 配置 Lync Server 以使用 System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205188(v=OCS.15)
ms:contentKeyID: 49314001
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置 Lync Server 以使用 System Center Operations Manager

 

_**上一次修改主题：** 2012-10-22_

要将您的 Microsoft Lync Server 2013 基础结构配置为与 System Center Operations Manager 结合使用，您必须执行以下三个操作：

  - 识别并配置您的主要 System Center Operations Manager 管理服务器。配置管理服务器包括安装 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2，以及使用 SQL Server 设置后端数据库。您需要使用的实际 SQL Server 版本取决于您所使用的 System Center Operations Manager 版本。有关详细信息，请参阅[配置主管理服务器](lync-server-2013-configuring-the-primary-management-server.md)。

  - 识别并配置要监控的 Lync Server 计算机。要使用 System Center Operations Manager 监控 Lync Server 计算机，必须安装 System Center Operations Manager 代理文件，并将每个服务器配置为充当代理。

  - 识别并配置要充当 Lync Server*观察程序节点* 的计算机。观察程序节点是指定期运行 Lync Server 综合事务的计算机，这些综合事务是用来确认关键 Lync Server 组件（如登录到系统的能力或交换即时消息的能力）是否按预期正常运行的 Windows PowerShell cmdlet。

本节中的主题包含执行其中每项任务的说明。

## 本节内容

  - [配置主管理服务器](lync-server-2013-configuring-the-primary-management-server.md)

  - [安装 Lync Server 2013 管理包](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [配置将受监控的 Lync Server 计算机](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [安装和配置观察程序节点](lync-server-2013-installing-and-configuring-watcher-nodes.md)

