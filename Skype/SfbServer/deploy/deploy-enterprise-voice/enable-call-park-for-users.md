---
title: 为呼叫服务中的用户启用Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: 为用户启用呼叫Skype for Business Server 企业语音。
ms.openlocfilehash: 87ac29c8f9b6c893149db8fb91561ee4b3cf1166
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843505"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>为呼叫服务中的用户启用Skype for Business
 
为用户启用呼叫Skype for Business Server 企业语音。
  
默认情况下，将禁用所有用户的呼叫等待。 在语音策略中为呼叫等待启用之前，用户无法呼叫或取回已呼叫。
  
可以在全局范围、站点范围或用户范围启用呼叫。 用户作用域优先于站点范围，而站点作用域优先于全局范围。 如果你有多个语音策略，请查看所有策略以启用呼叫管理，而不只是全局策略。
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>使用Skype for Business Server控制面板为用户启用呼叫等待

1. 以 **RTCUniversalServerAdmins** 组的成员或 **CsVoiceAdministrator、CsServerAdministrator** 或 **CsAdministrator** 管理角色 成员登录到计算机。 
    
2. 打开Skype for Business Server控制面板"。
    
3. 在左侧导航栏中，单击 **“语音路由”**。
    
4. 单击" **语音策略"** 选项卡。
    
5. 双击现有语音策略以打开" **编辑语音策略"** 对话框。
    
6. 在 **"呼叫功能"** 下，选择 **"启用呼叫管理"。**
    
7. 单击 **"** 确定"保存语音策略
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>使用 Cmdlet 为用户启用呼叫等待

1. 以 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 管理角色成员的身份登录计算机。
    
2. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
3. 运行：
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    例如，若要为默认全局语音策略启用呼叫等待：
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>另请参阅



[创建或修改语音策略，并配置 PSTN 用法Skype for Business](voice-policy-and-pstn-usage-records.md)

