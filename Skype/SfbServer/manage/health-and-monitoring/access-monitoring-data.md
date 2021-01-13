---
title: 访问 Skype for Business Server 中的监视数据
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 摘要：了解 Skype for Business Server 中使用的监视数据。
ms.openlocfilehash: deff5dc5c21437cd89282578d2bf3f546f444f94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826542"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a><span data-ttu-id="38e24-103">访问 Skype for Business Server 中的监视数据</span><span class="sxs-lookup"><span data-stu-id="38e24-103">Access monitoring data in Skype for Business Server</span></span>
 
<span data-ttu-id="38e24-104">**摘要：** 了解 Skype for Business Server 中使用的监视数据。</span><span class="sxs-lookup"><span data-stu-id="38e24-104">**Summary:** Learn about the monitoring data used in Skype for Business Server.</span></span>
  
<span data-ttu-id="38e24-p101">监控数据存储在一对 SQL Server 数据库中：LcsCdr 用于存储呼叫详细信息记录数据，而 QoEMetrics 用于存储用户体验质量数据。这两个数据库没有什么特别的；这意味着您可使用通常用于访问和分析 SQL Server 数据的任何工具访问这两个数据库中存储的数据。</span><span class="sxs-lookup"><span data-stu-id="38e24-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>
  
<span data-ttu-id="38e24-107">访问和分析监控数据应考虑的一个工具是 Skype for Business Server 监控报告。</span><span class="sxs-lookup"><span data-stu-id="38e24-107">One tool you should consider for accessing and analyzing monitoring data is the Skype for Business Server Monitoring Reports.</span></span> <span data-ttu-id="38e24-108">监控报告包含一组由 Microsoft SQL Server Reporting Service 发布的标准报告。</span><span class="sxs-lookup"><span data-stu-id="38e24-108">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="38e24-109">这些报告可通过 Web 浏览器进行访问，它们提供了使用情况、呼叫诊断信息和媒体质量信息，所有这些信息全部基于呼叫详细记录 (CDR) 和用户体验质量 (QoE) 数据库中存储的 CDR 和 QoE 记录。</span><span class="sxs-lookup"><span data-stu-id="38e24-109">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="38e24-110">监控报告随 Skype for Business Server 一起提供，可以在安装 Skype for Business Server 并配置监控后从 Skype for Business Server 部署向导进行安装。</span><span class="sxs-lookup"><span data-stu-id="38e24-110">Monitoring Reports ship with Skype for Business Server and can be installed from the Skype for Business Server Deployment Wizard after Skype for Business Server has been installed and monitoring has been configured.</span></span>
  
<span data-ttu-id="38e24-p103">如前所述，监控报告需要使用 SQL Server Reporting Service。SQL Server Reporting Service 可在安装 SQL Server 时安装，也可以在安装 SQL Server 后随时安装。</span><span class="sxs-lookup"><span data-stu-id="38e24-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>
  
<span data-ttu-id="38e24-113">有关详细信息，请参阅主题 Install [Monitoring Reports in Skype for Business Server.](../../deploy/deploy-monitoring/install-monitoring-reports.md)</span><span class="sxs-lookup"><span data-stu-id="38e24-113">For more information, see the topic [Install Monitoring Reports in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).</span></span>
  

