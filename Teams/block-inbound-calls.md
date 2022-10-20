---
title: 阻止 Microsoft Teams 中的入站调用
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: ''
description: 了解如何使用 PowerShell 管理入站调用阻止。
ms.openlocfilehash: 01d1fb08d0b0cca4bc0a35ca77109e976d63a1f0
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614425"
---
# <a name="block-inbound-calls"></a>阻止入站调用

Microsoft 呼叫计划、直接路由和运营商连接支持阻止来自公共交换电话网络的入站呼叫 (PSTN) 。 此功能允许管理员在租户全局级别定义数字模式和异常的列表，以便可以针对列表检查每个传入租户的 PSTN 调用的调用方 ID 以进行匹配。 如果进行了匹配，则会拒绝传入调用。

此入站调用阻止功能仅适用于源自 PSTN 且仅适用于租户全局级别的入站调用。 单个 Teams 用户无法操作此列表。 Teams 客户端确实允许单个用户阻止 PSTN 调用。 有关最终用户如何实现呼叫阻止的信息，请参阅 [Teams 中的“管理呼叫设置](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)”。

> [!NOTE]
> 被阻止的调用方在被阻止时可能会遇到略有不同的行为。 此行为基于被阻止调用方的运营商如何处理不允许成功完成呼叫的通知。 示例可能包括一条运营商消息，指出呼叫无法以拨号方式完成，或者只是删除呼叫。

请注意，目前无法使用 Teams 管理中心管理呼叫阻止。

## <a name="manage-call-blocking-by-using-powershell"></a>使用 PowerShell 管理呼叫阻止

若要管理呼叫阻止，需要定义一个或多个号码模式来阻止呼叫，定义号码模式的异常，并启用呼叫阻止功能。

数字块模式定义为正则表达式模式。 表达式的顺序不重要- 列表中匹配的第一个模式会导致调用被阻止。 在阻止的调用方列表中添加或删除的新号码或模式可能需要长达 24 小时才能使模式处于活动状态。

### <a name="activate-the-call-blocking-feature"></a>激活呼叫阻止功能

若要查看和激活调用阻止功能，请使用 **Get-and Set-CsTenantBlockingCallingNumbers** Teams PowerShell 模块 cmdlet。

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) 返回全局阻止号码列表的入站块号模式和入站豁免号模式参数。 此 cmdlet 还会返回是否已启用阻止 (True 还是 False) 。 

- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) 允许指定在租户级别是打开还是关闭全局租户阻止的调用。

### <a name="manage-block-number-patterns"></a>管理块号模式

使用 **New-**、 **Get-**、 **Set-**、 **Test-** 和 **Remove-CsInboundBlockedNumberPattern** Teams PowerShell 模块 cmdlet 管理数字模式。 

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) 返回添加到租户列表的所有阻止编号模式的列表，包括名称、说明、启用 (True/False) 和 Pattern。

- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) 向租户列表添加阻止的数字模式。

- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) 从租户列表中删除阻止的数字模式。

- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) 修改租户列表中阻止的数字模式的一个或多个参数。

- [Test-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) 测试是否将阻止来自给定电话号码的呼叫。


### <a name="examples"></a>示例

#### <a name="block-a-number"></a>阻止数字

在下面的示例中，租户管理员希望阻止来自号码范围 1 (312) 555-0000 到 1 (312) 555-9999 的所有呼叫。 创建数字模式，以便匹配带 + 前缀的范围内的数字和不带 + 前缀的范围内的数字。 无需在电话号码中包含符号和 () ，因为系统会在匹配之前对这些符号进行条带。  若要打开数字模式，请将 **Enabled** 参数设置为 True。 若要禁用此特定数字模式，请将参数设置为 False。

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

在下一个示例中，租户管理员希望阻止来自 1 号 (412) 555-1234 的所有呼叫。 若要打开数字模式， **已启用** 参数设置为 True。

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

创建新模式会将模式添加为默认启用。 说明是一个可选字段，用于提供详细信息。

我们建议你提供一个有意义的名称，以便轻松理解添加模式的原因。 若要阻止垃圾邮件号码，请考虑将规则命名为与匹配的数字模式相同的规则，然后根据需要在说明中添加其他信息。

