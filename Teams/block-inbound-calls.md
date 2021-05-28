---
title: 阻止传入Microsoft Teams
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
ms.openlocfilehash: e584e9f0c16ef77424121c37ce87c6d63afb4b92
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689760"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="a70a9-102">阻止入站呼叫</span><span class="sxs-lookup"><span data-stu-id="a70a9-102">Block inbound calls</span></span>

<span data-ttu-id="a70a9-103">Microsoft 呼叫计划、直接路由和接线员连接都支持阻止来自 PSTN 呼叫的公共 (呼叫) 。</span><span class="sxs-lookup"><span data-stu-id="a70a9-103">Microsoft Calling Plans, Direct Routing, and Operator Connect all support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="a70a9-104">此功能允许管理员在租户全局级别定义号码模式列表，以便可以针对列表检查每个传入到租户的 PSTN 呼叫的来电显示是否匹配。</span><span class="sxs-lookup"><span data-stu-id="a70a9-104">This feature allows an administrator to define a  list of number patterns at the tenant global level so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="a70a9-105">如果进行了匹配，则拒绝传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="a70a9-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="a70a9-106">此入站呼叫阻止功能仅适用于源自 PSTN 的入站呼叫，并且仅适用于租户全局级别。</span><span class="sxs-lookup"><span data-stu-id="a70a9-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant global level.</span></span> <span data-ttu-id="a70a9-107">单个Teams用户无法操作此列表。</span><span class="sxs-lookup"><span data-stu-id="a70a9-107">Individual Teams users can’t manipulate this list.</span></span> <span data-ttu-id="a70a9-108">客户端Teams允许单个用户阻止 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="a70a9-108">The Teams client does allow individual users to block PSTN calls.</span></span> <span data-ttu-id="a70a9-109">有关最终用户如何实现呼叫阻止的信息，请参阅在 Teams 中[管理呼叫设置](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)。</span><span class="sxs-lookup"><span data-stu-id="a70a9-109">For information about how your end users can implement call blocking, see [Manage call settings in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span>

>[!NOTE]
> <span data-ttu-id="a70a9-110">被阻止的呼叫者在被阻止时可能遇到略有不同的行为。</span><span class="sxs-lookup"><span data-stu-id="a70a9-110">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="a70a9-111">行为基于被阻止呼叫者的运营商如何处理不允许成功完成呼叫的通知。</span><span class="sxs-lookup"><span data-stu-id="a70a9-111">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="a70a9-112">示例可能包括运营商消息，指出无法将呼叫作为已拨入完成，或只是删除呼叫。</span><span class="sxs-lookup"><span data-stu-id="a70a9-112">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="a70a9-113">呼叫阻止管理员控件和信息</span><span class="sxs-lookup"><span data-stu-id="a70a9-113">Call blocking admin controls and information</span></span>

<span data-ttu-id="a70a9-114">阻止号码的管理员控件仅使用 PowerShell 提供。</span><span class="sxs-lookup"><span data-stu-id="a70a9-114">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="a70a9-115">数字块模式定义为正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="a70a9-115">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="a70a9-116">表达式的顺序不重要 – 列表中匹配的第一个模式会导致调用被阻止。</span><span class="sxs-lookup"><span data-stu-id="a70a9-116">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="a70a9-117">在阻止的呼叫者列表中添加或删除的新号码或模式可能需要多达 24 小时才能激活模式。</span><span class="sxs-lookup"><span data-stu-id="a70a9-117">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="a70a9-118">调用阻止 PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="a70a9-118">Call blocking PowerShell commands</span></span>

<span data-ttu-id="a70a9-119">使用 New-、Get-、Set-和 **Remove-CsInboundBlockedNumberPattern** cmdlet 管理数字模式。  </span><span class="sxs-lookup"><span data-stu-id="a70a9-119">You manage number patterns by using the **New-**, **Get-**, **Set-**, and **Remove-CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="a70a9-120">可以使用这些 cmdlet 管理给定的模式，包括切换给定模式的激活。</span><span class="sxs-lookup"><span data-stu-id="a70a9-120">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="a70a9-121">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) 返回添加到租户列表的所有阻止数字模式的列表，包括名称、说明、已启用 (True/False) 和每个模式。</span><span class="sxs-lookup"><span data-stu-id="a70a9-121">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="a70a9-122">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) 将阻止的编号模式添加到租户列表。</span><span class="sxs-lookup"><span data-stu-id="a70a9-122">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="a70a9-123">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) 从租户列表中删除阻止的编号模式。</span><span class="sxs-lookup"><span data-stu-id="a70a9-123">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="a70a9-124">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) 修改租户列表中的阻止数字模式的一个或多个参数。</span><span class="sxs-lookup"><span data-stu-id="a70a9-124">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="a70a9-125">通过 **Get-** 和 **Set-CsTenantBlockingCallingNumbers** cmdlet 管理查看和激活整个呼叫阻止功能。</span><span class="sxs-lookup"><span data-stu-id="a70a9-125">Viewing and activating the entire call blocking feature is managed through the **Get-** and **Set-CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="a70a9-126">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) 返回全局阻止编号列表的入站块数模式和入站豁免编号模式参数。</span><span class="sxs-lookup"><span data-stu-id="a70a9-126">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the inbound block number patterns and the inbound exempt number patterns parameters for the global blocked number list.</span></span> <span data-ttu-id="a70a9-127">此 cmdlet 还会返回阻止是否已启用 (True 或 False) 。</span><span class="sxs-lookup"><span data-stu-id="a70a9-127">This cmdlet also returns whether blocking has been Enabled (True or False).</span></span> <span data-ttu-id="a70a9-128">只有打开或关闭该功能，才能手动修改单个全局租户策略。</span><span class="sxs-lookup"><span data-stu-id="a70a9-128">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="a70a9-129">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) 允许修改在租户级别打开和关闭全局租户阻止的调用。</span><span class="sxs-lookup"><span data-stu-id="a70a9-129">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="a70a9-130">示例</span><span class="sxs-lookup"><span data-stu-id="a70a9-130">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="a70a9-131">阻止号码</span><span class="sxs-lookup"><span data-stu-id="a70a9-131">Block a number</span></span>

