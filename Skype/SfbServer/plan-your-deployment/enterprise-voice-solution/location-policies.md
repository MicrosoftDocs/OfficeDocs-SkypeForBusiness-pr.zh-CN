---
title: 规划业务 Server Skype 的位置策略
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: 阅读本主题可了解如何规划业务 Server 企业语音的增强型紧急服务 (E9-1-1) 部署 Skype 中的位置策略。
ms.openlocfilehash: 6717d6b7940ccf9cf7de403797d8bd4712f18144
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206759"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>规划业务 Server Skype 的位置策略
 
阅读本主题可了解如何规划业务 Server 企业语音的增强型紧急服务 (E9-1-1) 部署 Skype 中的位置策略。 
  
> [!NOTE]
> Skype 业务服务器现在支持的客户端的多个紧急号码的配置。 如果您想要配置多个紧急号码，则必须按照[Skype 业务服务器中的多个紧急号码规划](multiple-emergency-numbers.md)和[配置 Skype for Business 中的多个紧急号码](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)中的信息。 
  
使用适用于业务 Control Panel Skype 或使用[New-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet，您可以创建位置策略。 有关详细信息，请参阅[Skype 业务服务器中的创建位置策略](../../deploy/deploy-enterprise-voice/create-location-policies.md)。
  
每个位置策略包含以下信息：
  
 **启用增强型 9-1-1**
  
启用该值时，可为客户端启用增强型紧急服务 (E9-1-1)。 时客户端注册，它会尝试获取从位置信息服务位置，并将包括紧急呼叫的一部分的位置信息。
  
 **位置**
  
仅当**启用增强型 9-1-1** 为启用状态时才使用此设置。
  
你可以将**位置**设置配置为按如下所示定义客户端行为：
  
- 将该值设为**否**表示不会提示用户输入位置。
    
- 设为**是**表示将提示用户输入位置，但可以消除提示。
    
- 设为**免责声明**表示将会提示用户输入位置，并且当用户尝试消除提示时将显示免责声明。在所有情况下，用户都可以继续使用该客户端。
    
> [!NOTE]
> 如果在启用 E9-1-1 之前用户手动输入位置，则不会显示免责声明文本。已查看免责声明的用户将不能查看免责声明文本的更新。 
  
 **增强型紧急服务免责声明**
  
该设置指定当用户消除输入位置提示时显示的免责声明。 在业务服务器 Skype，可以使用位置策略设置为不同区域或不同的用户组的不同免责声明。
  
 **紧急拨号串（E9-1-1 拨号号码）**
  
此拨号串 (小于前导"+"，但包括由用户的拨号计划完成任何规范化) 表示呼叫紧急呼叫。 **紧急拨号串**使客户端包括有关呼叫的位置和回拨信息。
  
> [!NOTE]
> 如果您的组织不使用了外部访问前缀，不需要创建相应拨号计划的规范化规则"+"911 字符串发送出站路由到业务服务器; 运行 Skype 的服务器上的呼叫之前添加"+"将自动前加业务由于位置策略的客户端 Skype。 但是，如果您的网站使用了外部访问前缀，您需要添加规范化规则的适用拨号计划策略中去除的外部访问前缀，并将添加到"+"。 例如，如果您所在的位置使用 9 的外部访问前缀，并将用户拨打 9 911 放置紧急呼叫，客户端将使用其拨号计划策略规范化此到 +911 之前已拨的号码计算的呼叫者的位置配置文件中的路由。 
  
 **紧急拨号串掩码（E9-1-1 拨号掩码）**
  
一个分号分隔的拨号字符串列表，将转换为指定的**紧急拨号字符串**。 例如，你可能想要添加 112（欧洲大部分地区的紧急服务号码）。 欧洲业务用户的访问 Skype 可能不知道 911 是美国紧急号码，但他们可以拨打 112 并获得相同的结果。 根据与紧急拨号串，不包括"+"之前每个号码，并使用外部行访问代码，请确保中用户的拨号计划策略关闭访问代码数字去除规范化规则。
  
 **PSTN 用法**
  
包含确定紧急呼叫将转至哪一 SIP 中继、PSTN 网关或 ELIN 网关的路由路径的 PSTN 用法名称。
  
> [!NOTE]
> 一个用法只能分配给一个位置策略。 此 PSTN 用法将覆盖 PSTN 用法分配给用户的语音策略，但是仅适用于呼叫紧急拨号串或一个紧急拨号串掩码。 
  
 **通知 URI**
  
指定要在发出紧急呼叫时接收即时消息 (IM) 通知的安全人员的一个或多个 SIP URI。支持通讯组。
  
 **会议 URI**
  
指定在发出紧急呼叫时应加入会议的外线直拨分机 (DID) 号码（通常是安全服务台号码）。 
  
 **会议模式**
  
指定会议 URI 将使用单向还是双向通信加入紧急呼叫。 
  
 **位置刷新间隔**
  
指定从位置信息服务的位置更新的客户端请求之间的时间 （以小时为单位）。 该值可以设置为 1 和 12 之间的任意值。 默认值为 4。
  

