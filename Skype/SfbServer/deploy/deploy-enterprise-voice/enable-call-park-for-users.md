---
title: 在 Skype for Business 中为用户启用呼叫等待
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: 在 Skype for Business Server 服务中为用户启用呼叫企业语音。
ms.openlocfilehash: e9bbc42f5940af0cfc94ab83eae981dd023c9fcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830952"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>在 Skype for Business 中为用户启用呼叫等待
 
在 Skype for Business Server 服务中为用户启用呼叫企业语音。
  
默认情况下，为所有用户禁用呼叫等待。 在语音策略中为呼叫等待启用之前，用户无法呼叫或取回已呼叫。
  
可以在全局范围、站点范围或用户范围启用呼叫。 用户作用域优先于站点范围，站点作用域优先于全局范围。 如果你有多个语音策略，请查看所有策略以启用呼叫管理，而不只是全局策略。
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>使用 Skype for Business Server 控制面板为用户启用呼叫等待

1. 以 **RTCUniversalServerAdmins** 组的成员或 **CsVoiceAdministrator、CsServerAdministrator** 或 **CsAdministrator** 管理角色 的成员登录到计算机。 
    
2. 打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击 **“语音路由”**。
    
4. 单击 **"语音策略"** 选项卡。
    
5. 双击现有语音策略以打开 **"编辑语音策略"** 对话框。
    
6. 在 **"呼叫功能**"下，**选择"启用呼叫允许"。**
    
7. 单击 **"** 确定"保存语音策略
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>使用 Cmdlet 为用户启用呼叫等待

1. 以 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 管理角色成员的身份登录计算机。
    
2. 启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
3. 运行：
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    例如，若要为默认全局语音策略启用呼叫等待：
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>另请参阅



[在 Skype for Business 中创建或修改语音策略和配置 PSTN 用法记录](voice-policy-and-pstn-usage-records.md)

