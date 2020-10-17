---
title: Lync Server 2013：测试拨号计划
description: Lync Server 2013：测试拨号计划。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ef2e3fce9d1fbbb0186b1b7aef608834145d3e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556168"
---
# <a name="testing-the-dial-plan-in-lync-server-2013"></a><span data-ttu-id="4d7cb-103">在 Lync Server 2013 中测试拨号计划</span><span class="sxs-lookup"><span data-stu-id="4d7cb-103">Testing the dial plan in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d7cb-104">_**上次修改的主题：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="4d7cb-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d7cb-105">验证计划</span><span class="sxs-lookup"><span data-stu-id="4d7cb-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="4d7cb-106">每天</span><span class="sxs-lookup"><span data-stu-id="4d7cb-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d7cb-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="4d7cb-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="4d7cb-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d7cb-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d7cb-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="4d7cb-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="4d7cb-110">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="4d7cb-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="4d7cb-111">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsDialPlan cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="4d7cb-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialPlan cmdlet.</span></span> <span data-ttu-id="4d7cb-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4d7cb-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="4d7cb-113">说明</span><span class="sxs-lookup"><span data-stu-id="4d7cb-113">Description</span></span>

<span data-ttu-id="4d7cb-114">使用 Test-CsDialPlan cmdlet，可以查看将拨号计划应用于给定电话号码的结果。</span><span class="sxs-lookup"><span data-stu-id="4d7cb-114">The Test-CsDialPlan cmdlet enables you to see the results of applying a dial plan to a given telephone number.</span></span> <span data-ttu-id="4d7cb-115">拨号计划提供的信息（如应用规范化规则的方式），使企业语音用户可以打电话。</span><span class="sxs-lookup"><span data-stu-id="4d7cb-115">Dial plans provide information, such as how normalization rules are applied, required to enable Enterprise Voice users to make telephone calls.</span></span> <span data-ttu-id="4d7cb-116">给定一个已拨电话和拨号计划，此 cmdlet 将验证应用该拨号计划中的哪个规范化规则以及转换后的号码是什么。</span><span class="sxs-lookup"><span data-stu-id="4d7cb-116">Given a dialed number and a dial plan, this cmdlet will verify which normalization rule within the dial plan will be applied and what the translated number will be.</span></span>

<span data-ttu-id="4d7cb-117">您可以使用此 cmdlet 对号码转换问题进行故障排除，或验证如何对特定号码应用规则。</span><span class="sxs-lookup"><span data-stu-id="4d7cb-117">You can use this cmdlet for troubleshooting issues with number translations, or for verifying how to apply rules against certain numbers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="4d7cb-118">运行测试</span><span class="sxs-lookup"><span data-stu-id="4d7cb-118">Running the test</span></span>

<span data-ttu-id="4d7cb-119">Test-CsDialPlan cmdlet 要求您执行两项操作。</span><span class="sxs-lookup"><span data-stu-id="4d7cb-119">The Test-CsDialPlan cmdlet requires you to do two things.</span></span> <span data-ttu-id="4d7cb-120">首先，您必须获取正在测试的拨号计划的实例;可以使用 Get-CsDialPlan cmdlet 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4d7cb-120">First, you must obtain an instance of the dial plan being tested; that can be done by using the Get-CsDialPlan cmdlet.</span></span> <span data-ttu-id="4d7cb-121">其次，必须指定必须规范化的电话号码。</span><span class="sxs-lookup"><span data-stu-id="4d7cb-121">Second, you must specify the phone number that has to be normalized.</span></span> <span data-ttu-id="4d7cb-122">用于电话号码的格式应与用户拨打/输入的号码相匹配。</span><span class="sxs-lookup"><span data-stu-id="4d7cb-122">The format that is used for the phone number should match the number as dialed/entered by a user.</span></span> <span data-ttu-id="4d7cb-123">例如，此命令检索 RedmondDialPlan 的拨号计划实例，并检查电话号码12065551219是否可以规范化：</span><span class="sxs-lookup"><span data-stu-id="4d7cb-123">For example, this command retrieves an instance of the dial plan, RedmondDialPlan, and checks whether the phone number 12065551219 can be normalized:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

<span data-ttu-id="4d7cb-124">如果您有一个在此示例中自动添加国家/地区代码 (的规范化规则，则 1) ，区号 (206) ，那么您可能需要检查电话号码5551219，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4d7cb-124">If you have a normalization rule that automatically adds the country code (in this example, 1) and the area code (206), then you might want to check the phone number 5551219, as follows:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

