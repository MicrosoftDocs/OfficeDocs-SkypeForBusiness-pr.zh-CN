---
title: 通知应用程序的部署过程Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: 通知应用程序的部署过程和Skype for Business Server 企业语音。
---

# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>通知应用程序的部署过程Skype for Business Server
 
通知应用程序的部署过程和Skype for Business Server 企业语音。
  
通知应用程序是一项 企业语音 功能，它使您能够配置对未分配分机 (的调用会发生什么情况，这些分机对组织有效，但不分配给用户或电话) 。 例如，可以将对未分配号码的呼叫配置为播放消息或转接至其他目标，或者同时执行这两种操作。
  
部署通知应用程序时，通知应用程序会作为响应组应用程序的一项功能Standard Edition前端服务器或 企业语音。 需要通过上载音频文件或配置文本到语音转换 (TTS) 和配置未分配号码表来配置通知。
  
本节概述部署通知应用程序所涉及的步骤。 在配置企业语音之前，必须部署这些通知。 部署通知应用程序所需的组件时，将安装并启用企业语音。
  
**通知部署过程**

|**阶段**|**步骤**|**Roles**|**部署文档**|
|:-----|:-----|:-----|:-----|
|配置通知设置  <br/> | 通过录制并上载音频文件或使用文本到语音转换 (TTS) 来创建通知。 <br/>  配置未分配号码表中的未分配号码范围，然后将其与相应的通知关联。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[在邮件中删除通知Skype for Business Server](create-an-announcement.md) <br/> [Create or modify an unassigned number range in Skype for Business Server](create-or-modify-an-unassigned-number-range.md) <br/> |
|验证通知部署  <br/> |通过侦听通知来进行测试以验证配置是否按预期工作。  <br/> |-  <br/> |[ (中) 验证通知部署Skype for Business](optional-verify-announcement-deployment.md) <br/> |
   

