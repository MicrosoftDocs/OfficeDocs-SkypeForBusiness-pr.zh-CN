---
title: 在 Skype for Business Online 中阻止入站呼叫
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
ms.openlocfilehash: 16a646af3e456bb68a2a582cad7d6b742100c650
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820912"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="54dbd-102">阻止入站呼叫</span><span class="sxs-lookup"><span data-stu-id="54dbd-102">Block inbound calls</span></span>

<span data-ttu-id="54dbd-103">Skype for Business Online 呼叫计划现在支持阻止来自公共电话交换网和 PSTN (的) 。</span><span class="sxs-lookup"><span data-stu-id="54dbd-103">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="54dbd-104">此功能允许定义一个租户全局数字模式列表，以便可以针对列表检查每个传入到租户的 PSTN 呼叫的呼叫者 ID 是否匹配。</span><span class="sxs-lookup"><span data-stu-id="54dbd-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="54dbd-105">如果进行了匹配，则拒绝传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="54dbd-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="54dbd-106">此入站呼叫阻止功能仅适用于源自 PSTN 的入站呼叫，并且仅适用于租户全局。</span><span class="sxs-lookup"><span data-stu-id="54dbd-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="54dbd-107">它并非按用户提供。</span><span class="sxs-lookup"><span data-stu-id="54dbd-107">It's not available on a per-user basis.</span></span>  

<span data-ttu-id="54dbd-108">此功能尚不可用于直接路由。</span><span class="sxs-lookup"><span data-stu-id="54dbd-108">This feature isn't yet available for Direct Routing.</span></span>

>[!NOTE]
> <span data-ttu-id="54dbd-109">被阻止的调用方在被阻止时可能遇到略有不同的行为。</span><span class="sxs-lookup"><span data-stu-id="54dbd-109">Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="54dbd-110">此行为基于被阻止呼叫者的运营商如何处理不允许成功完成呼叫的通知。</span><span class="sxs-lookup"><span data-stu-id="54dbd-110">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="54dbd-111">示例可能包括运营商消息，指出无法将呼叫作为已拨叫完成，或只是丢弃呼叫。</span><span class="sxs-lookup"><span data-stu-id="54dbd-111">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="54dbd-112">呼叫阻止管理员控件和信息</span><span class="sxs-lookup"><span data-stu-id="54dbd-112">Call blocking admin controls and information</span></span>

<span data-ttu-id="54dbd-113">阻止号码的管理控件仅使用 PowerShell 提供。</span><span class="sxs-lookup"><span data-stu-id="54dbd-113">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="54dbd-114">数字块模式定义为正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="54dbd-114">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="54dbd-115">表达式的顺序不重要 – 列表中匹配的第一个模式会导致调用被阻止。</span><span class="sxs-lookup"><span data-stu-id="54dbd-115">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="54dbd-116">在阻止的呼叫者列表中添加或删除的新号码或模式可能需要多达 24 小时才能激活模式。</span><span class="sxs-lookup"><span data-stu-id="54dbd-116">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="54dbd-117">调用阻止 PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="54dbd-117">Call blocking PowerShell commands</span></span>

<span data-ttu-id="54dbd-118">数字模式通过命令 ```CsInboundBlockedNumberPattern``` ```New``` 、、和 ```Get``` ```Set``` 进行管理 ```Remove``` 。</span><span class="sxs-lookup"><span data-stu-id="54dbd-118">Number patterns are managed through the ```CsInboundBlockedNumberPattern``` commands ```New```, ```Get```, ```Set```, and ```Remove```.</span></span> <span data-ttu-id="54dbd-119">可以使用这些 cmdlet 来管理给定的模式，包括切换给定模式激活的能力。</span><span class="sxs-lookup"><span data-stu-id="54dbd-119">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="54dbd-120">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) 返回添加到租户列表的所有阻止数字模式的列表，包括名称、说明、已启用 (True/False) 和每个模式。</span><span class="sxs-lookup"><span data-stu-id="54dbd-120">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="54dbd-121">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) 将阻止的编号模式添加到租户列表。</span><span class="sxs-lookup"><span data-stu-id="54dbd-121">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="54dbd-122">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) 从租户列表中删除阻止的编号模式。</span><span class="sxs-lookup"><span data-stu-id="54dbd-122">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="54dbd-123">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) 修改租户列表中的被阻止数字模式的一个或多个参数。</span><span class="sxs-lookup"><span data-stu-id="54dbd-123">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="54dbd-124">通过命令和 .管理查看和激活整个呼叫阻止 ```CsTenantBlockingCallingNumbers``` ```Get``` 功能 ```Set``` 。</span><span class="sxs-lookup"><span data-stu-id="54dbd-124">Viewing and activating the entire call blocking feature is managed through the ```CsTenantBlockingCallingNumbers``` commands ```Get``` and ```Set```.</span></span>

