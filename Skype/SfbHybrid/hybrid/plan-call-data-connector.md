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
ms.openlocfilehash: f47f0969d102408299678842b18bb503eaf6aea0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110548"
---
# <a name="plan-call-data-connector"></a>规划呼叫数据连接器

## <a name="overview"></a>概述

本主题介绍实施 Skype for Business Server 呼叫数据连接器的好处、规划注意事项和要求。 有关配置呼叫数据连接器的信息，请参阅配置 [呼叫数据连接器](configure-call-data-connector.md)。


呼叫数据连接器极大地简化了混合环境中呼叫监控，因为不再需要使用不同的本地和联机工具集来监视所有用户的呼叫质量。 无论用户是在本地还是联机，都可以选择在线查看整个组织的通话质量。

使用呼叫数据连接器，可以使用单个工具集执行以下任务：

- 监视 Microsoft Teams、Skype for Business Online 和 Skype for Business Server 中的用户体验。

- 查看并排查整个网络的问题。

- 为呼叫分析分配支持人员角色和管理员角色，以便支持人员可以查看他们的责任领域并排除其故障。

通过呼叫数据连接器，Skype for Business Server 将呼叫数据推送到云服务，以便你可以利用 Skype for Business Online 呼叫分析 (CA) 和呼叫质量仪表板 (CQD) 工具，如下图所示：

![SfB 云语音邮件](../../sfbserver2019/media/call-data-connector-plan-1.png)

服务器将用户体验质量 (QoE) 和呼叫详细信息记录 (CDR) 数据推送到联机服务。

通话分析和 CQD 工具使你可以监视通话质量，并解决 Microsoft Teams 和 Skype for Business 服务的连接问题，如下所示：

- 通话分析侧重于特定通话的质量问题。 它显示有关 Skype for Business 帐户中每个用户的呼叫和会议的详细信息。  借助通话分析，你可以向支持人员分配权限，支持人员可以监视呼叫，而无需访问 Skype for Business 管理中心的其余部分。

- 通话质量仪表板重点关注整个组织的网络性能和问题。 Skype for Business 管理员和网络工程师使用此工具对网络性能进行故障排除和优化。

有关详细信息，请参阅通话 [分析和通话质量仪表板](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)。

当然，你可能希望在本地保留一些通话质量数据。 例如，如果您将第三方解决方案与自定义报表和工作流一同使用，则可能会这样。  呼叫数据连接器允许你配置向联机服务发送数据，同时在本地服务器上保留数据副本，如下图所示：

![SfB 云语音邮件](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>要求

以下要求假定你已在支持的拓扑中部署了 Skype for Business Server。  有关部署 Skype for Business Server 和支持的拓扑结构的信息，请参阅 [Topology Basics](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md)。 若要配置呼叫数据连接器，您必须：

- 启用混合连接。 如果你已部署 Skype for Business Server 并且想要启用呼叫数据连接器，则必须确保在本地环境和联机环境之间设置了混合连接。 这有时称为拆分域配置。

   有关详细信息，请参阅规划 Skype for Business Server 与 [Microsoft 365 或 Office 365](plan-hybrid-connectivity.md) 之间的混合连接和配置 Skype for Business Server 与 [Microsoft 365 或 Office 365](configure-hybrid-connectivity.md)之间的混合连接。

- 向 Microsoft 365 或 Office 365 组织进行身份验证，并确保已启用以下角色：

  - Skype for Business Server 管理员
  - Microsoft 365 或 Office 365 全局管理员

- 如果尚未打开，请打开通话质量仪表板，如打开和使用 Microsoft Teams 和 Skype for Business Online 的通话质量 [仪表板中所述](/microsoftteams/turning-on-and-using-call-quality-dashboard)。

- 使用本地 LCSCdr 和 QoEMetrics 数据库启用监控的前端池。 如果没有这一点，呼叫数据连接器将没有要处理的指标数据。

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