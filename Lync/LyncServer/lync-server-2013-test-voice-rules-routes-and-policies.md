---
title: Lync Server 2013：测试语音规则、路由和策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbf04728db30bada37e43f14b33420ede1ce9258
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a><span data-ttu-id="c5f79-102">在 Lync Server 2013 中测试语音规则、路由和策略</span><span class="sxs-lookup"><span data-stu-id="c5f79-102">Test voice rules, routes, and policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5f79-103">_**上次修改的主题：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="c5f79-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5f79-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="c5f79-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c5f79-105">每月</span><span class="sxs-lookup"><span data-stu-id="c5f79-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5f79-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="c5f79-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c5f79-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5f79-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5f79-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="c5f79-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c5f79-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="c5f79-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c5f79-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsVoiceUser cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="c5f79-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceUser cmdlet.</span></span> <span data-ttu-id="c5f79-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c5f79-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c5f79-112">Description</span><span class="sxs-lookup"><span data-stu-id="c5f79-112">Description</span></span>

<span data-ttu-id="c5f79-113">当用户进行电话呼叫时，呼叫到达其目标所需的路由取决于分配给该用户的策略和拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c5f79-113">When a user makes a phone call, the route the call takes to reach its destination depends on both the policies and dial plans assigned to that user.</span></span> <span data-ttu-id="c5f79-114">在给定用户的 SIP 地址和电话号码的情况下，CsVoiceUser cmdlet 会验证相关用户是否可以完成对该号码的呼叫。</span><span class="sxs-lookup"><span data-stu-id="c5f79-114">Given a user’s SIP address and a phone number, the Test-CsVoiceUser cmdlet verifies whether the user in question can complete a call to that number.</span></span> <span data-ttu-id="c5f79-115">如果测试成功，CsVoiceUser 将返回以下内容：</span><span class="sxs-lookup"><span data-stu-id="c5f79-115">If the test succeeds, Test-CsVoiceUser returns the following:</span></span>

  - <span data-ttu-id="c5f79-116">转换为. 164 格式的数字（基于用户的拨号计划）</span><span class="sxs-lookup"><span data-stu-id="c5f79-116">The number translated to E.164 format (based on the user’s dial plan)</span></span>

  - <span data-ttu-id="c5f79-117">提供该转换的规范化规则</span><span class="sxs-lookup"><span data-stu-id="c5f79-117">The normalization rule that supplied that translation</span></span>

  - <span data-ttu-id="c5f79-118">使用的语音路由（基于路由优先级）;</span><span class="sxs-lookup"><span data-stu-id="c5f79-118">The voice route used (based on route priority);</span></span>

  - <span data-ttu-id="c5f79-119">将用户语音策略链接到语音路由的电话用法。</span><span class="sxs-lookup"><span data-stu-id="c5f79-119">The phone usage that linked the user’s voice policy to the voice route.</span></span>

<span data-ttu-id="c5f79-120">CsVoiceUser 使您能够确定特定的电话号码是否会按预期进行路由和转换，并可帮助解决单个用户遇到的与呼叫相关的问题。</span><span class="sxs-lookup"><span data-stu-id="c5f79-120">Test-CsVoiceUser enables you to determine whether a specific phone number will route and translate as expected, and can help troubleshoot call-related problems that are experienced by individual users.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c5f79-121">运行测试</span><span class="sxs-lookup"><span data-stu-id="c5f79-121">Running the test</span></span>

<span data-ttu-id="c5f79-122">运行 CsVoiceUser cmdlet 时，您必须提供以下两条信息：要拨打的号码（DialedNumber）和要测试的用户帐户的标识。</span><span class="sxs-lookup"><span data-stu-id="c5f79-122">When running the Test-CsVoiceUser cmdlet you must supply two pieces of information: the number being dialed (DialedNumber) and the Identity of the user account being tested.</span></span> <span data-ttu-id="c5f79-123">例如，以下命令将测试具有 SIP 地址 sip:kenmyer@litwareinc.com 的用户拨打电话号码 + 1206555-1219 的能力：</span><span class="sxs-lookup"><span data-stu-id="c5f79-123">For example, this command tests the ability of the user who has the SIP address sip:kenmyer@litwareinc.com to make a call to the phone number +1206555-1219:</span></span>

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

