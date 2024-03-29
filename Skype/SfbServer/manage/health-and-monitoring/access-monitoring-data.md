---
title: 访问监控数据Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 摘要：了解 Skype for Business Server。
---

# <a name="access-monitoring-data-in-skype-for-business-server"></a>访问监控数据Skype for Business Server
 
**摘要：** 了解在远程管理中使用的Skype for Business Server。
  
监控数据存储在一对 SQL Server 数据库中：LcsCdr 用于存储呼叫详细信息记录数据，而 QoEMetrics 用于存储用户体验质量数据。这两个数据库没有什么特别的；这意味着您可使用通常用于访问和分析 SQL Server 数据的任何工具访问这两个数据库中存储的数据。
  
您应该考虑用于访问和分析监控数据的一个工具是监控Skype for Business Server报告。 监控报告包含一组由 Microsoft SQL Server Reporting Service 发布的标准报告。 这些报告可通过 Web 浏览器进行访问，它们提供了使用情况、呼叫诊断信息和媒体质量信息，所有这些信息全部基于呼叫详细记录 (CDR) 和用户体验质量 (QoE) 数据库中存储的 CDR 和 QoE 记录。 监控报告随Skype for Business Server一起提供，在安装监控Skype for Business Server配置监控Skype for Business Server可以从部署向导安装监控报告。
  
如前所述，监控报告需要使用 SQL Server Reporting Service。SQL Server Reporting Service 可在安装 SQL Server 时安装，也可以在安装 SQL Server 后随时安装。
  
有关详细信息，请参阅主题 Install [Monitoring Reports in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md)。
  

