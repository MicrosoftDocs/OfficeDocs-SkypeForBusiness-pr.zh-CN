---
title: 在 Skype for Business Online 中阻止入站呼叫
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: b238d69087c5b29e6d9abc898e91c44fd8053411
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266059"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="33793-102">阻止入站呼叫</span><span class="sxs-lookup"><span data-stu-id="33793-102">Block inbound calls</span></span>

<span data-ttu-id="33793-103">Skype for Business Online 通话计划现支持阻止来自公共交换电话网络（PSTN）的入站呼叫。</span><span class="sxs-lookup"><span data-stu-id="33793-103">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="33793-104">此功能允许定义用于数字模式的租户全局列表，以便可以针对该列表检查与该租户的每个传入 PSTN 呼叫的呼叫方 ID。</span><span class="sxs-lookup"><span data-stu-id="33793-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="33793-105">如果进行了匹配，则会拒绝传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="33793-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="33793-106">此入站呼叫阻止功能仅适用于从 PSTN 发起的入站呼叫，并且仅适用于租户-全球基础。</span><span class="sxs-lookup"><span data-stu-id="33793-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="33793-107">它在每用户基础上不可用。</span><span class="sxs-lookup"><span data-stu-id="33793-107">It's not available on a per-user basis.</span></span>  

<span data-ttu-id="33793-108">此功能尚不可用于直接路由。</span><span class="sxs-lookup"><span data-stu-id="33793-108">This feature isn't yet available for Direct Routing.</span></span>

>[!NOTE]
> <span data-ttu-id="33793-109">被阻止的呼叫者在被阻止时可能会遇到稍有不同的行为。</span><span class="sxs-lookup"><span data-stu-id="33793-109">Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="33793-110">该行为基于被阻止的呼叫者的运营商的运营商如何处理不允许成功完成呼叫的通知。</span><span class="sxs-lookup"><span data-stu-id="33793-110">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="33793-111">例如，可能包括一条指示呼叫无法通过拨号完成的载波消息，或只是断开通话。</span><span class="sxs-lookup"><span data-stu-id="33793-111">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="33793-112">呼叫阻止管理员控制和信息</span><span class="sxs-lookup"><span data-stu-id="33793-112">Call blocking admin controls and information</span></span>

<span data-ttu-id="33793-113">阻止号码的管理员控制仅使用 PowerShell 提供。</span><span class="sxs-lookup"><span data-stu-id="33793-113">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="33793-114">数字块模式定义为正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="33793-114">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="33793-115">表达式的顺序是不重要的-列表中的第一个模式将导致调用被阻止。</span><span class="sxs-lookup"><span data-stu-id="33793-115">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="33793-116">在 "阻止的呼叫者" 列表中添加或删除的新号码或图案可能需要长达24小时才能使模式变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="33793-116">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="33793-117">呼叫阻止 PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="33793-117">Call blocking PowerShell commands</span></span>

<span data-ttu-id="33793-118">数字模式通过```CsInboundBlockedNumberPattern```命令```New```、 ```Get``` ```Set```、和```Remove```进行管理。</span><span class="sxs-lookup"><span data-stu-id="33793-118">Number patterns are managed through the ```CsInboundBlockedNumberPattern``` commands ```New```, ```Get```, ```Set```, and ```Remove```.</span></span> <span data-ttu-id="33793-119">你可以使用这些 cmdlet 管理给定模式，包括切换给定模式的激活的功能。</span><span class="sxs-lookup"><span data-stu-id="33793-119">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="33793-120">[CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern)返回添加到租户列表的所有阻止的数字模式的列表，包括名称、说明、Enabled （True/False）和模式。</span><span class="sxs-lookup"><span data-stu-id="33793-120">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="33793-121">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern)将阻止的数字模式添加到租户列表。</span><span class="sxs-lookup"><span data-stu-id="33793-121">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="33793-122">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern)从租户列表中删除阻止的数字模式。</span><span class="sxs-lookup"><span data-stu-id="33793-122">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="33793-123">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern)修改租户列表中被阻止的数字模式的一个或多个参数。</span><span class="sxs-lookup"><span data-stu-id="33793-123">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="33793-124">查看和激活整个呼叫阻止功能通过```CsTenantBlockingCallingNumbers```命令```Get```和```Set```进行管理。</span><span class="sxs-lookup"><span data-stu-id="33793-124">Viewing and activating the entire call blocking feature is managed through the ```CsTenantBlockingCallingNumbers``` commands ```Get``` and ```Set```.</span></span>

- <span data-ttu-id="33793-125">[CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers)返回全局被阻止的号码列表的参数，包括 "已启用" （True/False）。</span><span class="sxs-lookup"><span data-stu-id="33793-125">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="33793-126">只有在打开或关闭该功能时，才能手动修改单个全局租户策略。</span><span class="sxs-lookup"><span data-stu-id="33793-126">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="33793-127">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers)允许将全局租户阻止的通话修改为在租户级别启用和禁用。</span><span class="sxs-lookup"><span data-stu-id="33793-127">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="33793-128">示例</span><span class="sxs-lookup"><span data-stu-id="33793-128">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="33793-129">阻止号码</span><span class="sxs-lookup"><span data-stu-id="33793-129">Block a number</span></span>

