---
title: 在 Skype for Business 服务器中部署监视
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 摘要：了解如何在 Skype for Business 服务器中部署监视。
ms.openlocfilehash: 7f3bd96b814b45b625612aae9b56a706dfff470f
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001142"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>在 Skype for Business 服务器中部署监视

**摘要：** 了解如何在 Skype for Business 服务器中部署监视。

在执行这些任务之前，请查看[Skype For Business 服务器中的监视计划](../../plan-your-deployment/monitoring.md)。

您通常通过完成以下两个步骤在拓扑中实现监控服务：

1. 在设置新的 Skype for Business 服务器池的同时启用监视。 （在 Skype for Business 服务器中，监视功能在逐个池的基础上启用或禁用。）请注意，你可以为池启用监视，而无需实际收集监视数据，此过程将在本文档的 "配置呼叫详细记录" 和 "体验设置质量" 部分中介绍。

2. 使监控存储（即，监控数据库）与新池关联。请注意，一个监控存储可与多个池关联。根据驻留在注册器池中的用户数，这意味着，您不必为每个池设置单独的监控数据库。一个监控存储可供多个池使用。

尽管在创建新池的同时启用监控通常更为简单，但也可以创建新池并禁用监控。如果执行此操作，以后可以使用拓扑生成器启用该服务：拓扑生成器提供为池启用或禁用监控或将池与不同监控存储关联的方式。请记住，即使不再存在监控服务器角色，你仍需要创建一个或多个监控存储：用于存储监控服务所收集数据的后端数据库。可以使用 Microsoft SQL Server 2008 R2、Microsoft SQL Server 2012 或 Microsoft SQL Server 2014 创建这些后端数据库。

> [!NOTE]
> 如果已为池启用监视，则可以禁用收集监视数据的过程，而无需更改拓扑： Skype for Business Server 提供了一种禁用（稍后重新启用）呼叫详细记录（CDR）或质量的方法体验（QoE）数据收集。 有关详细信息，请参阅本文的“配置呼叫详细记录和用户体验质量设置”部分。

Skype for business 服务器监视报告的一个其他重要增强功能是 Skype for business 服务器监视报告现在支持 IPv6：使用 "IP 地址" 字段的报表将显示 IPv4 或 IPv6 地址，具体取决于：1） SQL 查询正在使用;和（2）将 IPv6 地址存储在监视数据库中的位置。

> [!NOTE]
> 确保 SQL Server 代理服务启动类型为“自动”，并且 SQL Server 代理服务正在针对容纳监控数据库的 SQL 实例运行，以便默认监控 SQL Server 维护作业在 SQL Server 代理服务的控制下按计划运行。

本文档将指导你完成为 Skype for business 服务器安装和配置监视和监视报告的过程。 本文提供了会对您有所帮助的分步说明：

- 在拓扑中启用监控并使监控存储与前端池关联。

- 安装 SQL Server Reporting Services 和 Skype for Business 服务器监视报告。 监控报告是预配置的报告，其中提供不同视图，便于查看监控数据库中存储的信息。

- 配置呼叫详细记录 (CDR) 和用户体验质量 (QoE) 数据收集。 通话详细记录为您提供了一种跟踪 Skype for business 服务器功能（如 IP 语音电话（VoIP）电话呼叫）的使用方式的方式。即时消息（IM）;文件传输;音频/视频（A/V）会议;和应用程序共享会话。 QoE 指标跟踪在组织内进行的音频和视频呼叫的质量，包括丢失的网络数据包数、背景噪音和“抖动”量（数据包延迟的差异）等内容。

- 从监控数据库中手动清除 CDR 和/或 QoE 记录。

## <a name="deployment-checklist-for-monitoring"></a>监控的部署清单

虽然已安装并在每个前端服务器上激活了监视，但必须先执行几个步骤，然后才能实际收集 Skype for business 服务器的监视数据。 以下清单中概述了这些步骤：