<span data-ttu-id="c5f79-124">电话号码的格式应设置为您希望拨打它的方式。</span><span class="sxs-lookup"><span data-stu-id="c5f79-124">The phone number should be formatted in the way that you expect it to be dialed.</span></span> <span data-ttu-id="c5f79-125">例如，如果用户在发出长途呼叫之前通常不拨打1，则应使用以下格式：</span><span class="sxs-lookup"><span data-stu-id="c5f79-125">For example, if users typically do not dial the 1 before placing a long distance call then you should use this format:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="c5f79-126">当然，在这种情况下，如果您没有可将数字2065551219正确转换为 Lync Server 使用的 e.164 电话格式的规范化规则，则测试将失败。</span><span class="sxs-lookup"><span data-stu-id="c5f79-126">Of course, in that case, the test will fail if you do not have a normalization rule that can correctly translate the number 2065551219 into the E.164 telephone format that is used by Lync Server.</span></span> <span data-ttu-id="c5f79-127">有关详细信息，请参阅帮助主题 CsVoiceNormalizationRule cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c5f79-127">For more information, see the help topic New-CsVoiceNormalizationRule cmdlet.</span></span>

<span data-ttu-id="c5f79-128">如果要对每个用户帐户运行此相同的测试，可以使用类似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="c5f79-128">If you want to run this same test against each of your user accounts, you can use a command similar to the following:</span></span>

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

<span data-ttu-id="c5f79-129">有关详细信息，请参阅 CsVoiceUser cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="c5f79-129">For more information, see the Help documentation for the Test-CsVoiceUser cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c5f79-130">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="c5f79-130">Determining success or failure</span></span>

<span data-ttu-id="c5f79-131">如果测试成功完成（即，如果用户可以拨打指定号码），则输出将显示与转换的电话号码、匹配的规范化规则和语音路由类似的信息：</span><span class="sxs-lookup"><span data-stu-id="c5f79-131">If the test is completed successfully (that is, if the user can make a phone call to the specified number), the output will show information like the translated phone number and the matching normalization rule and voice route:</span></span>

<span data-ttu-id="c5f79-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="c5f79-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span></span>

<span data-ttu-id="c5f79-133">\----------------    ------------    ------------------    -------------</span><span class="sxs-lookup"><span data-stu-id="c5f79-133">\----------------    ------------    ------------------    -------------</span></span>

<span data-ttu-id="c5f79-134">\+12065551219 Descripti .。。   LocalRoute 本地</span><span class="sxs-lookup"><span data-stu-id="c5f79-134">\+12065551219        Descripti...    LocalRoute            Local</span></span>

<span data-ttu-id="c5f79-135">由于 Windows PowerShell 屏幕的限制，至少一些返回的信息（尤其是匹配规范化规则的完整说明）可能不会在屏幕上显示。</span><span class="sxs-lookup"><span data-stu-id="c5f79-135">Because of the limitations of the Windows PowerShell screen, at least some returned information (most notably the full description of the matching normalization rule) might not appear on-screen.</span></span> <span data-ttu-id="c5f79-136">如果只对测试的成功或失败感兴趣，则可能无关紧要。</span><span class="sxs-lookup"><span data-stu-id="c5f79-136">If you are only interested in the success or failure of the test, then this might not matter.</span></span> <span data-ttu-id="c5f79-137">如果您想要查看返回数据的完整详细信息，请在运行测试时将输出通过管道传递给格式列表 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c5f79-137">If you would prefer to see the full details of the returned data then pipe the output to the Format-List cmdlet when running the test:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

<span data-ttu-id="c5f79-138">这将以更易于读取器的格式显示输出：</span><span class="sxs-lookup"><span data-stu-id="c5f79-138">That will display the output in a more reader-friendly format:</span></span>

<span data-ttu-id="c5f79-139">TranslatedNumber： + 12065551219</span><span class="sxs-lookup"><span data-stu-id="c5f79-139">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="c5f79-140">MatchingRule： Description =;模式 = ^ （\\d{11}） $;转换 = + $ 1;</span><span class="sxs-lookup"><span data-stu-id="c5f79-140">MatchingRule : Description=;Pattern=^(\\d{11})$;Translation=+$1;</span></span>

