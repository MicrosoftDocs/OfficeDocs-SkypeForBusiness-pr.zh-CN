---
title: 为 Skype for Business 中的用户启用呼叫寄存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: 在 Skype for business Server Enterprise Voice 中启用呼叫寄存的用户。
ms.openlocfilehash: 326b1156ea3b300301b46324d90dbc7dde088b3d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291586"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>为 Skype for Business 中的用户启用呼叫寄存
 
在 Skype for business Server Enterprise Voice 中启用呼叫寄存的用户。
  
默认情况下, 将对所有用户禁用 "呼叫寄存"。 用户不能寄存通话或检索寄存的呼叫, 直到它们在语音策略中被启用呼叫寄存。
  
你可以在全局范围内或在网站范围或用户范围内启用呼叫寄存。 用户作用域优先于站点作用域，而站点作用域又优先于全局作用域。 如果你有多个语音策略, 请查看所有策略以启用呼叫寄存, 而不仅仅是全局策略。
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>使用 Skype for Business 服务器 "控制面板" 为用户启用呼叫寄存

1. 以 **RTCUniversalServerAdmins** 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开 "Skype for Business 服务器" 控制面板。
    
3. 在左侧导航栏中，单击“语音路由”****。
    
4. 单击“语音策略”**** 选项卡。
    
5. 双击现有语音策略以打开“编辑语音策略”**** 对话框。
    
6. 在“呼叫功能”**** 下，选择“启用呼叫寄存”****。
    
7. 单击“确定”**** 保存语音策略。
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>使用 Cmdlet 为用户启用呼叫寄存

1. 以 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 管理角色成员的身份登录计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
3. 运行：
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    例如, 若要为默认全局语音策略启用呼叫寄存, 请执行以下操作:
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>另请参阅



[在 Skype for Business 中创建或修改语音策略和配置 PSTN 使用记录](voice-policy-and-pstn-usage-records.md)