<span data-ttu-id="a70a9-132">在下面的示例中，租户管理员希望阻止来自号码范围 1 (312) 555-0000 到 1 (312) 555-9999 的所有调用。</span><span class="sxs-lookup"><span data-stu-id="a70a9-132">In the following example, the tenant administrator wants to block all calls coming from the number range 1 (312) 555-0000 to 1 (312) 555-9999.</span></span> <span data-ttu-id="a70a9-133">创建数字模式，以便匹配范围中带 + 前缀的数字和范围中不带 + 前缀的数字。</span><span class="sxs-lookup"><span data-stu-id="a70a9-133">The number pattern is created so that both numbers in range with + prefixed and numbers in the range without + prefixed are matched.</span></span> <span data-ttu-id="a70a9-134">你不需要在电话号码中包括符号和 () ，因为系统在匹配之前会剥离这些符号。</span><span class="sxs-lookup"><span data-stu-id="a70a9-134">You don’t need to include the symbols – and () in the phone numbers because the system strips these symbols before matching.</span></span>  <span data-ttu-id="a70a9-135">若要启用数字模式，Enabled **参数设置为** True。</span><span class="sxs-lookup"><span data-stu-id="a70a9-135">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span> <span data-ttu-id="a70a9-136">若要禁用此特定数字模式，将 参数设置为 False。</span><span class="sxs-lookup"><span data-stu-id="a70a9-136">To disable this specific number pattern, set the parameter to False.</span></span>

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

