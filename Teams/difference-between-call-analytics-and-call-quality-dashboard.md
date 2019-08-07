---
title: 通话分析和通话质量仪表板
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: conceptual
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 了解 "呼叫分析" 和 "呼叫质量" 仪表板以及何时使用它们监视和解决呼叫质量问题。
ms.openlocfilehash: 535d3bf6ce2abf69143fb270e01bf4f0c2e230dc
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2019
ms.locfileid: "34433596"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>通话分析和通话质量仪表板

Microsoft 团队和 Skype for business 为你提供了两种监视和解决通话质量问题的方法: 调用分析和通话质量仪表板 (CQD)。 本文介绍这两种情况, 并告诉你何时使用每一个。

调用分析和 CQD 并行运行, 并且可以独立使用, 也可以一起使用。 例如, 说通信支持专家确定他们需要更多帮助来解决呼叫问题。 通信支持专家将呼叫传递到通信支持工程师, 该工程师可以访问呼叫分析中的更多信息, 而不是通信支持专家。 反过来, 通信支持工程师可以向网络工程师发出警报, 以解决问题。 网络工程师可能会检查 CQD, 以了解整个网站相关问题是否可能是引起呼叫问题的问题。

## <a name="whats-call-analytics-and-when-should-i-use-it"></a>什么是呼叫分析, 何时应使用它？

**"呼叫分析" 现在可在[Microsoft 团队管理中心](https://admin.teams.microsoft.com)中使用。** 若要查看用户的所有呼叫信息和数据, 请使用 "**通话记录**" 选项卡。你可以通过在用户的配置文件页面上搜索用户, 方法是从仪表板中搜索用户或从左侧导航中的**用户**寻找用户来执行此操作。

"呼叫分析" 显示有关与 Microsoft 团队或 Skype for business 帐户中的每个用户的特定呼叫和会议相关的设备、网络和连接的详细信息。 为什么此用户的通话不太好？ 使用呼叫分析, Office 365 管理员或训练有素的帮助台工程师可以调查与他的通话相关的设备、网络、连接和其他因素, 以解决 Microsoft 团队和 Skype for business 中的呼叫质量和连接问题。

若要在 Microsoft 团队管理中心中查看用户的此信息, 请单击用户详细信息页面中该用户的 "**通话记录**" 选项卡, 显示用户在过去30天内参与的所有呼叫和会议。

![所有分析用户数据的屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

若要获取有关给定会话的其他信息 (包括详细媒体和网络统计信息), 请单击某个会话以查看详细信息。

![呼叫分析用户会话数据的屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

如果您希望非管理员 (例如来自外部供应商的支持人员) 使用呼叫分析, 您可以分配权限以便他们可以使用呼叫分析, 但不能访问 Microsoft 团队管理中心的其余部分: 
  
- **支持通信的帮助台代理专业权限**: 代理在 "调用分析" 中看到一组有限的数据和个人身份信息 (PII)。 他们可以对通话进行故障排除, 但他们会将会议问题移交给通信支持工程师。
    
- **支持通信支持工程师权限的帮助台工程师**: 工程师查看呼叫分析中的所有可用数据, 并对通话和会议进行故障排除。 他们拥有通话记录和客户信息的完全访问权限。

> [!NOTE]
> 通信支持专家角色等效于预览门户中的第1层支持角色, 并且通信支持工程师角色等同于预览门户中的第2层支持角色。

有关通信支持专家和通信支持工程师角色的详细信息, 请参阅[使用 Microsoft 团队管理员角色管理团队](using-admin-roles.md)。

> [!IMPORTANT]
> 帮助台代理权限和网络拓扑上载在 Microsoft 团队管理中心中可用。 通信支持专家和通信支持工程师可使用此门户访问呼叫分析和通话质量仪表板。
    
有关设置呼叫分析的详细信息, 请参阅[设置 Skype For Business 呼叫分析](set-up-call-analytics.md)。 有关帮助台代理如何与呼叫分析配合使用的详细信息, 请参阅[使用呼叫分析解决通话质量不佳问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>什么是通话质量仪表板, 何时应使用它？
  
呼叫分析旨在帮助管理员和支持人员工程师解决特定通话的通话质量问题, 通话质量仪表板 (CQD) 旨在帮助团队管理员、Skype for Business 管理员和网络工程师优化网络。 CQD 将焦点从特定用户转移, 而是查看整个团队或 Skype for business 组织的聚合信息。 有关更多详细信息, 请参阅[适用于团队和 Skype for Business Online 的通话质量仪表板的功能](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD)。
  
用户的通话质量可能很差是由于网络问题也会影响其他许多用户。 个人通话体验在 CQD 中不可见, 但捕获使用 Microsoft 团队或 Skype for business 进行的整体通话质量。 有了 CQD, 整体模式可能会变得显而易见, 使网络工程师能够做出明智的通话质量评估。 CQD 提供了通话质量指标的报告, 可帮助你深入了解整个通话质量、服务器客户端流、客户端客户端流和语音质量[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)。
  
![通话质量仪表板的屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

通过 CQD 的位置增强的报表, 可以评估用户建筑物内的聚合呼叫质量和可靠性, 以确定问题是独立于单个用户还是影响更大的用户段。

![通话质量仪表板的位置增强的报表的屏幕截图。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

> [!NOTE]
> 若要在 CQD 中启用生成或特定于终结点的视图, 管理员必须在 CQD 租户数据上载页面上[上载生成或终结点信息](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information)。 

如果希望非管理员 (如帮助台代理) 使用呼叫质量仪表板, 则可以向这些用户分配**团队通信支持工程师**、**团队沟通支持专家**或**报表读者**角色。 具有以下角色的用户可以访问呼叫质量仪表板:

- 全局管理员
- 全局阅读器
- Skype for Business 管理员
- Teams 服务管理员
- Teams 通信管理员
- Teams 通信支持工程师
- 团队沟通支持专家
- 报表读者

> [!NOTE]
> 团队通信支持工程师、团队通信支持专家和报表读者角色无法在 CQD 的租户数据上载页面上修改文件, 也无法为租户激活 CQD。

有关这些角色的详细信息, 请参阅[关于 Office 365 管理员角色](/office365/admin/add-users/about-admin-roles)。

有关 CQD 的详细信息, 请参阅[打开和使用 Microsoft 团队和 skype for Business online 的呼叫质量仪表板](turning-on-and-using-call-quality-dashboard.md)和[Microsoft 团队和 Skype for Business Online 的通话质量仪表板中提供](dimensions-and-measures-available-in-call-quality-dashboard.md)的 skype For business online 和维度和度量。
  
## <a name="related-topics"></a>相关主题

[视频: 通话质量概述](https://aka.ms/teams-quality)

[设置通话分析](set-up-call-analytics.md)

[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[打开和使用 Microsoft 团队和 Skype for business Online 的通话质量仪表板](turning-on-and-using-call-quality-dashboard.md)
