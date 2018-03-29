---
title: Skype for Business Server 2015 中的通知应用程序部署过程
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: 部署过程和 Skype 业务服务器企业语音的发布应用程序的步骤。
ms.openlocfilehash: 2188faaf80b3caa89acafd7fdf441ab895d11c45
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的通知应用程序部署过程
 
部署过程和 Skype 业务服务器企业语音的发布应用程序的步骤。
  
发布应用程序是企业语音功能，使您能够配置未指定扩展 （扩展适用于您的组织，但不是会分配给一个人或一部电话） 对的调用会发生什么情况。 例如，可以将对未分配号码的呼叫配置为播放消息或转接至其他目标，或者同时执行这两种操作。
  
发布应用程序时部署企业语音作为特征响应组上的应用程序的前端服务器或标准版服务器安装。 需要上载音频文件或配置文本到语音转换 (TTS)，并配置未分配号码表来配置通知。
  
本节概述了部署发布应用程序所涉及的步骤。 配置通知之前，您必须部署企业语音。 发布应用程序所需的组件已安装并启用部署企业语音时。
  
**通知部署过程**

|**阶段**|**步骤**|**角色**|**部署文档**|
|:-----|:-----|:-----|:-----|
|配置通知设置  <br/> | 通过录制并上载音频文件或使用文本到语音转换 (TTS) 来创建通知。 <br/>  配置未分配号码表中的未分配号码范围，然后将其与相应的通知关联。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[创建或删除公告在 Skype 的业务服务器 2015](create-an-announcement.md) <br/> [创建或修改业务服务器 2015 Skype 在未分配编号范围](create-or-modify-an-unassigned-number-range.md) <br/> |
|验证通知部署  <br/> |通过侦听通知来进行测试以验证配置是否按预期工作。  <br/> |-  <br/> |[（可选）验证在企业 2015年的 Skype 发布部署](optional-verify-announcement-deployment.md) <br/> |
   

