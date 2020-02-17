---
title: Lync Server 2013：测试拨号计划
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
ms.openlocfilehash: 4c35d204a8a3fa16ff38dbcce89c0c8f36da2039
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a><span data-ttu-id="a2ed5-102">在 Lync Server 2013 中测试拨号计划</span><span class="sxs-lookup"><span data-stu-id="a2ed5-102">Testing the dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2ed5-103">_**上次修改的主题：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="a2ed5-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2ed5-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="a2ed5-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a2ed5-105">每天</span><span class="sxs-lookup"><span data-stu-id="a2ed5-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2ed5-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="a2ed5-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a2ed5-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2ed5-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2ed5-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="a2ed5-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a2ed5-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="a2ed5-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a2ed5-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Grant-csdialplan cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="a2ed5-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialPlan cmdlet.</span></span> <span data-ttu-id="a2ed5-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a2ed5-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a2ed5-112">描述</span><span class="sxs-lookup"><span data-stu-id="a2ed5-112">Description</span></span>

<span data-ttu-id="a2ed5-113">Grant-csdialplan cmdlet 使您能够查看将拨号计划应用于给定电话号码的结果。</span><span class="sxs-lookup"><span data-stu-id="a2ed5-113">The Test-CsDialPlan cmdlet enables you to see the results of applying a dial plan to a given telephone number.</span></span> <span data-ttu-id="a2ed5-114">拨号计划提供的信息（如应用规范化规则的方式），使企业语音用户可以打电话。</span><span class="sxs-lookup"><span data-stu-id="a2ed5-114">Dial plans provide information, such as how normalization rules are applied, required to enable Enterprise Voice users to make telephone calls.</span></span> <span data-ttu-id="a2ed5-115">给定一个已拨电话和拨号计划，此 cmdlet 将验证应用该拨号计划中的哪个规范化规则以及转换后的号码是什么。</span><span class="sxs-lookup"><span data-stu-id="a2ed5-115">Given a dialed number and a dial plan, this cmdlet will verify which normalization rule within the dial plan will be applied and what the translated number will be.</span></span>

<span data-ttu-id="a2ed5-116">您可以使用此 cmdlet 对号码转换问题进行故障排除，或验证如何对特定号码应用规则。</span><span class="sxs-lookup"><span data-stu-id="a2ed5-116">You can use this cmdlet for troubleshooting issues with number translations, or for verifying how to apply rules against certain numbers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a2ed5-117">运行测试</span><span class="sxs-lookup"><span data-stu-id="a2ed5-117">Running the test</span></span>

<span data-ttu-id="a2ed5-118">Grant-csdialplan cmdlet 要求您执行两项操作。</span><span class="sxs-lookup"><span data-stu-id="a2ed5-118">The Test-CsDialPlan cmdlet requires you to do two things.</span></span> <span data-ttu-id="a2ed5-119">首先，您必须获取正在测试的拨号计划的实例;可以使用 Grant-csdialplan cmdlet 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a2ed5-119">First, you must obtain an instance of the dial plan being tested; that can be done by using the Get-CsDialPlan cmdlet.</span></span> <span data-ttu-id="a2ed5-120">其次，必须指定必须规范化的电话号码。</span><span class="sxs-lookup"><span data-stu-id="a2ed5-120">Second, you must specify the phone number that has to be normalized.</span></span> <span data-ttu-id="a2ed5-121">用于电话号码的格式应与用户拨打/输入的号码相匹配。</span><span class="sxs-lookup"><span data-stu-id="a2ed5-121">The format that is used for the phone number should match the number as dialed/entered by a user.</span></span> <span data-ttu-id="a2ed5-122">例如，此命令检索 RedmondDialPlan 的拨号计划实例，并检查电话号码12065551219是否可以规范化：</span><span class="sxs-lookup"><span data-stu-id="a2ed5-122">For example, this command retrieves an instance of the dial plan, RedmondDialPlan, and checks whether the phone number 12065551219 can be normalized:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

<span data-ttu-id="a2ed5-123">如果您具有自动添加国家/地区代码（在此示例中为1）和区号（206）的规范化规则，则您可能需要检查电话号码5551219，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a2ed5-123">If you have a normalization rule that automatically adds the country code (in this example, 1) and the area code (206), then you might want to check the phone number 5551219, as follows:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

