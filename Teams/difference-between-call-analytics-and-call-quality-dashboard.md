---
title: 通话分析和通话质量仪表板
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: conceptual
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 了解有关呼叫分析和呼叫质量仪表板以及何时使用它们来监视和解决呼叫质量问题。
ms.openlocfilehash: c85bcecd31c978616e5394740efac6bb5c28c07c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199792"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>通话分析和通话质量仪表板

Microsoft 团队和 for Business 的 Skype 提供两种方法可以监视和解决呼叫质量问题： 呼叫分析和呼叫质量仪表板 (CQD)。 本文介绍这两类，并告诉您何时使用每个。

呼叫分析和 CQD 并行运行和可在独立或一起使用。 例如，假设 communications 支持专家确定所需解决呼叫问题的更多帮助。 Communications 支持专家将传递对通信支持工程师，哪些人有权调用分析中的信息比通信支持专业人员的调用。 反过来，communications 支持工程师可以通知问题的网络工程师。 网络工程师可能会检查 CQD 以查看整个网站相关问题可能是参与呼叫问题的原因。

## <a name="whats-call-analytics-and-when-should-i-use-it"></a>什么是呼叫分析，我何时应使用它？

**呼叫分析现已推出[Microsoft 团队管理中心](https://admin.teams.microsoft.com)中。** 若要查看的所有呼叫信息和用户的数据，请使用**通话记录**选项卡。您可以通过仪表板用户可以搜索用户的配置文件页上查找或**用户**的左侧导航中查找用户执行此操作。

呼叫分析显示设备、 网络和与特定的呼叫和会议中每个用户的 Microsoft 团队或 Skype 业务帐户相关的连接的详细的信息。 此用户未为什么必须质量欠佳的呼叫下午的？ 使用呼叫分析，Office 365 管理员或培训帮助台代理可以调查设备、 网络、 连接和解决的 Microsoft 团队和 Skype for Business 中的呼叫质量和连接问题其呼叫相关的其他因素。

若要查看此信息的用户的 Microsoft 团队管理中心中，单击**呼叫历史记录**选项卡中的用户详细信息页，显示该用户参与 30 天内的所有呼叫和会议的用户。

![调用分析用户数据。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

要获取有关给定会话包括详细的媒体和网络统计信息的其他信息，请单击的会话，若要查看的详细信息。

![调用分析用户会话数据。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

如果您希望非管理员，例如从外部供应商，帮助台代理用于呼叫的分析，就可以分配权限，以便他们可以使用调用分析，但不是能访问的 Microsoft 团队管理中心的其余部分： 
  
- **通过通信帮助台代理支持专员权限**： 代理，请参阅一组有限的数据和呼叫分析中的个人身份信息 (PII)。 它们可以解决呼叫，但它们将交给会议问题的通信支持工程师。
    
- **通过通信帮助台代理支持工程师权限**： 代理，请参阅呼叫分析中的所有可用数据和解决呼叫和会议。 拥有完全访问呼叫日志和客户信息。

> [!NOTE]
> Communications 支持专家角色等效从预览门户第 1 层支持角色和 communications 支持工程师角色等效从预览门户第 2 层支持角色。

有关 communications 支持专家和通信支持工程师角色，请参阅[管理团队使用的 Microsoft 团队管理角色](using-admin-roles.md)。

> [!IMPORTANT]
> 帮助台代理权限和网络拓扑上载在管理中心中的 Microsoft 团队是可用。 Communications 支持专家和 Communications 支持工程师可以使用此门户访问呼叫分析和呼叫质量仪表板。
    
有关设置呼叫分析的详细信息，请参阅[Set up 商业调用分析的 Skype](set-up-call-analytics.md)。 有关帮助台代理与呼叫分析的工作原理的详细信息，请参阅[使用呼叫分析解决质量欠佳的呼叫质量](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>什么是呼叫质量仪表板中，以及何时使用它？
  
调用分析旨在帮助管理员，帮助台代理诊断与特定的呼叫的呼叫质量问题，而呼叫质量仪表板 (CQD) 旨在帮助团队 admins，对于业务管理员 Skype 和网络工程师优化网络。 CQD 从特定的用户将焦点移和改为查看聚合信息针对整个团队或 Skype 业务组织。 有关详细信息，请参阅[呼叫质量仪表板个团队和 Skype 业务 online 的功能](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD)。
  
也许用户的质量欠佳的呼叫质量是由于还影响多个其他用户的网络问题。 单个呼叫体验不显示在 CQD，但捕获 for Business 中使用的 Microsoft 团队或 Skype 所做的呼叫的总体质量。 与 CQD，总体模式可能成为明显，允许网络工程师进行的呼叫质量的明智的评估。 CQD 提供报告为您提供深入的呼叫质量指标的总体呼叫质量、 服务器到客户端流、 客户端客户端流和语音质量[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)。
  
![呼叫质量仪表板的屏幕截图。 显示的选项卡是整体呼叫的质量、-客户端，客户端-服务器客户端和语音质量 SLA。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

借助 CQD 的 Location-Enhanced 报告，可以评估聚合呼叫质量和可靠性中用户的构建以确定问题是否被隔离到单个用户，或者影响的用户更大条线段。

![呼叫质量仪表板位置增强报告的屏幕截图。 显示的选项卡是概述，建筑物-有线，建筑物-WiFi 和 Mobile (LTE)。 正在应用筛选器以查看特定大厦内的流。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

> [!NOTE]
> 若要启用 CQD 中构建或特定于终结点的视图，管理员必须在 CQD 的租户数据上载页上的[上载构建或终结点的信息](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information)。 

如果您希望非管理员，帮助台代理，如用于呼叫质量仪表板中，您可以分配这些用户的**团队 Communications 支持工程师**、**团队 Communications 支持专员**或**报告读者**角色。 具有以下角色的用户可以访问呼叫质量仪表板：

- 全局管理员
- Skype 的业务管理员
- Teams 服务管理员
- Teams 通信管理员
- Teams 通信支持工程师
- 团队 Communications 支持专家
- 报告读者

> [!NOTE]
> 团队 Communications 支持工程师、 团队 Communications 支持专家，和报告读者角色不能修改 CQD 的租户数据上载页面上的文件也不激活 CQD 租户。

有关这些角色的详细信息，请参阅[有关 Office 365 管理员角色](/office365/admin/add-users/about-admin-roles)。

有关 CQD 的详细信息，请参阅[打开和使用的 Microsoft 团队和 Skype 业务 online 呼叫质量仪表板](turning-on-and-using-call-quality-dashboard.md)和[维度和度量值的 Microsoft 团队和 Skype 业务 online 呼叫质量仪表板中可用](dimensions-and-measures-available-in-call-quality-dashboard.md)。
  
## <a name="related-topics"></a>相关主题

[视频： 呼叫质量概述](https://aka.ms/teams-quality)

[设置通话分析](set-up-call-analytics.md)

[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[打开和使用呼叫质量仪表板的 Microsoft 团队和 Skype 业务 online](turning-on-and-using-call-quality-dashboard.md)