|**阶段**|**步骤**|**角色和组成员身份**|**文档**|
|:-----|:-----|:-----|:-----|
|**安装必备硬件和软件** <br/> |在将充当要进行监视的后端数据存储的计算机上安装受支持版本的 Microsoft SQL Server。  <br/> |还是本地管理员组的成员的域用户。  <br/> |[Supported Hardware](https://technet.microsoft.com/library/5f9c085d-205e-4235-9061-9ad875283cb0.aspx) <br/> [Server Software and Infrastructure Support](https://technet.microsoft.com/library/4ee5fe38-0191-4710-9aa2-df8895e8c51b.aspx) <br/> |
|**创建相应的内部拓扑以支持监控** <br/> |使用 Skype for Business Server 拓扑生成器将监视数据库添加到拓扑，然后发布更新后的拓扑。  <br/> |若要定义拓扑，则为是本地用户组成员的用户。  <br/> 若要发布拓扑，则为 Domain Administrators 组和 RTCUniversalServerAdmins 组的成员的用户。  <br/> |[将监视存储与 Skype for Business 服务器中的前端池相关联](associate-a-monitoring-store.md) <br/> |
|**启用相应的监控设置** <br/> |启用全局和/或站点作用域的呼叫详细记录 (CDR) 和/或用户体验质量 (QoE) 监视。  <br/> |为 RTCUniversalServerAdmins 组的用户，或分配有提供对 CsCdrConfiguration 和 CsQoEConfiguration cmdlet 的访问权限的 RBAC 角色的用户。  <br/> |[配置 Skype for Business Server 中的 "呼叫详细记录" 和 "体验质量" 设置](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>启用监控

虽然统一的数据收集代理会在每台前端服务器上自动安装和激活，但这并不意味着你将在完成安装 Skype for Business 服务器时自动开始收集监视数据。 相反，你必须执行两项任务：必须将你的前端服务器/前端池与监控数据库关联，并且必须在全局范围和/或站点范围启用呼叫详细记录 (CDR) 和/或体验质量 (QoE) 监控。

有关将前端服务器或前端池与监视数据库相关联的分步说明，请参阅部署指南中的主题[将监视存储与 Skype For Business 服务器中的前端池相关联](associate-a-monitoring-store.md)。 在创建这些关联后，在新的 Skype for Business 服务器拓扑发布后，你仍然无法收集监视数据。 这是因为，默认情况下，在安装 Skype for Business 服务器时，将禁用 CDR 和 QoE 数据收集。

若要开始数据收集，您将需要启用 CDR 和/或 QoE 监控。 （请注意，你无需同时启用 CDR 和 QoE 监视; 如果你愿意，可以启用一种类型的监视，同时禁用另一种类型。）若要在全局范围内启用 CDR 监视，请从 Skype for Business 服务器管理外壳程序内运行以下命令：

```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

或者，您可以在 Skype for Business Server 控制面板中启用 CDR 监视。 在 "Skype for Business 服务器" 控制面板中，完成以下过程：

1. 单击“**监控**”。

2. 在“**呼叫详细记录**”选项卡上，双击“**全局**”设置。

3. 在“**编辑呼叫详细记录(CDR)设置**”窗格中，选择“**启用 CDR 监控**”，然后单击“**提交**”。

若要在全局范围内启用 QoE 监控，请从 Skype for Business Server Management Shell 中运行此命令：

```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

如果您愿意，也可以在 Skype for Business Server 控制面板中启用 QoE 监控。 从控制面板中，完成以下过程：

1. 单击“**监控**”。

2. 在“**用户体验质量数据**”选项卡上，双击“**全局**”设置。

3. 在“**编辑体验质量(QoE)设置**”窗格中，选择“**启用 QoE 数据监控**”，然后单击“**提交**”。

您已看到，上面的示例在全局范围启用监控；即，它们在贵组织内启用 CDR 和 QoE 监控。 您也可以在站点范围创建单独的 CDR 和 QoE 配置设置，然后有选择地为每个站点启用或禁用监控。 例如，可以为您的 Redmond 站点启用 CDR 监控，而为您的 Dublin 站点禁用 CDR 监控。 有关管理监视配置设置的详细信息，请参阅部署指南主题[配置 Skype For Business 服务器中的 "呼叫详细记录" 和 "体验质量" 设置](call-detail-recording-and-qoe.md)。

## <a name="see-also"></a>另请参阅

[在 Skype for Business 服务器中规划监视](../../plan-your-deployment/monitoring.md)
