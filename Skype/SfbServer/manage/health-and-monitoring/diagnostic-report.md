---
title: Skype for Business 服务器中的诊断报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: '摘要: 了解 Skype for Business 服务器中的诊断报告。'
ms.openlocfilehash: d71906f2407a0daadc04417ab60a23c86f5eeb52
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305771"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>Skype for Business 服务器中的诊断报告
 
**摘要:** 了解 Skype for Business 服务器中的诊断报告。
  
诊断报告提供失败的会话的诊断和故障排除信息。 此信息包括在会话失败时所报告的诊断 ID 和诊断标头。 诊断 ID 是附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），而诊断标头提供诊断 ID 的附带说明。 该报告可能还包含报告组件所了解的有价值的故障排除详细信息。 例如：
  
- 由生成故障的 PSTN 网关提供的原因代码。在 PSTN 网络上，传出呼叫失败时，会自动生成 ISDN 用户部分 (ISUP) 原因代码。例如，PSTN 网关可能会发送原因代码 34，指示不存在可用于完成呼叫的任何电路或信道。
    
- 针对连接失败的对等方 FQDN、端口和 Winsock 错误。
    
- 针对 DNS 解析失败所查找的名称。每次客户端联系名称服务器并请求与指定的设备名称相对应的 IP 地址时，都会进行 DNS 解析。
    
## <a name="accessing-the-diagnostic-report"></a>访问诊断报告

可通过在 Skype for Business Server 或会议详细信息报告[中单击对等会话详细信息报告](peer-to-peer-session-detail-report.md)上的诊断报告 (详细信息) 指标来访问诊断报告。
  
## <a name="filters"></a>筛选器

无。您不能对诊断报告进行筛选。
  
## <a name="metrics"></a>指标

下表列出了各会话的诊断报告中提供的信息。
  
**诊断报告指标**

|**名称** - 按 WAN 链路进行筛选（筛选器位于图形右侧）。|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**报告时间** <br/> |否  <br/> |记录报告的日期和时间。  <br/> |
|**响应代码** <br/> |否  <br/> |会话失败时发送的 SIP 响应代码。  <br/> |
|**请求类型** <br/> |否  <br/> |失败的 SIP 请求类型。例如，INVITE、BYE 或 SERVICE。  <br/> |
|**来源** <br/> |否  <br/> |错误的来源。  <br/> |
|**源用户 URI** <br/> |否  <br/> |发起会话的用户的 SIP 地址。  <br/> |
|**源用户代理** <br/> |否  <br/> |发起会话的用户的终结点使用的软件。  <br/> |
|**诊断 ID** <br/> |否  <br/> |附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。  <br/> |
|**内容类型** <br/> |否  <br/> |失败的媒体内容类型。例如，常见内容类型为 Application/sdp。会话描述协议 (SDP) 是用于会话公告、会话邀请及其他形式的多媒体会话启动的标准 Internet 协议。  <br/> |
|**应用程序** <br/> |否  <br/> |错误涉及的应用程序。  <br/> |
|**目标用户 URI** <br/> |否  <br/> |受邀加入会话的用户的 SIP 地址。  <br/> |
|**会议加入时间（毫秒）** <br/> |否  <br/> |用户加入会议所需的时间量（以毫秒为单位）。  <br/> |
|**诊断标头** <br/> |否  <br/> |诊断 ID 描述  <br/> |
   
可以在[Ms Diagnostics 标题页面](https://msdn.microsoft.com/en-us/library/gg132446%28v=office.12%29.aspx)上找到诊断错误列表。
  

