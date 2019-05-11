---
title: Skype for Business 中配置呼叫寄存设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: 修改 Skype 中的业务 Server 企业语音的呼叫寄存设置。
ms.openlocfilehash: 2f833e956f09213f1dfa3da440a6c6d9b17fa6b2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893068"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a>Skype for Business 中配置呼叫寄存设置

修改 Skype 中的业务 Server 企业语音的呼叫寄存设置。

如果您不想要使用默认呼叫寄存设置，您可以自定义它们。 安装呼叫寄存应用程序时，默认情况下配置全局设置。 您可以修改全局设置，也可以指定特定于站点的设置。 使用 **New-CsCpsConfiguration** cmdlet 可创建新的特定于站点的设置。 使用 **Set-CsCpsConfiguration** cmdlet 可修改现有设置。

> [!NOTE]
> 寄存呼叫超时且回拨失败时，我们建议您至少为要使用的回退目标配置 **OnTimeoutURI** 选项。

使用 **New-CsCpsConfiguration** cmdlet 或 **Set-CsCpsConfiguration** cmdlet 配置以下任何设置：


| **此选项：**                     | **指定以下内容：**                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **CallPickupTimeoutThreshold** <br/> | 呼叫寄存后到回拨此前应答呼叫的电话之前等待的时间。  <br/> 该值必须采用 hh:mm:ss 的格式输入，以便指定小时数、分钟数和秒数。最小值为 10 秒，最大值为 10 分钟。默认值为 00:01:30。  <br/> |
| **EnableMusicOnHold** <br/>          | 寄存呼叫时是否向呼叫者播放音乐。  <br/> 值为 True 或 False。默认值为 True。  <br/>                                                                                                                                                                                                                 |
| **MaxCallPickupAttempts** <br/>      | 在将寄存呼叫转接到为 **OnTimeoutURI** 指定的回退统一资源标识符 (URI) 之前该寄存呼叫回拨应答电话的次数。默认值为 1。<br/>                                                                                                                         |
| **OnTimeoutURI** <br/>               | 用户或未应答的寄存的呼叫路由到超出**MaxCallPickupAttempts**时的响应组的 SIP 地址。 <br/> 值必须是字符串 sip 开头的 SIP URI:。 例如，sip:bob@contoso.com。 默认情况下不转发地址。  <br/>                                                   |

### <a name="to-configure-call-park-settings"></a>配置呼叫寄存设置

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

2. 运行：

   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > 使用**Get-cssite** cmdlet 来标识该网站。 有关详细信息，请参阅 for Business Server Management Shell 文档的 Skype。

    例如：

   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>另请参阅

[在 Skype for Business 2015 中自定义呼叫寄存保持音乐](customize-call-park-music-on-hold.md)

[新 CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[Set-cscpsconfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[Get-cssite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)
