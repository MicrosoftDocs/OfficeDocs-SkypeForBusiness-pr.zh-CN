---
title: Lync Server 2013：测试 PSTN 电话呼叫路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 750efc8ced1dbb4c048d10c879f0bfa2dd4a4f32
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="a512c-102">在 Lync Server 2013 中测试 PSTN 电话呼叫路由</span><span class="sxs-lookup"><span data-stu-id="a512c-102">Testing PSTN phone call routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a512c-103">_**上次修改的主题：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="a512c-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a512c-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="a512c-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a512c-105">每天</span><span class="sxs-lookup"><span data-stu-id="a512c-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a512c-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="a512c-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a512c-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a512c-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a512c-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="a512c-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a512c-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="a512c-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a512c-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行<strong>test-csintertrunkrouting</strong> cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="a512c-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="a512c-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a512c-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a512c-112">描述</span><span class="sxs-lookup"><span data-stu-id="a512c-112">Description</span></span>

<span data-ttu-id="a512c-113">**Test-csintertrunkrouting** cmdlet 验证是否可以将呼叫从一个 SIP 路由到另一个 SIP。</span><span class="sxs-lookup"><span data-stu-id="a512c-113">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="a512c-114">为此，将为 cmdlet 提供一个电话号码和一个中继配置。</span><span class="sxs-lookup"><span data-stu-id="a512c-114">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="a512c-115">然后， **test-csintertrunkrouting**将报告针对指定号码的反向匹配路由和匹配 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="a512c-115">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="a512c-116">请注意，仅当中继具有匹配指定电话号码的号码模式并且中继至少共享一个 PSTN 用法时，才能在中继之间进行路由。</span><span class="sxs-lookup"><span data-stu-id="a512c-116">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a512c-117">运行测试</span><span class="sxs-lookup"><span data-stu-id="a512c-117">Running the test</span></span>

<span data-ttu-id="a512c-118">下面显示的命令将返回匹配的路由和匹配的电话用法，使用户能够使用 Redmond 网站的中继配置设置呼叫电话号码1-206-555-1219。</span><span class="sxs-lookup"><span data-stu-id="a512c-118">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a512c-119">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="a512c-119">Determining success or failure</span></span>

<span data-ttu-id="a512c-120">如果可以从一个 SIP 向另一个 SIP 路由呼叫，您将收到与以下内容类似的输出：</span><span class="sxs-lookup"><span data-stu-id="a512c-120">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="a512c-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span><span class="sxs-lookup"><span data-stu-id="a512c-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="a512c-122">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="a512c-122">\------------------ ------------- --------------</span></span>

<span data-ttu-id="a512c-123">RedmondRoute LocalUsage {RedmondRoute}</span><span class="sxs-lookup"><span data-stu-id="a512c-123">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="a512c-124">如果测试未成功，您将收到与以下内容类似的输出：</span><span class="sxs-lookup"><span data-stu-id="a512c-124">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="a512c-125">测试-Test-csintertrunkrouting：无法处理参数上的参数转换</span><span class="sxs-lookup"><span data-stu-id="a512c-125">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="a512c-126">"为 microsoft.rtc.management.writableconfig.settings.trunkconfiguration.trunkconfiguration"。</span><span class="sxs-lookup"><span data-stu-id="a512c-126">'TrunkConfiguration'.</span></span> <span data-ttu-id="a512c-127">无效的 TrunkConfigurationsetting （参数）。</span><span class="sxs-lookup"><span data-stu-id="a512c-127">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="a512c-128">指定一个</span><span class="sxs-lookup"><span data-stu-id="a512c-128">Specify a</span></span>

<span data-ttu-id="a512c-129">有效设置（参数），然后重试。</span><span class="sxs-lookup"><span data-stu-id="a512c-129">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="a512c-130">行：1字符：79</span><span class="sxs-lookup"><span data-stu-id="a512c-130">At line:1 char:79</span></span>

<span data-ttu-id="a512c-131">\+Test-csintertrunkrouting-TargetNumber "电话： + 12065551219"</span><span class="sxs-lookup"><span data-stu-id="a512c-131">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="a512c-132">\-为 microsoft.rtc.management.writableconfig.settings.trunkconfiguration.trunkconfiguration $t .。。</span><span class="sxs-lookup"><span data-stu-id="a512c-132">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="a512c-133">\+CategoryInfo： InvalidData：（:)\[Test-csintertrunkrouting\]，Par</span><span class="sxs-lookup"><span data-stu-id="a512c-133">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="a512c-134">ameterBindingArgumentTransformationException</span><span class="sxs-lookup"><span data-stu-id="a512c-134">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="a512c-135">\+FullyQualifiedErrorId： ParameterArgumentTransformationError，Microsoft。</span><span class="sxs-lookup"><span data-stu-id="a512c-135">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="a512c-136">简.TestOcsInterTrunkRoutingCmdlet 的管理</span><span class="sxs-lookup"><span data-stu-id="a512c-136">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a512c-137">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="a512c-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="a512c-138">以下是**测试 test-csintertrunkrouting**可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="a512c-138">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="a512c-139">您指定的参数无效。</span><span class="sxs-lookup"><span data-stu-id="a512c-139">You specified invalid parameters.</span></span> <span data-ttu-id="a512c-140">中继可能尚未正确配置，并且指定的目标号码可能不正确或无效。</span><span class="sxs-lookup"><span data-stu-id="a512c-140">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a512c-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a512c-141">See Also</span></span>


[<span data-ttu-id="a512c-142">CsTrunk</span><span class="sxs-lookup"><span data-stu-id="a512c-142">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="a512c-143">Remove-cstrunkconfiguration</span><span class="sxs-lookup"><span data-stu-id="a512c-143">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

