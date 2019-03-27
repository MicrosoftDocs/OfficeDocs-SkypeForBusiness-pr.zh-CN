---
title: 自定义业务保留 inSkype 的呼叫寄存音乐
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: 自定义音乐中 Skype 业务 Server 企业语音呼叫寄存。
ms.openlocfilehash: e3d1ccdf70278173bf5a3a448e5330a24879d117
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895431"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>自定义业务保留 inSkype 的呼叫寄存音乐
 
自定义音乐中 Skype 业务 Server 企业语音呼叫寄存。
  
您可以指定您自己的音乐文件用于保持音乐，而不是业务服务器附带 Skype 的默认音乐文件。 若要自定义保留音乐，请使用 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet。
  
> [!NOTE]
> 如果您自定义保留音乐并希望多个网站相同的音乐，则必须配置运行呼叫寄存应用程序的每个网站的音乐文件。 
  
### <a name="to-customize-the-music-file"></a>自定义音乐文件

1. 登录到计算机的业务 Server Management Shell 的 Skype 或使用**Delegate Setup Permissions**中所述的必要用户权限的 RTCUniversalServerAdmins 组成员身份的安装。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
3. 运行：
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > 使用 **Get-CsService** cmdlet 可标识服务。 有关详细信息，请参阅[Get-csservice](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)。 
  
    以下示例说明了如何以字节数组的形式获取文件 soothingmusic.wma 的内容并将其分配给变量。 然后，将音频文件指定为呼叫寄存的保留音乐文件。 有关详细信息，请参阅[Set-cscallparkservicemusiconholdfile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)。
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>另请参阅

[Set-cscallparkservicemusiconholdfile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
