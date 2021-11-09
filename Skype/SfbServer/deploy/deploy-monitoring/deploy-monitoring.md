---
title: 在远程部署Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 摘要：了解如何在 Skype for Business Server 中部署监控。
ms.openlocfilehash: 5e3fdf468067b707ee1dd97c5458f3612d78653d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855076"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>在远程部署Skype for Business Server

**摘要：** 了解如何在部署中部署Skype for Business Server。

在执行这些任务之前，请查看规划[Skype for Business Server。](../../plan-your-deployment/monitoring.md)

通常，您将通过完成以下两个步骤在拓扑中实施监控服务：

1. 在设置新池的同时启用监控Skype for Business Server池。  (在 Skype for Business Server 中，按池启用或禁用监控。) 请注意，您可以为池启用监控，而无需实际收集监控数据，本文档的"配置呼叫详细记录和用户体验质量 设置"一节中介绍了此过程。

2. 使监控存储（即，监控数据库）与新池关联。请注意，一个监控存储可与多个池关联。根据驻留在注册器池中的用户数，这意味着，您不必为每个池设置单独的监控数据库。一个监控存储可供多个池使用。

尽管在创建新池的同时启用监控通常更为简单，但也可以创建新池并禁用监控。 如果执行此操作，以后可以使用拓扑生成器启用该服务：拓扑生成器提供为池启用或禁用监控或将池与不同监控存储关联的方式。 请记住，即使不再具有监控服务器角色，您仍然需要创建一个或多个监控存储：用于存储监控服务收集的数据的后端数据库。 这些后端数据库可以使用 Microsoft SQL Server 2008 R2、Microsoft SQL Server 2012、Microsoft SQL Server 2014 或 Microsoft SQL Server 2019 创建。

> [!NOTE]
> 如果为池启用了监控，您可以禁用收集监控数据的过程，而无需更改拓扑：Skype for Business Server 提供了一种禁用 (然后稍后重新启用) 呼叫详细信息记录 (CDR) 或用户体验质量 (QoE) 数据收集的方法。 有关详细信息，请参阅本文的“配置呼叫详细记录和用户体验质量设置”部分。

Skype for Business Server 中监控的另一个重要增强功能是，Skype for Business Server 监控报告现在支持 IPv6：使用 IP 地址字段的报告将显示 IPv4 或 IPv6 地址，具体取决于：1) 使用的 SQL 查询;和 2) IPv6 地址是否存储在监控数据库中。

> [!NOTE]
> 确保 SQL Server 代理服务启动类型为"自动"，并且 SQL Server 代理服务为包含监控数据库的 SQL 实例运行，以便默认监控 SQL Server 维护作业可以在 SQL Server 代理服务的控制下按计划运行。

本文档将指导您完成安装和配置监控报告以及监控报告Skype for Business Server。 本文提供了会对您有所帮助的分步说明：

- 在拓扑中启用监控并使监控存储与前端池关联。

- 安装SQL Server Reporting Services监控Skype for Business Server报告。 监控报告是预配置的报告，其中提供不同视图，便于查看监控数据库中存储的信息。

- 配置 QoE (QOE) 的呼叫详细信息记录和 (用户体验) 记录。 呼叫详细信息记录提供了一种跟踪呼叫功能Skype for Business Server，例如 IP 语音 (VoIP) 呼叫;即时消息传输 (IM) ;文件传输;音频/视频 (A/V) 会议;和应用程序共享会话。 QoE 指标跟踪在组织内进行的音频和视频呼叫的质量，包括丢失的网络数据包数、背景噪音和“抖动”量（数据包延迟的差异）等内容。

- 从监控数据库中手动清除 CDR 和/或 QoE 记录。

## <a name="deployment-checklist-for-monitoring"></a>用于监视的部署清单

尽管已在每台前端服务器上安装并激活了监控，但您仍然必须先执行几个步骤，然后才能实际收集监控数据的 Skype for Business Server。 以下清单中概述了这些步骤：

