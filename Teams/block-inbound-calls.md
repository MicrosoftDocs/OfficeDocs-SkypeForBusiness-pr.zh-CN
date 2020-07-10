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
# <a name="block-inbound-calls"></a><span data-ttu-id="4d851-102">阻止入站呼叫</span><span class="sxs-lookup"><span data-stu-id="4d851-102">Block inbound calls</span></span>

<span data-ttu-id="4d851-103">电话系统直接路由和通话计划支持阻止来自公共交换电话网络 (PSTN) 的入站呼叫。</span><span class="sxs-lookup"><span data-stu-id="4d851-103">Phone System Direct Routing and Calling Plans support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="4d851-104">此功能允许定义用于数字模式的租户全局列表，以便可以针对该列表检查与该租户的每个传入 PSTN 呼叫的呼叫方 ID。</span><span class="sxs-lookup"><span data-stu-id="4d851-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="4d851-105">如果进行了匹配，则会拒绝传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="4d851-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="4d851-106">此入站呼叫阻止功能仅适用于从 PSTN 发起的入站呼叫，并且仅适用于租户-全球基础。</span><span class="sxs-lookup"><span data-stu-id="4d851-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="4d851-107">它在每用户基础上不可用。</span><span class="sxs-lookup"><span data-stu-id="4d851-107">It's not available on a per-user basis.</span></span>  

>[!NOTE]
> <span data-ttu-id="4d851-108">被阻止的呼叫者在被阻止后可能会遇到稍有不同的行为。</span><span class="sxs-lookup"><span data-stu-id="4d851-108">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="4d851-109">该行为基于被阻止的呼叫者的运营商的运营商如何处理不允许成功完成呼叫的通知。</span><span class="sxs-lookup"><span data-stu-id="4d851-109">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="4d851-110">例如，可能包括一条指示呼叫无法通过拨号完成的载波消息，或只是断开通话。</span><span class="sxs-lookup"><span data-stu-id="4d851-110">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="4d851-111">呼叫阻止管理员控制和信息</span><span class="sxs-lookup"><span data-stu-id="4d851-111">Call blocking admin controls and information</span></span>

<span data-ttu-id="4d851-112">阻止号码的管理员控制仅使用 PowerShell 提供。</span><span class="sxs-lookup"><span data-stu-id="4d851-112">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="4d851-113">数字块模式定义为正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="4d851-113">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="4d851-114">表达式的顺序是不重要的-列表中的第一个模式将导致调用被阻止。</span><span class="sxs-lookup"><span data-stu-id="4d851-114">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="4d851-115">在 "阻止的呼叫者" 列表中添加或删除的新号码或图案可能需要长达24小时才能使模式变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="4d851-115">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="4d851-116">呼叫阻止 PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="4d851-116">Call blocking PowerShell commands</span></span>

<span data-ttu-id="4d851-117">你可以使用**新**的、**获取**、**设置**、**删除**  - **CsInboundBlockedNumberPattern** cmdlet 管理数字模式。</span><span class="sxs-lookup"><span data-stu-id="4d851-117">You manage number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="4d851-118">你可以使用这些 cmdlet 管理给定模式，包括切换给定模式的激活的功能。</span><span class="sxs-lookup"><span data-stu-id="4d851-118">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="4d851-119">[CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern)返回添加到租户列表的所有阻止的数字模式的列表，包括名称、说明、已启用 (True/False) 和模式。</span><span class="sxs-lookup"><span data-stu-id="4d851-119">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="4d851-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern)将阻止的数字模式添加到租户列表。</span><span class="sxs-lookup"><span data-stu-id="4d851-120">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="4d851-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern)从租户列表中删除阻止的数字模式。</span><span class="sxs-lookup"><span data-stu-id="4d851-121">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="4d851-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern)修改租户列表中被阻止的数字模式的一个或多个参数。</span><span class="sxs-lookup"><span data-stu-id="4d851-122">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="4d851-123">查看和激活整个呼叫阻止功能是通过**Get**、 **Set**  - **CsTenantBlockingCallingNumbers** cmdlet 进行管理的。</span><span class="sxs-lookup"><span data-stu-id="4d851-123">Viewing and activating the entire call blocking feature is managed through the **Get**, **Set** -**CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="4d851-124">[CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers)返回全局被阻止的号码列表的参数，其中包括已启用 (True/False) 。</span><span class="sxs-lookup"><span data-stu-id="4d851-124">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="4d851-125">只有在打开或关闭该功能时，才能手动修改单个全局租户策略。</span><span class="sxs-lookup"><span data-stu-id="4d851-125">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="4d851-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers)允许将全局租户阻止的通话修改为在租户级别启用和禁用。</span><span class="sxs-lookup"><span data-stu-id="4d851-126">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="4d851-127">示例</span><span class="sxs-lookup"><span data-stu-id="4d851-127">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="4d851-128">阻止号码</span><span class="sxs-lookup"><span data-stu-id="4d851-128">Block a number</span></span>

