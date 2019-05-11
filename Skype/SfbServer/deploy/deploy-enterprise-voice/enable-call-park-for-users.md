---
title: Skype for Business 中的用户启用呼叫寄存
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
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Skype 中的呼叫寄存的用户启用业务 Server 企业语音。
ms.openlocfilehash: 228ff5549487df04a264ed217bed43196d93ca8d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892466"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Skype for Business 中的用户启用呼叫寄存
 
Skype 中的呼叫寄存的用户启用业务 Server 企业语音。
  
默认情况下，对所有用户禁用呼叫寄存。 用户无法寄存呼叫或取回寄存的呼叫，将在语音策略中启用呼叫寄存后。
  
您可以启用呼叫寄存在全局范围，或在 site 作用域或用户作用域。 用户作用域优先于站点作用域，而站点作用域又优先于全局作用域。 如果您有多个语音策略，请查看所有策略，以便启用呼叫寄存，而不仅仅是全局策略。
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>若要为用户启用呼叫寄存的业务 Server Control Panel 使用 Skype

1. 以 **RTCUniversalServerAdmins** 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“语音路由”****。
    
4. 单击“语音策略”**** 选项卡。
    
5. 双击现有语音策略以打开“编辑语音策略”**** 对话框。
    
6. 在“呼叫功能”**** 下，选择“启用呼叫寄存”****。
    
7. 单击“确定”**** 保存语音策略。
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>为用户启用呼叫寄存使用 Cmdlet

1. 以 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 管理角色成员的身份登录计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
3. 运行：
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    例如，若要为默认全局语音策略启用呼叫寄存：
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>另请参阅



[创建或修改语音策略和配置 PSTN 用法记录中的业务的 Skype](voice-policy-and-pstn-usage-records.md)

