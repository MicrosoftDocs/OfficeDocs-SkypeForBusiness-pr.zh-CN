---
title: 使用通话分析来排查通话质量不良问题
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 03/08/2019
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
ms.custom:
- Reporting
description: 使用有关设备、网络和连接的呼叫分析详细信息来解决与 Microsoft 团队和 Skype for business 通话和会议有关的用户问题。
ms.openlocfilehash: 2255afa0c2af8e1c672c2830009cfb34921ceed9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288193"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>使用通话分析来排查通话质量不良问题

呼叫分析可帮助你解决 Microsoft 团队和 Skype for business 的通话或连接问题。 "呼叫分析" 显示有关 Office 365 帐户中每个用户的呼叫和会议的设备、网络和连接的详细信息。 如果 "生成"、"网站" 和 "租户" 信息已添加到调用分析, 则它还将针对每个通话和会话显示。 通过呼叫分析提供的信息可以帮助你了解为什么用户的通话或会议体验不佳的原因。 
  
## <a name="call-analytics-permissions"></a>调用分析权限

作为管理员, 你可以完全访问呼叫分析的所有功能。 此外, 你可以将 Azure Active Directory 角色分配给支持人员。 将团队通信支持专家角色分配给应具有有限视图的调用分析的用户。 将团队通信支持工程师角色分配给需要访问调用分析的完整功能的用户。 这两个权限级别阻止访问 Microsoft 团队管理中心的其余部分。

通信支持专家处理基本的通话质量问题。 他们不会调查会议问题。 而是收集相关信息, 然后升级到通信支持工程师。 通信支持工程师查看有关通信支持专家隐藏的详细通话记录中的信息。 下表简要介绍了在使用呼叫分析时, 通信支持专家和通信支持工程师可使用的信息。

分配给你的权限级别确定在呼叫分析中你有权访问的信息类型:
  
- **团队服务管理员或团队通信管理员**: 您有权访问呼叫分析和 Microsoft 团队管理中心中的所有信息。
    
- **团队通信支持专家**: 在 "调用分析" 中看到一组有限的数据。 你可以对通话进行故障排除, 但你将向团队通信支持工程师分发会议问题。 您无法访问 Microsoft 团队管理中心的其余部分。
    
- **团队通信支持工程师**: 查看呼叫分析中的所有可用数据, 并可帮助解决与通话和会议有关的问题。 您无法访问 Microsoft 团队管理中心的其余部分。
    
> [!NOTE]
> 通信支持专家角色等效于第1层支持, 而通信支持工程师角色等效于第2层支持。

有关团队管理员角色的详细信息, 请参阅[使用 Microsoft 团队管理员角色管理团队](using-admin-roles.md)。 有关团队通信支持专家和团队通信支持工程师角色的详细比较, 请参阅[设置呼叫分析](set-up-call-analytics.md#set-call-analytics-permissions) 
  
如果需要有关权限的帮助, 请查看你的团队和 Skype for business 管理员。
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>使用呼叫分析解决通话质量问题

1. 通过团队通信支持或团队管理员凭据登录。

2. 在 web 浏览器中, *https://admin.teams.microsoft.com*转到。
    
3. 在**仪表板**上的 "**用户搜索**" 中, 开始键入要对其进行故障排除的用户的名称或 sip 地址, 或选择 "**查看用户**" 以查看用户列表。
    
    ![Microsoft 团队管理中心中的调用分析的用户搜索框的屏幕截图。](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. 从列表中选择用户。

5. 选择 "**呼叫历史记录**", 然后选择要进行故障排除的呼叫或会议。
    
    ![屏幕截图显示用户的 "通话历史记录" 页面。](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. 选择 "**高级**" 选项卡, 然后查找表示通话质量不佳或连接问题的黄色和红色项目。
    
    在每个通话或会议的 "会话详细信息" 中, 小问题显示为黄色。 (例如, 在以下屏幕截图中, 对于平均抖动、最大抖动和平均数据包丢失率, 这些值为黄色。)如果某个内容为黄色, 则它不在正常范围内, 它可能会导致问题, 但不太可能是问题的主要原因。 如果出现红色, 这是一个重大问题, 这很可能是本次会议的通话质量不佳的主要原因。 
    
    ![屏幕截图显示用户通话记录的 "高级" 选项卡 ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
在极少数情况下, 音频会话的体验数据质量未收到。 这通常是由呼叫丢弃并与客户端的连接引起的。 出现这种情况时,**无法使用**"会话分级"。
  
对于具有体验质量 (QoE) 数据的音频会话, 下表介绍了将会话限定为**差**的主要问题。
  
|**问题**|**区域**|**说明**|
|:-----|:-----|:-----|
|呼叫设置  <br/> |Session  <br/> |错误代码 Ms-诊断20-29 指示呼叫设置失败。 用户无法加入呼叫或会议。  <br/> |
|音频网络分类差通话  <br/> |Session  <br/> |遇到网络质量问题 (如数据包丢失、抖动、NMOS 下降、RTT 或隐藏比率)。 有关用于对不太好的通话进行分类的条件的详细信息, 请参阅此[Microsoft 博客文章](https://go.microsoft.com/fwlink/p/?linkid=852133)。  <br/> |
|设备不起作用  <br/> |Device  <br/> | 设备不能正常工作。 设备的运行比率为: <br/>  DeviceRenderNotFunctioningEventRatio > = 0.005 <br/>  DeviceCaptureNotFunctioningEventRatio > = 0.005 <br/> |
   
## <a name="related-topics"></a>相关主题
[设置通话分析](set-up-call-analytics.md)

[通话分析和通话质量仪表板](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
