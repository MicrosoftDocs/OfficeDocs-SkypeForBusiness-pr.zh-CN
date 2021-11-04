---
title: 阻止传入Microsoft Teams
ms.author: v-mahoffman
author: cichur
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
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: 4e7e6d40173bb5917a6cf540481257b21253eeaa
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766220"
---
# <a name="block-inbound-calls"></a>阻止入站呼叫

Microsoft 呼叫计划、直接路由和接线员连接都支持阻止来自 PSTN 呼叫的公共 (呼叫) 。 此功能允许管理员在租户全局级别定义号码模式列表，以便可以针对列表检查每个传入到租户的 PSTN 呼叫的来电显示是否匹配。 如果进行了匹配，则拒绝传入呼叫。

此入站呼叫阻止功能仅适用于源自 PSTN 的入站呼叫，并且仅适用于租户全局级别。 单个Teams用户无法操作此列表。 客户端Teams允许单个用户阻止 PSTN 呼叫。 有关最终用户如何实现呼叫阻止的信息，请参阅在 Teams 中[管理呼叫设置](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)。

>[!NOTE]
> 被阻止的呼叫者在被阻止时可能遇到略有不同的行为。 行为基于被阻止呼叫者的运营商如何处理不允许成功完成呼叫的通知。 示例可能包括运营商消息，指出无法将呼叫作为已拨入完成，或只是删除呼叫。

## <a name="call-blocking-admin-controls-and-information"></a>呼叫阻止管理员控件和信息

阻止号码的管理员控件仅使用 PowerShell 提供。 数字块模式定义为正则表达式模式。 表达式的顺序不重要 – 列表中匹配的第一个模式会导致调用被阻止。 在阻止的呼叫者列表中添加或删除的新号码或模式可能需要多达 24 小时才能激活模式。

## <a name="call-blocking-powershell-commands"></a>调用阻止 PowerShell 命令

使用 New-、Get-、Set-和 **Remove-CsInboundBlockedNumberPattern** cmdlet 管理数字模式。   可以使用这些 cmdlet 管理给定的模式，包括切换给定模式的激活。

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) 返回添加到租户列表的所有阻止数字模式的列表，包括名称、说明、已启用的 (True/False) 和每个模式。
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) 将阻止的编号模式添加到租户列表。
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) 从租户列表中删除阻止的编号模式。
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) 修改租户列表中的阻止数字模式的一个或多个参数。

通过 **Get-** 和 **Set-CsTenantBlockingCallingNumbers** cmdlet 管理查看和激活整个呼叫阻止功能。

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) 返回全局阻止编号列表的入站块数模式和入站豁免编号模式参数。 此 cmdlet 还会返回阻止是否已启用 (True 或 False) 。 只有打开或关闭该功能，才能手动修改单个全局租户策略。
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) 允许修改在租户级别打开和关闭全局租户阻止的调用。

### <a name="examples"></a>示例

#### <a name="block-a-number"></a>阻止号码

在下面的示例中，租户管理员希望阻止来自号码范围 1 (312) 555-0000 到 1 (312) 555-9999 的所有调用。 创建数字模式，以便匹配范围中带 + 前缀的数字和范围中不带 + 前缀的数字。 你不需要在电话号码中包括符号 - 和 () ，因为系统在匹配之前会剥离这些符号。  若要启用数字模式，Enabled **参数设置为** True。 若要禁用此特定数字模式，将 参数设置为 False。

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

下一示例中，租户管理员希望阻止来自 555-1234 (412) 1 的所有调用。 若要启用数字模式，Enabled **参数设置为** True。

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

创建新模式会添加默认启用的模式。 说明是一个可选字段，用于提供详细信息。

我们建议提供一个有意义的名称，以便轻松了解添加模式的原因。 如果只是阻止垃圾邮件号码，请考虑将规则命名为与匹配的数字模式相同的规则，并根据需要在说明中添加其他信息。

