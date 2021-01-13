---
title: 规划 Skype for Business Server 的忙碌选项
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: 阅读 Skype for Business Server 中的忙碌选项功能。
ms.openlocfilehash: 558d7486ca7aaa794c3114f5c210702a54e02fc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813692"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>规划 Skype for Business Server 的忙碌选项
 
阅读 Skype for Business Server 中的忙碌选项功能。
  
忙碌选项是 2016 年 7 月累积更新中引入的新语音策略，允许你配置在用户已接听电话或参加会议或将呼叫置于保留状态时如何处理传入呼叫。 可以使用忙音信号拒绝新呼叫或传入呼叫，也可以将新呼叫或传入呼叫转发到语音邮件。 
  
在配对前端池和 Survivable Branch Servers (SBS 服务器上支持忙碌选项策略) 。
  
本主题介绍忙碌选项的功能。 若要了解如何安装和配置忙碌选项，请参阅安装和配置 [Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)的忙碌选项。
  
## <a name="configuration-options"></a>配置选项

如果为组织启用了忙碌选项，则组织中所有用户（包括企业语音用户和非 企业语音用户）都可以使用以下功能：
  
- 忙碌 - 在用户忙碌时，新传入呼叫将因忙音信号被拒绝。
    
- Voicemail on Busy - 其中的新传入呼叫将在用户忙碌时转发到语音邮件。
    
忙碌选项功能提供故障转移功能。 如果出现问题，并且用户故障转移到另一台前端服务器或 Skype for Business Server 中的另一个池，则其忙碌选项设置将保留。
  
无论如何配置忙碌选项，呼叫或会议中的用户或呼叫保持的用户不会阻止发起新呼叫或会议。 
  
配置后，忙碌选项设置将作用于用户的 Skype for Business 呼叫设备和客户端。 根据用户的忙碌选项设置，被拒绝或发送到语音邮件的呼叫不会在用户登录的任何用户的呼叫设备（包括 Macintosh、Windows 桌面、移动客户端或 IP 电话）上响铃。 
  
用户将在 Skype for Business 客户端和设备上看到未接来电通知，并且也会收到电子邮件通知。 呼叫因忙碌而被拒绝的呼叫的呼叫者将在 Skype for Business 客户端中看到一条通知，指出他们尝试联系的用户正忙于其他呼叫。
  
可以使用 Skype for Business PowerShell cmdlet 将忙碌选项功能配置为：
  
- 为企业启用或禁用忙碌选项语音策略。
    
- 为企业中所有用户管理 Busy on Busy 或 Voicemail on Busy。
    
- 为特定前端池中的所有用户管理 Busy on Busy 或 Voicemail on Busy。
    
- 为用户列表管理 Busy on Busy 或 Voicemail on Busy。
    
- 为单个用户管理 Busy on Busy 或 Voicemail on Busy。
    
## <a name="interoperability-with-voice-applications"></a>与语音应用程序的互操作性

忙碌选项提供与 Skype for Business 中的以下语音应用程序的互操作性：
  
- 响应组 (RGS) 
    
  - 系统将忽略在响应组号码上设置的忙碌选项;允许多个并发呼叫。 
    
  - 对于忙碌选项设置的代理，响应组中的当前助理路由体验将保持不变。
    
  - 来自响应组向作为响应组代理的用户的呼叫不会受忙碌选项设置限制，并且将保持当前的 RGS 体验。
    
  - 与代理相关的非 RGS 呼叫将受其忙碌选项设置支持。
    
- Team Call－ 团队呼叫
    
  - 为团队呼叫设置的用户的传入呼叫将设置为忽略"忙碌时忙碌"和"忙时语音邮件"设置。
    
  - 对于为用户设置的忙碌选项，当前的团队呼叫体验将保持不变。
    
  - 向此类用户进行的非团队呼叫相关呼叫将受其忙碌选项设置支持。
    
- 管理员/管理员委派 
    
  - 对于设置为"行政/管理员委派"或"管理员"的用户的传入呼叫，其优先级将设置为忽略"忙碌时忙碌"和"忙时语音邮件"设置。
    
  - 当前"管理员/管理员委派"体验将保持不变，为管理员或管理员设置忙碌选项。
    
  - 非管理员/管理员委派与管理员相关的呼叫将受其忙碌选项设置支持。
    
- 共享线路外观 
    
  - 将忽略为共享线路外观设置的用户帐户的忙碌选项设置。 
    
  - 共享线路外观的本机 Busy on Busy 和 Voicemail on Busy 选项将改为可用。
    
- 呼叫收费服务 
    
  - 允许因超时而未取回且因超时而回响的已呼叫响铃到通过忙碌选项将呼叫接听到该呼叫的用户。 
    
- 呼叫会议
    
  - 电话会议中的用户被视为忙碌，新的传入呼叫将因忙音信号被拒绝或根据用户的忙碌选项设置转发到语音邮件。
    
  - 不会阻止参加会议的用户通过忙碌选项发起新呼叫或会议。
    
  - 参加会议的用户仍能够接收新的会议邀请，但新的对等呼叫将按照其忙碌选项设置被拒绝。
    
- 同时响铃和呼叫转发
    
    忙碌时忙碌功能不能用于同时响铃和呼叫转发。
    

