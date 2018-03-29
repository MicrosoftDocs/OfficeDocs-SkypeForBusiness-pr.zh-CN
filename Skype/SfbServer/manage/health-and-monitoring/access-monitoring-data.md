---
title: 访问 Skype for Business Server 2015 中的监控数据
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 摘要： 了解如何使用 Skype 业务服务器 2015年监视数据。
ms.openlocfilehash: 908ebbff4e88985cdba606098dc5a5ace271e30d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="access-monitoring-data-in-skype-for-business-server-2015"></a>访问 Skype for Business Server 2015 中的监控数据
 
**摘要：**了解有关使用 Skype 业务服务器 2015年监视数据。
  
监控数据存储在一对 SQL Server 数据库中：LcsCdr 用于存储呼叫详细信息记录数据，而 QoEMetrics 用于存储用户体验质量数据。这两个数据库没有什么特别之处；也就是说您可使用通常用于访问和分析 SQL Server 数据的任何工具访问这两个数据库中存储的数据。
  
应考虑用于访问和分析监视数据的工具之一是 Skype 的业务服务器监视报告。 监控报告包含一组由 Microsoft SQL Server Reporting Service 发布的标准报告。 这些报告可通过 Web 浏览器进行访问，它们提供了使用情况、呼叫诊断信息和媒体质量信息，所有这些信息全部基于呼叫详细记录 (CDR) 和用户体验质量 (QoE) 数据库中存储的 CDR 和 QoE 记录。 监视报告附带的业务服务器 2015年的 Skype，可以从安装 Skype 业务服务器部署向导后 Skype 业务服务器已安装和配置监视。
  
如前所述，监控报告需要使用 SQL Server Reporting Service。SQL Server Reporting Service 可在安装 SQL Server 时安装，也可以在安装 SQL Server 后随时安装。
  
有关详细信息，请参阅主题[在 Skype 的业务服务器 2015年安装监视报告](../../deploy/deploy-monitoring/install-monitoring-reports.md)在 Skype 业务服务器 2015年部署指南。
  

