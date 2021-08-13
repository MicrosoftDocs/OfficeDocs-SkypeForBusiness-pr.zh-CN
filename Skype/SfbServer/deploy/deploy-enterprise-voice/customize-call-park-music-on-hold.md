---
title: 在Skype for Business 中自定义呼叫等待音乐
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
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: 自定义呼叫管理中的呼叫保留Skype for Business Server 企业语音。
ms.openlocfilehash: 6dc080071df29e12a979e2591a73c02439a0a6271cda45b4105a009d1c70e307
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323534"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>在Skype for Business 中自定义呼叫等待音乐
 
自定义呼叫管理中的呼叫保留Skype for Business Server 企业语音。
  
您可以指定您自己的用于保持音乐的音乐文件，而不是默认音乐文件（Skype for Business Server）。 若要自定义保留音乐，请使用 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet。
  
> [!NOTE]
> 如果自定义保持音乐，并且希望多个站点具有相同的音乐，则必须为运行呼叫保留应用程序的每个站点配置音乐文件。 
  
### <a name="to-customize-the-music-file"></a>自定义音乐文件

1. 以 RTCUniversalServerAdmins 组的成员或必要的用户权限（如D委托安装权限中所述）登录到安装了命令行管理程序Skype for Business Server **的计算机。**
    
2. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
3. 运行：
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > 使用 **Get-CsService** cmdlet 可标识服务。 有关详细信息，请参阅[Get-CsService。](/powershell/module/skype/get-csservice?view=skype-ps) 
  
    以下示例说明了如何以字节数组的形式获取文件 soothingmusic.wma 的内容并将其分配给变量。 然后，将音频文件指定为呼叫寄存的保留音乐文件。 有关详细信息，请参阅 [Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)。
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>另请参阅

[Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps)