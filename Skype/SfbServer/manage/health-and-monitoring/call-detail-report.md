---
title: 为业务 Server Skype 中呼叫详情报告
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38862e35-3fec-41b9-a035-0b301942d446
description: 摘要： 了解用于在 Skype 业务服务器的呼叫详情报告。
ms.openlocfilehash: 3f560a2d4217b5afd61036b39100b39888fe577a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20978880"
---
# <a name="call-detail-report-in-skype-for-business-server"></a>为业务 Server Skype 中呼叫详情报告
 
**摘要：** 了解用于在 Skype 业务服务器的呼叫详情报告。
  
呼叫详情报告提供详细的看则单个呼叫;此报告包括几乎所有用户体验质量指标和 Skype 业务服务器收集的统计信息划分为报表节如：
  
- 呼叫信息 
    
- 呼叫者设备和信号指标
    
- 被叫方设备和信号指标
    
- 呼叫者客户端事件
    
- 被叫方客户端事件
    
- 音频流（呼叫者到被叫方）
    
- 视频流（呼叫者到被叫方）
    
- 音频流（被叫方到呼叫者）
    
- 视频流（被叫方到呼叫者）
    
请记住，您在指定报告上看到的类别和指标取决于两个因素：会话类型和会话中使用的终结点类型。例如，纯音频呼叫不会报告视频流的相关指标；这是因为该呼叫没有视频流。同样，您的报告可能列出了呼叫者统计信息，而没有列出被叫方统计信息。这通常是因为被叫方没有使用符合 SIP 的设备。终结点负责在呼叫结束时报告统计信息；但是，移动电话（不了解有关 SIP 或 SIP 统计信息的任何情况）无法报告此类信息。如果您呼叫某人且此人用其移动电话应答您的呼叫，则呼叫结束时您将不会获得来自该移动电话的报告。
  
呼叫详情报告在您尝试准确确定指定呼叫遇到媒体质量问题的原因时最为有用。
  
## <a name="accessing-the-call-detail-report"></a>访问呼叫详情报告

可以从下列任意报告中访问呼叫详情报告：
  
- [Location Report （通过单击呼叫量或质量欠佳的呼叫百分比指标） 的业务服务器 (位置 report.md) 的 Skype 中
    
- [Media Quality Summary Report 中 Skype 业务服务器 (summary.md) （通过单击呼叫量或质量欠佳的呼叫百分比指标）
    
- [媒体质量比较报告中的业务服务器 Skype](comparison.md) （通过单击[中的业务服务器 Skype Call List Report](call-list-report-0.md) ，然后单击详细信息指标）。
    
- [Skype 业务服务器中的 Server Performance Report](server-performance.md) （通过单击呼叫量或质量欠佳的呼叫百分比指标）
    
- [在业务服务器的 Skype Call List Report](call-list-report-0.md) （通过单击详细信息指标）
    
从呼叫详情报告中您可以访问[设备报告 Skype 业务服务器中](device-report.md)通过单击以下指标之一：
  
- 捕获设备
    
- 呈现设备
    
您还可以通过单击“A/V 边缘服务器”指标访问服务器媒体质量趋势报告。
  
## <a name="making-the-best-use-of-the-call-detail-report"></a>充分利用呼叫详情报告

呼叫详情报告通常包括 250 多个不同的指标，其中包括麦克风时间戳偏移、低 SNR 时间和近端回声时间等项目。如果您不记得所有这些指标实际度量的内容，请尝试将鼠标指针置于指标标签上方；通常，将显示描述该指标的工具提示。
  
如果查找指标时遇到问题，请在搜索框中键入指标标签的部分内容，然后单击“**查找**”。例如，如果你无法找到“低 SNR 时间”指标，请在搜索框中键入“SNR”，然后单击“**查找**”。
  
请注意，报告仅跟踪关于呼叫的信息。不记录呼叫本身。
  
## <a name="filters"></a>筛选器

无。您无法筛选呼叫详情报告。
  
## <a name="metrics"></a>指标

下表列出了每个呼叫的呼叫详情报告中提供的信息。
  
**呼叫详情报告指标**

|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**呼叫者 PAI** <br/> |否  <br/> |发起呼叫的用户的 P-Asserted-Identity。P-Asserted-Identity 用于传达受信任网络内用户经验证的身份。  <br/> |
|**呼叫者 URI** <br/> |否  <br/> |发起呼叫的用户的 SIP 地址。  <br/> |
|**呼叫者终结点** <br/> |否  <br/> |用于发出呼叫的设备。  <br/> |
|**呼叫者用户代理** <br/> |否  <br/> |发出呼叫的设备上使用的软件。  <br/> |
|**呼叫开始** <br/> |否  <br/> |最初发出呼叫的日期和时间。  <br/> |
|**中介服务器旁路呼叫** <br/> |否  <br/> |指示呼叫是否在不通过中介服务器的情况下连接到 PSTN 语音网关或合格的 IP-PBX。  <br/> |
|**呼叫者 OS** <br/> |否  <br/> |呼叫者计算机的操作系统。  <br/> |
|**呼叫者 CPU** <br/> |否  <br/> |发起呼叫的用户的计算机中安装的 CPU。  <br/> |
|**呼叫者 CPU 内核数** <br/> |否  <br/> |发起呼叫的人员使用的计算机中的处理器数量。  <br/> |
|**呼叫者 CPU 速度** <br/> |否  <br/> |发起呼叫的人员使用的计算机的 CPU 时钟频率。  <br/> |
|**呼叫者 CPU 虚拟化** <br/> |否  <br/> |发起呼叫的人员使用的计算机上使用的虚拟化（如果有）。  <br/> |
|**被叫方 PAI** <br/> |否  <br/> |受邀加入呼叫的用户的 P-Asserted-Identity。P-Asserted-Identity 用于传达受信任网络内用户经验证的身份。  <br/> |
|**被叫方 URI** <br/> |否  <br/> |被叫的用户的 SIP 地址。  <br/> |
|**被叫方终结点** <br/> |否  <br/> |用于接收呼叫的设备。  <br/> |
|**被叫方用户代理** <br/> |否  <br/> |接收呼叫的设备上使用的软件。  <br/> |
|**持续时间** <br/> |否  <br/> |呼叫的时长。  <br/> |
|**媒体旁路警告标记** <br/> |否  <br/> |在绕过中介服务器时发出的警告。  <br/> |
|**被叫方 OS** <br/> |否  <br/> |被叫用户的计算机的操作系统。  <br/> |
|**被叫方 CPU** <br/> |否  <br/> |被叫用户的计算机中安装的 CPU。  <br/> |
|**被叫方内核数** <br/> |否  <br/> |被叫人员使用的计算机中的处理器数量。  <br/> |
|**被叫方 CPU 速度** <br/> |否  <br/> |被叫人员使用的计算机的 CPU 时钟频率。  <br/> |
|**被叫方 CPU 虚拟化** <br/> |否  <br/> |被叫人员使用的计算机上使用的虚拟化（如果有）。  <br/> |
   

