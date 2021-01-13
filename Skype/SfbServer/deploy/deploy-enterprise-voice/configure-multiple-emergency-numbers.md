---
title: 在 Skype for Business 中配置多个紧急号码
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: 阅读本主题，了解如何在 Skype for Business Server 中配置多个紧急号码。
ms.openlocfilehash: fe53e914eb0c406a4f7013df2f6ec106fa781f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804102"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>在 Skype for Business 中配置多个紧急号码

阅读本主题，了解如何在 Skype for Business Server 中配置多个紧急号码。

Skype for Business Server 现在支持客户端的多个紧急号码。 多个紧急号码是 2016 年 6 月累积更新中引入的一项新功能。 在将环境配置为支持多个紧急号码之前，请务必阅读 Plan [for multiple emergency numbers in Skype for Business Server。](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)

> [!NOTE]
> 如果尚未升级到 2016 年 11 月累积更新，请参阅 [Skype for Business Server 2015 更新](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。 随着 2016 年 11 月累积更新，支持紧急号码的数量从 5 个增加至 100 个。

## <a name="configure-multiple-emergency-numbers"></a>配置多个紧急号码

若要配置多个紧急号码，请使用 New-CsEmergencyNumber cmdlet，然后使用 [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) 和 [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet 指定 EmergencyNumbers 参数。 有关所有位置策略参数的完整说明，例如 PSTN 用法和所需位置，请参阅[Set-CsLocationPolicy。](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)

以下命令使用 New-CsEmergency cmdlet 创建拨号字符串为 911 的新紧急号码：

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

下一个命令通过指定 Set-CsLocationPolicy cmdlet 中的 EmergencyNumbers 参数，将号码与指定的位置策略关联：

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

下一个示例中，使用单个拨号掩码 112 创建紧急号码：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

下一个命令将创建具有多个拨号掩码的紧急号码：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

下一个示例添加多个具有多个拨号掩码的紧急号码，然后将紧急号码与指定的位置策略关联：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

下一个示例为同时使用 911 和 450 的医疗保健提供商配置多个紧急号码：

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

下一个示例为伦敦市配置多个紧急号码：

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

下一个示例为印度配置多个紧急号码：

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

下一个示例删除 Dial 字符串为 911 和 Dial 掩码 112 和 999 的现有条目：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