<span data-ttu-id="a2ed5-124">有关详细信息，请参阅[grant-csdialplan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="a2ed5-124">For more information, see the Help documentation for the [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a2ed5-125">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="a2ed5-125">Determining success or failure</span></span>

<span data-ttu-id="a2ed5-126">Grant-csdialplan 与许多 Lync Server 测试 cmdlet 不同，因为它仅间接指示测试是成功还是失败。</span><span class="sxs-lookup"><span data-stu-id="a2ed5-126">Test-CsDialPlan differs from many of the Lync Server test cmdlets because it only indirectly indicates whether a test succeeded or failed.</span></span> <span data-ttu-id="a2ed5-127">使用 Grant-csdialplan 时，您不会收到类似于以下内容的返回输出，结果标记为 "已明确标记"：</span><span class="sxs-lookup"><span data-stu-id="a2ed5-127">When using Test-CsDialPlan you do not receive back output similar to this with the Result clearly labeled:</span></span>

<span data-ttu-id="a2ed5-128">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a2ed5-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a2ed5-129">结果：成功</span><span class="sxs-lookup"><span data-stu-id="a2ed5-129">Result : Success</span></span>

<span data-ttu-id="a2ed5-130">延迟：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="a2ed5-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="a2ed5-131">误差</span><span class="sxs-lookup"><span data-stu-id="a2ed5-131">Error :</span></span>

<span data-ttu-id="a2ed5-132">诊断</span><span class="sxs-lookup"><span data-stu-id="a2ed5-132">Diagnosis :</span></span>

<span data-ttu-id="a2ed5-133">相反，如果 Grant-csdialplan 成功，则您将收到能够成功转换和使用指定电话号码的规范化规则的相关信息：</span><span class="sxs-lookup"><span data-stu-id="a2ed5-133">Instead, if Test-CsDialPlan succeeds, then you'll receive information about the normalization rule that was able to successfully translate and use the specified phone number:</span></span>

<span data-ttu-id="a2ed5-134">TranslatedNumber： + 12065551219</span><span class="sxs-lookup"><span data-stu-id="a2ed5-134">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="a2ed5-135">MatchingRule： Description =;Pattern = ^ （\\d （11）） $;转换 = + $ 1;</span><span class="sxs-lookup"><span data-stu-id="a2ed5-135">MatchingRule : Description=;Pattern=^(\\d(11))$;Translation=+$1;</span></span>

<span data-ttu-id="a2ed5-136">Name = Prefix All;IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="a2ed5-136">Name=Prefix All; IsInternalExtension=False</span></span>

<span data-ttu-id="a2ed5-137">如果测试 Grant-csdialplan 失败（即，如果拨号计划没有可以转换指定电话号码的规范化规则），您将只收到如下所示的 "空" 输出：</span><span class="sxs-lookup"><span data-stu-id="a2ed5-137">If Test-CsDialPlan fails (that is, if the dial plan does not have a normalization rule that can translate the specified phone number), you'll just receive “empty” output as follows:</span></span>

<span data-ttu-id="a2ed5-138">TranslatedNumber :</span><span class="sxs-lookup"><span data-stu-id="a2ed5-138">TranslatedNumber :</span></span>

<span data-ttu-id="a2ed5-139">MatchingRule :</span><span class="sxs-lookup"><span data-stu-id="a2ed5-139">MatchingRule :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a2ed5-140">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="a2ed5-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="a2ed5-141">以下是测试 Grant-csdialplan 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="a2ed5-141">Here are some common reasons why Test-CsDialPlan might fail:</span></span>

  - <span data-ttu-id="a2ed5-142">在指定电话号码时，可能使用了不正确的格式。</span><span class="sxs-lookup"><span data-stu-id="a2ed5-142">You might have used an incorrect format when specifying the phone number.</span></span> <span data-ttu-id="a2ed5-143">拨号计划包括使 Lync Server 能够转换用户拨打或输入的电话号码的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="a2ed5-143">Dial plans include normalization rules that enable Lync Server to translate the phone numbers dialed or entered by a user.</span></span> <span data-ttu-id="a2ed5-144">因此，您的拨号计划应具有与用户可能拨打的号码相匹配的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="a2ed5-144">Therefore, your dial plan should have normalization rules that match the numbers users are likely to dial.</span></span> <span data-ttu-id="a2ed5-145">例如，如果用户可能拨打国家/地区代码、区号和电话号码本身，则意味着您的拨号计划应具有用于处理电话号码的规范化规则，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a2ed5-145">For example, if users might dial the country code, area code, and then the phone number itself, that means that your dial plan should have a normalization rule to handle phone numbers such as this:</span></span>
    
    <span data-ttu-id="a2ed5-146">12065551219</span><span class="sxs-lookup"><span data-stu-id="a2ed5-146">12065551219</span></span>
    
    <span data-ttu-id="a2ed5-147">但是，如果输入错误的电话号码（例如，不使用最后的数字），则 Grant-csdialplan 将失败。</span><span class="sxs-lookup"><span data-stu-id="a2ed5-147">However, if you enter an incorrect phone number (for example, leaving off the final digit), then Test-CsDialPlan will fail.</span></span> <span data-ttu-id="a2ed5-148">这是因为拨号计划有问题，但您输入的电话号码不是无法解释的。</span><span class="sxs-lookup"><span data-stu-id="a2ed5-148">That’s not because the dial plan is faulty but because you have entered a phone number than can’t be interpreted.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