<span data-ttu-id="4d851-129">在此示例中，"**已启用**" 和 "**说明**" 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="4d851-129">In this example, the **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="4d851-130">创建新模式会将模式添加为默认启用。</span><span class="sxs-lookup"><span data-stu-id="4d851-130">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="4d851-131">说明是提供详细信息的可选字段。</span><span class="sxs-lookup"><span data-stu-id="4d851-131">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="4d851-132">我们建议你提供一个有意义的名称，以便轻松了解添加模式的原因。</span><span class="sxs-lookup"><span data-stu-id="4d851-132">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="4d851-133">如果只是阻止垃圾邮件号码，请考虑将规则命名为与正在匹配的数字模式相同，并根据需要在描述中添加其他信息。</span><span class="sxs-lookup"><span data-stu-id="4d851-133">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="4d851-134">使用正则表达式 (Regex) 匹配模式。</span><span class="sxs-lookup"><span data-stu-id="4d851-134">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="4d851-135">在测试和验证之前，留出复制时间。</span><span class="sxs-lookup"><span data-stu-id="4d851-135">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="4d851-136">允许数字</span><span class="sxs-lookup"><span data-stu-id="4d851-136">Allow a number</span></span>

<span data-ttu-id="4d851-137">在此示例中，需要**标识**参数。</span><span class="sxs-lookup"><span data-stu-id="4d851-137">In this example, the **Identity** parameter is required.</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="4d851-138">如果身份未知，请使用**CsInboundBlockedNumberPattern** cmdlet 首先找到正确的模式，并记下标识。</span><span class="sxs-lookup"><span data-stu-id="4d851-138">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="4d851-139">然后，运行 CsTenantBlockedNumberPattern cmdlet 并传递相应**的**标识值。</span><span class="sxs-lookup"><span data-stu-id="4d851-139">Then, run the **Remove-CsTenantBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="4d851-140">在测试和验证之前，留出复制时间。</span><span class="sxs-lookup"><span data-stu-id="4d851-140">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="4d851-141">查看所有数字模式</span><span class="sxs-lookup"><span data-stu-id="4d851-141">View all number patterns</span></span>

<span data-ttu-id="4d851-142">运行此 cmdlet 将返回为租户输入的所有阻止号码的列表：</span><span class="sxs-lookup"><span data-stu-id="4d851-142">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="4d851-143">使用内置 PowerShell 筛选功能根据需要分析返回的值。</span><span class="sxs-lookup"><span data-stu-id="4d851-143">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="4d851-144">添加号码例外</span><span class="sxs-lookup"><span data-stu-id="4d851-144">Add number exceptions</span></span>

<span data-ttu-id="4d851-145">你可以使用 "**新建**"、"**获取**"、"**设置**" 和 "**删除**  - **CsTenantBlockNumberExceptionPattern** " cmdlet 将例外添加到阻止的数字模式。</span><span class="sxs-lookup"><span data-stu-id="4d851-145">You can add exceptions to blocked number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsTenantBlockNumberExceptionPattern** cmdlets.</span></span>

- <span data-ttu-id="4d851-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern)将数字异常模式添加到租户列表。</span><span class="sxs-lookup"><span data-stu-id="4d851-146">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="4d851-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern)返回添加到租户列表的所有数字异常模式的列表。</span><span class="sxs-lookup"><span data-stu-id="4d851-147">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="4d851-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern)将一个或多个参数修改为租户列表中的数字异常模式。</span><span class="sxs-lookup"><span data-stu-id="4d851-148">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="4d851-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern)从租户列表中删除数字异常模式。</span><span class="sxs-lookup"><span data-stu-id="4d851-149">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="4d851-150">示例</span><span class="sxs-lookup"><span data-stu-id="4d851-150">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="4d851-151">添加数字例外</span><span class="sxs-lookup"><span data-stu-id="4d851-151">Add a number exception</span></span>

<span data-ttu-id="4d851-152">在此示例中，创建新的数字异常模式，并将在默认情况下将模式添加为 "已启用"。</span><span class="sxs-lookup"><span data-stu-id="4d851-152">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="4d851-153">"**启用**" 和 "**说明**" 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="4d851-153">The **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="4d851-154">查看所有号码的例外情况</span><span class="sxs-lookup"><span data-stu-id="4d851-154">View all number exceptions</span></span>

<span data-ttu-id="4d851-155">在此示例中， **Identity**参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="4d851-155">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="4d851-156">如果未指定**Identity**参数，此 cmdlet 将返回为租户输入的所有数字异常模式的列表。</span><span class="sxs-lookup"><span data-stu-id="4d851-156">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="4d851-157">修改数字异常</span><span class="sxs-lookup"><span data-stu-id="4d851-157">Modify a number exception</span></span>

