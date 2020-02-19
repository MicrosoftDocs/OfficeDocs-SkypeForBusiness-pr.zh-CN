---
title: Lync Server 2013：针对语音策略测试电话号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7670e99fc7ac7688eff360a28be6f7280d6191b1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a><span data-ttu-id="9f89d-102">在 Lync Server 2013 中针对语音策略测试电话号码</span><span class="sxs-lookup"><span data-stu-id="9f89d-102">Test telephone number against a voice policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f89d-103">_**上次修改的主题：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="9f89d-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f89d-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="9f89d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9f89d-105">每月</span><span class="sxs-lookup"><span data-stu-id="9f89d-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f89d-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="9f89d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9f89d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f89d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f89d-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="9f89d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9f89d-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="9f89d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9f89d-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Set-csvoicepolicy cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="9f89d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="9f89d-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9f89d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9f89d-112">说明</span><span class="sxs-lookup"><span data-stu-id="9f89d-112">Description</span></span>

<span data-ttu-id="9f89d-113">企业语音用户对公共交换电话网络（PSTN）枢轴进行的传出电话呼叫的能力在很大程度上取决于三个方面：</span><span class="sxs-lookup"><span data-stu-id="9f89d-113">The ability of Enterprise Voice users to make outgoing phone calls over the Public Switched Telephone network (PSTN) hinges, in large part, on three things:</span></span>

  - <span data-ttu-id="9f89d-114">为用户分配的语音策略。</span><span class="sxs-lookup"><span data-stu-id="9f89d-114">The voice policy assigned to the user.</span></span>

  - <span data-ttu-id="9f89d-115">用于将呼叫从 Lync Server 路由到 PSTN 网络的语音路由。</span><span class="sxs-lookup"><span data-stu-id="9f89d-115">The voice routes used to route calls from Lync Server to the PSTN network.</span></span>

  - <span data-ttu-id="9f89d-116">PSTN 用法，即将语音策略连接到语音路由的 Lync Server 属性。</span><span class="sxs-lookup"><span data-stu-id="9f89d-116">The PSTN usage, a Lync Server property that connects a voice policy to a voice route.</span></span>

<span data-ttu-id="9f89d-117">PSTN 用法尤为重要：它是将语音策略连接到语音路由的属性。</span><span class="sxs-lookup"><span data-stu-id="9f89d-117">The PSTN usage is especially important: it’s the property that connects a voice policy to a voice route.</span></span> <span data-ttu-id="9f89d-118">（如果语音策略和语音路由有至少一个通用的 PSTN 用法，则称为 "已连接"。）可以在不指定 PSTN 用法的情况下配置语音策略。</span><span class="sxs-lookup"><span data-stu-id="9f89d-118">(A voice policy and a voice route are said to be connected if they have at least one PSTN usage in common.) Voice policies can be configured without specifying a PSTN usage.</span></span> <span data-ttu-id="9f89d-119">在这种情况下，分配了该策略的用户将无法通过 PSTN 网络发出传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="9f89d-119">In that case, users who were assigned that policy won't be able to make outgoing calls over the PSTN network.</span></span> <span data-ttu-id="9f89d-120">同样，没有至少一个指定 PSTN 用法的语音路由也无法将呼叫路由到 PSTN 网络。</span><span class="sxs-lookup"><span data-stu-id="9f89d-120">Likewise, voice routes that do not have at least one specified PSTN usage will be unable to route calls to the PSTN network.</span></span>

<span data-ttu-id="9f89d-121">Set-csvoicepolicy cmdlet 验证给定的语音策略是否有 PSTN 用法，以及该使用情况是否至少由一个语音路由共享。</span><span class="sxs-lookup"><span data-stu-id="9f89d-121">The Test-CsVoicePolicy cmdlet verifies that a given voice policy has a PSTN usage and that the usage is shared by at least one voice route.</span></span> <span data-ttu-id="9f89d-122">如果由 Set-csvoicepolicy 验证运行的验证成功，则 cmdlet 将返回找到的第一个有效的语音路由的名称，以及将该策略连接到路由的 PSTN 用法的名称。</span><span class="sxs-lookup"><span data-stu-id="9f89d-122">If the verification run by Test-CsVoicePolicy succeeds, the cmdlet will report back the name of the first valid voice route it finds, and also the name of the PSTN usage that connects the policy to the route.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9f89d-123">运行测试</span><span class="sxs-lookup"><span data-stu-id="9f89d-123">Running the test</span></span>