模式使用正则表达式 (正则表达式) 进行匹配。 有关详细信息，请参阅 [使用 Regex](#using-regex)。

在测试和验证之前，请留出时间进行复制。

#### <a name="allow-a-number"></a>允许数字

可以通过删除阻止的号码模式来允许号码调用。 在以下示例中，租户管理员希望允许 1 (412) 555-1234 再次进行呼叫。

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```

如果标识未知，请使用 **Get-CsInboundBlockedNumberPattern** cmdlet 首先找到正确的模式并记下标识。 然后，运行 **Remove-CsInboundBlockedNumberPattern** cmdlet 并传递相应的标识值。

在测试和验证之前，请留出时间进行复制。

#### <a name="view-all-number-patterns"></a>查看所有数字模式

以下 cmdlet 返回为租户输入的所有阻止号码的列表：

```powershell
Get-CsInboundBlockedNumberPattern
```

使用内置 PowerShell 筛选功能根据需要分析返回的值。

#### <a name="test-whether-a-number-is-blocked"></a>测试是否阻止数字

若要验证租户中是否阻止了某个数字，请使用 **Test-CsInboundBlockedNumberPattern** cmdlet。

**PhoneNumber** 参数是必需的，并且应该是一个数值字符串，无需任何其他字符，例如 +、或 () 。 如果租户中阻止了该数字，则生成的 **IsNumberBlocked** 参数将返回 True 值;如果参数未被阻止，则返回 False。

在以下示例中，可以看到电话号码 1 (312) 555-8884 被阻止，因为它位于上面的阻止范围中。 根据下面创建的豁免，允许电话号码 1 (312) 555-8883。

```PowerShell
Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558884

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : True
errorMessage    :

Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558883

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : False
errorMessage    :
```

### <a name="manage-number-exceptions"></a>管理数字异常

可以使用 **New-**、 **Get-**、 **Set-** 和 **Remove-CsInboundExemptNumberPattern** cmdlet 将异常添加到阻止的数字模式。

- [New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) 将数字异常模式添加到租户列表。

- [Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) 返回添加到租户列表的所有数字异常模式的列表。

- [Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) 将一个或多个参数修改为租户列表中的数字异常模式。

- [Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) 从租户列表中删除数字异常模式。

### <a name="examples"></a>示例

#### <a name="add-a-number-exception"></a>添加数字异常

在以下示例中，租户管理员希望允许电话号码 1 (312) 555-8882 和 1 (312) 555-8883 呼叫租户，即使这两个电话号码在上面的示例中已阻止的范围。 若要启用此功能，将创建新的数字异常模式，如下所示：

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

若要打开数字模式， **已启用** 参数设置为 True。 若要禁用此特定数字模式，请将参数设置为 False。

#### <a name="view-all-number-exceptions"></a>查看所有数字异常

在此示例中， **Identity** 参数是可选的。 如果未指定 **Identity** 参数，则此 cmdlet 将返回为租户输入的所有数字异常模式的列表。

```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Get-CsInboundExemptNumberPattern
```

#### <a name="modify-a-number-exception"></a>修改数字异常

**使用 Set-CsInboundExemptNumberPattern** cmdlet 可以修改给定数字模式标识的一个或多个参数。 在此示例中，需要 **标识** 参数。

```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string>
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a>删除数字异常

**Remove-CsInboundExemptNumberPattern** cmdlet 将从租户列表中删除给定的数字模式。 在此示例中，需要 **标识** 参数。

如果标识未知，请使用 **Get-CsInboundExemptNumberPattern** cmdlet 首先找到正确的模式并记下标识。 然后，运行 **Remove-CsInboundExemptNumberPattern** cmdlet 并传递相应的标识值。 在测试和验证之前，请留出时间进行复制。

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="using-regex"></a>使用 Regex

阻止调用方的模式匹配是使用 Regex 完成的。 可以联机使用多个工具来帮助验证正则表达式模式匹配。 如果你不熟悉 Regex 模式，我们建议你花一些时间来熟悉基础知识。 若要确保获得预期结果，请在将新的阻止号码匹配项添加到租户之前，使用工具验证模式匹配项。
