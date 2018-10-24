---
title: 在 Lync Server 2013 中访问监控数据
TOCTitle: 在 Lync Server 2013 中访问监控数据
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49888492
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中访问监控数据

 

_**上一次修改主题：** 2012-09-05_

监控数据存储在一对 SQL Server 数据库中：LcsCdr 用于存储呼叫详细信息记录数据，而 QoEMetrics 用于存储用户体验质量数据。这两个数据库没有什么特别的；这意味着您可使用通常用于访问和分析 SQL Server 数据的任何工具访问这两个数据库中存储的数据。

访问和分析监控数据时应考虑的一种工具是 Lync Server 监控报告。监控报告包含一组由 Microsoft SQL Server Reporting Service 发布的标准报告。这些报告可通过 Web 浏览器进行访问，它们提供了使用情况、呼叫诊断信息和媒体质量信息，所有这些信息全部基于呼叫详细记录 (CDR) 和用户体验质量 (QoE) 数据库中存储的 CDR 和 QoE 记录。监控报告是 Lync Server 2013 附带的，可在安装 Lync Server 和配置监控之后从 Lync Server 部署向导进行安装。

如前所述，监控报告需要使用 SQL Server Reporting Service。SQL Server Reporting Service 可在安装 SQL Server 时安装，也可以在安装 SQL Server 后随时安装。

有关详细信息，请参阅 Lync Server 2013 部署指南中的主题[安装 Lync Server 2013 监控报告](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)。

