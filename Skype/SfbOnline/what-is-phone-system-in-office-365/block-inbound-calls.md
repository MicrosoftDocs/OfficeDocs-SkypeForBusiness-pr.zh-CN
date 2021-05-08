---
title: 阻止 Skype for Business Online 中的入站呼叫
ms.author: v-cichur
author: cichur
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
ms.openlocfilehash: dae0d585df2f67904712e9220f16213a2f925369
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238028"
---
# <a name="block-inbound-calls"></a>阻止入站呼叫

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business联机呼叫计划现在支持阻止来自公共电话交换网和 PSTN (的) 。 此功能允许定义一个租户全局数字模式列表，以便可以针对列表检查每个传入到租户的 PSTN 呼叫的来电显示是否匹配。 如果进行了匹配，则拒绝传入呼叫。

此入站呼叫阻止功能仅适用于源自 PSTN 的入站呼叫，并且仅在租户全局的基础上工作。 它并非按用户提供。  

此功能尚不可用于直接路由。

>[!NOTE]
> 被阻止的呼叫者在被阻止时可能遇到略有不同的行为。 行为基于被阻止呼叫者的运营商如何处理不允许成功完成呼叫的通知。 示例可能包括运营商消息，指出无法将呼叫作为已拨入完成，或只是删除呼叫。

## <a name="call-blocking-admin-controls-and-information"></a>呼叫阻止管理员控件和信息

阻止号码的管理员控件仅使用 PowerShell 提供。 数字块模式定义为正则表达式模式。 表达式的顺序不重要 – 列表中匹配的第一个模式会导致调用被阻止。 在阻止的呼叫者列表中添加或删除的新号码或模式可能需要多达 24 小时才能激活模式。

## <a name="call-blocking-powershell-commands"></a>调用阻止 PowerShell 命令

数字模式通过命令 ```CsInboundBlockedNumberPattern``` ```New``` ```Get``` 、、 和 ```Set``` 进行管理 ```Remove``` 。 可以使用这些 cmdlet 管理给定的模式，包括切换给定模式的激活。
- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) 返回添加到租户列表的所有阻止数字模式的列表，包括名称、说明、已启用 (True/False) 和每个模式。
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) 将阻止的编号模式添加到租户列表。
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) 从租户列表中删除阻止的编号模式。
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) 修改租户列表中的阻止数字模式的一个或多个参数。

通过 命令 和 管理查看和激活整个呼叫阻止 ```CsTenantBlockingCallingNumbers``` ```Get``` 功能 ```Set``` 。

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) 返回全局阻止数字列表的参数，包括"已启用" (True/False) 。 只有打开或关闭该功能，才能手动修改单个全局租户策略。
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) 允许修改在租户级别打开和关闭全局租户阻止的调用。

### <a name="examples"></a>示例

#### <a name="block-a-number"></a>阻止号码

此示例中， ```-Enabled``` 和 ```-Description``` 参数是可选的：

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

创建新模式会添加默认启用的模式。 说明是一个可选字段，用于提供详细信息。

我们建议提供一个有意义的名称，以便轻松了解添加模式的原因。 如果只是阻止垃圾邮件号码，请考虑将规则命名为与匹配的数字模式相同的规则，并根据需要在说明中添加其他信息。

模式使用正则表达式和正则表达式 (正则表达式) 。 在测试和验证之前，请留出时间进行复制。

#### <a name="allow-a-number"></a>允许数字

本示例需要 ```-Identity``` 参数：

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
如果标识未知，请使用 ```Get-CsInboundBlockedNumberPattern``` cmdlet 首先找到正确的模式并记下标识。 然后，运行 ```Remove-CsTenantBlockedNumberPattern``` cmdlet 并传递相应的标识值。

在测试和验证之前，请留出时间进行复制。

#### <a name="view-all-number-patterns"></a>查看所有数字模式

运行此 cmdlet 会返回为租户输入的所有阻止号码的列表：

```powershell
Get-CsInboundBlockedNumberPattern
```

使用内置的 PowerShell 筛选功能可分析所需的返回值。

## <a name="add-number-exceptions"></a>添加数字异常

可以通过命令、 和 将异常添加到被阻止 ```CsTenantBlockNumberExceptionPattern``` ```New``` ```Get``` ```Set``` 的编号模式 ```Remove``` 。

- [New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) 将数字异常模式添加到租户列表。 
- [Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) 返回添加到租户列表的所有数字异常模式的列表。
- [Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) 将一个或多个参数修改为租户列表中的数字异常模式。
- [Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) 从租户列表中删除数字异常模式。

### <a name="examples"></a>示例

#### <a name="add-a-number-exception"></a>添加数字异常

本示例将创建一个新的数字异常模式，默认情况下，该模式将添加为"已启用"。 和 ```-Enabled``` ```-Description``` 参数是可选的。

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>查看所有数字异常

本示例中的 -Identity 参数是可选的。 如果 ```-Identity``` 未指定 参数，此 cmdlet 将返回为租户输入的所有数字异常模式的列表。
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>修改数字异常

此示例中，-Identity 参数是必需的。 ```Set-CsTenantBlockedNumberExceptionPattern```使用 cmdlet 可以修改给定数字模式标识的一个或多个参数。
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>删除数字异常

此示例中， ```-Identity``` 参数是必需的。 此 cmdlet 将删除租户列表中的给定数字模式。  如果标识未知，请使用 ```Get-CsInboundBlockedNumberPattern``` cmdlet 首先找到正确的模式并记下标识。 然后，运行 ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet 并传递相应的标识值。在测试和验证之前，请留出时间进行复制。  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>测试是否阻止了数字

使用 ```Test-CsInboundBlockedNumberPattern``` cmdlet 验证是否在租户中阻止了数字。
 
此示例中， ```-Phonenumber``` 和 ```-Tenant``` 参数是必需的。 参数 ```-PhoneNumber``` 应为不带任何其他字符（如 + 或 -）的数字字符串。 在 TRPS 中， ```-Tenant parameter``` 是可选的。 如果租户中阻止了数字，则生成的参数返回值为 True;如果未阻止，则返回 ```isNumberBlocked``` False。

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

## <a name="a-note-about-regex"></a>有关正则表达式的注释

如前面所述，阻止调用方的模式匹配通过使用正则表达式完成。 联机提供了多个工具来帮助验证正则表达式模式匹配。 如果不熟悉正则表达式模式，建议你花一些时间熟悉基础知识。 若要确保获得预期结果，在向租户添加新的阻止数字匹配之前，请使用验证模式匹配项的工具。 

## <a name="related-topics"></a>相关主题

- [设置计算机以使用 Skype for Business Online 管理Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
