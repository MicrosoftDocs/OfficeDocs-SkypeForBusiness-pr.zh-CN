---
title: 在 Microsoft Teams 中阻止入站呼叫
ms.author: v-cichur
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
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: ca2f8de5962572a08ab2a0ae7127446d14334c83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799902"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="f7c14-102">阻止入站呼叫</span><span class="sxs-lookup"><span data-stu-id="f7c14-102">Block inbound calls</span></span>

<span data-ttu-id="f7c14-103">电话系统直接路由和呼叫计划支持阻止来自公用电话交换网和 PSTN (的) 。</span><span class="sxs-lookup"><span data-stu-id="f7c14-103">Phone System Direct Routing and Calling Plans support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="f7c14-104">此功能允许定义一个租户全局数字模式列表，以便可以针对列表检查每个传入到租户的 PSTN 呼叫的呼叫者 ID 是否匹配。</span><span class="sxs-lookup"><span data-stu-id="f7c14-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="f7c14-105">如果进行了匹配，将拒绝传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="f7c14-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="f7c14-106">此入站呼叫阻止功能仅适用于源自 PSTN 的入站呼叫，并且仅适用于租户全局。</span><span class="sxs-lookup"><span data-stu-id="f7c14-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="f7c14-107">它并非按用户提供。</span><span class="sxs-lookup"><span data-stu-id="f7c14-107">It's not available on a per-user basis.</span></span>  

>[!NOTE]
> <span data-ttu-id="f7c14-108">被阻止的呼叫者在被阻止时可能遇到略有不同的行为。</span><span class="sxs-lookup"><span data-stu-id="f7c14-108">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="f7c14-109">此行为基于被阻止呼叫者的运营商如何处理不允许成功完成呼叫的通知。</span><span class="sxs-lookup"><span data-stu-id="f7c14-109">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="f7c14-110">示例可能包括运营商消息，指出无法将呼叫作为已拨叫完成，或只是丢弃呼叫。</span><span class="sxs-lookup"><span data-stu-id="f7c14-110">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="f7c14-111">呼叫阻止管理员控件和信息</span><span class="sxs-lookup"><span data-stu-id="f7c14-111">Call blocking admin controls and information</span></span>

<span data-ttu-id="f7c14-112">阻止号码的管理控件仅使用 PowerShell 提供。</span><span class="sxs-lookup"><span data-stu-id="f7c14-112">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="f7c14-113">数字块模式定义为正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="f7c14-113">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="f7c14-114">表达式的顺序不重要 – 列表中匹配的第一个模式会导致调用被阻止。</span><span class="sxs-lookup"><span data-stu-id="f7c14-114">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="f7c14-115">在阻止的呼叫者列表中添加或删除的新号码或模式可能需要多达 24 小时才能激活模式。</span><span class="sxs-lookup"><span data-stu-id="f7c14-115">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="f7c14-116">调用阻止 PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="f7c14-116">Call blocking PowerShell commands</span></span>

<span data-ttu-id="f7c14-117">使用 New、Get、Set、Remove      - **CsInboundBlockedNumberPattern** cmdlet 管理数字模式。</span><span class="sxs-lookup"><span data-stu-id="f7c14-117">You manage number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="f7c14-118">可以使用这些 cmdlet 来管理给定的模式，包括切换给定模式激活的能力。</span><span class="sxs-lookup"><span data-stu-id="f7c14-118">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="f7c14-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) 返回添加到租户列表的所有阻止数字模式的列表，包括名称、说明、已启用 (True/False) 和每个模式。</span><span class="sxs-lookup"><span data-stu-id="f7c14-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="f7c14-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) 将阻止的编号模式添加到租户列表。</span><span class="sxs-lookup"><span data-stu-id="f7c14-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="f7c14-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) 从租户列表中删除阻止的编号模式。</span><span class="sxs-lookup"><span data-stu-id="f7c14-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="f7c14-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) 修改租户列表中的被阻止数字模式的一个或多个参数。</span><span class="sxs-lookup"><span data-stu-id="f7c14-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="f7c14-123">通过 **Get、Set**   - **CsTenantBlockingCallingNumbers** cmdlet 管理查看和激活整个呼叫阻止功能。</span><span class="sxs-lookup"><span data-stu-id="f7c14-123">Viewing and activating the entire call blocking feature is managed through the **Get**, **Set** -**CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="f7c14-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) 返回全局阻止编号列表的参数，包括 Enabled (True/False) 。</span><span class="sxs-lookup"><span data-stu-id="f7c14-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="f7c14-125">只有打开或关闭该功能，才能手动修改单个全局租户策略。</span><span class="sxs-lookup"><span data-stu-id="f7c14-125">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="f7c14-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) 允许修改全局租户阻止的调用以在租户级别启用和关闭。</span><span class="sxs-lookup"><span data-stu-id="f7c14-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="f7c14-127">示例</span><span class="sxs-lookup"><span data-stu-id="f7c14-127">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="f7c14-128">阻止号码</span><span class="sxs-lookup"><span data-stu-id="f7c14-128">Block a number</span></span>

