---
title: 在 Skype for Business 中配置多个紧急号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: 阅读本主题, 了解如何在 Skype for Business 服务器中配置多个紧急号码。
ms.openlocfilehash: 184a0060ed2383a652928356ab2999aa55b3d7bd
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233695"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>在 Skype for Business 中配置多个紧急号码

阅读本主题, 了解如何在 Skype for Business 服务器中配置多个紧急号码。

Skype for business 服务器现支持客户端的多个紧急电话号码。 多个紧急号码是2016年6月累积更新中引入的一项新功能。 在配置环境以支持多个紧急号码之前, 请务必阅读[Skype For Business 服务器中的多个紧急号码计划](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)。

> [!NOTE]
> 如果您尚未升级到2016年11月累积更新, 请参阅[Skype for Business Server 2015 更新](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。 在2016年11月累积更新中, 支持的紧急号码数量从5增加到100。 

## <a name="configure-multiple-emergency-numbers"></a>配置多个紧急号码

若要配置多个紧急号码, 请使用 CsEmergencyNumber cmdlet, 然后使用[新的 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)和[CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet 指定 EmergencyNumbers 参数。 有关所有位置策略参数 (如 PSTN 使用和所需位置) 的完整说明, 请参阅[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)。

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

下一个命令将创建带有多个拨号掩码的紧急号码:

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


