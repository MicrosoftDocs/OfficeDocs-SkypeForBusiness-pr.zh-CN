---
title: 在 Skype for Business Server 2015 中部署监控
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 摘要： 了解如何部署 Skype 业务服务器 2015年的监控。
ms.openlocfilehash: a963db346f5d9f7904b43fc2032aa881295d1b77
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-monitoring-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中部署监控
 
**摘要：**了解如何部署 Skype 业务服务器 2015年的监控。
  
您通常通过完成以下两个步骤在拓扑中实现监控服务：
  
1. 启用监视一次设置新 Skype 业务服务器池。 （业务服务器 2015年的 Skype，在监视是启用或禁用按池由池。）请注意，您可以启用监视而无需实际收集的监视数据池进程节所述配置呼叫详细记录，并体验质量设置此文档。
    
2. 使监控存储（即，监控数据库）与新池关联。请注意，一个监控存储可与多个池关联。根据驻留在注册器池中的用户数，这意味着，您不必为每个池设置单独的监控数据库。一个监控存储可供多个池使用。
    
尽管在创建新池的同时启用监控通常更为简单，但也可以创建新池并禁用监控。如果执行此操作，以后可以使用拓扑生成器启用该服务：拓扑生成器提供为池启用或禁用监控或将池与不同监控存储关联的方式。请记住，即使不再存在监控服务器角色，你仍需要创建一个或多个监控存储：用于存储监控服务所收集数据的后端数据库。可以使用 Microsoft SQL Server 2008 R2、Microsoft SQL Server 2012 或 Microsoft SQL Server 2014 创建这些后端数据库。
  
> [!NOTE]
> 如果已对某个池启用监视您可以禁用收集监控数据而无需更改您的拓扑结构的过程： Skype 业务服务器提供一种方法，您可以禁用 （然后再以后重新启用） 呼叫详细记录 (CDR) 或质量体验 (QoE) 数据收集。 有关详细信息，请参阅本文的“配置呼叫详细记录和用户体验质量设置”部分。 
  
一个其他重要的增强功能来监视在 Skype 业务服务器 2015年 Skype 的业务服务器监视报告现在支持 IPv6 的事实： 使用 IP 地址字段的报表将显示 IPv4 或 IPv6 地址根据： 1) SQL查询正在使用;并且，2），或不 IPv6 地址存储于监视数据库。
  
> [!NOTE]
> 确保 SQL Server 代理服务启动类型为“自动”，并且 SQL Server 代理服务正在针对容纳监控数据库的 SQL 实例运行，以便默认监控 SQL Server 维护作业在 SQL Server 代理服务的控制下按计划运行。 
  
本文档将指导您完成安装和配置监视和监视报告为 Skype 业务服务器 2015年的过程。 本文提供了会对您有所帮助的分步说明：
  
- 在拓扑中启用监控并使监控存储与前端池关联。
    
- 安装 SQL Server 报告服务和 Skype 业务服务器的监控报告。 监控报告是预配置的报告，其中提供不同视图，便于查看监控数据库中存储的信息。
    
- 配置呼叫详细记录 (CDR) 和用户体验质量 (QoE) 数据收集。 呼叫详细记录提供了有助于您跟踪业务服务器功能，如语音 IP (VoIP) 电话联络; 通过 Skype 的用法即时消息 (IM);文件传输;音频/视频 (A / V) 会议;和应用程序共享会话。 QoE 指标跟踪在组织内进行的音频和视频呼叫的质量，包括丢失的网络数据包数、背景噪音和“抖动”量（数据包延迟的差异）等内容。
    
- 从监控数据库中手动清除 CDR 和/或 QoE 记录。
    
## <a name="deployment-checklist-for-monitoring"></a>监控的部署清单

监视已安装并在每个前端服务器上激活，尽管仍有几个必须采取的步骤您可以实际上正在为 Skype 的监视数据收集为业务服务器 2015年之前。 以下清单中概述了这些步骤：
  
