---
title: 在 Skype for Business 中配置多个紧急号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 81d3dbed919c936eb8a656d123f5c44e445044d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027793"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>在 Skype for Business 中配置多个紧急号码

阅读本主题，了解如何在 Skype for Business Server 中配置多个紧急号码。

Skype for Business Server 现在支持客户端的多个紧急号码。 "多个紧急号码" 是6月2016累积更新中引入的一项新功能。 在将环境配置为支持多个紧急号码之前，请务必阅读[Plan For Skype For Business Server 中的多个紧急号码](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)。

> [!NOTE]
> 如果尚未升级到2016年11月累积更新，请参阅[更新到 Skype For Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。 在11月2016累积更新中，支持紧急号码的数量从5增加到100。

## <a name="configure-multiple-emergency-numbers"></a>配置多个紧急号码

若要配置多个紧急号码，请使用 New-csemergencynumber cmdlet，然后将 EmergencyNumbers 参数指定为[new-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)和[new-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet。 有关所有位置策略参数的完整说明（如 PSTN 用法和所需的位置），请参阅[new-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)。

以下命令使用 CsEmergency cmdlet 创建带有拨号字符串911的新的紧急号码：

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

下一个命令通过在 New-cslocationpolicy cmdlet 中指定 EmergencyNumbers 参数，将该号码与指定的位置策略相关联：

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

在下一个示例中，使用单个拨号掩码（112）创建一个紧急号码：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

下一个命令将创建带有多个拨号掩码的紧急号码：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

下一个示例添加多个带多个拨号掩码的紧急号码，然后将紧急号码与指定的位置策略相关联：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

下一个示例为使用911和450的卫生保健提供商配置了多个紧急号码：

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

下一个示例为伦敦的城市配置了多个紧急号码：

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

下一个示例为印度配置了多个紧急号码：

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

下一个示例将删除带有拨号字符串911和拨号掩码112和999的现有条目：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
