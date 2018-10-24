---
title: Lync Server 2013：用于 Lync Server 的 Windows Update
TOCTitle: 用于 Lync Server 2013 的 Windows Update
ms:assetid: fe26ab32-b1a9-421d-9227-506703d4b834
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn518337(v=OCS.15)
ms:contentKeyID: 60505972
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 用于 Lync Server 2013 的 Windows Update

 

_**上一次修改主题：** 2013-12-05_

使用 Windows Update Services 经常检查和应用更新以及安全更新。这样做有助于防止其他系统组件出现漏洞，这些漏洞可能会导致攻击者能够使用管理员权限获取运行 Microsoft Lync Server 2013 的服务器的访问权，从而破坏 Lync Server 2013。

Microsoft SQL Server 2008 Express（64 位版本）的更新可在每个 Lync Server 2013 Standard Edition Server（对于后端数据库）和所有其他 Lync Server 2013 服务器角色（对于本地配置存储）上运行，除非已将这些数据库升级到 SQL Server 2008 R2 Express。您应将这些数据库视为日常安全更新维护的一部分，就像前端池的后端数据库上的 SQL Server、监控数据库和存档数据库一样。

## 最佳做法

  - 使用 Windows Update 保持系统最新。

