---
title: Lync Server 2013：测试语音配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9532327640be12351143632813d403edddf5c437
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a><span data-ttu-id="49d76-102">在 Lync Server 2013 中测试语音配置</span><span class="sxs-lookup"><span data-stu-id="49d76-102">Test voice configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49d76-103">_**主题上次修改时间：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="49d76-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49d76-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="49d76-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="49d76-105">每月</span><span class="sxs-lookup"><span data-stu-id="49d76-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49d76-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="49d76-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="49d76-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="49d76-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49d76-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="49d76-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="49d76-109">当使用 Lync Server 命令行管理程序在本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="49d76-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="49d76-110">使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsVoiceTestConfiguration cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="49d76-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceTestConfiguration cmdlet.</span></span> <span data-ttu-id="49d76-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="49d76-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="49d76-112">说明</span><span class="sxs-lookup"><span data-stu-id="49d76-112">Description</span></span>

<span data-ttu-id="49d76-113">Lync 服务器包括多个 Windows PowerShell cmdlet （如 CsVoiceRoute 和 CsVoicePolicy、Test New-cstrunkconfiguration），使你能够验证你的企业语音基础结构的各个部分-语音路线、语音政策、SIP 中继–按预期工作。</span><span class="sxs-lookup"><span data-stu-id="49d76-113">Lync Server includes several Windows PowerShell cmdlets (such as Test-CsVoiceRoute and Test-CsVoicePolicy, Test-CsTrunkConfiguration) that enable you to verify that the individual pieces of your Enterprise Voice infrastructure – voice routes, voice policies, SIP trunks – are working as expected.</span></span>

<span data-ttu-id="49d76-114">虽然对于所有单个部分都适用的企业语音，但这一点很重要：可以具有有效的语音路线、有效的语音策略和有效的 SIP 主干，但仍有用户无法拨打或接听电话。</span><span class="sxs-lookup"><span data-stu-id="49d76-114">While it’s important with Enterprise Voice that all the individual pieces work: it’s possible to have a valid voice route, a valid voice policy, and a valid SIP trunk, but still have users unable to make or receive phone calls.</span></span> <span data-ttu-id="49d76-115">因此，Lync 服务器还提供创建语音测试配置的功能。</span><span class="sxs-lookup"><span data-stu-id="49d76-115">Because of that, Lync Server also provides the ability to create voice test configurations.</span></span> <span data-ttu-id="49d76-116">语音测试配置表示常见的企业语音方案：您可以指定语音路线、语音政策和拨号计划等内容，然后验证这些个别项目是否能够协同工作，以便提供手机服务。</span><span class="sxs-lookup"><span data-stu-id="49d76-116">Voice test configurations represent common Enterprise Voice scenarios: you can specify such things as a voice route, a voice policy, and a dial plan, and then verify that those individual items are work able to work together to provide phone service.</span></span> <span data-ttu-id="49d76-117">此外，你可以在给定方案中验证你的预期。</span><span class="sxs-lookup"><span data-stu-id="49d76-117">In addition, you can validate your expectations in a given scenario.</span></span> <span data-ttu-id="49d76-118">例如，假设你希望拨入计划 A 和语音策略 B 的组合会导致呼叫通过语音路由 C 进行路由。您可以输入 "语音路由 C" 作为 ExpectedRoute。</span><span class="sxs-lookup"><span data-stu-id="49d76-118">For example, suppose that you expect that the combination of dial plan A and voice policy B would result in calls being routed over voice route C. You can enter voice route C as the ExpectedRoute.</span></span> <span data-ttu-id="49d76-119">运行测试时，如果未采用 "语音路由 C"，则测试将标记为 "已失败"。</span><span class="sxs-lookup"><span data-stu-id="49d76-119">When you run the test, if voice route C is not employed then the test will be marked as having failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="49d76-120">运行测试</span><span class="sxs-lookup"><span data-stu-id="49d76-120">Running the test</span></span>