- <span data-ttu-id="54dbd-125">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) 返回全局阻止编号列表的参数，包括 Enabled (True/False) 。</span><span class="sxs-lookup"><span data-stu-id="54dbd-125">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="54dbd-126">只有打开或关闭该功能，才能手动修改单个全局租户策略。</span><span class="sxs-lookup"><span data-stu-id="54dbd-126">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="54dbd-127">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) 允许在租户级别启用和关闭全局租户阻止的调用。</span><span class="sxs-lookup"><span data-stu-id="54dbd-127">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="54dbd-128">示例</span><span class="sxs-lookup"><span data-stu-id="54dbd-128">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="54dbd-129">阻止号码</span><span class="sxs-lookup"><span data-stu-id="54dbd-129">Block a number</span></span>

<span data-ttu-id="54dbd-130">此示例中，and ```-Enabled``` ```-Description``` 参数是可选的：</span><span class="sxs-lookup"><span data-stu-id="54dbd-130">In this example, the ```-Enabled``` and ```-Description``` parameters are optional:</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="54dbd-131">创建新模式会添加默认已启用的模式。</span><span class="sxs-lookup"><span data-stu-id="54dbd-131">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="54dbd-132">说明是一个可选字段，用于提供详细信息。</span><span class="sxs-lookup"><span data-stu-id="54dbd-132">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="54dbd-133">我们建议提供一个有意义的名称，以便轻松了解添加模式的原因。</span><span class="sxs-lookup"><span data-stu-id="54dbd-133">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="54dbd-134">如果只是阻止垃圾邮件号码，请考虑将规则命名为匹配的数字模式，并根据需要在说明中添加其他信息。</span><span class="sxs-lookup"><span data-stu-id="54dbd-134">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="54dbd-135">模式使用正则表达式和正则表达式 (正则表达式) 。</span><span class="sxs-lookup"><span data-stu-id="54dbd-135">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="54dbd-136">在测试和验证之前，请留出时间进行复制。</span><span class="sxs-lookup"><span data-stu-id="54dbd-136">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="54dbd-137">允许数字</span><span class="sxs-lookup"><span data-stu-id="54dbd-137">Allow a number</span></span>

<span data-ttu-id="54dbd-138">此示例中， ```-Identity``` 参数是必需的：</span><span class="sxs-lookup"><span data-stu-id="54dbd-138">In this example, the ```-Identity``` parameter is required:</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="54dbd-139">如果标识未知，请使用 cmdlet 先找到正确的模式并 ```Get-CsInboundBlockedNumberPattern``` 记下标识。</span><span class="sxs-lookup"><span data-stu-id="54dbd-139">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="54dbd-140">然后，运行 ```Remove-CsTenantBlockedNumberPattern``` cmdlet 并传递相应的标识值。</span><span class="sxs-lookup"><span data-stu-id="54dbd-140">Then, run the ```Remove-CsTenantBlockedNumberPattern``` cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="54dbd-141">在测试和验证之前，请留出时间进行复制。</span><span class="sxs-lookup"><span data-stu-id="54dbd-141">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="54dbd-142">查看所有数字模式</span><span class="sxs-lookup"><span data-stu-id="54dbd-142">View all number patterns</span></span>

