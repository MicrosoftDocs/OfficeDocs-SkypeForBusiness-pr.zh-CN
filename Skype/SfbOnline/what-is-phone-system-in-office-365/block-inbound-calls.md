---
title: 在 Skype for Business Online 中阻止入站呼叫
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
ms.localizationpriority: medium
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
description: 管理员可以了解如何在 Skype for Business Online 中阻止入站调用。
ms.openlocfilehash: 40b43f669ededf7ac334c25c79b5af09140c075d
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671648"
---
# <a name="block-inbound-calls"></a>阻止入站调用

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business联机呼叫计划现在支持阻止来自公共交换电话网络的入站呼叫 (PSTN) 。 此功能允许定义租户全局号码模式列表，以便可以根据列表对租户的每个传入 PSTN 调用的调用方 ID 进行匹配。 如果进行了匹配，则会拒绝传入调用。

此入站调用阻止功能仅适用于源自 PSTN 且仅适用于租户全局的入站调用。 它不按用户提供。

此功能尚不可用于直接路由。

>[!NOTE]
> 被阻止的调用方在被阻止时可能会遇到略有不同的行为。 此行为基于被阻止调用方的运营商如何处理不允许成功完成呼叫的通知。 示例可能包括一条运营商消息，指出呼叫无法以拨号方式完成，或者只是删除呼叫。

## <a name="call-blocking-admin-controls-and-information"></a>调用阻止管理员控件和信息

管理员仅使用 PowerShell 提供阻止数字的控件。 数字块模式定义为正则表达式模式。 表达式的顺序不重要 - 列表中匹配的第一个模式会导致调用被阻止。 在阻止的调用方列表中添加或删除的新号码或模式可能需要长达 24 小时才能使模式处于活动状态。

## <a name="call-blocking-powershell-commands"></a>调用阻止 PowerShell 命令

数字模式是通过```CsInboundBlockedNumberPattern```命令```Set``````New``````Get```、和 。```Remove``` 可以使用这些 cmdlet 来管理给定模式，包括切换给定模式的激活功能。
- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) 返回添加到租户列表中的所有阻止编号模式的列表，包括名称、说明、启用 (True/False) 和每个模式。
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) 向租户列表添加阻止的数字模式。
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) 从租户列表中删除阻止的数字模式。
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) 修改租户列表中阻止的数字模式的一个或多个参数。

查看和激活整个调用阻止功能是通过```CsTenantBlockingCallingNumbers```命令进行管理的```Get``````Set```。

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) 返回全局阻止编号列表的参数，包括“已启用” (True/False) 。 只有一个全局租户策略不能手动修改，只能打开或关闭该功能。
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) 允许修改在租户级别打开和关闭全局租户阻止的调用。

### <a name="examples"></a>示例

#### <a name="block-a-number"></a>阻止数字

在此示例中 ```-Enabled``` ，这些参数和 ```-Description``` 参数是可选的：

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

创建新模式会将模式添加为默认启用。 说明是一个可选字段，用于提供详细信息。

我们建议你提供一个有意义的名称，以便轻松理解添加模式的原因。 如果只是阻止垃圾邮件号码，请考虑将规则命名为与要匹配的数字模式相同的名称，并在说明中根据需要添加其他信息。

模式使用正则表达式 (正则表达式) 进行匹配。
在测试和验证之前，请留出时间进行复制。

#### <a name="allow-a-number"></a>允许数字

在此示例中，参数是必需的 ```-Identity``` ：

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```

如果标识未知，请使用 ```Get-CsInboundBlockedNumberPattern``` cmdlet 首先找到正确的模式并记下标识。 然后，运行 ```Remove-CsTenantBlockedNumberPattern``` cmdlet 并传递相应的标识值。

在测试和验证之前，请留出时间进行复制。

#### <a name="view-all-number-patterns"></a>查看所有数字模式

运行此 cmdlet 将返回为租户输入的所有阻止号码的列表：

```powershell
Get-CsInboundBlockedNumberPattern
```

使用内置 PowerShell 筛选功能根据需要分析返回的值。

## <a name="add-number-exceptions"></a>添加数字异常

可以通过命令、```Set``````New``````Get```命令、以及 ```Remove```..。添加异常以阻止的数字模式。```CsTenantBlockNumberExceptionPattern```

- [New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) 将数字异常模式添加到租户列表。
- [Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) 返回添加到租户列表的所有数字异常模式的列表。
- [Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) 将一个或多个参数修改为租户列表中的数字异常模式。
- [Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) 从租户列表中删除数字异常模式。

### <a name="examples"></a>示例

#### <a name="add-a-number-exception"></a>添加数字异常

在此示例中，将创建新的数字异常模式，默认情况下将添加已启用的模式。 参数 ```-Enabled``` 和 ```-Description``` 参数是可选的。

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"
```

#### <a name="view-all-number-exceptions"></a>查看所有数字异常

在此示例中，-Identity 参数是可选的。 ```-Identity```如果未指定参数，此 cmdlet 将返回为租户输入的所有数字异常模式的列表。

```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>修改数字异常

在此示例中，-Identity 参数是必需的。 使用 ```Set-CsTenantBlockedNumberExceptionPattern``` 该 cmdlet 可以修改给定数字模式标识的一个或多个参数。

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string>
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$"
```

#### <a name="remove-a-number-exception"></a>删除数字异常

在此示例中 ```-Identity``` ，参数是必需的。 此 cmdlet 将从租户列表中删除给定的数字模式。  如果标识未知，请使用 ```Get-CsInboundBlockedNumberPattern``` cmdlet 首先找到正确的模式并记下标识。 然后，运行 ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet 并传递相应的标识值。 在测试和验证之前，请留出时间进行复制。

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>测试是否阻止数字

```Test-CsInboundBlockedNumberPattern```使用该 cmdlet 验证租户中是否阻止了某个数字。

在此示例中 ```-Phonenumber``` ，需要这些参数和 ```-Tenant``` 参数。 该 ```-PhoneNumber``` 参数应该是一个数值字符串，没有任何其他字符，如 + 或 -。 在 TRPS 中 ```-Tenant parameter``` ，可选。 如果租户中阻止了该数字，则生成 ```isNumberBlocked``` 的参数返回 True 值;如果未阻止该数字，则返回 False 值。

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | True        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|httpResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | False        |         |

## <a name="a-note-about-regex"></a>有关 Regex 的说明

如前所述，阻止调用方的模式匹配是使用 Regex 完成的。 可以联机使用多个工具来帮助验证正则表达式模式匹配。 如果你不熟悉 Regex 模式，我们建议你花一些时间来熟悉基础知识。 若要确保获得预期结果，请在将新的阻止号码匹配项添加到租户之前，使用工具验证模式匹配项。

## <a name="related-topics"></a>相关主题

- [使用Windows PowerShell设置计算机以管理联机Skype for Business](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
