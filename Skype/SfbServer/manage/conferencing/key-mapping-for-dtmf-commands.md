---
title: 管理业务服务器中 Skype 的 DTMF 命令的键映射
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 摘要： 了解如何管理业务服务器中 Skype 的双音多频 (DTMF) 命令的键映射。
ms.openlocfilehash: 33ab031e6032b6246dd637bc55c9ec6b600f0c82
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898069"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>管理业务服务器中 Skype 的 DTMF 命令的键映射
 
**摘要：** 了解如何管理业务服务器中 Skype 的双音多频 (DTMF) 命令的键映射。
  
电话拨入式会议用户可以在电话小键盘上按键以执行双音多频 (DTMF) 命令。通过 DTMF 命令，拨入会议的用户可以使用其电话上的小键盘控制会议设置（例如，将自己静音和取消静音，或者锁定和解锁会议）。 
  
若要管理使用 DTMF 命令的键，用于 Skype **Get-csdialinconferencingdtmfconfiguration**、 **Set-csdialinconferencingdtmfconfiguration**，和**业务 Server Management Shell新 CsDialinConferencingDtmfConfiguration** cmdlet。
  
为站点创建新的 DTMF 设置后，站点设置将优先于全局设置。 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>管理 DTMF 命令的键映射

1. 以  RTCUniversalServerAdmins  组成员或者  Cs-ServerAdministrator  或  CsAdministrator  角色成员的身份登录计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
3. 若要查看用于电话拨入式会议的 DTMF 设置，请在命令提示符下运行下面的命令：
    
   ```
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. 若要修改用于电话拨入式会议的 DTMF 设置，请运行下面的 cmdlet，并对你要更改的每个选项指定要按下的键：
    
   ```
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. （可选）若要为特定站点创建其他 DTMF 命令集，请使用带有站点 Identity 的 **New-CsDialinConferencingDtmfConfiguration** cmdlet。
    
下面的示例可使启用或禁用通知所按的键和将所有与会者静音和取消静音所按的键交换。由于未指定 Identity，因此这些更改将应用于全局 DTMF 设置：
  
```
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

有关详细信息，请参阅[Get-csdialinconferencingdtmfconfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps)、 [Set-csdialinconferencingdtmfconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)和[新建 CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)。
  

