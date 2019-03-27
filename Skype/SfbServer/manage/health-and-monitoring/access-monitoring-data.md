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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885046"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a><span data-ttu-id="692a5-103">监视业务 Server 的 Skype 中的数据的访问</span><span class="sxs-lookup"><span data-stu-id="692a5-103">Access monitoring data in Skype for Business Server</span></span>
 
<span data-ttu-id="692a5-104">**摘要：** 了解 Business Server Skype 中使用的监控数据。</span><span class="sxs-lookup"><span data-stu-id="692a5-104">**Summary:** Learn about the monitoring data used in Skype for Business Server.</span></span>
  
<span data-ttu-id="692a5-p101">监控数据存储在一对 SQL Server 数据库中：LcsCdr 用于存储呼叫详细信息记录数据，而 QoEMetrics 用于存储用户体验质量数据。这两个数据库没有什么特别之处；也就是说您可使用通常用于访问和分析 SQL Server 数据的任何工具访问这两个数据库中存储的数据。</span><span class="sxs-lookup"><span data-stu-id="692a5-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>
  
<span data-ttu-id="692a5-107">您应考虑用于访问和分析监控数据的工具之一是业务服务器监控报告 Skype。</span><span class="sxs-lookup"><span data-stu-id="692a5-107">One tool you should consider for accessing and analyzing monitoring data is the Skype for Business Server Monitoring Reports.</span></span> <span data-ttu-id="692a5-108">监控报告包含一组由 Microsoft SQL Server Reporting Service 发布的标准报告。</span><span class="sxs-lookup"><span data-stu-id="692a5-108">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="692a5-109">这些报告可通过 Web 浏览器进行访问，它们提供了使用情况、呼叫诊断信息和媒体质量信息，所有这些信息全部基于呼叫详细记录 (CDR) 和用户体验质量 (QoE) 数据库中存储的 CDR 和 QoE 记录。</span><span class="sxs-lookup"><span data-stu-id="692a5-109">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="692a5-110">监控报告附带 Skype 业务服务器可以之后，安装从 Skype 业务 Server 部署向导 Skype 业务服务器已经安装并配置监控。</span><span class="sxs-lookup"><span data-stu-id="692a5-110">Monitoring Reports ship with Skype for Business Server and can be installed from the Skype for Business Server Deployment Wizard after Skype for Business Server has been installed and monitoring has been configured.</span></span>
  
<span data-ttu-id="692a5-p103">如前所述，监控报告需要使用 SQL Server Reporting Service。SQL Server Reporting Service 可在安装 SQL Server 时安装，也可以在安装 SQL Server 后随时安装。</span><span class="sxs-lookup"><span data-stu-id="692a5-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>
  
<span data-ttu-id="692a5-113">有关详细信息，请参阅主题[中的业务服务器 Skype 安装监控报告](../../deploy/deploy-monitoring/install-monitoring-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="692a5-113">For more information, see the topic [Install Monitoring Reports in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).</span></span>
  

