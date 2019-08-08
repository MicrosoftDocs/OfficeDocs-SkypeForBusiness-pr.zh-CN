---
title: 自定义呼叫驻留 inSkype for Business 的暂停音乐
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: 在 Skype for Business Server Enterprise Voice 中自定义呼叫寄存音乐处于暂候状态。
ms.openlocfilehash: 834e6e811637c120e675a674f51ac0edeaf90542
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245625"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>自定义呼叫驻留 inSkype for Business 的暂停音乐
 
在 Skype for Business Server Enterprise Voice 中自定义呼叫寄存音乐处于暂候状态。
  
你可以将自己的音乐文件指定为保留音乐, 而不是 Skype for Business 服务器随附的默认音乐文件。 若要自定义保留音乐，请使用 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet。
  
> [!NOTE]
> 如果你自定义暂停的音乐并希望同一音乐用于多个网站, 则必须为运行呼叫驻留应用程序的每个网站配置音乐文件。 
  
### <a name="to-customize-the-music-file"></a>自定义音乐文件

1. 登录到将 Skype for Business Server Management Shell 作为 RTCUniversalServerAdmins 组的成员或必要的用户权限 (如 "**委派设置权限**" 中所述) 进行安装的计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
3. 运行：
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > 使用 **Get-CsService** cmdlet 可标识服务。 有关详细信息, 请参阅[CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)。 
  
    以下示例说明了如何以字节数组的形式获取文件 soothingmusic.wma 的内容并将其分配给变量。 然后，将音频文件指定为呼叫寄存的保留音乐文件。 有关详细信息, 请参阅[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)。
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>另请参阅

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
