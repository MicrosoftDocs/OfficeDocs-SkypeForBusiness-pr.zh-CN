---
title: Skype for Business 中配置多个紧急号码
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: 阅读本主题可了解如何在 Skype for Business Server 中配置多个紧急号码。
ms.openlocfilehash: 64f9368b5d6eaac1c2f872ebf48152514cc99b34
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372683"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Skype for Business 中配置多个紧急号码

阅读本主题可了解如何在 Skype for Business Server 中配置多个紧急号码。

Skype 业务服务器现在支持的客户端的多个紧急号码。 多个紧急号码是年 6 月 2016年中引入的新功能累积更新。 在配置您的环境以支持多个紧急号码之前，请务必阅读[Plan for Business Server 的 Skype 中的多个紧急号码](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)。

> [!NOTE]
> 如果您具有尚未升级到年 11 月 2016年累积更新，请参阅[业务服务器 2015年的 Skype 更新](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。 与年 11 月 2016年累积更新，支持紧急号码数增大从 5 至 100。 

## <a name="configure-multiple-emergency-numbers"></a>配置多个紧急号码

若要配置多个紧急号码，请使用新建 CsEmergencyNumber cmdlet，然后 EmergencyNumbers 参数指定使用[New-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)和[设置 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet。 有关所有位置策略参数，如 PSTN 用法和所需的位置的完整说明，请参阅[设置 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)。

以下命令通过使用 New-CsEmergency cmdlet，创建了一个包含拨号串 911 的新紧急号码：

```
> $a = New-CsEmergencyNumber -DialString 911 
```

下一个命令通过在 Set-CsLocationPolicy cmdlet 中指定 EmergencyNumbers 参数，将此号码与指定的位置策略关联起来：

```
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 
```

在下一个示例中，创建了一个包含单个拨号掩码 112 的紧急号码：

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 
```

下面的命令创建多个拨号掩码紧急号码：

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
```

下一个示例添加了具有多个拨号掩码的多个紧急号码，然后将这些紧急号码与指定位置策略关联起来：

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 
```

下一个示例为使用 911 和 450 的医疗保健提供商配置了多个紧急号码：  

```
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

下一个示例为伦敦市配置了多个紧急号码：

```
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

下一个示例为印度配置了多个紧急号码：

```
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

下一个示例删除了包含拨号串 911 及拨号掩码 112 和 999 的现有条目。

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 
```