<span data-ttu-id="f7c14-129">此示例中 **，Enabled** 和 **Description** 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="f7c14-129">In this example, the **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="f7c14-130">创建新模式会添加默认已启用的模式。</span><span class="sxs-lookup"><span data-stu-id="f7c14-130">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="f7c14-131">说明是一个可选字段，用于提供详细信息。</span><span class="sxs-lookup"><span data-stu-id="f7c14-131">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="f7c14-132">我们建议提供一个有意义的名称，以便轻松了解添加模式的原因。</span><span class="sxs-lookup"><span data-stu-id="f7c14-132">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="f7c14-133">如果只是阻止垃圾邮件号码，请考虑将规则命名为匹配的数字模式，并根据需要在说明中添加其他信息。</span><span class="sxs-lookup"><span data-stu-id="f7c14-133">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="f7c14-134">模式使用正则表达式和正则表达式 (正则表达式) 。</span><span class="sxs-lookup"><span data-stu-id="f7c14-134">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="f7c14-135">在测试和验证之前，请留出时间进行复制。</span><span class="sxs-lookup"><span data-stu-id="f7c14-135">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="f7c14-136">允许数字</span><span class="sxs-lookup"><span data-stu-id="f7c14-136">Allow a number</span></span>

<span data-ttu-id="f7c14-137">此示例中 **，Identity** 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="f7c14-137">In this example, the **Identity** parameter is required.</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="f7c14-138">如果标识未知，请使用 **Get-CsInboundBlockedNumberPattern** cmdlet 先找到正确的模式并记下标识。</span><span class="sxs-lookup"><span data-stu-id="f7c14-138">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="f7c14-139">然后，运行 **Remove-CsTenantBlockedNumberPattern** cmdlet 并传递相应的标识值。</span><span class="sxs-lookup"><span data-stu-id="f7c14-139">Then, run the **Remove-CsTenantBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="f7c14-140">在测试和验证之前，请留出时间进行复制。</span><span class="sxs-lookup"><span data-stu-id="f7c14-140">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="f7c14-141">查看所有数字模式</span><span class="sxs-lookup"><span data-stu-id="f7c14-141">View all number patterns</span></span>

<span data-ttu-id="f7c14-142">运行此 cmdlet 将返回为租户输入的所有阻止号码的列表：</span><span class="sxs-lookup"><span data-stu-id="f7c14-142">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="f7c14-143">使用内置的 PowerShell 筛选功能，可分析所需的返回值。</span><span class="sxs-lookup"><span data-stu-id="f7c14-143">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="f7c14-144">添加数字例外</span><span class="sxs-lookup"><span data-stu-id="f7c14-144">Add number exceptions</span></span>

<span data-ttu-id="f7c14-145">可以使用New、Get、Set、Remove     - **CsTenantBlockNumberExceptionPattern** cmdlet 向被阻止的编号模式添加异常。</span><span class="sxs-lookup"><span data-stu-id="f7c14-145">You can add exceptions to blocked number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsTenantBlockNumberExceptionPattern** cmdlets.</span></span>

- <span data-ttu-id="f7c14-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) 将数字异常模式添加到租户列表。</span><span class="sxs-lookup"><span data-stu-id="f7c14-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="f7c14-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) 返回添加到租户列表的所有数字异常模式的列表。</span><span class="sxs-lookup"><span data-stu-id="f7c14-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="f7c14-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) 将一个或多个参数修改为租户列表中的数字异常模式。</span><span class="sxs-lookup"><span data-stu-id="f7c14-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="f7c14-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) 从租户列表中删除数字异常模式。</span><span class="sxs-lookup"><span data-stu-id="f7c14-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="f7c14-150">示例</span><span class="sxs-lookup"><span data-stu-id="f7c14-150">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="f7c14-151">添加数字异常</span><span class="sxs-lookup"><span data-stu-id="f7c14-151">Add a number exception</span></span>

<span data-ttu-id="f7c14-152">本示例将创建一个新的数字异常模式，默认情况下，该模式将添加为"已启用"。</span><span class="sxs-lookup"><span data-stu-id="f7c14-152">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="f7c14-153">Enabled 和 **Description** 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="f7c14-153">The **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="f7c14-154">查看所有数字异常</span><span class="sxs-lookup"><span data-stu-id="f7c14-154">View all number exceptions</span></span>

<span data-ttu-id="f7c14-155">本示例中的 **Identity** 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="f7c14-155">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="f7c14-156">如果 **未指定 Identity** 参数，此 cmdlet 将返回为租户输入的所有数字异常模式的列表。</span><span class="sxs-lookup"><span data-stu-id="f7c14-156">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="f7c14-157">修改数字异常</span><span class="sxs-lookup"><span data-stu-id="f7c14-157">Modify a number exception</span></span>

