---
title: 在呼叫中配置多个Skype for Business
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: 阅读本主题，了解如何在 Skype for Business Server 中配置多个紧急Skype for Business Server。
ms.openlocfilehash: d79a57e64d52bfc6b0f1d8ee9a9bd9c3c1509658
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833908"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>在呼叫中配置多个Skype for Business

阅读本主题，了解如何在 Skype for Business Server 中配置多个紧急Skype for Business Server。

Skype for Business Server现在支持客户端的多个紧急号码。 多个紧急号码是 2016 年 6 月累积更新中引入的新功能。 在将环境配置为支持多个紧急号码之前，请务必阅读规划多个紧急号码[Skype for Business Server。](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)

> [!NOTE]
> 如果尚未升级到 2016 年 11 月累积更新，请参阅[2015 年 11](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)月Skype for Business Server更新。 随着 2016 年 11 月累积更新，支持紧急号码的数量从 5 个增加至 100 个。

## <a name="configure-multiple-emergency-numbers"></a>配置多个紧急号码

若要配置多个紧急号码，请使用 New-CsEmergencyNumber cmdlet，然后使用 [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) 和 [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet 指定 EmergencyNumbers 参数。 有关所有位置策略参数（如 PSTN 用法和所需位置）的完整说明，请参阅 [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps)。

以下命令使用 cmdlet 创建一个拨号字符串为 911 的新紧急New-CsEmergency号码：

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

下一个命令通过指定 Set-CsLocationPolicy cmdlet 中的 EmergencyNumbers 参数，将号码与指定位置策略关联：

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

下一个示例使用单个拨号掩码 112 创建紧急号码：

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

下一个示例删除 Dial 字符串为 911 且 Dial 掩码为 112 和 999 的现有条目：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```