|**阶段**|**步骤**|**角色和组成员资格**|**文档**|
|:-----|:-----|:-----|:-----|
|**安装必备硬件和软件** <br/> |在将充当要进行监视的后端数据存储的计算机上安装受支持版本的 Microsoft SQL Server。  <br/> |还是本地管理员组的成员的域用户。  <br/> |[受支持的硬件](http://technet.microsoft.com/library/5f9c085d-205e-4235-9061-9ad875283cb0.aspx) <br/> [服务器软件和基础结构支持](http://technet.microsoft.com/library/4ee5fe38-0191-4710-9aa2-df8895e8c51b.aspx) <br/> |
|**创建相应的内部拓扑以支持监控** <br/> |使用 Skype 业务服务器 2015年拓扑生成器添加监视数据库拓扑，然后发布更新的拓扑。  <br/> |若要定义拓扑，则为是本地用户组成员的用户。  <br/> 若要发布拓扑，则为 Domain Administrators 组和 RTCUniversalServerAdmins 组的成员的用户。  <br/> |[将监视存储与 Skype 在前端池相关联的业务服务器 2015](associate-a-monitoring-store.md) <br/> |
|**启用相应的监控设置** <br/> |启用全局和/或站点作用域的呼叫详细记录 (CDR) 和/或用户体验质量 (QoE) 监视。  <br/> |为 RTCUniversalServerAdmins 组的用户，或分配有提供对 CsCdrConfiguration 和 CsQoEConfiguration cmdlet 的访问权限的 RBAC 角色的用户。  <br/> |[为业务服务器 2015年配置在 Skype 呼叫详细记录和体验质量设置](call-detail-recording-and-qoe.md) <br/> |
   
## <a name="enable-monitoring"></a>启用监控

虽然统一的数据收集代理会自动安装并在每个前端服务器上激活，但这并不表示会自动着手收集完成的业务服务器 2015年安装 Skype 的时刻的监控数据。 相反，你必须执行两项任务：必须将你的前端服务器/前端池与监控数据库关联，并且必须在全局范围和/或站点范围启用呼叫详细记录 (CDR) 和/或体验质量 (QoE) 监控。
  
将前端服务器或前端池与监视数据库相关联的分步说明，请参见部署指南 》 中[将一个前端池在业务服务器 2015年的 Skype 的监视存储相关联](associate-a-monitoring-store.md)的主题。 之后进行了这些关联，并为业务服务器拓扑结构您新 Skype 已发布之后，您将仍然不能收集监控数据。 这是因为，默认情况下，业务服务器 2015年安装 Skype 时禁用 CDR 和 QoE 数据收集。
  
若要开始数据收集，您将需要启用 CDR 和/或 QoE 监控。 （请注意，您不需要启用两个 CDR，QoE 监控; 如果您愿意，您可以启用一种类型的监视而禁用另一种类型）。若要启用 CDR 在全局范围内运行监视业务服务器管理外壳内 Skype 下面的命令：
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

或者，您可以启用监视从内 Skype 业务服务器控件面板的 CDR。 从 Skype 业务服务器控制面板中完成以下过程：
  
1. 单击“**监控**”。
    
2. 在“**呼叫详细记录**”选项卡上，双击“**全局**”设置。
    
3. 在“**编辑呼叫详细记录(CDR)设置**”窗格中，选择“**启用 CDR 监控**”，然后单击“**提交**”。
    
若要启用 QoE 监控在全局范围内，运行业务服务器管理外壳内 Skype 使用该命令：
  
```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

如果您愿意，您还可以启用 QoE 监控从内 Skype 业务服务器的控制面板。 从控制面板中，完成以下过程：
  
1. 单击“**监控**”。
    
2. 在“**用户体验质量数据**”选项卡上，双击“**全局**”设置。
    
3. 在“**编辑体验质量(QoE)设置**”窗格中，选择“**启用 QoE 数据监控**”，然后单击“**提交**”。
    
您已看到，上面的示例在全局范围启用监控；即，它们在贵组织内启用 CDR 和 QoE 监控。 您也可以在站点范围创建单独的 CDR 和 QoE 配置设置，然后有选择地为每个站点启用或禁用监控。 例如，可以为您的 Redmond 站点启用 CDR 监控，而为您的 Dublin 站点禁用 CDR 监控。 管理监控的配置设置的详细信息，请参阅部署指南主题[配置呼叫详细记录以及在业务服务器 2015年的 Skype 的体验质量设置](call-detail-recording-and-qoe.md)。
  