<span data-ttu-id="f7c14-158">此示例中 **，Identity** 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="f7c14-158">In this example, the **Identity** parameter is mandatory.</span></span> <span data-ttu-id="f7c14-159">**Set-CsTenantBlockedNumberExceptionPattern** cmdlet 允许修改给定数字模式标识的一个或多个参数。</span><span class="sxs-lookup"><span data-stu-id="f7c14-159">The **Set-CsTenantBlockedNumberExceptionPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="f7c14-160">删除数字异常</span><span class="sxs-lookup"><span data-stu-id="f7c14-160">Remove a number exception</span></span>

<span data-ttu-id="f7c14-161">此示例中 **，Identity** 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="f7c14-161">In this example, the **Identity** parameter is required.</span></span> <span data-ttu-id="f7c14-162">此 cmdlet 将删除租户列表中的给定数字模式。</span><span class="sxs-lookup"><span data-stu-id="f7c14-162">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="f7c14-163">如果标识未知，请使用 **Get-CsInboundBlockedNumberPattern** cmdlet 先找到正确的模式并记下标识。</span><span class="sxs-lookup"><span data-stu-id="f7c14-163">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="f7c14-164">然后，运行 **Remove-CsTenantBlockedNumberExceptionPattern** cmdlet 并传递相应的标识值。</span><span class="sxs-lookup"><span data-stu-id="f7c14-164">Then, run the **Remove-CsTenantBlockedNumberExceptionPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="f7c14-165">在测试和验证之前，请留出时间进行复制。</span><span class="sxs-lookup"><span data-stu-id="f7c14-165"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="f7c14-166">测试是否阻止了数字</span><span class="sxs-lookup"><span data-stu-id="f7c14-166">Test whether a number is blocked</span></span>

<span data-ttu-id="f7c14-167">使用 **Test-CsInboundBlockedNumberPattern** cmdlet 验证是否在租户中阻止了数字。</span><span class="sxs-lookup"><span data-stu-id="f7c14-167">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="f7c14-168">此示例中 **，PhoneNumber 和** **Tenant** 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="f7c14-168">In this example, the **PhoneNumber** and **Tenant** parameters are required.</span></span> <span data-ttu-id="f7c14-169">**PhoneNumber** 参数应为不带任何其他字符（如 + 或 -）的数字字符串。</span><span class="sxs-lookup"><span data-stu-id="f7c14-169">The **PhoneNumber** parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="f7c14-170">在 TRPS 中 **，Tenant 参数** 是可选的。</span><span class="sxs-lookup"><span data-stu-id="f7c14-170">In TRPS, the **Tenant parameter** is optional.</span></span> <span data-ttu-id="f7c14-171">如果租户中阻止了数字，则生成的 **isNumberBlocked** 参数返回值 True;如果未阻止，则返回 False。</span><span class="sxs-lookup"><span data-stu-id="f7c14-171">The resulting **isNumberBlocked** parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="f7c14-172">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="f7c14-172">httpResponseCode</span></span>  |<span data-ttu-id="f7c14-173">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="f7c14-173">isNumberBlocked</span></span>   |<span data-ttu-id="f7c14-174">errorMessage</span><span class="sxs-lookup"><span data-stu-id="f7c14-174">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f7c14-175">200</span><span class="sxs-lookup"><span data-stu-id="f7c14-175">200</span></span>    | <span data-ttu-id="f7c14-176">True</span><span class="sxs-lookup"><span data-stu-id="f7c14-176">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="f7c14-177">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="f7c14-177">httpResponseCode</span></span>  |<span data-ttu-id="f7c14-178">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="f7c14-178">isNumberBlocked</span></span>   |<span data-ttu-id="f7c14-179">errorMessage</span><span class="sxs-lookup"><span data-stu-id="f7c14-179">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f7c14-180">200</span><span class="sxs-lookup"><span data-stu-id="f7c14-180">200</span></span>    | <span data-ttu-id="f7c14-181">False</span><span class="sxs-lookup"><span data-stu-id="f7c14-181">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="f7c14-182">有关正则表达式的注释</span><span class="sxs-lookup"><span data-stu-id="f7c14-182">A note about Regex</span></span>

<span data-ttu-id="f7c14-183">如前面所述，阻止调用方的模式匹配是使用正则表达式完成。</span><span class="sxs-lookup"><span data-stu-id="f7c14-183">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="f7c14-184">在线提供了多个工具来帮助验证正则表达式模式匹配。</span><span class="sxs-lookup"><span data-stu-id="f7c14-184">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="f7c14-185">如果不熟悉正则表达式模式，建议你花一些时间熟悉基础知识。</span><span class="sxs-lookup"><span data-stu-id="f7c14-185">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="f7c14-186">若要确保获得预期的结果，请使用验证模式匹配项的工具，然后再向租户添加新的阻止编号匹配项。</span><span class="sxs-lookup"><span data-stu-id="f7c14-186">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>
