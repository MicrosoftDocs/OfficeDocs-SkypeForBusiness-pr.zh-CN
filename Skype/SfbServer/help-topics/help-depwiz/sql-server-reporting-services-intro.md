---
title: SQL Server Reporting Services（简介）
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f3cda686-6301-419c-af68-b49cc785e5fc
description: 每个前端池和 Survivable Branch Appliance 只能拥有一台关联的监控服务器。如果为站点启用监控，监控服务器会提供呼叫详细信息记录 (CDR) 和用户体验质量 (QoE) 数据收集和报告。
ms.openlocfilehash: 6a45508c3f95da02df966e4d9905020af1b9f9b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829572"
---
# <a name="sql-server-reporting-services-intro"></a><span data-ttu-id="e8e51-104">SQL Server Reporting Services（简介）</span><span class="sxs-lookup"><span data-stu-id="e8e51-104">SQL Server Reporting Services (Intro)</span></span>
 
<span data-ttu-id="e8e51-p102">每个前端池和 Survivable Branch Appliance 只能拥有一台关联的监控服务器。如果为站点启用监控，监控服务器会提供呼叫详细信息记录 (CDR) 和用户体验质量 (QoE) 数据收集和报告。</span><span class="sxs-lookup"><span data-stu-id="e8e51-p102">Each Front End pool and Survivable Branch Appliance can have only one Monitoring Server associated with it. When monitoring is enabled for the site, Monitoring Server provides call detail recording (CDR) and Quality of Experience (QoE) data collection and reporting.</span></span>
  
<span data-ttu-id="e8e51-107">站点中的所有池和多个中央站点的池可以使用相同的监控服务器，前提是使用量不超过监控服务器的容量。</span><span class="sxs-lookup"><span data-stu-id="e8e51-107">All pools at a site and the pools of multiple central sites can use the same Monitoring Server, if usage does not exceed the capacity of the Monitoring Server.</span></span> <span data-ttu-id="e8e51-108">有关设计支持监控的拓扑的详细信息，请参阅部署文档中的"将监控存储与 [Skype for Business Server 2015](../../deploy/deploy-monitoring/associate-a-monitoring-store.md) 中的前端池关联"。</span><span class="sxs-lookup"><span data-stu-id="e8e51-108">For details about designing a topology to support monitoring, see [Associate a monitoring store with a Front End pool in Skype for Business Server 2015](../../deploy/deploy-monitoring/associate-a-monitoring-store.md) in the Deployment documentation.</span></span>
  

