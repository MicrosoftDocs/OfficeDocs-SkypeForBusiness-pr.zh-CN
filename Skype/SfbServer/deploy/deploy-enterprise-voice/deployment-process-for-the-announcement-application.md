---
title: Skype for Business Server 中的发布应用程序的部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Skype for business Server 企业版中发布应用程序的部署过程和步骤。
ms.openlocfilehash: 2edb9364408658e9a164210a9fcd5a0196b10da7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245309"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Skype for Business Server 中的发布应用程序的部署过程
 
Skype for business Server 企业版中发布应用程序的部署过程和步骤。
  
"发布" 应用程序是一种企业语音功能, 可让你配置调用未分配的扩展 (对你的组织有效, 但未分配给某个人或手机的扩展) 所发生的情况。 例如，可以将对未分配号码的呼叫配置为播放消息或转接至其他目标，或者同时执行这两种操作。
  
在部署企业语音时, "发布" 应用程序作为 "响应组应用程序" 的一项功能安装在前端服务器或标准版服务器上。 需要上载音频文件或配置文本到语音转换 (TTS)，并配置未分配号码表来配置通知。
  
本部分概述了部署公告应用程序所涉及的步骤。 您必须先部署企业语音, 然后才能配置公告。 部署 "企业语音" 时, 安装并启用公告应用程序所需的组件。
  
**通知部署过程**

|**阶段**|**步骤**|**Roles**|**部署文档**|
|:-----|:-----|:-----|:-----|
|配置通知设置  <br/> | 通过录制并上载音频文件或使用文本到语音转换 (TTS) 来创建通知。 <br/>  配置未分配号码表中的未分配号码范围，然后将其与相应的通知关联。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[在 Skype for Business 服务器中创建或删除公告](create-an-announcement.md) <br/> [在 Skype for Business 服务器中创建或修改未分配的号码范围](create-or-modify-an-unassigned-number-range.md) <br/> |
|验证通知部署  <br/> |通过侦听通知来进行测试以验证配置是否按预期工作。  <br/> |-  <br/> |[可选在 Skype for Business 中验证公告部署](optional-verify-announcement-deployment.md) <br/> |
   

