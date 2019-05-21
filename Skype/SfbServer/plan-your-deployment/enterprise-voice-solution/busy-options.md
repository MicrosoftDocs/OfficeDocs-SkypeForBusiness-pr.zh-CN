---
title: 规划适用于 Skype for Business Server 的忙碌选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: 阅读有关 Skype for Business 服务器中的 "忙碌选项" 功能的信息。
ms.openlocfilehash: 8e88b4bf3b92c7fea9bcf79822e2711ff3bee7de
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277102"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>规划适用于 Skype for Business Server 的忙碌选项
 
阅读有关 Skype for Business 服务器中的 "忙碌选项" 功能的信息。
  
忙碌选项是 2016 年 7 月累积更新中引入的新语音策略，允许你配置当用户正在接听电话或参加会议或将呼叫置于等待状态时传入呼叫的处理方式。 可以通过忙音信号拒绝新呼叫或传入呼叫，也可以将新呼叫或传入呼叫转接到语音邮件。 
  
已配对前端池和 Survivable Branch Server (SBS) 上的故障转移和灾难恢复支持忙碌选项策略。
  
本主题描述忙碌选项的功能。 有关如何安装和配置忙碌选项的信息，请参阅[Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)。
  
## <a name="configuration-options"></a>配置选项

如果已为组织启用忙碌选项，则组织中的所有用户（企业语音用户和非企业语音用户）都可以使用以下功能：
  
- Busy on Busy - 如果用户忙碌，将通过忙音信号拒绝新的传入呼叫。
    
- Voicemail on Busy - 如果用户忙碌，新的传入呼叫会转接到语音邮件。
    
忙碌选项功能可提供故障转移功能。 如果出现问题, 并且用户故障转移到另一台前端服务器或 Skype for Business Server 中的另一个池, 则将保留其 "忙碌" 选项设置。
  
无论其忙碌选项如何配置，都不会阻止通话或会议中的用户或将呼叫置于等待状态的用户发起新呼叫或会议。   
  
配置完成后, "忙碌选项" 设置将对所有用户的 Skype for Business 呼叫设备和客户端生效。 基于用户的忙碌选项设置，被拒绝或发送至语言邮件的呼叫不会在用户已登录的任何呼叫设备（包括 Macintosh、Windows 桌面、移动客户端或 IP 电话）上响铃。 
  
用户将在其 Skype for Business 客户端和设备上看到错过的通话通知, 这些通知也将通过电子邮件通知。 由于 Busy on Busy 而被拒绝的呼叫的呼叫者将在其 Skype for Business 客户端中看到一个通知，表明他们尝试联系的用户正在通话中。
  
你可以使用 Skype for Business PowerShell cmdlet 配置 "忙碌选项" 功能, 以便:
  
- 为企业启用或禁用忙碌选项语言策略。
    
- 为企业中的所有用户管理 Busy on Busy 或 Voicemail on Busy。
    
- 为驻留在特定前端池中的所有用户管理 Busy on Busy 或 Voicemail on Busy。
    
- 为某些用户管理 Busy on Busy 或 Voicemail on Busy。
    
- 为某个用户管理 Busy on Busy 或 Voicemail on Busy。
    
## <a name="interoperability-with-voice-applications"></a>与语音应用程序的互操作性

在 Skype for Business 中, 繁忙选项提供与以下语音应用程序的互操作性:
  
- 响应组 (RGS)
    
  - 响应组号码上设置的忙碌选项将被系统忽略；允许多个并发呼叫。 
    
  - 对于具有忙碌选项设置的代理，响应组中的当前助理路由体验将保持不变。
    
  - 忙碌选项设置不会限制从响应组向属于响应组代理的用户发起的呼叫，并且当前的 RGS 体验将保持不变。
    
  - 向代理发起的非 RGS 相关呼叫将由其忙碌选项设置处理。
    
- Team Call－ 团队呼叫
    
  - 对设置为团队通话的用户的传入呼叫将优先于 "忽略占线" 和 "繁忙的语音邮件" 设置。
    
  - 使用为用户设置的忙碌选项时，当前的团队呼叫体验将保持不变。
    
  - 向此类用户发起的非团队呼叫相关呼叫将由其忙碌选项设置处理。
    
- 上级/管理员委派  
    
  - 为上司或管理员设置为老板/管理员委派的来电将优先于 "忽略繁忙" 和 "占线" 设置的 "占线"。
    
  - 使用为管理员或上级设置的忙碌选项时，当前的上级/管理员委派体验将保持不变。
    
  - 向管理员发起的非上级/管理员委派相关呼叫将由其忙碌选项设置处理。
    
- 共享线路外观    
    
  - 用户帐户中为共享线路外观设置的忙碌选项将被忽略。 
    
  - 共享线路外观的本地忙/闲电话将改为接受 "忙碌" 选项。
    
- 呼叫寄存服务  
    
  - 允许未检索到且由于超时而回拨的寄存呼叫对通过忙碌选项寄存呼叫的用户响铃。 
    
- 电话会议
    
  - 电话会议中的用户视为忙碌，并且将根据其忙碌选项设置通过忙音信号拒绝新的传入呼叫，或将新的传入呼叫转接到语音邮件。
    
  - 不会阻止会议中的用户通过忙碌选项发起新的呼叫或会议。
    
  - 会议中的用户仍可以接收到新会议邀请，但会根据其忙碌选项设置拒绝新的对等呼叫。
    
- 同时响铃和呼叫转移
    
    Busy on Busy 功能设计为不与同时响铃和呼叫转移一起使用。
    

