---
title: 规划呼叫数据连接器|呼叫质量仪表板监视混合分析
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Overview of using Skype for Business Online telemetry tools to monitor an on-premises implementation in a hybrid scenario.
ms.openlocfilehash: a0288f07c942f003cfece5aceaddf4139af84569
ms.sourcegitcommit: 9fcd9a7ae78e04cef90415c2a0f30a98fbf8270f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2021
ms.locfileid: "58407171"
---
# <a name="plan-call-data-connector"></a>规划呼叫数据连接器

## <a name="overview"></a>概述

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本主题介绍实施呼叫数据连接器的好处、规划注意事项Skype for Business Server要求。 有关配置呼叫数据连接器的信息，请参阅配置 [呼叫数据连接器](configure-call-data-connector.md)。


呼叫数据连接器极大地简化了混合环境中呼叫监控，因为不再需要使用不同的本地和联机工具集来监视所有用户的呼叫质量。 无论用户是在本地还是联机，都可以选择在线查看整个组织的通话质量。

使用呼叫数据连接器，可以使用单个工具集执行以下任务：

- 监视跨 Microsoft Teams、Skype for Business Online 和 Skype for Business Server 的用户体验。

- 查看并排查整个网络的问题。

- 为呼叫分析分配支持人员角色和管理员角色，以便支持人员可以查看他们的责任领域并排除其故障。

借助呼叫数据连接器，Skype for Business Server 将呼叫数据推送到云服务，以便你可以利用 Skype for Business Online Call Analytics (CA) 和呼叫质量仪表板 (CQD) 工具，如下图所示：

![SfB 云语音邮件图表。](../../sfbserver2019/media/call-data-connector-plan-1.png)

服务器将用户体验质量 (QoE) 和呼叫详细信息记录 (CDR) 数据推送到联机服务。

通话分析和 CQD 工具使您能够监视通话质量，并解决 Microsoft Teams 和 Skype for Business 服务的连接问题，如下所示：

- 通话分析侧重于特定通话的质量问题。 它显示有关用户帐户中每个用户的呼叫和会议Skype for Business的详细信息。  借助通话分析，你可以将权限分配给支持人员，该接线员随后可以监视呼叫，而无需访问管理中心Skype for Business的其余部分。

- 通话质量仪表板重点关注整个组织的网络性能和问题。 Skype for Business管理员和网络工程师使用此工具对网络性能进行故障排除和优化。

有关详细信息，请参阅 Call [Analytics 和 Call Quality Dashboard diagram with Monitoring Server details。](/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)

当然，你可能想要在本地保留一些通话质量数据。 例如，如果您将第三方解决方案与自定义报表和工作流一同使用，则可能会这样。  呼叫数据连接器允许你配置向联机服务发送数据，同时在本地服务器上保留数据副本，如下图所示：

![SfB 云语音邮件](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>要求

以下要求假定你已在Skype for Business Server拓扑中部署。  有关部署支持的拓扑Skype for Business Server，请参阅[Topology Basics](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md)。 若要配置呼叫数据连接器，您必须：

- 启用混合连接。 如果已部署Skype for Business Server，并且要启用呼叫数据连接器，则必须确保在本地环境和联机环境之间设置了混合连接。 这有时称为拆分域配置。

   有关详细信息，请参阅 Plan [hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md)和[Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md)。

- 向组织Microsoft 365 Office 365身份验证，并确保启用了以下角色：

  - Skype for Business Server管理员
  - Microsoft 365全局Office 365或全局管理员

- 如果尚未打开，请打开呼叫质量仪表板，如打开和使用呼叫质量仪表板[进行](/microsoftteams/turning-on-and-using-call-quality-dashboard)Microsoft Teams 和 Skype for Business Online 中所述。

- 使用本地 LCSCdr 和 QoEMetrics 数据库启用前端池进行监控。 如果没有这一点，呼叫数据连接器将没有要处理的指标数据。

> [!IMPORTANT]
> 如果未在前端池上启用监控，呼叫数据连接器将无法正常工作。

- 正确配置 [了服务器到服务器身份验证](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md)。 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>本地和在线通话质量仪表板与 CQD (比较) 报告

| 功能报告 | Skype for Business Online | Skype for Business Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| 应用程序共享指标 |是 | 受限 |
| 客户构建信息| 是 | 是 |
| 向下钻取分析 | 是 | 否 |
| 媒体可靠性指标 | 是 | 受限 |
| 开箱后报告 | 是 | 是 |
| 概述报告 | 是 | 否 |
| 每用户报告 | 是 | 是 |
| 报告集自定义 <br>  (、删除、修改报告)  | 是 | 是 |
| 基于视频的屏幕共享指标 | 是 | 否 |
| 用于编程访问的数据 API <br> 到 CQD | 否 | 是 |
||||