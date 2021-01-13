---
title: 在Skype for Business 中自定义呼叫保留音乐
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
description: 在 Skype for Business Server 服务中自定义保持呼叫企业语音。
ms.openlocfilehash: 766b51895acda27c0558352968d21a39764b13a6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837072"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>在Skype for Business 中自定义呼叫保留音乐
 
在 Skype for Business Server 服务中自定义保持呼叫企业语音。
  
你可以指定自己的用于保持音乐的音乐文件，而不是 Skype for Business Server 附带的默认音乐文件。 若要自定义保留音乐，请使用 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet。
  
> [!NOTE]
> 如果自定义保持音乐，并且希望多个网站具有相同的音乐，则必须为运行呼叫保留应用程序的每个站点配置音乐文件。 
  
### <a name="to-customize-the-music-file"></a>自定义音乐文件

1. 以 RTCUniversalServerAdmins 组的成员或委派安装权限中所述的必要用户权限登录到安装了 Skype for Business Server 命令行管理程序 的计算机 **。**
    
2. 启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
3. 运行：
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > 使用 **Get-CsService** cmdlet 可标识服务。 有关详细信息，请参阅[Get-CsService。](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps) 
  
    以下示例说明了如何以字节数组的形式获取文件 soothingmusic.wma 的内容并将其分配给变量。 然后，将音频文件指定为呼叫寄存的保留音乐文件。 有关详细信息，请参阅 [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)。
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>另请参阅

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
