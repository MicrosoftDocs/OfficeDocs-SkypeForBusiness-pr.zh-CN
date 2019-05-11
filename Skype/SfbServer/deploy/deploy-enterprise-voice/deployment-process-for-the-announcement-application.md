---
title: Skype 中为 Business Server 的通知应用程序的部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: 部署过程和 Skype 中为 Business Server 企业语音的通知应用程序的步骤。
ms.openlocfilehash: 27e22c95e58ac84fa3f27aef8b2d18cb1b1226dc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892557"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Skype 中为 Business Server 的通知应用程序的部署过程
 
部署过程和 Skype 中为 Business Server 企业语音的通知应用程序的步骤。
  
通知应用程序是一种企业语音功能，使您能够配置呼叫未分配的分机号 （扩展可用于您的组织，但未分配给联系人或电话） 会发生什么情况。 例如，可以将对未分配号码的呼叫配置为播放消息或转接至其他目标，或者同时执行这两种操作。
  
部署企业语音时，将作为前端服务器或 Standard Edition 服务器上的响应组应用程序功能安装通知应用程序。 需要上载音频文件或配置文本到语音转换 (TTS)，并配置未分配号码表来配置通知。
  
本节概述部署通知应用程序所涉及的步骤。 配置通知之前，必须部署企业语音。 安装和部署企业语音时启用通知应用程序所需的组件。
  
**通知部署过程**

|**阶段**|**步骤**|**Roles**|**部署文档**|
|:-----|:-----|:-----|:-----|
|配置通知设置  <br/> | 通过录制并上载音频文件或使用文本到语音转换 (TTS) 来创建通知。 <br/>  配置未分配号码表中的未分配号码范围，然后将其与相应的通知关联。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[创建或删除业务服务器中 Skype 通知](create-an-announcement.md) <br/> [创建或修改业务服务器 Skype 中的未分配号码范围](create-or-modify-an-unassigned-number-range.md) <br/> |
|验证通知部署  <br/> |通过侦听通知来进行测试以验证配置是否按预期工作。  <br/> |-  <br/> |[（可选）验证通知部署中的业务的 Skype](optional-verify-announcement-deployment.md) <br/> |
   

