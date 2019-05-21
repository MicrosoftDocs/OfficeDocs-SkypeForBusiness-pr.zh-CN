---
title: 为 Skype for Business Server 规划位置策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: 阅读本主题, 了解如何在 Skype for Business Server Enterprise Voice 中为增强的紧急服务 (E9-1) 部署计划位置策略。
ms.openlocfilehash: 8f21a5a0f54fbeaca4c46ed51bf4dafe4c2a3dcb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276752"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>为 Skype for Business Server 规划位置策略
 
阅读本主题, 了解如何在 Skype for Business Server Enterprise Voice 中为增强的紧急服务 (E9-1) 部署计划位置策略。 
  
> [!NOTE]
> Skype for business 服务器现支持客户端的多个紧急号码的配置。 如果想要配置多个紧急号码, 您必须按照计划中的信息, 在[skype For Business 服务器中输入多个紧急](multiple-emergency-numbers.md)号码, 并[在 skype For business 中配置多个紧急号码](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)。 
  
通过使用 Skype for Business 控制面板或使用[CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet 创建位置策略。 有关详细信息, 请参阅[在 Skype For Business 服务器中创建位置策略](../../deploy/deploy-enterprise-voice/create-location-policies.md)。
  
每个位置策略包含以下信息：
  
 **启用增强型 9-1-1**
  
启用该值时，可为客户端启用增强型紧急服务 (E9-1-1)。 客户端注册时, 它会尝试从位置信息服务获取位置, 并将位置信息包含在紧急呼叫的一部分中。
  
 **位置**
  
仅当**启用增强型 9-1-1** 为启用状态时才使用此设置。
  
你可以将**位置**设置配置为按如下所示定义客户端行为：
  
- 将该值设为**否**表示不会提示用户输入位置。
    
- 设为**是**表示将提示用户输入位置，但可以消除提示。
    
- 设为**免责声明**表示将会提示用户输入位置，并且当用户尝试消除提示时将显示免责声明。在所有情况下，用户都可以继续使用该客户端。
    
> [!NOTE]
> 如果在启用 E9-1-1 之前用户手动输入位置，则不会显示免责声明文本。已查看免责声明的用户将不能查看免责声明文本的更新。 
  
 **增强型紧急服务免责声明**
  
该设置指定当用户消除输入位置提示时显示的免责声明。 在 Skype for Business Server 中, 你可以使用位置策略为不同的区域设置或不同的用户集设置不同的免责声明。
  
 **紧急拨号串（E9-1-1 拨号号码）**
  
此拨号字符串 (较少前导 "+", 但包括由用户的拨号计划完成的任何规范化) 表示呼叫是紧急呼叫。 **紧急拨号串**使客户端包括有关呼叫的位置和回拨信息。
  
> [!NOTE]
> 如果您的组织不使用外部线路访问前缀, 则无需创建相应的拨号计划规范化规则, 以便在运行 Skype for business 服务器的服务器上将呼叫发送到出站路由之前将 "+" 添加到911字符串;作为位置策略的结果, Skype for Business 客户端将自动预置 "+"。 但是, 如果您的网站使用外部访问前缀, 则需要将规范化规则添加到可访问外部访问前缀的适用拨号计划策略, 并添加 "+"。 例如, 如果您的位置使用外部访问前缀 9, 并且用户将 9 911 拨打电话到拨打电话, 则在呼叫者的位置档案中, 客户端将使用其拨号计划策略将此号码与 + 911 进行规范化。 
  
 **紧急拨号串掩码（E9-1-1 拨号掩码）**
  
一个分号分隔的拨号字符串列表，将转换为指定的**紧急拨号字符串**。 例如，你可能想要添加 112（欧洲大部分地区的紧急服务号码）。 从欧洲访问 Skype for business 用户可能不知道911是美国的紧急电话号码, 但他们可以拨打112并获得相同的结果。 与 "紧急拨号字符串" 一样, 在每个号码前不要包含 "+", 如果您使用外部线路访问代码, 请确保用户的拨号计划策略中有规范化规则来去掉访问代码位。
  
 **PSTN 用法**
  
包含确定紧急呼叫将转至哪一 SIP 中继、PSTN 网关或 ELIN 网关的路由路径的 PSTN 用法名称。
  
> [!NOTE]
> 一个用法只能分配给一个位置策略。 此 PSTN 使用覆盖分配给用户语音策略的 PSTN 使用, 但仅适用于拨入紧急拨号字符串或其中一个紧急拨号字符串掩码的呼叫。 
  
 **通知 URI**
  
指定要在发出紧急呼叫时接收即时消息 (IM) 通知的安全人员的一个或多个 SIP URI。支持通讯组。
  
 **会议 URI**
  
指定在发出紧急呼叫时应加入会议的外线直拨分机 (DID) 号码（通常是安全服务台号码）。 
  
 **会议模式**
  
指定会议 URI 将使用单向还是双向通信加入紧急呼叫。 
  
 **位置刷新间隔**
  
指定从位置信息服务的位置更新的客户端请求之间的时间量 (以小时为单位)。 该值可以设置为 1 和 12 之间的任意值。 默认值为 4。
  

