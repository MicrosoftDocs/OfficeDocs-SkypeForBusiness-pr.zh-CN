---
title: 在 Skype for Business 2015 中配置呼叫寄存设置
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
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: 修改业务服务器企业语音在 Skype 呼叫公园设置。
ms.openlocfilehash: 56b0e2508fda61bddc94a6f8813708e8186c99c7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-call-park-settings-in-skype-for-business-2015"></a>在 Skype for Business 2015 中配置呼叫寄存设置
 
修改业务服务器企业语音在 Skype 呼叫公园设置。
  
如果您不想使用默认调用公园设置，您可以自定义它们。 调用公园应用程序安装时，默认情况下配置全局设置。 您可以修改全局设置，也可以指定特定于站点的设置。 使用**New CsCpsConfiguration** cmdlet 来创建新的特定于站点的设置。 使用**一组 CsCpsConfiguration** cmdlet 来修改现有的设置。
  
> [!NOTE]
> 寄存呼叫超时且回拨失败时，我们建议您至少为要使用的回退目标配置 **OnTimeoutURI** 选项。
  
使用**New CsCpsConfiguration** cmdlet 或**设置 CsCpsConfiguration** cmdlet 以配置以下设置：
  
|**这一选项：**|**指定此：**|
|:-----|:-----|
|**CallPickupTimeoutThreshold** <br/> |呼叫寄存后到回拨此前应答呼叫的电话之前等待的时间。  <br/> 该值必须采用 hh:mm:ss 的格式输入，以便指定小时数、分钟数和秒数。最小值为 10 秒，最大值为 10 分钟。默认值为 00:01:30。  <br/> |
|**EnableMusicOnHold** <br/> |寄存呼叫时是否向呼叫者播放音乐。  <br/> 值为 True 或 False。默认值为 True。  <br/> |
|**MaxCallPickupAttempts** <br/> |在将寄存呼叫转接到为 **OnTimeoutURI** 指定的回退统一资源标识符 (URI) 之前该寄存呼叫回拨应答电话的次数。默认值为 1。<br/> |
|**OnTimeoutURI** <br/> |超出 **MaxCallPickupAttempts** 时未应答的寄存呼叫将路由到的用户或响应组的 SIP 地址。 <br/> 值必须为以字符串 sip: 开头的 SIP URI。例如，sip:bob@contoso.com。默认情况下没有转接地址。<br/> |
   
### <a name="to-configure-call-park-settings"></a>若要配置呼叫公园设置

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 运行：
    
   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > 使用**Get CsSite** cmdlet 来标识网站。 有关详细信息，请参阅 Lync 服务器管理外壳程序文档。
  
    例如：
    
   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>另请参阅

#### 

[自定义业务 2015年的封存 inSkype 上的调用公园音乐](customize-call-park-music-on-hold.md)
#### 

[新 CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)
  
[一组 CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)
  
[获得 CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)

