---
title: 在 Skype for Business 2015 中自定义呼叫寄存保持音乐
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: 自定义音乐上的停留在 Skype 业务服务器企业语音调用公园。
ms.openlocfilehash: 5af98ee95c59f7fd945232f77d713255ca1c42d5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="customize-call-park-music-on-hold-inskype-for-business-2015"></a>在 Skype for Business 2015 中自定义呼叫寄存保持音乐
 
自定义音乐上的停留在 Skype 业务服务器企业语音调用公园。
  
您可以指定您自己的音乐文件用于处于等待状态，而不是默认的音乐文件附带 Skype 业务服务器的音乐。 若要自定义音乐候，使用**集 CsCallParkServiceMusicOnHoldFile** cmdlet。
  
> [!NOTE]
> 如果您自定义音乐候，并用于多个站点需要相同的音乐，必须配置为运行应用程序调用公园每个站点的音乐文件。 
  
### <a name="to-customize-the-music-file"></a>自定义音乐文件

1. 登录到业务服务器管理外壳的 Skype 为成员的 RTCUniversalServerAdmins 组或**委托安装程序权限**中所述的必要的用户权限的安装位置的计算机上。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 运行：
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > 使用**Get CsService** cmdlet 来标识服务。 有关详细信息，请参阅[获取 CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)。 
  
    以下示例说明了如何以字节数组的形式获取文件 soothingmusic.wma 的内容并将其分配给变量。 然后，将音频文件指定为呼叫寄存的保留音乐文件。 有关详细信息，请参阅[设置 CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)。
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>另请参阅

#### 

[一组 CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[获得 CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)

