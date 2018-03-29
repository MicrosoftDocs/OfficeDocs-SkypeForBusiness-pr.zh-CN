---
title: 在 Skype for Business 2015 中为用户启用呼叫寄存
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
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: 启用业务服务器企业语音调用公园在 Skype 的用户。
ms.openlocfilehash: 3af13e59541799a75c58f6e796bf07e7a978065e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="enable-call-park-for-users-in-skype-for-business-2015"></a>在 Skype for Business 2015 中为用户启用呼叫寄存
 
启用业务服务器企业语音调用公园在 Skype 的用户。
  
默认情况下，对所有用户禁用调用公园。 用户不能停放调用或检索暂停的调用直到它们对于调用公园在中启用了语音策略。
  
您可以启用呼叫公园在全局范围中，或者在站点范围或用户范围。 用户作用域优先于站点作用域，而站点作用域又优先于全局作用域。 如果您有多个语音策略，查看启用呼叫公园，不只是全球政策的所有策略。
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>要对用户的业务服务器控制面板来启用调用公园使用 Skype

1. 以 **RTCUniversalServerAdmins** 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开 Skype 业务服务器的控制面板。
    
3. 在左侧导航栏中，单击“语音路由”****。
    
4. 单击“语音策略”****选项卡。
    
5. 双击现有语音策略以打开“编辑语音策略”****对话框。
    
6. 在“呼叫功能”****下，选择“启用呼叫寄存”****。
    
7. 单击“确定”****保存语音策略。
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>若要使用 Cmdlet 以便挂断电话的用户

1. 以 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 管理角色成员的身份登录计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 运行：
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    例如，若要启用默认全局语音策略调用公园：
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>另请参阅

#### 

[创建或修改语音策略和业务 2015年的 Skype 在配置 PSTN 使用记录](voice-policy-and-pstn-usage-records.md)