<span data-ttu-id="49d76-121">在使用 Windows PowerShell 测试语音配置集合之前，必须首先使用 CsVoiceTestConfiguration cmdlet 检索这些配置设置的实例。</span><span class="sxs-lookup"><span data-stu-id="49d76-121">Before testing Voice configuration collections using Windows PowerShell, you must first use the Get-CsVoiceTestConfiguration cmdlet to retrieve an instance of these configuration settings.</span></span> <span data-ttu-id="49d76-122">然后，必须将该实例输送到 Test CsVoiceTestConfiguration。</span><span class="sxs-lookup"><span data-stu-id="49d76-122">That instance must then be piped to the Test-CsVoiceTestConfiguration.</span></span> <span data-ttu-id="49d76-123">例如：</span><span class="sxs-lookup"><span data-stu-id="49d76-123">For example:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="49d76-124">若要同时验证所有语音测试配置设置，请改用以下命令：</span><span class="sxs-lookup"><span data-stu-id="49d76-124">To validate all the voice test configuration settings at the same time, use this command instead:</span></span>

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

<span data-ttu-id="49d76-125">有关详细信息，请参阅 CsVoiceTestConfiguration cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="49d76-125">For more information, see the Help documentation for the Test-CsVoiceTestConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="49d76-126">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="49d76-126">Determining success or failure</span></span>

<span data-ttu-id="49d76-127">CsVoiceTestConfiguration cmdlet 报告测试是否失败，并提供有关每个成功测试的详细信息，例如翻译规则、语音路由和用于完成任务的 PSTN 使用：</span><span class="sxs-lookup"><span data-stu-id="49d76-127">The Test-CsVoiceTestConfiguration cmdlet reports whether a test failed or succeeded, and provides additional information about each successful test, such as the translation rule, voice route, and PSTN usage used to complete the task:</span></span>

<span data-ttu-id="49d76-128">结果：成功</span><span class="sxs-lookup"><span data-stu-id="49d76-128">Result:             Success</span></span>

<span data-ttu-id="49d76-129">TranslatedNumber： + 15551234</span><span class="sxs-lookup"><span data-stu-id="49d76-129">TranslatedNumber:   +15551234</span></span>

<span data-ttu-id="49d76-130">MatchingRule： Description =;模式 = ^ （\\d{4}） $;转换 = + 1\\d;Name = Test; IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="49d76-130">MatchingRule:       Description=;Pattern=^(\\d{4})$;Translation=+1\\d;Name=Test;IsInternalExtension=False</span></span>

<span data-ttu-id="49d76-131">FirstMatchingRoute：网站：雷德蒙</span><span class="sxs-lookup"><span data-stu-id="49d76-131">FirstMatchingRoute: site:Redmond</span></span>

<span data-ttu-id="49d76-132">MatchingUsage： Local</span><span class="sxs-lookup"><span data-stu-id="49d76-132">MatchingUsage:      Local</span></span>

<span data-ttu-id="49d76-133">如果测试失败，则结果报告为失败：</span><span class="sxs-lookup"><span data-stu-id="49d76-133">If the test fails then the result is reported as Fail:</span></span>

<span data-ttu-id="49d76-134">结果：失败</span><span class="sxs-lookup"><span data-stu-id="49d76-134">Result:             Fail</span></span>

<span data-ttu-id="49d76-135">TranslatedNumber:</span><span class="sxs-lookup"><span data-stu-id="49d76-135">TranslatedNumber:</span></span>   

<span data-ttu-id="49d76-136">FirstMatchingRoute:</span><span class="sxs-lookup"><span data-stu-id="49d76-136">FirstMatchingRoute:</span></span>

