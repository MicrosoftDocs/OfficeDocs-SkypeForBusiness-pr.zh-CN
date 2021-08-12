---
title: 规划用户的位置Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: 阅读本主题，了解如何在 (E9-1-1) 部署中规划增强型紧急服务Skype for Business Server 企业语音。
ms.openlocfilehash: 2007e0a530d82dc6b14dee9758c4eeeee75588ca2a81597e18f6a777093f0cf5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286611"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>规划用户的位置Skype for Business Server
 
阅读本主题，了解如何在 (E9-1-1) 部署中规划增强型紧急服务Skype for Business Server 企业语音。 
  
> [!NOTE]
> Skype for Business Server现在支持为客户端配置多个紧急号码。 如果要配置多个紧急号码，则必须按照在 Skype for Business Server 中规划多个[](multiple-emergency-numbers.md)紧急号码和在 Skype for Business 中配置多个紧急[号码中Skype for Business。](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) 
  
通过使用"控制面板"或Skype for Business [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet 创建位置策略。 有关详细信息，请参阅 Create [location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md)。
  
每个位置策略都包含以下信息：
  
 **启用增强型 9-1-1**
  
启用此值后，客户端将启用增强型紧急服务 (E9-1-1) 。 当客户端注册时，它会尝试从位置信息服务获取位置，并且将在紧急呼叫中包括位置信息。
  
 **位置**
  
此设置仅在启用增强型 **9-1-1 时** 使用。
  
可以配置" **位置"** 设置以定义客户端行为，如下所示：
  
- 将值设置为 **"否** "意味着不会提示用户输入位置。
    
- 将该值设置为 **"是** "意味着将提示用户输入位置，但可以消除提示。
    
- 将值设置为 **Disclaimer** 意味着将提示用户输入位置，并且如果用户尝试消除提示，也会显示免责声明。 在所有情况下，用户都可以继续使用客户端。
    
> [!NOTE]
> 如果用户在启用 E9-1-1 之前手动输入了位置，则不显示免责声明文本。 已查看免责声明的用户不会查看免责声明文本的更新。 
  
 **增强型紧急服务免责声明**
  
此设置指定用户在消除位置提示时看到的免责声明。 在Skype for Business Server中，您可以使用位置策略为不同的区域设置或不同的用户集设置不同的免责声明。
  
 **紧急拨号串 (E9-1-1 拨号号码)**
  
此拨号字符串 (前导"+"，但包括用户的拨号计划) 完成的任何规范化表示呼叫是紧急呼叫。 紧急 **拨号串** 使客户端在呼叫中包括位置和回拨信息。
  
> [!NOTE]
> 如果您的组织不使用外部线路访问前缀，则无需创建相应的拨号计划规范化规则，在将呼叫发送到运行 Skype for Business Server 的服务器的出站路由之前将"+"添加到 911 字符串;由于位置策略，Skype for Business客户端将自动预置"+"。 但是，如果站点使用外部访问前缀，则需要向适用的拨号计划策略添加规范化规则，该策略会去除外部访问前缀并添加"+"。 例如，如果位置使用外部访问前缀 9，而用户拨打 9 911 拨打紧急呼叫，则客户端将使用其拨号计划策略，在呼叫者的位置配置文件中的路由评估拨打的号码之前，将拨打的号码规范化为 +911。 
  
 **E9-1-1 拨号 (紧急拨号串掩码)**
  
转换为指定的紧急拨号字符串的拨号字符串的分号 **分隔列表**。 例如，你可能想要添加 112，这是大部分欧洲国家/地区紧急服务号码。 来自Skype for Business的用户可能不知道 911 是美国紧急号码，但他们可以拨打 112 并获取相同的结果。 与紧急拨号字符串一样，在每个号码之前不要包含"+"，如果使用外部线路接入编码，请确保用户的拨号计划策略中具有规范化规则，以去除访问代码数字。
  
 **PSTN 用法**
  
PSTN 用法的名称，其中包含确定将转到哪个 SIP 中继、PSTN 网关或 ELIN 网关紧急呼叫的路由路径。
  
> [!NOTE]
> 只能将一个用法分配给位置策略。 此 PSTN 用法会覆盖分配给用户的语音策略的 PSTN 用法，但仅适用于紧急拨号字符串或紧急拨号字符串掩码之一的呼叫。 
  
 **通知 URI**
  
指定在发出紧急呼叫时接收即时消息 (IM) 的安全人员的一个或多个 SIP URI。 支持通讯组。
  
 **会议 URI**
  
指定外线直拨 (DID) 号码 (通常是拨打紧急呼叫时应) 会议的安全服务台号码。 
  
 **会议模式**
  
指定会议 URI 是使用单向通信还是双向通信加入紧急呼叫。 
  
 **位置刷新间隔**
  
指定从位置信息 (位置更新) 客户端请求之间的时间量（以小时表示）。 该值可以设置为 1 到 12 之间的任意值。 默认值为 4。
