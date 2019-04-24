---
title: 部署监控 Skype 中的业务服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 摘要： 了解如何部署中 Skype 监控的企业服务器。
ms.openlocfilehash: 147d20c7a6b85ef294711602748ee474b4e9abd3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225509"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>部署监控 Skype 中的业务服务器

**摘要：** 了解如何部署中 Skype 监控的企业服务器。

在执行这些任务之前, 查看[规划中的业务服务器 Skype 监控](../../plan-your-deployment/monitoring.md)。

您通常通过完成以下两个步骤在拓扑中实现监控服务：

1. 您对业务服务器池的新 Skype 启用同时监控设置。 （Skype 业务服务器，在监控启用或禁用按池的池。）请注意，您可以启用监控而无需实际收集监视数据，池中此文档的配置 Call Detail Recording and Quality of Experience Settings 一节所述过程。

2. 使监控存储（即，监控数据库）与新池关联。请注意，一个监控存储可与多个池关联。根据驻留在注册器池中的用户数，这意味着，您不必为每个池设置单独的监控数据库。一个监控存储可供多个池使用。

尽管在创建新池的同时启用监控通常更为简单，但也可以创建新池并禁用监控。如果执行此操作，以后可以使用拓扑生成器启用该服务：拓扑生成器提供为池启用或禁用监控或将池与不同监控存储关联的方式。请记住，即使不再存在监控服务器角色，你仍需要创建一个或多个监控存储：用于存储监控服务所收集数据的后端数据库。可以使用 Microsoft SQL Server 2008 R2、Microsoft SQL Server 2012 或 Microsoft SQL Server 2014 创建这些后端数据库。

> [!NOTE]
> 如果池的监控已经启用您可以禁用收集监视数据，而无需更改您的拓扑的过程： Skype 业务服务器提供了一种方法，以禁用 （然后再稍后重新启用） 呼叫详细信息记录 (CDR) 或质量用户体验 (QoE) 数据收集。 有关详细信息，请参阅本文的“配置呼叫详细记录和用户体验质量设置”部分。

一个监控中 Skype 业务服务器是因为业务服务器监控报告的 Skype 现在支持 IPv6 的其他重要改进： 使用 IP 地址字段的报告将显示任一 IPv4 或 IPv6 地址，具体取决于： 1) SQL 查询正在使用;以及 2），或不存储在监控数据库中的 IPv6 地址。

> [!NOTE]
> 确保 SQL Server 代理服务启动类型为“自动”，并且 SQL Server 代理服务正在针对容纳监控数据库的 SQL 实例运行，以便默认监控 SQL Server 维护作业在 SQL Server 代理服务的控制下按计划运行。

本文档指导您完成安装和配置监控和监控报告的 Skype 业务服务器的过程。 本文提供了会对您有所帮助的分步说明：

- 在拓扑中启用监控并使监控存储与前端池关联。

- 安装监控报告的业务服务器的 SQL Server Reporting Services 和 Skype。 监控报告是预配置的报告，其中提供不同视图，便于查看监控数据库中存储的信息。

- 配置呼叫详细记录 (CDR) 和用户体验质量 (QoE) 数据收集。 呼叫详细信息记录提供了一种方法，用于跟踪使用情况的 Skype IP (电话 VoIP) 电话呼叫; 例如语音的业务服务器功能即时消息 (IM);文件传输;音频/视频 (A / V) 会议;和应用程序共享会话。 QoE 指标跟踪在组织内进行的音频和视频呼叫的质量，包括丢失的网络数据包数、背景噪音和“抖动”量（数据包延迟的差异）等内容。

- 从监控数据库中手动清除 CDR 和/或 QoE 记录。

## <a name="deployment-checklist-for-monitoring"></a>监控的部署清单

尽管监控已经安装并在每台前端服务器上激活，但仍有以下几个您必须采取的步骤之前可以实际的业务服务器的 Skype 收集监视数据。 以下清单中概述了这些步骤：