<span data-ttu-id="a70a9-137">下一示例中，租户管理员希望阻止来自 555-1234 (1) 1 的所有调用。</span><span class="sxs-lookup"><span data-stu-id="a70a9-137">In the next example, the tenant administrator wants to block all calls coming from the number 1 (412) 555-1234.</span></span> <span data-ttu-id="a70a9-138">若要启用数字模式，Enabled **参数设置为** True。</span><span class="sxs-lookup"><span data-stu-id="a70a9-138">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span>

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

<span data-ttu-id="a70a9-139">创建新模式会添加默认启用的模式。</span><span class="sxs-lookup"><span data-stu-id="a70a9-139">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="a70a9-140">说明是一个可选字段，用于提供详细信息。</span><span class="sxs-lookup"><span data-stu-id="a70a9-140">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="a70a9-141">我们建议提供一个有意义的名称，以便轻松了解添加模式的原因。</span><span class="sxs-lookup"><span data-stu-id="a70a9-141">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="a70a9-142">如果只是阻止垃圾邮件号码，请考虑将规则命名为与匹配的数字模式相同的规则，并根据需要在说明中添加其他信息。</span><span class="sxs-lookup"><span data-stu-id="a70a9-142">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="a70a9-143">模式使用正则表达式和正则表达式 (正则表达式) 。</span><span class="sxs-lookup"><span data-stu-id="a70a9-143">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="a70a9-144">有关详细信息，请参阅 [使用正则表达式](#using-regex)。</span><span class="sxs-lookup"><span data-stu-id="a70a9-144">For more information, see [Using Regex](#using-regex).</span></span>

<span data-ttu-id="a70a9-145">在测试和验证之前，请留出时间进行复制。</span><span class="sxs-lookup"><span data-stu-id="a70a9-145">Allow time for replication before you test and validate.</span></span> 

#### <a name="allow-a-number"></a><span data-ttu-id="a70a9-146">允许数字</span><span class="sxs-lookup"><span data-stu-id="a70a9-146">Allow a number</span></span>

<span data-ttu-id="a70a9-147">您可以通过删除阻止的号码模式来允许呼叫号码。</span><span class="sxs-lookup"><span data-stu-id="a70a9-147">You can allow a number to call by removing the blocked number pattern.</span></span> <span data-ttu-id="a70a9-148">在下面的示例中，租户管理员希望允许 1 (412) 555-1234 再次进行调用。</span><span class="sxs-lookup"><span data-stu-id="a70a9-148">In the following example, the tenant administrator wants to allow 1 (412) 555-1234 to make calls again.</span></span>

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
<span data-ttu-id="a70a9-149">如果标识未知，请使用 **Get-CsInboundBlockedNumberPattern** cmdlet 首先找到正确的模式并记下标识。</span><span class="sxs-lookup"><span data-stu-id="a70a9-149">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="a70a9-150">然后，运行 **Remove-CsInboundBlockedNumberPattern** cmdlet 并传递相应的标识值。</span><span class="sxs-lookup"><span data-stu-id="a70a9-150">Then, run the **Remove-CsInboundBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="a70a9-151">在测试和验证之前，请留出时间进行复制。</span><span class="sxs-lookup"><span data-stu-id="a70a9-151">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="a70a9-152">查看所有数字模式</span><span class="sxs-lookup"><span data-stu-id="a70a9-152">View all number patterns</span></span>

<span data-ttu-id="a70a9-153">运行此 cmdlet 会返回为租户输入的所有阻止号码的列表：</span><span class="sxs-lookup"><span data-stu-id="a70a9-153">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="a70a9-154">使用内置的 PowerShell 筛选功能可分析所需的返回值。</span><span class="sxs-lookup"><span data-stu-id="a70a9-154">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="a70a9-155">添加数字异常</span><span class="sxs-lookup"><span data-stu-id="a70a9-155">Add number exceptions</span></span>

<span data-ttu-id="a70a9-156">可以使用 **New-、Get-、Set-** 和 **Remove-CsInboundExemptNumberPattern** cmdlet 将异常添加到阻止的编号模式。  </span><span class="sxs-lookup"><span data-stu-id="a70a9-156">You can add exceptions to blocked number patterns by using the **New-**, **Get-**, **Set-**, and **Remove-CsInboundExemptNumberPattern** cmdlets.</span></span>

- <span data-ttu-id="a70a9-157">[New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) 将数字异常模式添加到租户列表。</span><span class="sxs-lookup"><span data-stu-id="a70a9-157">[New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="a70a9-158">[Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) 返回添加到租户列表的所有数字异常模式的列表。</span><span class="sxs-lookup"><span data-stu-id="a70a9-158">[Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="a70a9-159">[Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) 将一个或多个参数修改为租户列表中的数字异常模式。</span><span class="sxs-lookup"><span data-stu-id="a70a9-159">[Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="a70a9-160">[Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) 从租户列表中删除数字异常模式。</span><span class="sxs-lookup"><span data-stu-id="a70a9-160">[Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="a70a9-161">示例</span><span class="sxs-lookup"><span data-stu-id="a70a9-161">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="a70a9-162">添加数字异常</span><span class="sxs-lookup"><span data-stu-id="a70a9-162">Add a number exception</span></span>

<span data-ttu-id="a70a9-163">在下面的示例中，租户管理员希望允许电话号码 1 (312) 555-8882 和 1 (312) 555-8883 向租户拨打电话，即使这两个电话号码位于上述示例中阻止的范围内。</span><span class="sxs-lookup"><span data-stu-id="a70a9-163">In the following example, the tenant administrator wants to allow the phone numbers 1 (312) 555-8882 and 1 (312) 555-8883 to make calls to the tenant, even if these two phone numbers are in the range that has been blocked in the example above.</span></span> <span data-ttu-id="a70a9-164">若要启用此功能，将创建一个新的数字异常模式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a70a9-164">To enable this, a new number exception pattern is created as follows:</span></span>

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

<span data-ttu-id="a70a9-165">若要启用数字模式，Enabled **参数设置为** True。</span><span class="sxs-lookup"><span data-stu-id="a70a9-165">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span> <span data-ttu-id="a70a9-166">若要禁用此特定数字模式，将 参数设置为 False。</span><span class="sxs-lookup"><span data-stu-id="a70a9-166">To disable this specific number pattern, set the parameter to False.</span></span>


#### <a name="view-all-number-exceptions"></a><span data-ttu-id="a70a9-167">查看所有数字异常</span><span class="sxs-lookup"><span data-stu-id="a70a9-167">View all number exceptions</span></span>

<span data-ttu-id="a70a9-168">本示例中的 **Identity** 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="a70a9-168">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="a70a9-169">如果 **未指定 Identity** 参数，此 cmdlet 将返回为租户输入的所有数字异常模式的列表。</span><span class="sxs-lookup"><span data-stu-id="a70a9-169">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```
 
```powershell
Get-CsInboundExemptNumberPattern 
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="a70a9-170">修改数字异常</span><span class="sxs-lookup"><span data-stu-id="a70a9-170">Modify a number exception</span></span>

<span data-ttu-id="a70a9-171">**Set-CsInboundExemptNumberPattern** cmdlet 允许修改给定数字模式标识的一个或多个参数。</span><span class="sxs-lookup"><span data-stu-id="a70a9-171">The **Set-CsInboundExemptNumberPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span> <span data-ttu-id="a70a9-172">此示例中 **，Identity** 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="a70a9-172">In this example, the **Identity** parameter is required.</span></span>
 
```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="a70a9-173">删除数字异常</span><span class="sxs-lookup"><span data-stu-id="a70a9-173">Remove a number exception</span></span>

<span data-ttu-id="a70a9-174">**Remove-CsInboundExemptNumberPattern** cmdlet 将删除租户列表中的给定数字模式。</span><span class="sxs-lookup"><span data-stu-id="a70a9-174">The **Remove-CsInboundExemptNumberPattern** cmdlet will remove the given number pattern from the tenant list.</span></span> <span data-ttu-id="a70a9-175">此示例中 **，Identity** 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="a70a9-175">In this example, the **Identity** parameter is required.</span></span> 

<span data-ttu-id="a70a9-176">如果标识未知，请使用 **Get-CsInboundExemptNumberPattern** cmdlet 首先找到正确的模式并记下标识。</span><span class="sxs-lookup"><span data-stu-id="a70a9-176">If the identity isn't known, use the **Get-CsInboundExemptNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="a70a9-177">然后，运行 **Remove-CsInboundExemptNumberPattern** cmdlet 并传递相应的标识值。</span><span class="sxs-lookup"><span data-stu-id="a70a9-177">Then, run the **Remove-CsInboundExemptNumberPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="a70a9-178">在测试和验证之前，请留出时间进行复制。</span><span class="sxs-lookup"><span data-stu-id="a70a9-178"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="a70a9-179">测试是否阻止了数字</span><span class="sxs-lookup"><span data-stu-id="a70a9-179">Test whether a number is blocked</span></span>

<span data-ttu-id="a70a9-180">使用 **Test-CsInboundBlockedNumberPattern** cmdlet 验证是否在租户中阻止了数字。</span><span class="sxs-lookup"><span data-stu-id="a70a9-180">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="a70a9-181">**PhoneNumber** 参数是必需的，应是不带任何其他字符的数字字符串，例如 +、- 或 () 。</span><span class="sxs-lookup"><span data-stu-id="a70a9-181">The **PhoneNumber** parameter is required, and should be a numeric string without any additional characters, such as +, - or ().</span></span> <span data-ttu-id="a70a9-182">如果租户中阻止了数字，则生成的 **IsNumberBlocked** 参数返回值为 True;参数返回 False（如果未阻止）。</span><span class="sxs-lookup"><span data-stu-id="a70a9-182">The resulting **IsNumberBlocked** parameter returns a value of True if the number is blocked in the tenant; the parameter returns False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a><span data-ttu-id="a70a9-183">示例</span><span class="sxs-lookup"><span data-stu-id="a70a9-183">Examples</span></span>

<span data-ttu-id="a70a9-184">在这些示例中，可以看到电话号码 1 (312) 555-8884 被阻止，因为它位于上述阻止范围内，而电话号码 1 (312) 555-8883 允许呼叫，因为它应该基于上面创建的豁免。</span><span class="sxs-lookup"><span data-stu-id="a70a9-184">In these examples you can see that the phone number 1 (312) 555-8884 is blocked as it should be due to it being in the blocked range above, while the phone number 1 (312) 555-8883 is allowed to call as it should be based on the exemption created above.</span></span>

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

## <a name="using-regex"></a><span data-ttu-id="a70a9-185">使用正则表达式</span><span class="sxs-lookup"><span data-stu-id="a70a9-185">Using Regex</span></span>

<span data-ttu-id="a70a9-186">阻止调用方的模式匹配通过使用正则表达式完成。</span><span class="sxs-lookup"><span data-stu-id="a70a9-186">The pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="a70a9-187">联机提供了多个工具来帮助验证正则表达式模式匹配。</span><span class="sxs-lookup"><span data-stu-id="a70a9-187">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="a70a9-188">如果不熟悉正则表达式模式，建议你花一些时间熟悉基础知识。</span><span class="sxs-lookup"><span data-stu-id="a70a9-188">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="a70a9-189">若要确保获得预期结果，在向租户添加新的阻止数字匹配之前，请使用验证模式匹配项的工具。</span><span class="sxs-lookup"><span data-stu-id="a70a9-189">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>