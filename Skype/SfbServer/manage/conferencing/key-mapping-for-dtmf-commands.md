---
title: 在部署中管理 DTMF 命令的Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 摘要：了解如何在 Skype for Business Server 中管理双音多频 (DTMF) 键Skype for Business Server。
ms.openlocfilehash: f4b380bddb9a0bc244887c44c85f02157f75b0e6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837634"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>在部署中管理 DTMF 命令的Skype for Business Server
 
**摘要：** 了解如何在 Skype for Business Server 中管理双音多频 (DTMF) 键映射。
  
电话拨入式会议用户可以在电话小键盘上按键以执行双音多频 (DTMF) 命令。 通过 DTMF 命令，拨入会议的用户可以使用其电话上的小键盘控制会议设置（例如，将自己静音和取消静音，或者锁定和解锁会议）。 
  
要管理用于 DTMF 命令的密钥，请通过 **Get-CsDialinConferencingDtmfConfiguration、Set-CsDialinConferencingDtmfConfiguration** 和 **New-CsDialinConferencingDtmfConfiguration** cmdlet 使用 Skype for Business Server 命令行管理程序。 
  
为站点创建新的 DTMF 设置后，站点设置将优先于全局设置。 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>管理 DTMF 命令的键映射

1. 以 RTCUniversalServerAdmins 组成员或者 Cs-ServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。
    
2. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
3. 若要查看用于电话拨入式会议的 DTMF 设置，在命令提示符下运行以下命令：
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. 要修改用于电话拨入式会议的 DTMF 设置，请运行以下 cmdlet 并指定要更改的每个选项所按的键：
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. （可选）要为特定站点创建其他 DTMF 命令集，请使用带有站点 Identity 的 **New-CsDialinConferencingDtmfConfiguration** cmdlet。
    
以下示例将切换启用或禁用通知所按的键和将所有参与者静音和取消静音所按的键。 由于未指定 Identity，因此这些更改适用于全局 DTMF 设置：
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

有关详细信息，请参阅[Get-CsDialInConferencingDtmfConfiguration、Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps)和[New-CsDialInConferencingDtmfConfiguration。](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) [](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)
