---
title: 'Lync Server 2013: 根据语音路线测试电话号码'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed50971c9656d454a44eeee627de95c187ef008f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="28313-102">根据 Lync Server 2013 中的语音路线测试电话号码</span><span class="sxs-lookup"><span data-stu-id="28313-102">Test telephone number against a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28313-103">_**主题上次修改时间:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="28313-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28313-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="28313-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="28313-105">每月</span><span class="sxs-lookup"><span data-stu-id="28313-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28313-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="28313-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="28313-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="28313-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28313-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="28313-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="28313-109">当使用 Lync Server 命令行管理程序在本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="28313-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="28313-110">使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsVoiceRoute cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="28313-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceRoute cmdlet.</span></span> <span data-ttu-id="28313-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="28313-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="28313-112">说明</span><span class="sxs-lookup"><span data-stu-id="28313-112">Description</span></span>

<span data-ttu-id="28313-113">语音路由与语音策略协同工作, 帮助将企业语音呼叫路由到 PSTN 网络。</span><span class="sxs-lookup"><span data-stu-id="28313-113">Voice routes work together with voice policies to help route Enterprise Voice calls to the PSTN network.</span></span> <span data-ttu-id="28313-114">每个语音路由都包含一个正则表达式 (数字模式), 用于标识将通过给定语音路线路由的电话号码: 路由将能够处理与此正则表达式匹配的任何电话号码。</span><span class="sxs-lookup"><span data-stu-id="28313-114">Each voice route includes a regular expression (a number pattern) that identifies the phone numbers that will be routed through a given voice route: the route will be able to handle any phone numbers that match this regular expression.</span></span> <span data-ttu-id="28313-115">例如, 语音路由可能有一个正则表达式, 可使其处理任何10位数字。</span><span class="sxs-lookup"><span data-stu-id="28313-115">For example, a voice route might have a regular expression that enables it to handle any 10-digit number.</span></span> <span data-ttu-id="28313-116">这意味着路由将能够处理如下所示的电话号码:</span><span class="sxs-lookup"><span data-stu-id="28313-116">That means the route would be able to handle a phone number such as this:</span></span>

  - <span data-ttu-id="28313-117">2065551219</span><span class="sxs-lookup"><span data-stu-id="28313-117">2065551219</span></span>

<span data-ttu-id="28313-118">路由将无法处理以下两个数字中的任何一个, 其中两个数字都没有10个数字:</span><span class="sxs-lookup"><span data-stu-id="28313-118">The route would not be able to handle either of the following two numbers, neither of which has 10 digits:</span></span>

  - <span data-ttu-id="28313-119">5551219</span><span class="sxs-lookup"><span data-stu-id="28313-119">5551219</span></span>

  - <span data-ttu-id="28313-120">12065551219</span><span class="sxs-lookup"><span data-stu-id="28313-120">12065551219</span></span>

<span data-ttu-id="28313-121">CsVoiceRoute cmdlet 验证给定的语音路线是否可以路由指定的电话号码。</span><span class="sxs-lookup"><span data-stu-id="28313-121">The Test-CsVoiceRoute cmdlet verifies whether a given voice route can route a specified phone number.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="28313-122">运行测试</span><span class="sxs-lookup"><span data-stu-id="28313-122">Running the test</span></span>

<span data-ttu-id="28313-123">验证语音路线路由指定电话号码的能力是两步过程。</span><span class="sxs-lookup"><span data-stu-id="28313-123">Verifying the ability of a voice route to route a specified phone number is a two-step process.</span></span> <span data-ttu-id="28313-124">首先, 你必须使用 CsVoiceRoute cmdlet 来返回该语音路由的实例, 然后你必须使用 CsVoiceRoute cmdlet 验证该路由处理目标电话号码的能力。</span><span class="sxs-lookup"><span data-stu-id="28313-124">First you have to use the Get-CsVoiceRoute cmdlet to return an instance of that voice route, and then you have to use the Test-CsVoiceRoute cmdlet to verify the ability of that route to handle the target phone number.</span></span> <span data-ttu-id="28313-125">例如, 此命令将验证 RedmondVoiceRoute 的语音路线是否可以路由电话号码 2065551219:</span><span class="sxs-lookup"><span data-stu-id="28313-125">For example, this command verifies whether the RedmondVoiceRoute voice route can route the phone number 2065551219:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="28313-126">请注意, 输入的电话号码应为您希望用户拨打该号码时输入。</span><span class="sxs-lookup"><span data-stu-id="28313-126">Note that the phone number should be typed as you expect users to dial that number.</span></span> <span data-ttu-id="28313-127">例如, 如果您不希望用户在拨号时包括国家代码和区号, 则使用类似于以下语法的语法:</span><span class="sxs-lookup"><span data-stu-id="28313-127">For example, if you do not expect users to include the country code and area code when dialing, then use syntax similar to this:</span></span>