<span data-ttu-id="49d76-137">MatchingUsage:</span><span class="sxs-lookup"><span data-stu-id="49d76-137">MatchingUsage:</span></span>      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="49d76-138">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="49d76-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="49d76-139">由于语音测试配置测试将测试多个不同项目-包括语音策略、拨号计划、语音路由等，因此可能会导致测试失败的几个不同因素。</span><span class="sxs-lookup"><span data-stu-id="49d76-139">Because voice test configuration testing tests several different items – including voice policies, dial plans, voice routes, and so on – there are several different factors that could result in a failed test.</span></span> <span data-ttu-id="49d76-140">如果测试失败，您的第一步是使用 CsVoiceTestConfiguration cmdlet 查看配置设置本身：</span><span class="sxs-lookup"><span data-stu-id="49d76-140">If a test fails, your first step should be to review the configuration settings themselves by using the Get-CsVoiceTestConfiguration cmdlet:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

<span data-ttu-id="49d76-141">如果正确配置了设置，请在包含详细参数的同时重新运行测试：</span><span class="sxs-lookup"><span data-stu-id="49d76-141">If the settings seem to be configured correctly, re-run the test while including the Verbose parameter:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="49d76-142">详细参数将提供由 Test CsVoiceTestConfiguration 执行的每个操作的分步帐户，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="49d76-142">The Verbose parameter will provide a step-by-step account of each action taken by Test-CsVoiceTestConfiguration as shown in this example:</span></span>

<span data-ttu-id="49d76-143">详细：正在加载拨号计划： "Global"</span><span class="sxs-lookup"><span data-stu-id="49d76-143">VERBOSE: Loading dial plan: "Global"</span></span>

<span data-ttu-id="49d76-144">详细：加载语音策略： "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="49d76-144">VERBOSE: Loading voice policy: "RedmondDialPlan"</span></span>

<span data-ttu-id="49d76-145">此分步帐户可能会提供一个有用的线索，如测试实际失败的位置。</span><span class="sxs-lookup"><span data-stu-id="49d76-145">This step-by-step account might provide a useful clue as to where the test actually failed.</span></span> <span data-ttu-id="49d76-146">如果不是，则可以使用其他 Windows PowerShell cmdlet （如 Test-CsVoicePolicy），然后系统地开始验证语音测试配置设置中包含的单个组件。</span><span class="sxs-lookup"><span data-stu-id="49d76-146">If not, you can then use other Windows PowerShell cmdlets (such as Test-CsVoicePolicy) and methodically begin to verify the individual components that are included in the voice test configuration settings.</span></span>

<span data-ttu-id="49d76-147">此外，请注意，测试可以路由呼叫，但仍会将其标记为失败，但仍可这样做。如果输入 ExpectedRoute、ExpectedTranslatedNumber 和 ExpectedUsage 的值，并且不满足这些任何预期条件，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="49d76-147">In addition to that, be aware that it’s possible for a test to be able to route a call and yet still be marked as a failure; that can occur if you enter values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage, and any of those expectations are not met.</span></span> <span data-ttu-id="49d76-148">例如，假设您输入了 "语音路由 C" 作为预期的语音路线，但测试实际上是使用 "语音路由 D" 完成呼叫。在这种情况下，测试将标记为 "失败"，因为未使用预期的语音路由。</span><span class="sxs-lookup"><span data-stu-id="49d76-148">For example, suppose that you enter voice route C as your expected voice route, but the test actually completes the call using voice route D. In that case the test will be marked as Failed because the expected voice route was not used.</span></span> <span data-ttu-id="49d76-149">如果测试失败，你可以删除 ExpectedRoute、ExpectedTranslatedNumber 和 ExpectedUsage 的值，然后重新运行测试。</span><span class="sxs-lookup"><span data-stu-id="49d76-149">If a test fails, you might remove the values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage and then re-run the test.</span></span> <span data-ttu-id="49d76-150">这将帮助你确定失败是因为通话无法完成，还是你想要一件事并真的收到另一种情况。</span><span class="sxs-lookup"><span data-stu-id="49d76-150">That will help you determine whether the failure was because the call couldn't be completed, or because you expect one thing and actually received another.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="49d76-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49d76-151">See Also</span></span>


[<span data-ttu-id="49d76-152">Test-CsVoiceTestConfiguration</span><span class="sxs-lookup"><span data-stu-id="49d76-152">Test-CsVoiceTestConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