<span data-ttu-id="54dbd-143">运行此 cmdlet 将返回为租户输入的所有阻止号码的列表：</span><span class="sxs-lookup"><span data-stu-id="54dbd-143">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="54dbd-144">使用内置的 PowerShell 筛选功能，可分析所需的返回值。</span><span class="sxs-lookup"><span data-stu-id="54dbd-144">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="54dbd-145">添加数字例外</span><span class="sxs-lookup"><span data-stu-id="54dbd-145">Add number exceptions</span></span>

<span data-ttu-id="54dbd-146">可以通过命令、和向被阻止的数模式 ```CsTenantBlockNumberExceptionPattern``` ```New``` ```Get``` 添加 ```Set``` 例外 ```Remove``` 。</span><span class="sxs-lookup"><span data-stu-id="54dbd-146">You can add exceptions to blocked number patterns through the ```CsTenantBlockNumberExceptionPattern``` commands, ```New```, ```Get```, ```Set```, and ```Remove```.</span></span>

- <span data-ttu-id="54dbd-147">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) 将数字异常模式添加到租户列表。</span><span class="sxs-lookup"><span data-stu-id="54dbd-147">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="54dbd-148">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) 返回添加到租户列表的所有数字异常模式的列表。</span><span class="sxs-lookup"><span data-stu-id="54dbd-148">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="54dbd-149">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) 将一个或多个参数修改为租户列表中的数字异常模式。</span><span class="sxs-lookup"><span data-stu-id="54dbd-149">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="54dbd-150">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) 从租户列表中删除数字异常模式。</span><span class="sxs-lookup"><span data-stu-id="54dbd-150">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="54dbd-151">示例</span><span class="sxs-lookup"><span data-stu-id="54dbd-151">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="54dbd-152">添加数字例外</span><span class="sxs-lookup"><span data-stu-id="54dbd-152">Add a number exception</span></span>

<span data-ttu-id="54dbd-153">本示例将创建一个新的数字异常模式，默认情况下，该模式将添加为已启用。</span><span class="sxs-lookup"><span data-stu-id="54dbd-153">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="54dbd-154">和 ```-Enabled``` ```-Description``` 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="54dbd-154">The ```-Enabled``` and ```-Description``` parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="54dbd-155">查看所有数字异常</span><span class="sxs-lookup"><span data-stu-id="54dbd-155">View all number exceptions</span></span>

<span data-ttu-id="54dbd-156">本示例中的 -Identity 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="54dbd-156">In this example, the -Identity parameter is optional.</span></span> <span data-ttu-id="54dbd-157">如果未指定参数，此 cmdlet 将返回为租户输入的所有数字 ```-Identity``` 异常模式的列表。</span><span class="sxs-lookup"><span data-stu-id="54dbd-157">If the ```-Identity``` parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="54dbd-158">修改数字异常</span><span class="sxs-lookup"><span data-stu-id="54dbd-158">Modify a number exception</span></span>

<span data-ttu-id="54dbd-159">此示例中，-Identity 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="54dbd-159">In this example, the -Identity parameter is mandatory.</span></span> <span data-ttu-id="54dbd-160">```Set-CsTenantBlockedNumberExceptionPattern```该 cmdlet 允许修改给定数字模式标识的一个或多个参数。</span><span class="sxs-lookup"><span data-stu-id="54dbd-160">The ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="54dbd-161">删除数字异常</span><span class="sxs-lookup"><span data-stu-id="54dbd-161">Remove a number exception</span></span>

<span data-ttu-id="54dbd-162">此示例中， ```-Identity``` 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="54dbd-162">In this example, the ```-Identity``` parameter is required.</span></span> <span data-ttu-id="54dbd-163">此 cmdlet 将删除租户列表中的给定数字模式。</span><span class="sxs-lookup"><span data-stu-id="54dbd-163">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="54dbd-164">如果标识未知，请使用 cmdlet 先找到正确的模式并 ```Get-CsInboundBlockedNumberPattern``` 记下标识。</span><span class="sxs-lookup"><span data-stu-id="54dbd-164">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="54dbd-165">然后，运行 ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet 并传递相应的标识值。</span><span class="sxs-lookup"><span data-stu-id="54dbd-165">Then, run the ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="54dbd-166">在测试和验证之前，请留出时间进行复制。</span><span class="sxs-lookup"><span data-stu-id="54dbd-166"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="54dbd-167">测试是否阻止了数字</span><span class="sxs-lookup"><span data-stu-id="54dbd-167">Test whether a number is blocked</span></span>

