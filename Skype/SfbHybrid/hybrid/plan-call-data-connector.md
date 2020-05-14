---
title: 规划呼叫数据连接器 |呼叫质量仪表板监控混合分析
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
description: 概述如何使用 Skype for Business Online 遥测工具监视混合方案中的本地实现。
ms.openlocfilehash: 30ff8aebc739e0602f9700cbe9120d230845a023
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221312"
---
# <a name="plan-call-data-connector"></a>规划呼叫数据连接器

## <a name="overview"></a>概述

本主题介绍了实现 Skype for Business Server 呼叫数据连接器的优点、规划注意事项和要求。 有关配置呼叫数据连接器的详细信息，请参阅[Configure Call Data connector](configure-call-data-connector.md)。


呼叫数据连接器极大地简化了混合环境中的呼叫监视，因为您不再需要使用不同的内部部署和联机工具来监视所有用户的呼叫质量。 无论您的用户是驻留在本地还是联机，您都可以选择查看整个组织的呼叫质量。

使用 "呼叫数据连接器"，您可以使用单个工具集执行以下任务：

- 在 Microsoft 团队、Skype for Business Online 和 Skype for Business Server 中监视你的用户体验。

- 查看整个网络中的问题并进行故障排除。

- 为呼叫分析分配帮助台和管理员角色，以便让帮助台工作人员能够查看和解决他们的责任领域。

使用呼叫数据连接器，Skype for Business 服务器将呼叫数据推送到云服务，以便您可以利用 Skype for Business Online 呼叫分析（CA）和通话质量仪表板（CQD）工具，如下图所示：

![SfB 云语音邮件](../../sfbserver2019/media/call-data-connector-plan-1.png)

服务器将体验质量（QoE）和呼叫详细信息记录（CDR）数据推送到在线服务。

通过呼叫分析和 CQD 工具，您可以监控呼叫的质量，并解决 Microsoft 团队和 Skype for business 服务的连接问题，如下所示：

- 呼叫分析重点关注特定呼叫的质量问题。 它显示有关 Skype for Business 帐户中每个用户的呼叫和会议的详细信息。  使用呼叫分析，可以向支持人员操作员分配权限，然后可以在不访问 Skype for business 管理中心的其余部分的情况下监视呼叫。

- 呼叫质量仪表板侧重于整个组织中的网络性能和问题。 Skype for Business 管理员和网络工程师使用此工具对网络性能进行故障排除和优化。

有关详细信息，请参阅[Call Analytics And Call Quality 仪表板](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)。

当然，您可能希望在本地保留一些呼叫质量数据。 例如，如果您使用的是具有自定义报告和工作流的第三方解决方案，则可能会出现这种情况。  呼叫数据连接器允许您配置将数据发送到联机服务，同时还在本地服务器上保留数据的副本，如下图所示：

![SfB 云语音邮件](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>Requirements

以下要求假定您已在受支持的拓扑中部署了 Skype for Business 服务器。  有关部署 Skype for Business Server 和受支持的拓扑的详细信息，请参阅[拓扑基础](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics)。 若要配置呼叫数据连接器，必须执行以下操作：

- 启用混合连接。 如果已部署 Skype for Business Server，并且想要启用呼叫数据连接器，则必须确保在本地和联机环境之间设置混合连接。 这有时称为拆分域配置。

   有关详细信息，请参阅[规划 skype for Business server 与 microsoft 365 或 office 365 之间的混合连接](plan-hybrid-connectivity.md)和[配置 Skype for Business server 与 Microsoft 365 或 office 365 之间的混合连接](configure-hybrid-connectivity.md)。

- 对 Microsoft 365 或 Office 365 组织进行身份验证，并确保已启用以下角色：

  - Skype for Business Server 管理员
  - Microsoft 365 或 Office 365 全局管理员

- 如果尚未执行此操作，请按照[打开和使用 Microsoft 团队和 Skype for Business Online 的通话质量仪表板](/microsoftteams/turning-on-and-using-call-quality-dashboard)中所述，打开呼叫质量仪表板。

- 使用本地 LCSCdr 和 QoEMetrics 数据库启用用于监视的前端池。 如果不这样做，则调用数据连接器将不会有要使用的指标数据。

> [!IMPORTANT]
> 如果前端池上未启用监控，则呼叫数据连接器将无法正常工作。

- 正确配置了[服务器到服务器身份验证](https://docs.microsoft.com/skypeforbusiness/manage/authentication/server-to-server-and-partner-applications)。 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>内部部署和在线通话质量仪表板（CQD）报告的比较

| 功能报告 | Skype for Business Online | Skype for Business Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| 应用程序共享指标 |是 | 范围 |
| 客户建筑物信息| 是 | 是 |
| 深入分析 | 可访问 | 否 |
| 媒体可靠性指标 | 是 | 范围 |
| 开箱即用报告 | 是 | 是 |
| 概述报告 | 可访问 | 否 |
| 每用户报告 | 是 | 是 |
| 报表集自定义 <br> （添加、删除、修改报表） | 是 | 是 |
| 基于视频的屏幕共享指标 | 可访问 | 否 |
| 用于编程访问的数据 Api <br> 到 CQD | 否 | 是 |
||||
