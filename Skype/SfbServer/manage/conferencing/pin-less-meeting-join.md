---
title: 在会议部署中配置无 PIN Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 摘要：了解如何在 Skype for Business Server 中配置无 PIN 会议加入Skype for Business Server。
ms.openlocfilehash: 82101f391b4b0713495eade53e092fefff8a053e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385710"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>在会议部署中配置无 PIN Skype for Business Server
 
**摘要：** 了解如何在 Skype for Business Server 中配置无 PIN 会议加入Skype for Business Server。
  
当拨入呼叫者尝试加入会议时，如果演示者尚未在呼叫中，并且拨入呼叫者尚未输入主持人 PIN，则会议 自动助理 (CAA) 服务将呼叫者放在一个与大厅 &#x2014; 不同的保持笔中。 无 PIN 会议加入选项允许拨入呼叫者加入会议，无需输入领导者 PIN，即使他们是第一个呼叫者。 
  
配置此功能时，请牢记以下事项：
  
- 仅适用于私人会议。
    
- 允许 PSTN 呼叫者在没有经过身份验证的用户的情况下留在私人会议中。
    
- 更改设置后，它适用于所有现有和新的私人会议。
    
- 可以在组织者的站点或全局级别启用。
    
- 可以针对以下任一项设置可以绕过大厅的选项： 
    
  - **来自我的组织的任何人与呼叫者直接进入**
    
  - **任何人 (与呼叫**) 联系的任何人 (这是默认设置。) 
    
- 当配置为启用无 PIN 加入时，CAA 服务仍提示输入领导者 PIN。 无论输入了 PIN，用户都可以加入会议。 但是，保留输入领导者 PIN 的能力允许拨入呼叫者以领导者身份进行身份验证并在必要时管理会议。
    
## <a name="configure-pin-less-meeting-join"></a>配置无 PIN 会议加入

若要为用户启用无 PIN 会议加入，请使用带 AllowAnonymousPstnActivation 参数的 [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet，如下所示：
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

例如，以下命令为站点 Redmond 启用无 PIN 会议加入：
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

出于安全考虑，当启用无 PIN 会议加入时，你可能希望通过确保 ConferencingPolicy 设置如下来限制匿名用户拨出：
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

有关详细信息，请参阅 [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