<span data-ttu-id="54dbd-168">使用该 ```Test-CsInboundBlockedNumberPattern``` cmdlet 验证是否在租户中阻止了一个数字。</span><span class="sxs-lookup"><span data-stu-id="54dbd-168">Use the ```Test-CsInboundBlockedNumberPattern``` cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="54dbd-169">此示例中 ```-Phonenumber``` ，and ```-Tenant``` 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="54dbd-169">In this example, the ```-Phonenumber``` and ```-Tenant``` parameters are required.</span></span> <span data-ttu-id="54dbd-170">该 ```-PhoneNumber``` 参数应为不带任何其他字符（如 + 或 -）的数字字符串。</span><span class="sxs-lookup"><span data-stu-id="54dbd-170">The ```-PhoneNumber``` parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="54dbd-171">在 TRPS 中 ```-Tenant parameter``` ，可选。</span><span class="sxs-lookup"><span data-stu-id="54dbd-171">In TRPS, the ```-Tenant parameter``` is optional.</span></span> <span data-ttu-id="54dbd-172">如果租户中阻止了数字，则生成的参数返回值 True;如果未阻止，则返回 ```isNumberBlocked``` False。</span><span class="sxs-lookup"><span data-stu-id="54dbd-172">The resulting ```isNumberBlocked``` parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="54dbd-173">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="54dbd-173">httpResponseCode</span></span>  |<span data-ttu-id="54dbd-174">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="54dbd-174">isNumberBlocked</span></span>   |<span data-ttu-id="54dbd-175">errorMessage</span><span class="sxs-lookup"><span data-stu-id="54dbd-175">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="54dbd-176">200</span><span class="sxs-lookup"><span data-stu-id="54dbd-176">200</span></span>    | <span data-ttu-id="54dbd-177">True</span><span class="sxs-lookup"><span data-stu-id="54dbd-177">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="54dbd-178">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="54dbd-178">httpResponseCode</span></span>  |<span data-ttu-id="54dbd-179">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="54dbd-179">isNumberBlocked</span></span>   |<span data-ttu-id="54dbd-180">errorMessage</span><span class="sxs-lookup"><span data-stu-id="54dbd-180">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="54dbd-181">200</span><span class="sxs-lookup"><span data-stu-id="54dbd-181">200</span></span>    | <span data-ttu-id="54dbd-182">False</span><span class="sxs-lookup"><span data-stu-id="54dbd-182">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="54dbd-183">有关正则表达式的注释</span><span class="sxs-lookup"><span data-stu-id="54dbd-183">A note about Regex</span></span>

<span data-ttu-id="54dbd-184">如前面所述，阻止调用方的模式匹配是使用正则表达式完成。</span><span class="sxs-lookup"><span data-stu-id="54dbd-184">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="54dbd-185">在线提供了多个工具来帮助验证正则表达式模式匹配。</span><span class="sxs-lookup"><span data-stu-id="54dbd-185">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="54dbd-186">如果不熟悉正则表达式模式，建议你花一些时间熟悉基础知识。</span><span class="sxs-lookup"><span data-stu-id="54dbd-186">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="54dbd-187">若要确保获得预期的结果，请使用一个工具来验证模式匹配项，然后再向租户添加新的阻止编号匹配项。</span><span class="sxs-lookup"><span data-stu-id="54dbd-187">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="54dbd-188">相关主题</span><span class="sxs-lookup"><span data-stu-id="54dbd-188">Related topics</span></span>

- [<span data-ttu-id="54dbd-189">使用 Skype for Business Online 设置计算机以Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="54dbd-189">Set up your computer to manage Skype for Business Online by using Windows PowerShell</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
