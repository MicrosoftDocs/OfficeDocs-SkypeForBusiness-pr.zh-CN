---
title: 监视业务 Server 的 Skype 中的数据的访问
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 摘要： 了解如何在 Skype 用于 Business Server 监视数据。
ms.openlocfilehash: 096a20119f0d7f368165aae53e2b3164cb817d63
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197588"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>监视业务 Server 的 Skype 中的数据的访问
 
**摘要：** 了解 Business Server Skype 中使用的监控数据。
  
监控数据存储在一对 SQL Server 数据库中：LcsCdr 用于存储呼叫详细信息记录数据，而 QoEMetrics 用于存储用户体验质量数据。这两个数据库没有什么特别之处；也就是说您可使用通常用于访问和分析 SQL Server 数据的任何工具访问这两个数据库中存储的数据。
  
您应考虑用于访问和分析监控数据的工具之一是业务服务器监控报告 Skype。 监控报告包含一组由 Microsoft SQL Server Reporting Service 发布的标准报告。 这些报告可通过 Web 浏览器进行访问，它们提供了使用情况、呼叫诊断信息和媒体质量信息，所有这些信息全部基于呼叫详细记录 (CDR) 和用户体验质量 (QoE) 数据库中存储的 CDR 和 QoE 记录。 监控报告附带 Skype 业务服务器可以之后，安装从 Skype 业务 Server 部署向导 Skype 业务服务器已经安装并配置监控。
  
如前所述，监控报告需要使用 SQL Server Reporting Service。SQL Server Reporting Service 可在安装 SQL Server 时安装，也可以在安装 SQL Server 后随时安装。
  
有关详细信息，请参阅主题[中的业务服务器 Skype 安装监控报告](../../deploy/deploy-monitoring/install-monitoring-reports.md)。
  

