---
title: 阻止 Microsoft 团队中的入站呼叫
ms.author: v-lanac
author: lanachin
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
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: 3bb1222f0662228e5c0de7b2253cbac162571b1e
ms.sourcegitcommit: a36514c7c8ea47bde4edb09c11ff99061b1f74c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094678"
---
# <a name="block-inbound-calls"></a>阻止入站呼叫

电话系统直接路由和通话计划支持阻止来自公共交换电话网络 (PSTN) 的入站呼叫。 此功能允许定义用于数字模式的租户全局列表，以便可以针对该列表检查与该租户的每个传入 PSTN 呼叫的呼叫方 ID。 如果进行了匹配，则会拒绝传入呼叫。

此入站呼叫阻止功能仅适用于从 PSTN 发起的入站呼叫，并且仅适用于租户-全球基础。 它在每用户基础上不可用。  

>[!NOTE]
> 被阻止的呼叫者在被阻止后可能会遇到稍有不同的行为。 该行为基于被阻止的呼叫者的运营商的运营商如何处理不允许成功完成呼叫的通知。 例如，可能包括一条指示呼叫无法通过拨号完成的载波消息，或只是断开通话。

## <a name="call-blocking-admin-controls-and-information"></a>呼叫阻止管理员控制和信息

阻止号码的管理员控制仅使用 PowerShell 提供。 数字块模式定义为正则表达式模式。 表达式的顺序是不重要的-列表中的第一个模式将导致调用被阻止。 在 "阻止的呼叫者" 列表中添加或删除的新号码或图案可能需要长达24小时才能使模式变为活动状态。

## <a name="call-blocking-powershell-commands"></a>呼叫阻止 PowerShell 命令

你可以使用**新**的、**获取**、**设置**、**删除**  - **CsInboundBlockedNumberPattern** cmdlet 管理数字模式。 你可以使用这些 cmdlet 管理给定模式，包括切换给定模式的激活的功能。

- [CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern)返回添加到租户列表的所有阻止的数字模式的列表，包括名称、说明、已启用 (True/False) 和模式。
- [New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern)将阻止的数字模式添加到租户列表。
- [Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern)从租户列表中删除阻止的数字模式。
- [Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern)修改租户列表中被阻止的数字模式的一个或多个参数。

查看和激活整个呼叫阻止功能是通过**Get**、 **Set**  - **CsTenantBlockingCallingNumbers** cmdlet 进行管理的。

- [CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers)返回全局被阻止的号码列表的参数，其中包括已启用 (True/False) 。 只有在打开或关闭该功能时，才能手动修改单个全局租户策略。
- [Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers)允许将全局租户阻止的通话修改为在租户级别启用和禁用。

### <a name="examples"></a>示例

#### <a name="block-a-number"></a>阻止号码

在此示例中，"**已启用**" 和 "**说明**" 参数是可选的。

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

创建新模式会将模式添加为默认启用。 说明是提供详细信息的可选字段。

我们建议你提供一个有意义的名称，以便轻松了解添加模式的原因。 如果只是阻止垃圾邮件号码，请考虑将规则命名为与正在匹配的数字模式相同，并根据需要在描述中添加其他信息。

使用正则表达式 (Regex) 匹配模式。 在测试和验证之前，留出复制时间。

#### <a name="allow-a-number"></a>允许数字

在此示例中，需要**标识**参数。

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
如果身份未知，请使用**CsInboundBlockedNumberPattern** cmdlet 首先找到正确的模式，并记下标识。 然后，运行 CsTenantBlockedNumberPattern cmdlet 并传递相应**的**标识值。

在测试和验证之前，留出复制时间。

#### <a name="view-all-number-patterns"></a>查看所有数字模式

运行此 cmdlet 将返回为租户输入的所有阻止号码的列表：

```powershell
Get-CsInboundBlockedNumberPattern
```

使用内置 PowerShell 筛选功能根据需要分析返回的值。

## <a name="add-number-exceptions"></a>添加号码例外

你可以使用 "**新建**"、"**获取**"、"**设置**" 和 "**删除**  - **CsTenantBlockNumberExceptionPattern** " cmdlet 将例外添加到阻止的数字模式。

- [New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern)将数字异常模式添加到租户列表。 
- [Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern)返回添加到租户列表的所有数字异常模式的列表。
- [Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern)将一个或多个参数修改为租户列表中的数字异常模式。
- [Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern)从租户列表中删除数字异常模式。

### <a name="examples"></a>示例

#### <a name="add-a-number-exception"></a>添加数字例外

在此示例中，创建新的数字异常模式，并将在默认情况下将模式添加为 "已启用"。 "**启用**" 和 "**说明**" 参数是可选的。

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>查看所有号码的例外情况

在此示例中， **Identity**参数是可选的。 如果未指定**Identity**参数，此 cmdlet 将返回为租户输入的所有数字异常模式的列表。
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>修改数字异常

在此示例中， **Identity**参数是必需的。 **CsTenantBlockedNumberExceptionPattern** cmdlet 允许你为给定的数字模式标识修改一个或多个参数。
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>删除数字异常

在此示例中，需要**标识**参数。 此 cmdlet 将从租户列表中删除给定的数字模式。  如果身份未知，请使用**CsInboundBlockedNumberPattern** cmdlet 首先找到正确的模式，并记下标识。 然后，运行 CsTenantBlockedNumberExceptionPattern cmdlet 并传递相应**的**标识值。在测试和验证之前，留出复制时间。  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>测试是否阻止了某个号码

使用**CsInboundBlockedNumberPattern** cmdlet 验证租户中的某个数字是否已被阻止。
 
在此示例中，需要**电话号码**和**租户**参数。 **电话号码**参数应为不带任何其他字符的数字字符串，如 + 或-。 在 TRPS 中，**租户参数**是可选的。 如果该数字在租户中被阻止，则所得到的**isNumberBlocked**参数将返回 True 值，如果该数字未被阻止，则返回 False。

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

## <a name="a-note-about-regex"></a>有关 Regex 的笔记

如前面所述，阻止调用方的模式匹配是使用 Regex 完成的。 可联机使用多个工具来帮助验证 Regex 模式匹配。 如果你不熟悉 Regex 模式，我们建议你花一些时间来熟悉基础知识。 若要确保获得预期的结果，请使用用于验证模式匹配的工具，然后再将新的阻止数字匹配添加到你的租户。
