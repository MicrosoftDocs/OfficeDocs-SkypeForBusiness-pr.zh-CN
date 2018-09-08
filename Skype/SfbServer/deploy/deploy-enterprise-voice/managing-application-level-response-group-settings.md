---
title: 管理应用程序级 Skype for Business 中的响应组设置
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
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: 管理应用程序级响应组设置，如音乐上保留和回响设置中的业务 Server 企业语音的 Skype。
ms.openlocfilehash: 4a44ee8988925025b81eac6bd1ee340a3bbef81b
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "23890941"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>管理应用程序级 Skype for Business 中的响应组设置
 
管理应用程序级响应组设置，如音乐上保留和回响设置中的业务 Server 企业语音的 Skype。
  
响应组应用程序的应用程序级别设置包括默认上保留音乐配置、 默认上保留音乐音频文件、 代理回拨宽限期和呼叫上下文配置。 你只能针对每个池定义一组应用程序级别设置。 若要查看应用程序级别设置，请使用**Get-csrgsconfiguration** cmdlet。 若要修改的应用程序级别设置，请使用**Set-csrgsconfiguration** cmdlet。
  
只有未定义任何自定义保持音乐时，才会在呼叫处于呼叫等待状态时播放默认保持音乐。呼叫上下文仅适用于分配给互动工作流的队列。如果启用呼叫上下文，则代理可以在收到呼叫时查看呼叫者等待时间或工作流问题和解答等信息。
  
### <a name="to-modify-response-group-application-level-settings"></a>若要修改响应组应用程序级别设置

1. 以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 在该命令行处，运行：
    
   ```
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    例如：
    
   ```
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    要指定一个音频文件以用作默认的保持音乐，您需要首先导入该音频文件。例如：
    
   ```
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>另请参阅

[Get-csrgsconfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-csrgsconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-csrgsaudiofile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)