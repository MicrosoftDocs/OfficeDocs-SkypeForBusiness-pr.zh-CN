---
title: 规划呼叫数据连接器
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 使用业务联机遥测工具的 Skype 要监视的本地实现在混合方案的概述。
ms.openlocfilehash: 2c491a217f02af77a25f362697e6f89aceb9470c
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2018
ms.locfileid: "25030698"
---
# <a name="plan-call-data-connector"></a>规划呼叫数据连接器

[!INCLUDE [disclaimer](../disclaimer.md)]

## <a name="overview"></a>概述
本主题介绍优点、 规划注意事项和 Skype 实现业务服务器调用数据连接器的要求。 配置呼叫数据连接器的详细信息，请参阅[配置呼叫数据连接器](configure-call-data-connector.md)。

> [!NOTE]
> 在公共预览发布，只呼叫分析仪表板才可用。

调用数据连接器可大大简化呼叫监视混合环境中，因为您不再需要不同的内部部署和联机工具集用于监视所有您用户的呼叫质量。 驻留在本地或联机用户是否，您可以选择要查看为整个组织的呼叫质量。

与调用数据连接器，您可以使用一个工具集执行以下任务：

- 跨 Microsoft 团队、 业务 online Skype 和 Skype 业务 server 监视您的用户体验。

- 查看和解决跨网络问题。

- 为呼叫 Analytics 分配支持人员和管理员角色，以便可以为帮助台工作者可以查看和解决其责任范围提供强大功能。 

使用呼叫数据连接器，业务服务器 Skype 调用将数据推送到云服务，以便您可以利用业务联机呼叫分析 (CA) 和呼叫质量仪表板 (CQD) 的工具，Skype 下图中所示：

![SfB 云语音邮件](../../sfbserver2019/media/call-data-connector-plan-1.png)

服务器将用户体验质量 (QoE) 和呼叫详细信息记录 (CDR) 数据推送到联机服务。

调用分析和 CQD 工具，可以监视呼叫的质量和解决与 Microsoft 团队和 Skype 业务服务的连接问题，如下所示：

- 与特定的呼叫的质量问题上调用分析焦点。 它业务帐户 Skype 中显示有关呼叫和会议的每个用户的详细的信息。  与呼叫分析，就可以与用户然后可以呼叫监视没有访问权限的 Skype 其余业务管理中心的帮助台运算符分配权限。

- 呼叫质量仪表板着重于网络性能和跨组织问题。 为业务管理员和网络工程师 Skype 使用此工具来解决并优化网络性能。

有关详细信息，请参阅[呼叫分析和呼叫质量仪表板](https://docs.microsoft.com/en-us/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)。

当然，您可能想要保留在本地一些呼叫质量数据。 例如，如果与自定义的报告和工作流使用第三方解决方案，这可能是这种情况。  调用数据连接器可以同时还在您的本地服务器上，保留一份数据，如下图中所示配置发送数据的联机服务：

![SfB 云语音邮件](../../sfbserver2019/media/call-data-connector-plan-2.png)


## <a name="requirements"></a>要求

以下要求假定您已有 Skype 业务服务器部署中支持的拓扑。  有关部署 Skype 业务服务器和支持的拓扑的详细信息，请参阅[拓扑基础知识](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics)。

- 混合连接性。 如果您已有 Skype 业务部署的服务器，并且您想要启用呼叫数据连接器，您必须确保已设置您的本地和联机环境之间的混合连接。 此有时也称为拆分域配置。 

   有关详细信息，请参阅[规划之间 Skype Business Server 和 Office 365 的混合连接性](plan-hybrid-connectivity.md)和[Skype Business Server 和 Office 365 之间配置混合连接性](configure-hybrid-connectivity.md)。

- 若要配置呼叫数据连接器，必须对 Office 365 租户，并确保已启用的以下角色：

   - Skype 的业务服务器管理员 
   - Office 365 全局管理员 

- 如果您未，打开呼叫质量仪表板[打开和使用的 Microsoft 团队和 Skype 业务 online 呼叫质量仪表板](/microsoftteams/turning-on-and-using-call-quality-dashboard)中所述。

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>在本地和联机呼叫质量仪表板 (CQD) 的比较报告

| 功能报告 | Skype for Business Online | Skype for Business Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| 应用程序共享指标 |是 | 有限 |
| 客户构建信息| 是 | 是 |
| 深入分析 | 是 | 否 |
| 媒体可靠性指标 | 是 | 有限 |
| 即开报告 | 是 | 是 |
| 概述报告 | 是 | 否 |
| 每用户报告 | 是 | 是 |
| 设置自定义报表 <br> （添加、 删除、 修改报表） | 是 | 是 |
| 基于视频的屏幕共享指标 | 是 | 否 |
| 用于编程访问的数据 Api <br> 到 CQD | 否 | 是 |



