<span data-ttu-id="4d851-158">在此示例中， **Identity**参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="4d851-158">In this example, the **Identity** parameter is mandatory.</span></span> <span data-ttu-id="4d851-159">**CsTenantBlockedNumberExceptionPattern** cmdlet 允许你为给定的数字模式标识修改一个或多个参数。</span><span class="sxs-lookup"><span data-stu-id="4d851-159">The **Set-CsTenantBlockedNumberExceptionPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="4d851-160">删除数字异常</span><span class="sxs-lookup"><span data-stu-id="4d851-160">Remove a number exception</span></span>

<span data-ttu-id="4d851-161">在此示例中，需要**标识**参数。</span><span class="sxs-lookup"><span data-stu-id="4d851-161">In this example, the **Identity** parameter is required.</span></span> <span data-ttu-id="4d851-162">此 cmdlet 将从租户列表中删除给定的数字模式。</span><span class="sxs-lookup"><span data-stu-id="4d851-162">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="4d851-163">如果身份未知，请使用**CsInboundBlockedNumberPattern** cmdlet 首先找到正确的模式，并记下标识。</span><span class="sxs-lookup"><span data-stu-id="4d851-163">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="4d851-164">然后，运行 CsTenantBlockedNumberExceptionPattern cmdlet 并传递相应**的**标识值。</span><span class="sxs-lookup"><span data-stu-id="4d851-164">Then, run the **Remove-CsTenantBlockedNumberExceptionPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="4d851-165">在测试和验证之前，留出复制时间。</span><span class="sxs-lookup"><span data-stu-id="4d851-165"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="4d851-166">测试是否阻止了某个号码</span><span class="sxs-lookup"><span data-stu-id="4d851-166">Test whether a number is blocked</span></span>

<span data-ttu-id="4d851-167">使用**CsInboundBlockedNumberPattern** cmdlet 验证租户中的某个数字是否已被阻止。</span><span class="sxs-lookup"><span data-stu-id="4d851-167">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="4d851-168">在此示例中，需要**电话号码**和**租户**参数。</span><span class="sxs-lookup"><span data-stu-id="4d851-168">In this example, the **PhoneNumber** and **Tenant** parameters are required.</span></span> <span data-ttu-id="4d851-169">**电话号码**参数应为不带任何其他字符的数字字符串，如 + 或-。</span><span class="sxs-lookup"><span data-stu-id="4d851-169">The **PhoneNumber** parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="4d851-170">在 TRPS 中，**租户参数**是可选的。</span><span class="sxs-lookup"><span data-stu-id="4d851-170">In TRPS, the **Tenant parameter** is optional.</span></span> <span data-ttu-id="4d851-171">如果该数字在租户中被阻止，则所得到的**isNumberBlocked**参数将返回 True 值，如果该数字未被阻止，则返回 False。</span><span class="sxs-lookup"><span data-stu-id="4d851-171">The resulting **isNumberBlocked** parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="4d851-172">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="4d851-172">httpResponseCode</span></span>  |<span data-ttu-id="4d851-173">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="4d851-173">isNumberBlocked</span></span>   |<span data-ttu-id="4d851-174">errorMessage</span><span class="sxs-lookup"><span data-stu-id="4d851-174">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="4d851-175">200</span><span class="sxs-lookup"><span data-stu-id="4d851-175">200</span></span>    | <span data-ttu-id="4d851-176">True</span><span class="sxs-lookup"><span data-stu-id="4d851-176">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="4d851-177">httpResponseCode</span><span class="sxs-lookup"><span data-stu-id="4d851-177">httpResponseCode</span></span>  |<span data-ttu-id="4d851-178">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="4d851-178">isNumberBlocked</span></span>   |<span data-ttu-id="4d851-179">errorMessage</span><span class="sxs-lookup"><span data-stu-id="4d851-179">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="4d851-180">200</span><span class="sxs-lookup"><span data-stu-id="4d851-180">200</span></span>    | <span data-ttu-id="4d851-181">False</span><span class="sxs-lookup"><span data-stu-id="4d851-181">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="4d851-182">有关 Regex 的笔记</span><span class="sxs-lookup"><span data-stu-id="4d851-182">A note about Regex</span></span>

<span data-ttu-id="4d851-183">如前面所述，阻止调用方的模式匹配是使用 Regex 完成的。</span><span class="sxs-lookup"><span data-stu-id="4d851-183">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="4d851-184">可联机使用多个工具来帮助验证 Regex 模式匹配。</span><span class="sxs-lookup"><span data-stu-id="4d851-184">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="4d851-185">如果你不熟悉 Regex 模式，我们建议你花一些时间来熟悉基础知识。</span><span class="sxs-lookup"><span data-stu-id="4d851-185">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="4d851-186">若要确保获得预期的结果，请使用用于验证模式匹配的工具，然后再将新的阻止数字匹配添加到你的租户。</span><span class="sxs-lookup"><span data-stu-id="4d851-186">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>