<span data-ttu-id="4d7cb-125">有关详细信息，请参阅 [grant-csdialplan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="4d7cb-125">For more information, see the Help documentation for the [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="4d7cb-126">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="4d7cb-126">Determining success or failure</span></span>

<span data-ttu-id="4d7cb-127">Test-CsDialPlan 与许多 Lync Server 测试 cmdlet 不同，因为它仅间接指示测试是成功还是失败。</span><span class="sxs-lookup"><span data-stu-id="4d7cb-127">Test-CsDialPlan differs from many of the Lync Server test cmdlets because it only indirectly indicates whether a test succeeded or failed.</span></span> <span data-ttu-id="4d7cb-128">使用 Test-CsDialPlan 时，您不会收到与以下内容类似的返回输出结果，并对结果进行了明确标记：</span><span class="sxs-lookup"><span data-stu-id="4d7cb-128">When using Test-CsDialPlan you do not receive back output similar to this with the Result clearly labeled:</span></span>

<span data-ttu-id="4d7cb-129">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4d7cb-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4d7cb-130">结果：成功</span><span class="sxs-lookup"><span data-stu-id="4d7cb-130">Result : Success</span></span>

<span data-ttu-id="4d7cb-131">延迟：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="4d7cb-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="4d7cb-132">误差</span><span class="sxs-lookup"><span data-stu-id="4d7cb-132">Error :</span></span>

<span data-ttu-id="4d7cb-133">诊断</span><span class="sxs-lookup"><span data-stu-id="4d7cb-133">Diagnosis :</span></span>

<span data-ttu-id="4d7cb-134">相反，如果 Test-CsDialPlan 成功，则您将收到能够成功转换和使用指定电话号码的规范化规则的相关信息：</span><span class="sxs-lookup"><span data-stu-id="4d7cb-134">Instead, if Test-CsDialPlan succeeds, then you'll receive information about the normalization rule that was able to successfully translate and use the specified phone number:</span></span>

<span data-ttu-id="4d7cb-135">TranslatedNumber： + 12065551219</span><span class="sxs-lookup"><span data-stu-id="4d7cb-135">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="4d7cb-136">MatchingRule： Description =;模式 = ^ (\\ d (11) # B3 $;转换 = + $ 1;</span><span class="sxs-lookup"><span data-stu-id="4d7cb-136">MatchingRule : Description=;Pattern=^(\\d(11))$;Translation=+$1;</span></span>

<span data-ttu-id="4d7cb-137">Name = Prefix All;IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="4d7cb-137">Name=Prefix All; IsInternalExtension=False</span></span>

<span data-ttu-id="4d7cb-138">如果 Test-CsDialPlan 失败 (也就是说，如果拨号计划没有可将指定的电话号码转换) 的规范化规则，您将只收到如下所示的 "空" 输出：</span><span class="sxs-lookup"><span data-stu-id="4d7cb-138">If Test-CsDialPlan fails (that is, if the dial plan does not have a normalization rule that can translate the specified phone number), you'll just receive “empty” output as follows:</span></span>

<span data-ttu-id="4d7cb-139">TranslatedNumber :</span><span class="sxs-lookup"><span data-stu-id="4d7cb-139">TranslatedNumber :</span></span>

<span data-ttu-id="4d7cb-140">MatchingRule :</span><span class="sxs-lookup"><span data-stu-id="4d7cb-140">MatchingRule :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="4d7cb-141">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="4d7cb-141">Reasons why the test might have failed</span></span>

<span data-ttu-id="4d7cb-142">下面是 Test-CsDialPlan 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="4d7cb-142">Here are some common reasons why Test-CsDialPlan might fail:</span></span>

  - <span data-ttu-id="4d7cb-143">在指定电话号码时，可能使用了不正确的格式。</span><span class="sxs-lookup"><span data-stu-id="4d7cb-143">You might have used an incorrect format when specifying the phone number.</span></span> <span data-ttu-id="4d7cb-144">拨号计划包括使 Lync Server 能够转换用户拨打或输入的电话号码的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="4d7cb-144">Dial plans include normalization rules that enable Lync Server to translate the phone numbers dialed or entered by a user.</span></span> <span data-ttu-id="4d7cb-145">因此，您的拨号计划应具有与用户可能拨打的号码相匹配的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="4d7cb-145">Therefore, your dial plan should have normalization rules that match the numbers users are likely to dial.</span></span> <span data-ttu-id="4d7cb-146">例如，如果用户可能拨打国家/地区代码、区号和电话号码本身，则意味着您的拨号计划应具有用于处理电话号码的规范化规则，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4d7cb-146">For example, if users might dial the country code, area code, and then the phone number itself, that means that your dial plan should have a normalization rule to handle phone numbers such as this:</span></span>
    
    <span data-ttu-id="4d7cb-147">12065551219</span><span class="sxs-lookup"><span data-stu-id="4d7cb-147">12065551219</span></span>
    
    <span data-ttu-id="4d7cb-148">但是，如果输入不正确的电话号码 (例如，不使用最后的数字) ，Test-CsDialPlan 将失败。</span><span class="sxs-lookup"><span data-stu-id="4d7cb-148">However, if you enter an incorrect phone number (for example, leaving off the final digit), then Test-CsDialPlan will fail.</span></span> <span data-ttu-id="4d7cb-149">这是因为拨号计划有问题，但您输入的电话号码不是无法解释的。</span><span class="sxs-lookup"><span data-stu-id="4d7cb-149">That’s not because the dial plan is faulty but because you have entered a phone number than can’t be interpreted.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