`-TargetNumber "5551219"`

<span data-ttu-id="28313-128">在这种情况下, 目标号码将同时保留国家/地区代码和区号。</span><span class="sxs-lookup"><span data-stu-id="28313-128">In this case, the target number leaves out both the country code and the area code.</span></span>

<span data-ttu-id="28313-129">若要使用单个命令来根据指定的目标号码测试所有语音路由, 请使用如下语法:</span><span class="sxs-lookup"><span data-stu-id="28313-129">To use a single command to test all the voice routes against a specified target number, use syntax such as the following:</span></span>

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="28313-130">有关详细信息, 请参阅 CsVoiceRoute cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="28313-130">For more information, see the Help documentation for the Test-CsVoiceRoute cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="28313-131">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="28313-131">Determining success or failure</span></span>

<span data-ttu-id="28313-132">如果语音路由可以路由目标电话号码, CsVoiceRoute cmdlet 只会返回值 True:</span><span class="sxs-lookup"><span data-stu-id="28313-132">If the voice route can route the target phone number the Test-CsVoiceRoute cmdlet just returns the value True:</span></span>

<span data-ttu-id="28313-133">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="28313-133">MatchesPattern</span></span>

\--------------

<span data-ttu-id="28313-134">True</span><span class="sxs-lookup"><span data-stu-id="28313-134">True</span></span>

<span data-ttu-id="28313-135">这意味着路由可以处理与目标号码类似的号码。</span><span class="sxs-lookup"><span data-stu-id="28313-135">That means that route can handle numbers similar to the target number.</span></span> <span data-ttu-id="28313-136">如果语音路由无法处理目标号码, 则 Test-CsVoiceRoute 返回值 False:</span><span class="sxs-lookup"><span data-stu-id="28313-136">If the voice route is can't handle the target number then Test-CsVoiceRoute returns the value False:</span></span>

<span data-ttu-id="28313-137">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="28313-137">MatchesPattern</span></span>

\--------------

<span data-ttu-id="28313-138">False</span><span class="sxs-lookup"><span data-stu-id="28313-138">False</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="28313-139">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="28313-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="28313-140">测试语音路由时, "失败" 是一个相对术语。</span><span class="sxs-lookup"><span data-stu-id="28313-140">When testing voice routes, “failure” is a relative term.</span></span> <span data-ttu-id="28313-141">在这种情况下, 它不意味着路由是以 "损坏;" 为目标的, 而是指路由无法处理目标号码。</span><span class="sxs-lookup"><span data-stu-id="28313-141">In this case, it doesn’t mean that the route is somehow “broken;” instead, it just means that the route can't handle the target number.</span></span> <span data-ttu-id="28313-142">这可能是因为语音路由配置不正确。</span><span class="sxs-lookup"><span data-stu-id="28313-142">That could be because the voice route was configured incorrectly.</span></span> <span data-ttu-id="28313-143">这也可能意味着该路由从未用于处理使用此模式的数字。</span><span class="sxs-lookup"><span data-stu-id="28313-143">It could also mean that the route was never intended to handle numbers using this pattern.</span></span> <span data-ttu-id="28313-144">例如, 如果您不希望通过给定路线将呼叫路由到其他国家/地区, 可以将路由配置为拒绝包括国家/地区代码的所有电话号码。</span><span class="sxs-lookup"><span data-stu-id="28313-144">For example, if you do not want to route calls to other countries over a given route that route might be configured to reject all phone numbers that include a country code.</span></span> <span data-ttu-id="28313-145">如果 CsVoiceRoute 返回 False (如果你希望它返回 True), 请验证是否正确键入了目标编号。</span><span class="sxs-lookup"><span data-stu-id="28313-145">If Test-CsVoiceRoute returns False when you expected it to return True, verify that you typed the target number in correctly.</span></span> <span data-ttu-id="28313-146">如果执行此操作, 请使用与此类似的命令查看为该路由配置的 NumberPattern:</span><span class="sxs-lookup"><span data-stu-id="28313-146">If you did, then use a command similar to this one to view the NumberPattern configured for the route:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="28313-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28313-147">See Also</span></span>


[<span data-ttu-id="28313-148">Test-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="28313-148">Test-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

