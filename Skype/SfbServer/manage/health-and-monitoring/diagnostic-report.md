---
title: 诊断报告中Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: 摘要：了解诊断报告中Skype for Business Server。
ms.openlocfilehash: ef930870e918cd11f2525914e6f5716d7d685bfec224480c1eb88b3a280e3fa3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54297218"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>诊断报告中Skype for Business Server
 
**摘要：** 了解诊断报告中Skype for Business Server。
  
诊断报告提供失败的会话的诊断和故障排除信息。 此信息包括在会话失败时所报告的诊断 ID 和诊断标头。 诊断 ID 是附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），而诊断标头提供诊断 ID 的附带说明。 该报告可能还包含报告组件所了解的有价值的故障排除详细信息。 例如：
  
- 由生成故障的 PSTN 网关提供的原因代码。在 PSTN 网络上，传出呼叫失败时，会自动生成 ISDN 用户部分 (ISUP) 原因代码。例如，PSTN 网关可能会发送原因代码 34，指示不存在可用于完成呼叫的任何电路或信道。
    
- 针对连接失败的对等方 FQDN、端口和 Winsock 错误。
    
- 针对 DNS 解析失败所查找的名称。每次客户端联系名称服务器并请求与指定的设备名称相对应的 IP 地址时，都会进行 DNS 解析。
    
## <a name="accessing-the-diagnostic-report"></a>访问诊断报告

通过单击 Skype for Business Server 中的点对点会话详细信息报告或会议详细信息报告的诊断报告 (详细信息) 指标可以访问诊断报告[](peer-to-peer-session-detail-report.md)。
  
## <a name="filters"></a>筛选器

无。您不能对诊断报告进行筛选。
  
## <a name="metrics"></a>度量标准

下表列出了各会话的诊断报告中提供的信息。
  
**诊断报告指标**

|**名称**|**是否可按此项排序？**|**说明**|
|:-----|:-----|:-----|
|**报告时间** <br/> |否  <br/> |记录报告的日期和时间。  <br/> |
|**响应代码** <br/> |否  <br/> |会话失败时发送的 SIP 响应代码。  <br/> |
|**请求类型** <br/> |否  <br/> |失败的 SIP 请求类型。例如，INVITE、BYE 或 SERVICE。  <br/> |
|**Source** <br/> |否  <br/> |错误的来源。  <br/> |
|**源用户 URI** <br/> |否  <br/> |发起会话的用户的 SIP 地址。  <br/> |
|**源用户代理** <br/> |否  <br/> |发起会话的用户的终结点使用的软件。  <br/> |
|**诊断 ID** <br/> |否  <br/> |附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。  <br/> |
|**内容类型** <br/> |否  <br/> |失败的媒体内容类型。例如，常见内容类型为 Application/sdp。会话描述协议 (SDP) 是用于会话公告、会话邀请及其他形式的多媒体会话启动的标准 Internet 协议。  <br/> |
|**应用程序** <br/> |否  <br/> |错误涉及的应用程序。  <br/> |
|**目标用户 URI** <br/> |否  <br/> |受邀加入会话的用户的 SIP 地址。  <br/> |
|**会议加入时间（毫秒）** <br/> |否  <br/> |用户加入会议所需的时间量（以毫秒为单位）。  <br/> |
|**诊断标头** <br/> |否  <br/> |诊断 ID 描述  <br/> |
   
可在 [Ms-Diagnostics](/openspecs/office_protocols/ms-ocer/f6787b39-0842-43ca-94a2-6afadda5f0a3)标头页上找到诊断错误列表。