<span data-ttu-id="33793-130">在此示例中， ```-Enabled``` " ```-Description```和" 参数是可选的：</span><span class="sxs-lookup"><span data-stu-id="33793-130">In this example, the ```-Enabled``` and ```-Description``` parameters are optional:</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="33793-131">创建新模式会将模式添加为默认启用。</span><span class="sxs-lookup"><span data-stu-id="33793-131">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="33793-132">说明是提供详细信息的可选字段。</span><span class="sxs-lookup"><span data-stu-id="33793-132">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="33793-133">我们建议你提供一个有意义的名称，以便轻松了解添加模式的原因。</span><span class="sxs-lookup"><span data-stu-id="33793-133">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="33793-134">如果只是阻止垃圾邮件号码，请考虑将规则命名为与正在匹配的数字模式相同，并根据需要在描述中添加其他信息。</span><span class="sxs-lookup"><span data-stu-id="33793-134">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="33793-135">使用正则表达式（Regex）匹配模式。</span><span class="sxs-lookup"><span data-stu-id="33793-135">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="33793-136">在测试和验证之前，留出复制时间。</span><span class="sxs-lookup"><span data-stu-id="33793-136">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="33793-137">允许数字</span><span class="sxs-lookup"><span data-stu-id="33793-137">Allow a number</span></span>

<span data-ttu-id="33793-138">在此示例中， ```-Identity```参数是必需的：</span><span class="sxs-lookup"><span data-stu-id="33793-138">In this example, the ```-Identity``` parameter is required:</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="33793-139">如果身份未知，请使用```Get-CsInboundBlockedNumberPattern``` cmdlet 首先找到正确的模式，并记下标识。</span><span class="sxs-lookup"><span data-stu-id="33793-139">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="33793-140">然后，运行```Remove-CsTenantBlockedNumberPattern``` cmdlet 并传递相应的标识值。</span><span class="sxs-lookup"><span data-stu-id="33793-140">Then, run the ```Remove-CsTenantBlockedNumberPattern``` cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="33793-141">在测试和验证之前，留出复制时间。</span><span class="sxs-lookup"><span data-stu-id="33793-141">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="33793-142">查看所有数字模式</span><span class="sxs-lookup"><span data-stu-id="33793-142">View all number patterns</span></span>

<span data-ttu-id="33793-143">运行此 cmdlet 将返回为租户输入的所有阻止号码的列表：</span><span class="sxs-lookup"><span data-stu-id="33793-143">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="33793-144">使用内置 PowerShell 筛选功能根据需要分析返回的值。</span><span class="sxs-lookup"><span data-stu-id="33793-144">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="33793-145">添加号码例外</span><span class="sxs-lookup"><span data-stu-id="33793-145">Add number exceptions</span></span>

<span data-ttu-id="33793-146">你可以```CsTenantBlockNumberExceptionPattern```通过命令、 ```New``` ```Get``` ```Set```、、和```Remove```来向阻止的数字模式添加例外。</span><span class="sxs-lookup"><span data-stu-id="33793-146">You can add exceptions to blocked number patterns through the ```CsTenantBlockNumberExceptionPattern``` commands, ```New```, ```Get```, ```Set```, and ```Remove```.</span></span>

- <span data-ttu-id="33793-147">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern)将数字异常模式添加到租户列表。</span><span class="sxs-lookup"><span data-stu-id="33793-147">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="33793-148">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern)返回添加到租户列表的所有数字异常模式的列表。</span><span class="sxs-lookup"><span data-stu-id="33793-148">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="33793-149">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern)将一个或多个参数修改为租户列表中的数字异常模式。</span><span class="sxs-lookup"><span data-stu-id="33793-149">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="33793-150">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern)从租户列表中删除数字异常模式。</span><span class="sxs-lookup"><span data-stu-id="33793-150">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="33793-151">示例</span><span class="sxs-lookup"><span data-stu-id="33793-151">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="33793-152">添加数字例外</span><span class="sxs-lookup"><span data-stu-id="33793-152">Add a number exception</span></span>

<span data-ttu-id="33793-153">在此示例中，创建新的数字异常模式，并将在默认情况下将模式添加为 "已启用"。</span><span class="sxs-lookup"><span data-stu-id="33793-153">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="33793-154">" ```-Enabled```和```-Description``` " 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="33793-154">The ```-Enabled``` and ```-Description``` parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="33793-155">查看所有号码的例外情况</span><span class="sxs-lookup"><span data-stu-id="33793-155">View all number exceptions</span></span>

<span data-ttu-id="33793-156">在此示例中，-Identity 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="33793-156">In this example, the -Identity parameter is optional.</span></span> <span data-ttu-id="33793-157">如果未```-Identity```指定该参数，此 cmdlet 将返回为租户输入的所有数字异常模式的列表。</span><span class="sxs-lookup"><span data-stu-id="33793-157">If the ```-Identity``` parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="33793-158">修改数字异常</span><span class="sxs-lookup"><span data-stu-id="33793-158">Modify a number exception</span></span>