模式使用正则表达式和正则表达式 (正则表达式) 。 有关详细信息，请参阅 [使用正则表达式](#using-regex)。

在测试和验证之前，请留出时间进行复制。 

#### <a name="allow-a-number"></a>允许数字

您可以通过删除阻止的号码模式来允许呼叫号码。 在下面的示例中，租户管理员希望允许 1 (412) 555-1234 再次进行调用。

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
如果标识未知，请使用 **Get-CsInboundBlockedNumberPattern** cmdlet 首先找到正确的模式并记下标识。 然后，运行 **Remove-CsInboundBlockedNumberPattern** cmdlet 并传递相应的标识值。

在测试和验证之前，请留出时间进行复制。

#### <a name="view-all-number-patterns"></a>查看所有数字模式

运行此 cmdlet 会返回为租户输入的所有阻止号码的列表：

```powershell
Get-CsInboundBlockedNumberPattern
```

使用内置的 PowerShell 筛选功能，可分析所需的返回值。

## <a name="add-number-exceptions"></a>添加数字异常

可以使用 **New-、Get-、Set-** 和 **Remove-CsInboundExemptNumberPattern** cmdlet 将异常添加到阻止的编号模式。  

- [New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) 将数字异常模式添加到租户列表。 
- [Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) 返回添加到租户列表的所有数字异常模式的列表。
- [Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) 将一个或多个参数修改为租户列表中的数字异常模式。
- [Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) 从租户列表中删除数字异常模式。

### <a name="examples"></a>示例

#### <a name="add-a-number-exception"></a>添加数字异常

在下面的示例中，租户管理员希望允许电话号码 1 (312) 555-8882 和 1 (312) 555-8883 呼叫租户，即使这两个电话号码位于上述示例中阻止的范围内。 若要启用此功能，将创建一个新的数字异常模式，如下所示：

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

若要启用数字模式，Enabled **参数设置为** True。 若要禁用此特定数字模式，将 参数设置为 False。


#### <a name="view-all-number-exceptions"></a>查看所有数字异常

本示例中的 **Identity** 参数是可选的。 如果 **未指定 Identity** 参数，此 cmdlet 将返回为租户输入的所有数字异常模式的列表。
 
```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```
 
```powershell
Get-CsInboundExemptNumberPattern 
```

#### <a name="modify-a-number-exception"></a>修改数字异常

**Set-CsInboundExemptNumberPattern** cmdlet 允许修改给定数字模式标识的一个或多个参数。 此示例中 **，Identity** 参数是必需的。
 
```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a>删除数字异常

**Remove-CsInboundExemptNumberPattern** cmdlet 将删除租户列表中的给定数字模式。 此示例中 **，Identity** 参数是必需的。 

如果标识未知，请使用 **Get-CsInboundExemptNumberPattern** cmdlet 首先找到正确的模式并记下标识。 然后，运行 **Remove-CsInboundExemptNumberPattern** cmdlet 并传递相应的标识值。在测试和验证之前，请留出时间进行复制。  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a>测试是否阻止了数字

使用 **Test-CsInboundBlockedNumberPattern** cmdlet 验证是否在租户中阻止了数字。
 
**PhoneNumber** 参数是必需的，应为不带任何其他字符的数字字符串，例如 +、- 或 () 。 如果租户中阻止了该数字，则生成的 **IsNumberBlocked** 参数返回值 True;参数返回 False（如果未阻止）。

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a>示例

在这些示例中，可以看到电话号码 1 (312) 555-8884 被阻止，因为它应位于上述阻止范围内，而电话号码 1 (312) 555-8883 允许呼叫，因为它应该基于上面创建的豁免。

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

## <a name="using-regex"></a>使用正则表达式

阻止调用方的模式匹配通过使用正则表达式完成。 联机提供了多个工具来帮助验证正则表达式模式匹配。 如果不熟悉正则表达式模式，建议你花一些时间熟悉基础知识。 若要确保获得预期结果，在向租户添加新的阻止数字匹配之前，请使用验证模式匹配项的工具。