<span data-ttu-id="9f89d-124">若要运行 Set-csvoicepolicy cmdlet，必须首先使用 Set-csvoicepolicy cmdlet 检索要测试的语音策略的实例;然后，必须将该实例通过管道传递到 Set-csvoicepolicy。</span><span class="sxs-lookup"><span data-stu-id="9f89d-124">To run the Test-CsVoicePolicy cmdlet you must first use the Get-CsVoicePolicy cmdlet retrieve an instance of the voice policy to be tested; that instance must then be piped to Test-CsVoicePolicy.</span></span> <span data-ttu-id="9f89d-125">例如：</span><span class="sxs-lookup"><span data-stu-id="9f89d-125">For example:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="9f89d-126">请注意，此命令不使用 Set-csvoicepolicy 检索语音策略实例将失败：</span><span class="sxs-lookup"><span data-stu-id="9f89d-126">Note that this command, which does not use Get-CsVoicePolicy to retrieve a voice policy instance, will fail:</span></span>

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

<span data-ttu-id="9f89d-127">如果要根据指定的电话号码检查所有语音策略，请使用类似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="9f89d-127">If you want to check all the voice policies against a specified phone number then use a command similar to this:</span></span>

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="9f89d-128">请注意，必须使用 e.164 格式指定 TargetNumber。</span><span class="sxs-lookup"><span data-stu-id="9f89d-128">Note that the TargetNumber must be specified by using the E.164 format.</span></span> <span data-ttu-id="9f89d-129">Set-csvoicepolicy 不会尝试将电话号码正常化或转换为. 164 格式。</span><span class="sxs-lookup"><span data-stu-id="9f89d-129">Test-CsVoicePolicy won't attempt to normalize or translate phone numbers into the E.164 format.</span></span>

<span data-ttu-id="9f89d-130">有关详细信息，请参阅 Set-csvoicepolicy cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="9f89d-130">For more information, see the Help documentation for the Test-CsVoicePolicy cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9f89d-131">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="9f89d-131">Determining success or failure</span></span>

<span data-ttu-id="9f89d-132">如果语音策略可以找到匹配的语音路由和匹配的 PSTN 用法，则将在屏幕上显示路由和使用：</span><span class="sxs-lookup"><span data-stu-id="9f89d-132">If the voice policy can find both a matching voice route and a matching PSTN usage, then both the route and the usage will be displayed on-screen:</span></span>

<span data-ttu-id="9f89d-133">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="9f89d-133">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="9f89d-134">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="9f89d-134">\------------------ -------------</span></span>

<span data-ttu-id="9f89d-135">RedmondVoiceRoute RedmondPstnUsage</span><span class="sxs-lookup"><span data-stu-id="9f89d-135">RedmondVoiceRoute RedmondPstnUsage</span></span>

<span data-ttu-id="9f89d-136">如果找不到合适的语音路由或合适的 PSTN 用法，将在屏幕上显示空白属性值：</span><span class="sxs-lookup"><span data-stu-id="9f89d-136">If either an appropriate voice route or an appropriate PSTN usage cannot be found then blank property values will be displayed on-screen:</span></span>

<span data-ttu-id="9f89d-137">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="9f89d-137">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="9f89d-138">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="9f89d-138">\------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9f89d-139">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="9f89d-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="9f89d-140">如果 Set-csvoicepolicy 不返回一个匹配项，则表明语音策略不会与语音路由共享 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="9f89d-140">If Test-CsVoicePolicy does not return a match that could mean that the voice policy does not share a PSTN usage with a voice route.</span></span> <span data-ttu-id="9f89d-141">若要验证，请使用与以下内容类似的 cmdlet 来验证是否为语音策略分配了 PSTN 用法：</span><span class="sxs-lookup"><span data-stu-id="9f89d-141">To verify that, use a cmdlet similar to the following to verify that PSTN usages assigned to the voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

<span data-ttu-id="9f89d-142">接下来，运行此命令以确定 PSTN 用法分配给每个语音路由：</span><span class="sxs-lookup"><span data-stu-id="9f89d-142">Next, run this command to determine the PSTN usages assign to each of your voice routes:</span></span>

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

<span data-ttu-id="9f89d-143">如果看到任何匹配项（即，如果你看到一个或多个与语音策略共用一个 PSTN 用法的语音路由），则应运行 CsVoiceRoute cmdlet 以验证语音路由是否可以拨打提供的电话号码。</span><span class="sxs-lookup"><span data-stu-id="9f89d-143">If you see any matches (that is, if you see one or more voice routes that share at least one PSTN usage with your voice policy), you should then run the Test-CsVoiceRoute cmdlet to verify that the voice route can dial the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9f89d-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f89d-144">See Also</span></span>


[<span data-ttu-id="9f89d-145">Test-Set-csvoicepolicy</span><span class="sxs-lookup"><span data-stu-id="9f89d-145">Test-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

