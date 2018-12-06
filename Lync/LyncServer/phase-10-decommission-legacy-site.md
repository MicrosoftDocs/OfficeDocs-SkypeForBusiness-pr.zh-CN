---
title: 第 10 阶段：停用旧站点
TOCTitle: 第 10 阶段：停用旧站点
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205300(v=OCS.15)
ms:contentKeyID: 49314380
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 第 10 阶段：停用旧站点

 

_**上一次修改主题：** 2016-12-08_

下列主题提供停用池、从 Office Communications Server 2007 R2 的旧部署中停用和删除服务器和池的指南。并非本节中列出的所有过程都是必需的。请阅读下面每个主题中的信息，以确定要使用的停用过程。

> [!CAUTION]
> 如果将电话拨入式会议的会议目录导入 Lync Server 2013，则在开始停用池前，应将会议目录所有权转移到 Lync Server 2013，这一点非常重要。如果停用池时没有先转移会议目录所有权，则所有迁移会议的拨入功能将不再起作用。必须为旧池中的每个会议目录执行一次转移所有权的步骤。


> [!IMPORTANT]
> 有关在停用旧环境之前迁移和升级 Microsoft 统一通信托管 API (UCMA) 应用程序的信息，请参阅 <a href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</a>


## 本节内容

  - [移动会议目录](move-conference-directories.md)

  - [更新 DNS SRV 记录](update-dns-srv-records_1.md)

  - [停用服务器和池](decommissioning-servers-and-pools.md)

  - [删除 BackCompatSite](remove-backcompatsite.md)