<span data-ttu-id="33793-159">在此示例中，-Identity 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="33793-159">In this example, the -Identity parameter is mandatory.</span></span> <span data-ttu-id="33793-160">该```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet 允许你为给定的数字模式标识修改一个或多个参数。</span><span class="sxs-lookup"><span data-stu-id="33793-160">The ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="33793-161">删除数字异常</span><span class="sxs-lookup"><span data-stu-id="33793-161">Remove a number exception</span></span>

<span data-ttu-id="33793-162">在此示例中， ```-Identity```参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="33793-162">In this example, the ```-Identity``` parameter is required.</span></span> <span data-ttu-id="33793-163">此 cmdlet 将从租户列表中删除给定的数字模式。</span><span class="sxs-lookup"><span data-stu-id="33793-163">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="33793-164">如果身份未知，请使用```Get-CsInboundBlockedNumberPattern``` cmdlet 首先找到正确的模式，并记下标识。</span><span class="sxs-lookup"><span data-stu-id="33793-164">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="33793-165">然后，运行```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet 并传递相应的标识值。</span><span class="sxs-lookup"><span data-stu-id="33793-165">Then, run the ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="33793-166">在测试和验证之前，留出复制时间。</span><span class="sxs-lookup"><span data-stu-id="33793-166"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="33793-167">测试是否阻止了某个号码</span><span class="sxs-lookup"><span data-stu-id="33793-167">Test whether a number is blocked</span></span>

<span data-ttu-id="33793-168">使用```Test-CsInboundBlockedNumberPattern``` cmdlet 验证某个号码是否在租户中被阻止。</span><span class="sxs-lookup"><span data-stu-id="33793-168">Use the ```Test-CsInboundBlockedNumberPattern``` cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="33793-169">在此示例中， ```-Phonenumber``` " ```-Tenant```和" 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="33793-169">In this example, the ```-Phonenumber``` and ```-Tenant``` parameters are required.</span></span> <span data-ttu-id="33793-170">该```-PhoneNumber```参数应为不带任何其他字符（如 + 或-）的数字字符串。</span><span class="sxs-lookup"><span data-stu-id="33793-170">The ```-PhoneNumber``` parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="33793-171">在 TRPS 中， ```-Tenant parameter``` "可选"。</span><span class="sxs-lookup"><span data-stu-id="33793-171">In TRPS, the ```-Tenant parameter``` is optional.</span></span> <span data-ttu-id="33793-172">如果该```isNumberBlocked```数字在租户中被阻止，则结果参数返回 True，如果该数字未被阻止，则返回 False。</span><span class="sxs-lookup"><span data-stu-id="33793-172">The resulting ```isNumberBlocked``` parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="33793-173">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="33793-173">httpResponseCode</span></span>  |<span data-ttu-id="33793-174">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="33793-174">isNumberBlocked</span></span>   |<span data-ttu-id="33793-175">errorMessage</span><span class="sxs-lookup"><span data-stu-id="33793-175">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="33793-176">200</span><span class="sxs-lookup"><span data-stu-id="33793-176">200</span></span>    | <span data-ttu-id="33793-177">True</span><span class="sxs-lookup"><span data-stu-id="33793-177">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="33793-178">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="33793-178">httpResponseCode</span></span>  |<span data-ttu-id="33793-179">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="33793-179">isNumberBlocked</span></span>   |<span data-ttu-id="33793-180">errorMessage</span><span class="sxs-lookup"><span data-stu-id="33793-180">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="33793-181">200</span><span class="sxs-lookup"><span data-stu-id="33793-181">200</span></span>    | <span data-ttu-id="33793-182">False</span><span class="sxs-lookup"><span data-stu-id="33793-182">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="33793-183">有关 Regex 的笔记</span><span class="sxs-lookup"><span data-stu-id="33793-183">A note about Regex</span></span>

<span data-ttu-id="33793-184">如前面所述，阻止调用方的模式匹配是使用 Regex 完成的。</span><span class="sxs-lookup"><span data-stu-id="33793-184">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="33793-185">可联机使用多个工具来帮助验证 Regex 模式匹配。</span><span class="sxs-lookup"><span data-stu-id="33793-185">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="33793-186">如果你不熟悉 Regex 模式，我们建议你花一些时间来熟悉基础知识。</span><span class="sxs-lookup"><span data-stu-id="33793-186">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="33793-187">若要确保获得预期的结果，请使用用于验证模式匹配的工具，然后再将新的阻止数字匹配添加到你的租户。</span><span class="sxs-lookup"><span data-stu-id="33793-187">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="33793-188">相关主题</span><span class="sxs-lookup"><span data-stu-id="33793-188">Related topics</span></span>

- [<span data-ttu-id="33793-189">将计算机设置为使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="33793-189">Set up your computer to manage Skype for Business Online by using Windows PowerShell</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
