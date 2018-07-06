---
title: 呼叫分析和呼叫质量仪表板
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 了解有关呼叫分析和呼叫质量仪表板以及何时使用它们来监视和解决 Skype for Business 中的呼叫质量问题。
ms.openlocfilehash: 3871db21fef268f9589246b31ee285aa117d0412
ms.sourcegitcommit: 26d93a15c9d4704c08f3fabc5635839ce2456b2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "20205083"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>呼叫分析和呼叫质量仪表板

Microsoft 团队和 for Business 的 Skype 提供两种方法可以监视和解决呼叫质量问题： 呼叫分析和呼叫质量仪表板。 本文介绍这两类，并告诉您何时使用每个。
  
> [!NOTE]
> 呼叫分析现已在 Microsoft 团队和 Skype 的业务管理中心，网址为https://admin.teams.microsoft.com。 调用分析中的可用仅最近 30 天的数据。
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a>什么是呼叫分析，我何时应使用它？

呼叫分析显示设备、 网络和与特定的呼叫和会议中每个用户的 Microsoft 团队或 Skype 业务帐户相关的连接的详细的信息。 如果您是 Office 365 管理员，您可以使用调用分析解决的 Microsoft 团队和 Skype for Business 中的呼叫质量和连接问题。

> [!NOTE]
> 帮助台代理权限和网络拓扑上载中将提供新的管理门户在几个月。

如果您希望非管理员，例如从外部供应商，帮助台代理用于呼叫的分析，就可以分配权限，以便他们可以使用调用分析，但不是能访问业务管理中心的 Skype 的其余部分： 
  
- **第 1 层权限的帮助台代理**： 代理，请参阅一组有限的数据和呼叫分析中的个人身份信息 (PII)。 它们可以解决呼叫，但它们将交给会议问题的第 2 层代理。
    
- **第 2 层权限的帮助台代理**： 代理，请参阅呼叫分析中的所有可用数据和解决呼叫和会议。 拥有完全访问呼叫日志和客户信息。
    
有关设置呼叫分析的详细信息，请参阅[Set up 商业调用分析的 Skype](set-up-call-analytics.md)。 有关帮助台代理与呼叫分析的工作原理的详细信息，请参阅[使用呼叫分析解决质量欠佳的呼叫质量](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>什么是呼叫质量仪表板中，以及何时使用它？

呼叫分析为您提供了有关呼叫质量用户遇到详细的具体信息。 为何用户 Tony Smith 未有此下午质量欠佳的呼叫？ 使用呼叫分析，Microsoft 团队或业务管理员或培训帮助台代理的 Skype 可以调查设备、 网络、 连接和与 Tony 的呼叫相关的其他因素。
  
其中 CA 旨在帮助管理员和帮助台代理排除特定的呼叫，呼叫质量问题呼叫质量仪表板 (CQD) 旨在帮助 Skype 对于业务管理员和网络工程师优化网络。 CQD 从特定的用户将焦点移，而是检查业务组织整个 Skype 聚合信息。 
  
也许 Tony 的质量欠佳的呼叫质量是由于还影响多个其他用户的网络问题。 Tony 的单个呼叫体验不显示在 CQD，但捕获 for Business 使用 Skype 进行的呼叫的总体质量。 与 CQD，总体模式可能成为明显，允许网络工程师进行的呼叫质量的明智的评估。 CQD 提供报告为您提供深入的呼叫质量指标的总体呼叫质量、 服务器到客户端和客户端客户端流和语音质量[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)。 
  
![呼叫质量仪表板中的 Business Admin Center Skype 的屏幕截图。 显示的选项卡是整体呼叫的质量、-客户端，客户端-服务器客户端和视图质量 SLA。](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
有关详细信息，请参阅[业务 online Skype 调用质量仪表板的功能](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD)。
  
呼叫分析和 CQD 并行运行和可在独立或一起使用。 例如，假设 1 层代理确定所需解决呼叫问题的更多帮助。 第 1 层代理传入呼叫发送给第 2 层代理，第 1 层代理比呼叫分析中有权访问的详细信息。 反过来，第 2 层代理可以通知问题的网络工程师。 网络工程师可以检查 CQD 以查看整个网站相关问题可能是参与呼叫问题的原因。
  
有关 CQD 的详细信息，请参阅[打开和使用的 Microsoft 团队和 Skype 业务 online 呼叫质量仪表板](turning-on-and-using-call-quality-dashboard.md)和[维度和度量值的 Microsoft 团队和 Skype 业务 online 呼叫质量仪表板中可用](dimensions-and-measures-available-in-call-quality-dashboard.md)。
  
## <a name="related-topics"></a>相关主题
[设置 Skype for Business 通话分析](set-up-call-analytics.md)

[使用通话分析解决 Skype for Business 通话质量不佳的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

  
 
