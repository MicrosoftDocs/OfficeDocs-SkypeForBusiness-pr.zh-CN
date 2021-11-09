---
title: 报告中的对等会话详细信息Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
description: 摘要：了解 Skype for Business Server 中的对等会话详细信息报告。
ms.openlocfilehash: fe49c455391583a02f873769a75d86da62fe2a25
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829966"
---
# <a name="peer-to-peer-session-detail-report-in-skype-for-business-server"></a>报告中的对等会话详细信息Skype for Business Server
 
**摘要：** 了解会议报告中的对等会话详细信息Skype for Business Server。
  
点对点会话详细信息报告返回有关点对点会话的详细信息。例如，如果您选择即时消息会话，则此报告将告知您会话中两个用户各自发送的消息数。
  
## <a name="accessing-the-peer-to-peer-session-detail-report"></a>访问点对点会话详细信息报告

可以从下列任一报告（可从监控报告主页中访问所有这些报告）访问点对点会话详细信息报告：
  
- IP 电话清单报告
    
- 用户活动报告
    
- 呼叫允许控制报告
    
- 故障列表报告 
    
从点对点会话详细信息报告中，可以通过单击诊断报告Skype for Business Server"详细信息"指标[](diagnostic-report.md)来访问 (报告) 报告。 此外，还可以通过单击这两个指标之一来访问主要故障报告：
  
- 响应
    
- 诊断 ID
    
## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>最充分地利用点对点会话详细信息报告

点对点会话详细信息报告包括大量指标，其中有许多指标是系统管理员所不熟悉的。不过，通常您只需将鼠标指针悬停在指标标签的上方即可查看提供了指标的简要说明的工具提示。
  
请注意，给定报告上显示的实际指标将取决于您所选的点对点会话的类型。音频/视频会话将报告一组与即时消息会话不同的指标。
  
还可以将鼠标指针悬停在响应代码和诊断 ID 指标的上方来获取这些值的描述：
  
## <a name="filters"></a>筛选器

无。无法筛选点对点会话详细信息报告。
  
## <a name="session-information-metrics"></a>会话信息指标

下表列出了每个会话的点对点会话详细信息报告中提供的信息。
  
**会话信息指标**

|**名称**|**说明**|
|:-----|:-----|
|**池 FQDN** <br/> |会话中涉及的注册器池或边缘服务器的完全限定域名 (FQDN)。  <br/> |
|**邀请时间** <br/> |最初发送会话邀请的日期和时间。  <br/> |
|**响应时间** <br/> |收到邀请接受函的日期和时间。  <br/> |
|**来源用户** <br/> |发起会话的用户的 SIP 地址。  <br/> |
|**源用户代理** <br/> |发起会话的用户的终结点使用的软件。  <br/> |
|**源用户为内部用户** <br/> |指示启动会话的用户是否登录到内部网络。  <br/> |
|**源用户与桌面电话集成** <br/> |指示启动会话的用户使用的终结点是否与其桌面电话集成。  <br/> |
|**会话优先级** <br/> |分配给会话的优先级。有效优先级有：未知、非紧急、正常和紧急。  <br/> |
|**响应代码** <br/> |会话失败时发送的 SIP 响应代码。  <br/> |
|**前端** <br/> |会议中使用的前端服务器的名称。  <br/> |
|**捕获时间** <br/> |记录会话信息的日期和时间。  <br/> |
|**结束时间** <br/> |会话结束的日期和时间。  <br/> |
|**目标用户** <br/> |受邀加入会话的用户的 SIP 地址。  <br/> |
|**目标用户代理** <br/> |受邀加入会话的用户的终结点使用的软件。  <br/> |
|**目标用户为内部用户** <br/> |指示受邀加入会话的用户是否登录到内部网络。  <br/> |
|**目标用户与桌面电话集成** <br/> |指示受邀加入会话的用户使用的终结点是否与其桌面电话集成。  <br/> |
|**为重试会话** <br/> |指示会话是否是在尝试重试以前失败的会话。  <br/> |
|**诊断 ID** <br/> |附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。将光标停留在 ID 号上可查看有关该 ID 的其他信息。  <br/> |
   
## <a name="metrics-for-modalities"></a>形式指标

下表列出了每种会话形式的点对点会话详细信息报告中提供的信息。
  
**形式指标**

|**名称**|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**形式** <br/> |否  <br/> |会话中使用的形式。例如，即时消息 (IM) 或文件传输。  <br/> |
|**源用户消息** <br/> |否  <br/> |启动会话的用户发送的消息数。  <br/> |
|**目标用户消息** <br/> |否  <br/> |受邀加入会话的用户发送的消息数。  <br/> |
   
## <a name="metrics-for-diagnostic-reports"></a>诊断报告指标

下表列出了每个诊断报告的点对点会话详细信息报告中提供的信息。
  
**诊断报告指标**

|**名称**|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**详细信息** <br/> |否  <br/> |当您单击此项时，报告显示会话的诊断报告。  <br/> |
|**报告时间** <br/> |否  <br/> |记录报告的日期和时间。  <br/> |
|**请求** <br/> |否  <br/> |SIP 请求类型。例如 INVITE 或 BYE。  <br/> |
|**诊断 ID** <br/> |否  <br/> |附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。  <br/> |
|**内容类型** <br/> |否  <br/> |会议中使用的媒体内容的类型。例如，常见内容类型为 Application/sdp。会话描述协议 (SDP) 是用于会话公告、会话邀请及其他形式的多媒体会话启动的标准 Internet 协议。  <br/> |
|**报告者** <br/> |否  <br/> |报告问题的计算机（即客户端或服务器）。  <br/> |
   

