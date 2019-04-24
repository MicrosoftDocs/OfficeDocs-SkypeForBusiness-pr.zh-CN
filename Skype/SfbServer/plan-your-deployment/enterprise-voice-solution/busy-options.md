---
title: 规划适用于 Skype for Business Server 的忙碌选项
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: 阅读有关 Skype 中的忙选项功能业务服务器。
ms.openlocfilehash: 41e34dbb4eaf4a264ba1cec3756cc53c78992611
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207074"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>规划适用于 Skype for Business Server 的忙碌选项
 
阅读有关 Skype 中的忙选项功能业务服务器。
  
忙碌选项是 2016 年 7 月累积更新中引入的新语音策略，允许你配置当用户正在接听电话或参加会议或将呼叫置于等待状态时传入呼叫的处理方式。 可以通过忙音信号拒绝新呼叫或传入呼叫，也可以将新呼叫或传入呼叫转接到语音邮件。 
  
已配对前端池和 Survivable Branch Server (SBS) 上的故障转移和灾难恢复支持忙碌选项策略。
  
本主题描述忙碌选项的功能。 有关如何安装和配置忙碌选项的信息，请参阅[Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)。
  
## <a name="configuration-options"></a>配置选项

如果已为组织启用忙碌选项，则组织中的所有用户（企业语音用户和非企业语音用户）都可以使用以下功能：
  
- Busy on Busy - 如果用户忙碌，将通过忙音信号拒绝新的传入呼叫。
    
- Voicemail on Busy - 如果用户忙碌，新的传入呼叫会转接到语音邮件。
    
忙碌选项功能可提供故障转移功能。 如果出现问题，并且用户故障转移到另一个前端服务器或另一个池中 Skype 业务服务器，将保留其忙选项设置。
  
无论其忙碌选项如何配置，都不会阻止通话或会议中的用户或将呼叫置于等待状态的用户发起新呼叫或会议。   
  
配置后，忙选项设置为有效商业调用设备和客户端的所有用户的 Skype。 基于用户的忙碌选项设置，被拒绝或发送至语言邮件的呼叫不会在用户已登录的任何呼叫设备（包括 Macintosh、Windows 桌面、移动客户端或 IP 电话）上响铃。 
  
用户将业务客户端和设备，其 Skype 上查看错过的呼叫通知，便可得到通知通过电子邮件以及。 由于 Busy on Busy 而被拒绝的呼叫的呼叫者将在其 Skype for Business 客户端中看到一个通知，表明他们尝试联系的用户正在通话中。
  
您可以使用 Skype 业务 PowerShell cmdlet 配置选项忙功能：
  
- 为企业启用或禁用忙碌选项语言策略。
    
- 为企业中的所有用户管理 Busy on Busy 或 Voicemail on Busy。
    
- 为驻留在特定前端池中的所有用户管理 Busy on Busy 或 Voicemail on Busy。
    
- 为某些用户管理 Busy on Busy 或 Voicemail on Busy。
    
- 为某个用户管理 Busy on Busy 或 Voicemail on Busy。
    
## <a name="interoperability-with-voice-applications"></a>与语音应用程序的互操作性

忙选项提供以下语音应用程序中的业务的 Skype 的互操作性：
  
- 响应组 (RGS)
    
  - 响应组号码上设置的忙碌选项将被系统忽略；允许多个并发呼叫。 
    
  - 对于具有忙碌选项设置的代理，响应组中的当前助理路由体验将保持不变。
    
  - 忙碌选项设置不会限制从响应组向属于响应组代理的用户发起的呼叫，并且当前的 RGS 体验将保持不变。
    
  - 向代理发起的非 RGS 相关呼叫将由其忙碌选项设置处理。
    
- Team Call－ 团队呼叫
    
  - 将确定优先级传入呼叫的团队呼叫设置用户忽略上忙闲和忙碌设置语音邮件。
    
  - 使用为用户设置的忙碌选项时，当前的团队呼叫体验将保持不变。
    
  - 向此类用户发起的非团队呼叫相关呼叫将由其忙碌选项设置处理。
    
- 上级/管理员委派  
    
  - 将优先顺序到用户的经理/管理员委派为上级或管理员可以设置的传入呼叫忽略上忙闲和忙碌设置语音邮件。
    
  - 使用为管理员或上级设置的忙碌选项时，当前的上级/管理员委派体验将保持不变。
    
  - 向管理员发起的非上级/管理员委派相关呼叫将由其忙碌选项设置处理。
    
- 共享线路外观    
    
  - 用户帐户中为共享线路外观设置的忙碌选项将被忽略。 
    
  - 将改为有效共享的行外观上忙碌的本机闲和忙碌选项的语音邮件。
    
- 呼叫寄存服务  
    
  - 允许未检索到且由于超时而回拨的寄存呼叫对通过忙碌选项寄存呼叫的用户响铃。 
    
- 电话会议
    
  - 电话会议中的用户视为忙碌，并且将根据其忙碌选项设置通过忙音信号拒绝新的传入呼叫，或将新的传入呼叫转接到语音邮件。
    
  - 不会阻止会议中的用户通过忙碌选项发起新的呼叫或会议。
    
  - 会议中的用户仍可以接收到新会议邀请，但会根据其忙碌选项设置拒绝新的对等呼叫。
    
- 同时响铃和呼叫转移
    
    Busy on Busy 功能设计为不与同时响铃和呼叫转移一起使用。
    

