---
title: 使用呼叫分析解决较差的通话质量
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: 使用有关设备、网络和连接的每用户呼叫分析详细信息，解决与 Microsoft 团队通话和会议有关的用户问题。
ms.openlocfilehash: 8bee41e79f2610adcb9a1fed3f895c728526f5ea
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583621"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>使用呼叫分析解决较差的通话质量

本文介绍如果你是团队管理员或团队沟通支持专家或工程师，如何使用呼叫分析来解决对单个用户的不良 Microsoft 团队通话或会议质量问题。


  
## <a name="call-analytics-permissions"></a>调用分析权限

本文假定你已设置呼叫分析。 如果您没有，请阅读[为团队设置呼叫分析](set-up-call-analytics.md)。

## <a name="introduction-to-call-analytics"></a>通话分析简介

通话分析显示有关团队使用 Office 365 帐户中的每个用户的呼叫和会议的详细信息。 其中包括有关设备、网络、连接和通话质量的信息 (其中任何一项都可能是较差的通话或会议质量) 因素。 如果你上载建筑物、网站和租户信息，还将为每个呼叫和会议显示此信息。 使用呼叫分析可帮助你了解为什么用户通话或会议体验不佳的原因。

"呼叫分析" 显示通话或会议的每个腿，例如，从一个参与者到第二个参与者。 通过分析这些详细信息，团队管理员可以隔离问题区域并确定质量较差的根本原因。
   
作为团队管理员，您可以完全访问每个用户的所有呼叫分析数据。 此外，你可以将 Azure Active Directory 角色分配给支持人员。 若要了解有关这些角色的详细信息，请参阅[向支持人员和帮助台人员提供权限](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)。 不要错过[每个团队支持 "角色" 的功能](#what-does-each-teams-support-role-do)。

## <a name="where-to-find-per-user-call-analytics"></a>在哪里可以找到每用户呼叫分析

若要查看用户的所有呼叫信息和数据，请转到[团队管理中心](https://admin.teams.microsoft.com)。 在 "**用户**" 下，选择用户，然后在用户的配置文件页面上打开 "**通话记录**" 选项卡。 在这里，你将在过去30天内找到该用户的所有通话和会议。

![所有分析用户数据的屏幕截图](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

若要获取有关给定会话的其他信息（包括详细的媒体和网络统计信息），请单击某个会话以查看详细信息。

![呼叫分析用户会话数据的屏幕截图](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)
  
## <a name="what-does-each-teams-support-role-do"></a>每个团队支持什么角色？

**团队通信支持专家** (第1层支持) 处理基本的通话质量问题。 他们不会调查会议问题。 而是收集相关信息，然后升级到通信支持工程师。 

**团队通信支持工程师** (第2层支持) 可查看来自团队通信支持专家隐藏的详细呼叫日志中的信息。 下表列出了每个团队通信支持角色可用的信息。

下表告诉你每个用户的信息对每个通信支持角色可用。

|**活动**|**信息**|通信支持**专家**可以看到的内容|通信支持**工程师**看到的内容|
|:-----|:-----|:-----|:-----|
|**呼叫** <br/> |呼叫者姓名  <br/> |仅限代理搜索的用户的名称。  <br/> |用户名。  <br/> |
||收件人姓名  <br/> |显示为内部用户或外部用户。  <br/> |收件人姓名。  <br/> |
||主叫方电话号码  <br/> |除最后三位数字之外的整个电话号码都被用星号符号混淆。 例如，15552823 * * *。  <br/> |除最后三位数字之外的整个电话号码都被用星号符号混淆。 例如，15552823 * * *。  <br/> |
||收件人电话号码  <br/> |除最后三位数字之外的整个电话号码都被用星号符号混淆。 例如，15552823 * * *。  <br/> |除最后三位数字之外的整个电话号码都被用星号符号混淆。 例如，15552823 * * *。  <br/> |
||**通话详情**  > "**高级**" 选项卡 <br/> |未显示信息。  <br/> |显示所有详细信息，如设备名称、IP 地址、子网映射等。  <br/> |
||**通话详情**  > **高级**  > "**调试**" 选项卡 <br/> |未显示信息。  <br/> |显示所有详细信息，如 DNS 后缀和 SSID。  <br/> |
|**会议** <br/> |参与者姓名  <br/> |仅限代理搜索的用户的名称。 标识为内部用户或外部用户的其他参与者。  <br/> |显示所有名称。  <br/> |
||参与者计数  <br/> |参与者的数量。  <br/> |参与者的数量。  <br/> |
||会话详细信息  <br/> |与异常一起显示的会话详细信息。 仅显示对其进行代理搜索的用户的名称。 标识为内部用户或外部用户的其他参与者。 用星号符号进行混淆的电话号码的最后三位数字。  <br/> |显示的会话详细信息。 显示的用户名和会话详细信息。 用星号符号进行混淆的电话号码的最后三位数字。  <br/> |
||||
  
## <a name="troubleshoot-user-call-quality-problems"></a>解决用户呼叫质量问题 

1. 打开 "团队管理中心" (https://admin.teams.microsoft.com) 并通过团队通信支持或团队管理员凭据登录。

2. 在**仪表板**上的 "**用户搜索**" 中，开始键入要对其进行故障排除的用户的名称或 SIP 地址，或选择 "**查看用户**" 以查看用户列表。

3. 从列表中选择用户。

4. 选择 "**呼叫历史记录**"，然后选择要进行故障排除的呼叫或会议。
    
5. 选择 "**高级**" 选项卡，然后查找表示通话质量不佳或连接问题的黄色和红色项目。
    
    在每个通话或会议的 "会话详细信息" 中，小问题显示为黄色。 如果某个内容为黄色，则它不在正常范围内，它可能会导致问题，但不太可能是问题的主要原因。 如果出现红色，这是一个重大问题，这很可能是本次会议的通话质量不佳的主要原因。 
      
在极少数情况下，音频会话的体验数据质量未收到。 这通常是由于断开的呼叫或与客户端的连接终止所致。 出现这种情况时，**无法使用**"会话分级"。
  
对于具有经验 (QoE) 数据的音频会话，下表介绍了将会话限定为**差**的主要问题。
  
|**问题**|**区域**|**说明**|
|:-----|:-----|:-----|
|呼叫设置  <br/> |Session  <br/> |错误代码 Ms-诊断20-29 指示呼叫设置失败。 用户无法加入呼叫或会议。  <br/> |
|音频网络分类差通话  <br/> |Session  <br/> |遇到 (的网络质量问题，例如数据包丢失、抖动、NMOS 下降、RTT 或隐藏比率) 。  <br/> |
|设备不起作用  <br/> |Device  <br/> | 设备不能正常工作。 设备的运行比率为： <br/>  DeviceRenderNotFunctioningEventRatio >= 0.005 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0.005 <br/> |
   

## <a name="related-topics"></a>相关主题

[设置每用户呼叫分析](set-up-call-analytics.md)



  
 