<span data-ttu-id="c5f79-141">Name = Prefix All; IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="c5f79-141">Name=Prefix All;IsInternalExtension=False</span></span>

<span data-ttu-id="c5f79-142">FirsMatchingRoute： LocalRoute</span><span class="sxs-lookup"><span data-stu-id="c5f79-142">FirsMatchingRoute : LocalRoute</span></span>

<span data-ttu-id="c5f79-143">MatchingUsage： Local</span><span class="sxs-lookup"><span data-stu-id="c5f79-143">MatchingUsage : Local</span></span>

<span data-ttu-id="c5f79-144">如果测试失败，CsVoiceUser 将返回一组空的属性值：</span><span class="sxs-lookup"><span data-stu-id="c5f79-144">If the test fails, Test-CsVoiceUser will return an empty set of property values:</span></span>

<span data-ttu-id="c5f79-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="c5f79-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="c5f79-146">\---------------- ------------ ------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="c5f79-146">\---------------- ------------ ------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c5f79-147">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="c5f79-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="c5f79-148">CsVoiceUser cmdlet 可能失败的原因有很多：可能没有可以转换提供的电话号码的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="c5f79-148">There are any number of reasons why the Test-CsVoiceUser cmdlet might fail: there might not be a normalization rule that can translate the provided phone number.</span></span> <span data-ttu-id="c5f79-149">语音路由可能存在问题。</span><span class="sxs-lookup"><span data-stu-id="c5f79-149">There could be problems with the voice route.</span></span> <span data-ttu-id="c5f79-150">向有问题的用户分配的拨号计划可能存在配置问题。</span><span class="sxs-lookup"><span data-stu-id="c5f79-150">There could be a configuration issue with the dial plan assigned to the user in question.</span></span> <span data-ttu-id="c5f79-151">因此，在运行 CsVoiceUser cmdlet 时，您可能希望包含 Verbose 参数：</span><span class="sxs-lookup"><span data-stu-id="c5f79-151">Because of that, you might want to include the Verbose parameter when you are running the Test-CsVoiceUser cmdlet:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

<span data-ttu-id="c5f79-152">在包含详细 cmdlet 时，CsVoiceUser 将颁发在执行检查时采取的所有步骤的详细帐户。</span><span class="sxs-lookup"><span data-stu-id="c5f79-152">When the Verbose cmdlet is included, Test-CsVoiceUser will issue a detailed account of all the steps in takes when conducting its checks.</span></span> <span data-ttu-id="c5f79-153">例如，您可能会看到类似于以下的步骤：</span><span class="sxs-lookup"><span data-stu-id="c5f79-153">For example, you might see steps similar to these:</span></span> 

<span data-ttu-id="c5f79-154">详细：查找标识为 "sip:kenmyer@litwareinc.com" 的用户</span><span class="sxs-lookup"><span data-stu-id="c5f79-154">VERBOSE: Locating user with identity "sip:kenmyer@litwareinc.com"</span></span>

<span data-ttu-id="c5f79-155">VERBOSE：正在加载拨号计划： "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="c5f79-155">VERBOSE: Loading dial plan: "RedmondDialPlan"</span></span>

<span data-ttu-id="c5f79-156">此附加信息可提供有关可执行的步骤以查明故障原因的提示。</span><span class="sxs-lookup"><span data-stu-id="c5f79-156">This additional information can provide hints as to the steps that you can take to pinpoint the cause of the failure.</span></span> <span data-ttu-id="c5f79-157">例如，此处显示的详细输出告诉我们，被测试的用户已被分配了拨号计划 RedmondDialPlan。</span><span class="sxs-lookup"><span data-stu-id="c5f79-157">For example, the verbose output shown here tells us that the user being tested was assigned the dial plan RedmondDialPlan.</span></span> <span data-ttu-id="c5f79-158">如果测试失败，则下一个逻辑下一步是验证 RedmondDialPlan 是否可以转换提供的电话号码。</span><span class="sxs-lookup"><span data-stu-id="c5f79-158">If the test has failed, one logical next step would be to verify that RedmondDialPlan can translate the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5f79-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5f79-159">See Also</span></span>


[<span data-ttu-id="c5f79-160">Test-CsVoiceUser</span><span class="sxs-lookup"><span data-stu-id="c5f79-160">Test-CsVoiceUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