|**阶段**|**步骤**|**角色和组成员身份**|**文档**|
|:-----|:-----|:-----|:-----|
|**安装必备软硬件** <br/> |在将充当要进行监视的后端数据存储的计算机上安装受支持版本的 Microsoft SQL Server。  <br/> |还是本地管理员组的成员的域用户。  <br/> |[支持的硬件](/previous-versions/office/lync-server-2013/lync-server-2013-supported-hardware) <br/> [服务器软件和基础结构支持](/previous-versions/office/lync-server-2013/lync-server-2013-server-software-and-infrastructure-support) <br/> |
|**创建相应的内部拓扑以支持监控** <br/> |使用Skype for Business Server生成器将监控数据库添加到拓扑，然后发布更新的拓扑。  <br/> |若要定义拓扑，则为是本地用户组成员的用户。  <br/> 若要发布拓扑，则为 Domain Administrators 组和 RTCUniversalServerAdmins 组的成员的用户。  <br/> |[将监控存储与池中的前端池Skype for Business Server](associate-a-monitoring-store.md) <br/> |
|**启用相应的监控设置** <br/> |在全局和/或 (范围内启用呼叫详细信息记录) CDR (QoE) 监控用户体验和/或用户体验质量。  <br/> |为 RTCUniversalServerAdmins 组的用户，或分配有提供对 CsCdrConfiguration 和 CsQoEConfiguration cmdlet 的访问权限的 RBAC 角色的用户。  <br/> |[配置呼叫详细信息记录和用户体验质量设置Skype for Business Server](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>启用监控

尽管会在每台前端服务器上自动安装并激活统一数据收集代理，但这并不意味着您将在安装完统一数据之后自动开始收集Skype for Business Server。 相反，您必须执行两项操作：必须将前端服务器/前端池与监控数据库关联，并且必须在全局范围和/或站点范围启用呼叫详细记录 (CDR) 和/或用户体验质量 (QoE) 监控。

有关将前端服务器或前端池与监控数据库关联的分步说明，请参阅部署指南中的主题将监控存储与[](associate-a-monitoring-store.md)Skype for Business Server 中的前端池关联。 建立这些关联后，发布新的 Skype for Business Server 拓扑后，您仍无法收集监控数据。 这是因为默认情况下，在安装 CDR 和 QoE 数据收集时，会Skype for Business Server。

若要开始数据收集，您将需要启用 CDR 和/或 QoE 监控。  (请注意，不需要同时启用 CDR 和 QoE 监控;如果您愿意，您可以启用一种类型的监控，同时禁用另一种类型。) 若要在全局范围启用 CDR 监控，请从命令行管理程序内部运行以下Skype for Business Server命令：

```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

或者，也可以从"控制面板"中Skype for Business Server CDR 监控。 从"Skype for Business Server控制面板"中，完成以下过程：

1. 单击“监控”。

2. 在“呼叫详细记录”选项卡上，双击“全局”设置。

3. 在“编辑呼叫详细记录(CDR)设置”窗格中，选择“启用 CDR 监控”，然后单击“提交”。

若要在全局范围启用 QoE 监控，请从命令行管理程序Skype for Business Server此命令：

```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

如果愿意，还可以从"控制面板"中Skype for Business Server QoE 监控。 从控制面板中，完成以下过程：

1. 单击“监控”。

2. 在“用户体验质量数据”选项卡上，双击“全局”设置。

3. 在“编辑体验质量(QoE)设置”窗格中，选择“启用 QoE 数据监控”，然后单击“提交”。

您已看到，上面的示例在全局范围启用监控；即，它们在贵组织内启用 CDR 和 QoE 监控。 您也可以在站点范围创建单独的 CDR 和 QoE 配置设置，然后有选择地为每个站点启用或禁用监控。 例如，可以为您的 Redmond 站点启用 CDR 监控，而为您的 Dublin 站点禁用 CDR 监控。 有关管理监控配置设置的详细信息，请参阅部署指南主题 Configure [call detail recording and Quality of Experience settings in Skype for Business Server](call-detail-recording-and-qoe.md)。

## <a name="see-also"></a>另请参阅

[规划在 Skype for Business Server](../../plan-your-deployment/monitoring.md)