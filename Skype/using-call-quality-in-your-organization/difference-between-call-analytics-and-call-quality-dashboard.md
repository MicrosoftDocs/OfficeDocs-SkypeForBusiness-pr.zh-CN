---
title: "呼叫分析和呼叫质量仪表板之间的区别是什么？"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 5/31/2017
ms.audience: Admin
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
description: "Learn about Call Analytics and Call Quality Dashboard and when to use them to monitor and troubleshoot call-quality problems in Skype for Business."
---

# 呼叫分析和呼叫质量仪表板之间的区别是什么？

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
Skype for Business为您提供了两种方法可以监控和呼叫质量问题疑难解答︰ 呼叫分析和呼叫质量仪表板。本文介绍这两种，并告诉您何时使用每个区域。
  
> [!NOTE]
> 正在预览呼叫分析。文本和图像此处所述可能与您的体验。 
  
## 什么是呼叫分析，以及何时使用它？

呼叫分析显示有关设备、 网络和连接到的特定呼叫和会议的Skype for Business帐户中的每个用户相关的详细的信息。如果您是Skype for Business管理员，您可以使用呼叫分析Skype for Business呼叫质量和连接问题疑难解答。
  
如果您希望非管理员，例如技术支持人员代理从外部的供应商，要使用呼叫分析，您可以分配权限，以便他们可以使用呼叫分析，但不是能访问Skype for Business管理中心中的其余部分︰
  
- **技术支持人员代理层 1 权限** ︰ 代理看到一组有限的数据和个人身份信息 (PII) 在呼叫分析。他们可以解决呼叫，但它们将交给问题会议 2 层工程师。
    
- **技术支持人员代理层 2 权限** ︰ 代理查看所有可用的数据，在呼叫分析和疑难解答呼叫和会议。他们拥有完全访问权限来呼叫日志和客户的信息。
    
有关呼叫分析设置的详细信息，请参阅[设置 Skype for Business 呼叫分析](set-up-skype-for-business-call-analytics.md)。有关如何技术支持人员代理可以处理呼叫分析的详细信息，请参阅[使用呼叫分析来进行故障排除较差 Skype for Business 呼叫质量](use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality.md)。
  
## 什么是呼叫质量面板中，以及何时使用它？

呼叫分析提供有关呼叫质量经验丰富的用户的详细的特定信息。为什么用户 Tony Smith 是否有不佳呼叫下午？使用呼叫分析， Skype for Business管理员或培训的技术支持人员代理可以调查设备、 网络、 连接以及与 Tony 的呼叫相关的其他因素。
  
可以在其中 CA 旨在帮助管理员和技术支持人员代理的疑难解答呼叫质量特定呼叫、 呼叫质量仪表板 (CQD) 旨在帮助Skype for Business管理员和网络工程师优化网络。CQD 从特定用户将焦点移，而是检查聚合为整个Skype for Business组织信息。
  
也许 Tony 的较差的呼叫质量是由于网络问题，还会影响许多其他用户。Tony 的单个调用体验未显示在 CQD，但使用Skype for Business进行呼叫的整体质量，将捕获。CQD，与整体模式可能会很明显，从而网络工程师，以使明智的评估的呼叫质量。 CQD 提供让您的见解的呼叫质量度量的报表整体呼叫质量、 客户端服务器和客户端流和语音质量[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)。
  
![Screenshot of Call Quality Dashboard in the Skype for Business Admin Center. Tabs shown are Overall Call Quality, Server - Client, Client - Client, and View Quality SLA.](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
有关详细信息，请参阅[Skype for Business Online 呼叫质量仪表板的功能](turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-bu.md#BKMK_FeaturesOfTheCQD)。
  
呼叫分析和 CQD 并行运行，并且可以单独或一起使用。例如，假设 1 层工程师确定他们需要疑难解答呼叫问题的更多帮助。第 1 层工程师传递给第 2 层代理，呼叫分析中有权访问的详细信息，第 1 层工程师比呼叫。反过来，第 2 层代理可以通知网络工程师到问题。网络工程师可能检查 CQD 以查看是否整体网站相关问题可能是调用问题特约原因。
  
有关 CQD 的详细信息，请参阅[打开并使用 Microsoft 团队和 Skype for Business Online 的呼叫质量仪表板](turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-bu.md)和[维度和度量值提供为 Microsoft 团队呼叫质量仪表板和 Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard-for-microsoft-teams.md)。
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