|**阶段**|**步骤**|**角色和组成员身份**|**文档**|
|:-----|:-----|:-----|:-----|
|**安装必备硬件和软件** <br/> |在将充当要进行监视的后端数据存储的计算机上安装受支持版本的 Microsoft SQL Server。  <br/> |还是本地管理员组的成员的域用户。  <br/> |[Supported Hardware](https://technet.microsoft.com/library/5f9c085d-205e-4235-9061-9ad875283cb0.aspx) <br/> [Server Software and Infrastructure Support](https://technet.microsoft.com/library/4ee5fe38-0191-4710-9aa2-df8895e8c51b.aspx) <br/> |
|**创建相应的内部拓扑以支持监控** <br/> |业务 Server 拓扑生成器，若要添加的使用 Skype 监控数据库到拓扑，然后发布已更新的拓扑。  <br/> |若要定义拓扑，则为是本地用户组成员的用户。  <br/> 若要发布拓扑，则为 Domain Administrators 组和 RTCUniversalServerAdmins 组的成员的用户。  <br/> |[将监控存储与 Skype 中的前端池相关联的业务服务器](associate-a-monitoring-store.md) <br/> |
|**启用相应的监控设置** <br/> |启用全局和/或站点作用域的呼叫详细记录 (CDR) 和/或用户体验质量 (QoE) 监视。  <br/> |为 RTCUniversalServerAdmins 组的用户，或分配有提供对 CsCdrConfiguration 和 CsQoEConfiguration cmdlet 的访问权限的 RBAC 角色的用户。  <br/> |[为业务 Server Skype 中配置呼叫详细信息记录和用户体验质量设置](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>启用监控

虽然自动安装并在每台前端服务器上激活统一的数据收集代理，但这并不表示，您将会自动开始，仍未完成业务服务器安装 Skype 收集监视数据。 相反，你必须执行两项任务：必须将你的前端服务器/前端池与监控数据库关联，并且必须在全局范围和/或站点范围启用呼叫详细记录 (CDR) 和/或体验质量 (QoE) 监控。

将前端服务器或前端池与监控数据库相关联的分步说明，请参阅部署指南中的主题[将 Skype 业务服务器中的前端池与监控存储相关联](associate-a-monitoring-store.md)。 进行了这些关联后，并发布您的企业服务器拓扑的新 Skype 后，您将仍然不能以收集监视数据。 这是因为默认情况下，为业务服务器安装 Skype 时禁用 CDR 和 QoE 数据集。

若要开始数据收集，您将需要启用 CDR 和/或 QoE 监控。 （请注意，不需要启用这两个 CDR 和 QoE 监控; 如果愿意，您可以启用一种类型的同时保持其他类型禁用监控）启用 CDR 在全局范围运行监控业务 Server 命令行管理程序从 Skype 中的以下命令：

```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

此外，您可以启用 CDR 监控从中 Skype 业务 Server Control Panel。 从业务 Server 控制面板的 Skype 中完成以下过程：

1. 单击“**监控**”。

2. 在“**呼叫详细记录**”选项卡上，双击“**全局**”设置。

3. 在“**编辑呼叫详细记录(CDR)设置**”窗格中，选择“**启用 CDR 监控**”，然后单击“**提交**”。

若要启用 QoE 监控在全局范围内中, 运行此命令从 Skype 的业务 Server 命令行管理程序：

```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

如果您愿意，您还可以启用 QoE 监控从 Skype 中的业务 Server Control Panel。 从控制面板中，完成以下过程：

1. 单击“**监控**”。

2. 在“**用户体验质量数据**”选项卡上，双击“**全局**”设置。

3. 在“**编辑体验质量(QoE)设置**”窗格中，选择“**启用 QoE 数据监控**”，然后单击“**提交**”。

您已看到，上面的示例在全局范围启用监控；即，它们在贵组织内启用 CDR 和 QoE 监控。 您也可以在站点范围创建单独的 CDR 和 QoE 配置设置，然后有选择地为每个站点启用或禁用监控。 例如，可以为您的 Redmond 站点启用 CDR 监控，而为您的 Dublin 站点禁用 CDR 监控。 管理监控配置设置的详细信息，请参阅[配置呼叫详细信息记录和 Skype 业务服务器中的用户体验质量设置](call-detail-recording-and-qoe.md)的部署指南主题。

## <a name="see-also"></a>另请参阅

[规划 Business Server Skype 中监控](../../plan-your-deployment/monitoring.md)
