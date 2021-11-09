---
title: 在呼叫管理中配置呼叫Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: 修改呼叫管理中的呼叫Skype for Business Server 企业语音。
ms.openlocfilehash: 686484fd42982f2b64623b652851482b85d3e1b8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833928"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a>在呼叫管理中配置呼叫Skype for Business

修改呼叫管理中的呼叫Skype for Business Server 企业语音。

如果不想使用默认呼叫呼叫管理设置，可以自定义这些设置。 安装呼叫管理应用程序时，默认情况下将配置全局设置。 您可以修改全局设置，也可以指定特定于站点的设置。 使用 **New-CsCpsConfiguration** cmdlet 可创建新的特定于站点的设置。 使用 **Set-CsCpsConfiguration** cmdlet 可修改现有设置。

> [!NOTE]
> 寄存呼叫超时且回拨失败时，我们建议您至少为要使用的回退目标配置 **OnTimeoutURI** 选项。

使用 **New-CsCpsConfiguration** cmdlet 或 **Set-CsCpsConfiguration** cmdlet 配置以下任何设置：


| **此选项：**                     | **指定以下内容：**                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **CallPickupTimeoutThreshold** <br/> | 呼叫寄存后到回拨此前应答呼叫的电话之前等待的时间。  <br/> 该值必须采用 hh:mm:ss 的格式输入，以便指定小时数、分钟数和秒数。最小值为 10 秒，最大值为 10 分钟。默认值为 00:01:30。  <br/> |
| **EnableMusicOnHold** <br/>          | 寄存呼叫时是否向呼叫者播放音乐。  <br/> 值为 True 或 False。默认值为 True。  <br/>                                                                                                                                                                                                                 |
| **MaxCallPickupAttempts** <br/>      | 在将寄存呼叫转接到为 **OnTimeoutURI** 指定的回退统一资源标识符 (URI) 之前该寄存呼叫回拨应答电话的次数。默认值为 1。<br/>                                                                                                                         |
| **OnTimeoutURI** <br/>               | 超出 **MaxCallPickupAttempts** 时未应答的寄存呼叫将路由到的用户或响应组的 SIP 地址。 <br/> 值必须为以字符串 sip: 开头的 SIP URI。例如，sip:bob@contoso.com。默认情况下没有转接地址。<br/>                                                   |

### <a name="to-configure-call-park-settings"></a>配置呼叫呼叫管理设置

1. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**

2. 运行：

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > 使用 **Get-CsSite** cmdlet 可标识站点。 有关详细信息，请参阅命令行Skype for Business Server命令行管理程序文档。

    例如：

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>另请参阅

[Customize Call Park music on hold inSkype for Business 2015](customize-call-park-music-on-hold.md)

[New-CsCpsConfiguration](/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[Set-CsCpsConfiguration](/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[Get-CsSite](/powershell/module/skype/get-cssite?view=skype-ps)