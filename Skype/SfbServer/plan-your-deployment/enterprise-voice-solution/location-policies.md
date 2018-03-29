---
title: 为 Skype for Business Server 2015 规划位置策略
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: 阅读本主题，以了解如何规划业务服务器企业语音增强紧急服务 (E9-1-1) 部署在 Skype 的位置策略。
ms.openlocfilehash: 246a4bcddece986d9488c5e2bccbbece5f1a2cc9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-location-policies-for-skype-for-business-server-2015"></a>为 Skype for Business Server 2015 规划位置策略
 
阅读本主题，以了解如何规划业务服务器企业语音增强紧急服务 (E9-1-1) 部署在 Skype 的位置策略。 
  
> [!NOTE]
> Skype 业务服务器现在支持的客户端配置的多个紧急号码。 如果您想要配置多个紧急号码，您必须遵循[多个紧急号码业务服务器 2015年的 Skype 中规划](multiple-emergency-numbers.md)和[配置多个紧急号码业务 2015年的 Skype 在](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)中的信息。 
  
通过 Skype 业务控制面板或通过使用[New CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet，您创建的位置策略。 有关详细信息，请参阅[创建业务服务器 2015年的 Skype 的位置策略](../../deploy/deploy-enterprise-voice/create-location-policies.md)。
  
每个位置策略包含以下信息：
  
 **启用增强型 9-1-1**
  
启用该值时，可为客户端启用增强型紧急服务 (E9-1-1)。 当客户端注册时，它试图获取位置信息服务中的位置，并将包括位置信息作为紧急调用的一部分。
  
 **位置**
  
仅当启用**启用增强 9-1-1**时，则使用此设置。
  
你可以将**位置**设置配置为按如下所示定义客户端行为：
  
- 将该值设为**否**表示不会提示用户输入位置。
    
- 设为**是**表示将提示用户输入位置，但可以消除提示。
    
- 设为**免责声明**表示将会提示用户输入位置，并且当用户尝试消除提示时将显示免责声明。在所有情况下，用户都可以继续使用该客户端。
    
> [!NOTE]
> 如果在启用 E9-1-1 之前用户手动输入位置，则不会显示免责声明文本。已查看免责声明的用户将不能查看免责声明文本的更新。 
  
 **增强型紧急服务免责声明**
  
该设置指定当用户消除输入位置提示时显示的免责声明。 在 Skype 业务服务器，您可以使用位置策略设置为不同的区域设置或不同的用户组不同免责声明。
  
 **紧急拨号串（E9-1-1 拨号号码）**
  
此拨号字符串 (更少的前导"+"，但包括由用户的拨号计划完成任何正常化) 表示是一个紧急调用的调用。 **紧急拨号串**使客户端包括有关呼叫的位置和回拨信息。
  
> [!NOTE]
> 如果您的组织不使用外部线接入前缀，您不需要创建相应拨号计划规范化规则添加一个"+"到 911 之前发送到出站路由业务服务器; 运行 Skype 的服务器上调用字符串"+"将自动预置通过 Skype 业务客户端的位置策略的结果。 但是，如果您的站点使用一个外部访问前缀，您需要将规范化规则添加到适用拨号计划策略，以去除外部访问前缀并添加"+"。 例如，如果您所在的位置使用 9 的外部访问前缀和用户拨打 9 911 要发出紧急呼叫，客户端将使用其拨号计划策略标准化这对之前的 +911 通过在调用方的位置配置文件中的路由计算拨叫的号码。 
  
 **紧急拨号串掩码（E9-1-1 拨号掩码）**
  
一个分号分隔的拨号字符串列表，将转换为指定的**紧急拨号字符串**。 例如，你可能想要添加 112（欧洲大部分地区的紧急服务号码）。 来自欧洲的企业用户正在访问 Skype 可能不知道 911 是美国紧急号码，但他们可以拨打 112 和获得相同的结果。 如与紧急拨号字符串，但不包含一个"+"前每个数字，而且如果您使用外部行访问代码，请确保用户的拨号计划策略来访问代码数字中剥离中规范化规则。
  
 **PSTN 用法**
  
包含确定紧急呼叫将转至哪一 SIP 中继、PSTN 网关或 ELIN 网关的路由路径的 PSTN 用法名称。
  
> [!NOTE]
> 一个用法只能分配给一个位置策略。 此 PSTN 用法将覆盖指派给用户的语音策略，PSTN 用法，但仅适用于调用放置紧急拨号字符串或一个紧急拨号字符串面具。 
  
 **通知 URI**
  
指定要在发出紧急呼叫时接收即时消息 (IM) 通知的安全人员的一个或多个 SIP URI。支持通讯组。
  
 **会议 URI**
  
指定在发出紧急呼叫时应加入会议的外线直拨分机 (DID) 号码（通常是安全服务台号码）。 
  
 **会议模式**
  
指定会议 URI 将使用单向还是双向通信加入紧急呼叫。 
  
 **位置刷新间隔**
  
指定的位置信息服务从一个位置更新的客户端请求之间的时间 （以小时为单位）。 该值可以设置为 1 和 12 之间的任意值。 默认值为 4。
  

