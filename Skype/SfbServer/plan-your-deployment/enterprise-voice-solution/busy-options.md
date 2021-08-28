---
title: 规划忙碌选项Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: 阅读有关"忙碌选项"功能的信息Skype for Business Server。
ms.openlocfilehash: c43a5a0cae0a798f3c38c62b4a1c7895d9704fbb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583876"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>规划忙碌选项Skype for Business Server
 
阅读有关"忙碌选项"功能的信息Skype for Business Server。
  
忙碌选项是 2016 年 7 月累积更新中引入的新语音策略，允许你配置在用户已接听电话或参加会议或将呼叫置于保持状态时如何处理传入呼叫。 可以使用繁忙信号拒绝新呼叫或传入呼叫，也可以将新呼叫或传入呼叫转发到语音邮件。 
  
SBS 服务器上配对的前端池和 Survivable Branch Servers 支持故障转移和灾难恢复的忙碌选项 (SBS) 。
  
本主题介绍忙碌选项的功能。 若要了解如何安装和配置忙碌选项，请参阅安装和配置忙碌选项[Skype for Business Server。](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)
  
## <a name="configuration-options"></a>配置选项

如果为组织启用了忙碌选项，则组织中所有用户（包括企业语音和非企业语音用户）都可以使用以下功能：
  
- Busy on Busy - 在用户忙碌时，新传入呼叫将因繁忙信号而被拒绝。
    
- Busy 上的语音邮件 - 在用户忙碌时，新传入呼叫将转发到语音邮件。
    
忙碌选项功能提供故障转移功能。 如果出现问题且用户故障转移到其他前端服务器或 Skype for Business Server中的另一个池，将保留其忙碌选项设置。
  
无论用户如何配置忙碌选项，呼叫或会议中的用户或呼叫保持的用户不会阻止发起新呼叫或会议。 
  
配置后，忙碌选项设置将作用于用户的所有呼叫Skype for Business和客户端。 根据用户的忙碌选项设置，被拒绝或发送到语音邮件的呼叫不会在用户登录的任何呼叫设备（包括 Macintosh、Windows 桌面、移动客户端或 IP 电话）上响铃。 
  
用户将在自己的客户端和设备上Skype for Business未接来电通知，并且也会收到电子邮件通知。 呼叫因忙碌而被拒绝的呼叫的呼叫者将在其 Skype for Business 客户端中看到一条通知，指出他们尝试联系的用户正在进行另一个呼叫。
  
可以使用 PowerShell cmdlet 配置忙碌选项Skype for Business以下项：
  
- 为用户启用或禁用忙碌选项语音Enterprise。
    
- 为用户中的所有用户管理 Busy on Busy 或 Voicemail on Busy Enterprise。
    
- 为特定前端池中的所有用户管理 Busy on Busy 或 Voicemail on Busy。
    
- 为用户列表管理 Busy on Busy 或 Voicemail on Busy。
    
- 为单个用户管理 Busy on Busy 或 Voicemail on Busy。
    
## <a name="interoperability-with-voice-applications"></a>与语音应用程序的互操作性

忙碌选项提供与应用程序中以下语音应用程序的Skype for Business：
  
- 响应组 (RGS) 
    
  - 系统将忽略在响应组号码上设置的忙碌选项;将允许多个并发呼叫。 
    
  - 对于"忙碌选项"设置的"代理"，响应组中的当前助理路由体验将保持不变。
    
  - 从响应组向作为响应组代理的用户的呼叫不会受忙碌选项设置限制，并且将保持当前的 RGS 体验。
    
  - 对代理的非 RGS 相关呼叫将受其忙碌选项设置支持。
    
- Team Call－ 团队呼叫
    
  - 向为团队呼叫设置的用户的传入呼叫将优先忽略 Busy on Busy 和 Voicemail on Busy 设置。
    
  - 为用户设置忙碌选项后，当前的团队呼叫体验将保持不变。
    
  - 对此类用户进行的非团队呼叫相关呼叫将受其忙碌选项设置支持。
    
- 领导/管理员委派 
    
  - 对于设置为"高级/管理员委派"或"管理员"的用户的传入呼叫，其优先级将设置为忽略 Busy on Busy 和 Voicemail on Busy 设置。
    
  - 对于为管理员或领导设置的忙碌选项，当前的"上线/管理员委派"体验将保持不变。
    
  - 对管理员的非管理员/管理员委派相关呼叫将受其忙碌选项设置支持。
    
- 共享线路外观 
    
  - 将忽略为共享线路外观设置的用户帐户上的忙碌选项设置。 
    
  - 将改为使用共享线路外观的本机 Busy on Busy 和 Voicemail on Busy 选项。
    
- 呼叫 Parking Service 
    
  - 允许因超时而未取回且因超时而回响的已呼叫响铃到通过忙碌选项将呼叫接听到的用户。 
    
- 呼叫会议
    
  - 电话会议中的用户被视为忙碌，新的传入呼叫将因忙音信号而被拒绝，或根据用户的忙碌选项设置转发到语音邮件。
    
  - 不会阻止参加会议的用户通过忙碌选项发起新呼叫或会议。
    
  - 参加会议的用户仍能够接收新的会议邀请，但新的对等呼叫将被拒绝，其忙碌选项设置将被拒绝。
    
- 同时响铃和呼叫转发
    
    Busy on Busy 功能不能用于同时响铃和呼叫转发。
    

