---
title: "调用分析和呼叫质量仪表板之间的区别是什么？"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
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
description: "了解如何调用分析和呼叫质量控制板以及何时使用它们来监视并排除在业务的 Skype 通话质量问题。"
ms.openlocfilehash: a17b98451013f24810fd437fa3eb638f98610a8f
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="whats-the-difference-between-call-analytics-and-call-quality-dashboard"></a>调用分析和呼叫质量仪表板之间的区别是什么？

Skype 业务为您提供了两种方法可以监视并排除呼叫质量问题： 调用分析和呼叫质量仪表板。 这篇文章介绍这两类，并告诉您何时使用每个。
  
> [!NOTE]
> 调用分析目前在预览中。 文本和此处所述的图像可能会不匹配您的体验。 
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a>调用的分析，是什么和什么时候应该使用它吗？

调用分析显示有关设备、 网络和连接与特定的电话和 Skype 业务帐户的每个用户的会议详细的信息。 如果您是 Skype 业务管理员，可以使用调用分析诊断 Skype 业务呼叫质量和连接问题。
  
如果想让非管理员，帮助台代理从外部供应商，如用于调用的分析，您可以分配权限，以便他们可以使用调用分析但不是能访问业务管理中心的 Skype 的其余部分： 
  
- **使用第 1 层权限的帮助台代理**： 代理查看一组有限的数据和调用分析中的个人身份信息 (PII)。 它们可以解决电话，但他们将交接问题会议到第 2 层工程师。
    
- **第 2 层的权限与帮助台代理**： 代理查看所有可用的数据调用分析中，并解决联络和会议。 它们具有完全访问权限来调用日志和客户信息。
    
有关调用分析设置的详细信息，请参阅[设置业务调用分析的 Skype](set-up-call-analytics.md)。 有关如何帮助台代理调用分析处理的详细信息，请参阅[使用调用分析诊断较差的呼叫质量](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>呼叫质量面板中，是什么和什么时候应该使用它吗？

调用分析为您提供了有关用户遇到通话质量的详细的具体信息。 为什么用户 Tony Smith 未有差调用此下午？ 使用调用分析，商业管理或经过培训的技术支持代理 Skype 可以调查设备、 网络、 连接性和与 Tony 的调用相关的其他因素。
  
其中 CA 旨在帮助管理员和帮助台代理解决特定呼叫，通话质量问题呼叫质量仪表板 (CQD) 旨在帮助 Skype 业务管理员和网络工程师优化网络。 CQD 从特定用户将焦点移，而是检查整个 Skype 业务组织的聚合信息。 
  
也许 Tony 的差的呼叫质量是由于网络问题，也影响许多其他用户。 Tony 的单个呼叫体验 CQD 中, 看不到但被捕获的业务使用 Skype 电话的整体质量。 使用 CQD，整体模式可能会变得明显，允许网络工程师进行明智的呼叫质量评估。 CQD 提供呼叫质量测量数据，为您提供深入的洞察力的报告总体呼叫质量、 服务器端和客户端客户端流和语音质量[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)。 
  
![在业务管理中心的 Skype 通话质量仪表板的屏幕快照。 选项卡显示所调用的总体质量、 服务器-客户端，客户端-客户端和视图质量 SLA。](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
有关更多详细信息，请参阅[的联机业务 Skype 呼叫质量仪表板的功能](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD)。
  
调用分析和 CQD 并行运行，而且可以单独或一起使用。 例如，假设第 1 层工程师确定他们需要诊断呼叫问题的更多帮助。 第 1 层工程师通过调用第 2 层工程师，第 1 层工程师比调用分析中具有访问权限的详细信息。 反过来，第 2 层工程师可以提醒问题的网络工程师。 网络工程师可能检查 CQD 整体网站有关的问题可能是特约呼叫问题的原因。
  
CQD 有关详细信息，请参阅[打开并使用 Microsoft 小组和 Skype 的在线业务的呼叫质量面板](turning-on-and-using-call-quality-dashboard.md)和[维度和度量值在 Microsoft 小组和 Skype 的在线业务呼叫质量仪表板中可用](dimensions-and-measures-available-in-call-quality-dashboard.md)。
  
## <a name="related-topics"></a>相关主题
[设置 Skype for Business 通话分析](set-up-call-analytics.md)

[使用通话分析解决 Skype for Business 通话质量不佳的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)