---
title: Lync Server 2013：检查对电话号码的中继配置
description: Lync Server 2013：检查对电话号码的中继配置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cdfe1a2a9c5c87310ad561464960c5a01fea7b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543538"
---
# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a><span data-ttu-id="409a3-103">在 Lync Server 2013 中检查对电话号码的中继配置</span><span class="sxs-lookup"><span data-stu-id="409a3-103">Check trunk configuration against a phone number in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="409a3-104">_**上次修改的主题：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="409a3-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="409a3-105">验证计划</span><span class="sxs-lookup"><span data-stu-id="409a3-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="409a3-106">每月</span><span class="sxs-lookup"><span data-stu-id="409a3-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="409a3-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="409a3-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="409a3-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="409a3-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="409a3-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="409a3-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="409a3-110">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="409a3-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="409a3-111">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsTrunkConfiguration cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="409a3-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="409a3-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="409a3-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="409a3-113">说明</span><span class="sxs-lookup"><span data-stu-id="409a3-113">Description</span></span>

<span data-ttu-id="409a3-114">SIP 中继将 Lync Server 内部企业语音网络连接到以下任一项：</span><span class="sxs-lookup"><span data-stu-id="409a3-114">SIP trunks connect the Lync Server internal Enterprise Voice network to any of the following:</span></span>

  - <span data-ttu-id="409a3-115">公开交换的电话网络 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="409a3-115">The Public Switched Telephone network (PSTN).</span></span>

  - <span data-ttu-id="409a3-116"> (PBX) 的 IP 公共分支 exchange。</span><span class="sxs-lookup"><span data-stu-id="409a3-116">An IP-public branch exchange (PBX).</span></span>

  - <span data-ttu-id="409a3-117"> (SBC) 的会话边界控制器。</span><span class="sxs-lookup"><span data-stu-id="409a3-117">A Session Border Controller (SBC).</span></span>

<span data-ttu-id="409a3-118">Test-CsTrunkConfiguration cmdlet 验证) 用户拨打的电话号码 (是否可以转换为 e.164 网络，并通过指定的 SIP 中继进行路由。</span><span class="sxs-lookup"><span data-stu-id="409a3-118">The Test-CsTrunkConfiguration cmdlet verifies that a phone number (as dialed by a user) can be converted to the E.164 network and routed over a specified SIP trunk.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="409a3-119">运行测试</span><span class="sxs-lookup"><span data-stu-id="409a3-119">Running the test</span></span>

<span data-ttu-id="409a3-120">若要运行 Test-CsTrunkConfiguration cmdlet，必须首先使用 Get-CsTrunkConfiguration cmdlet 检索 SIP 中继配置设置的实例;然后，将该实例通过管道传递到 Remove-cstrunkconfiguration：</span><span class="sxs-lookup"><span data-stu-id="409a3-120">To run the Test-CsTrunkConfiguration cmdlet you must first use the Get-CsTrunkConfiguration cmdlet to retrieve an instance of your SIP trunk configuration settings; that instance is then piped to Test-CsTrunkConfiguration:</span></span>

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="409a3-121">运行 Test-CsTrunkConfiguration 而不先运行 Get-CsTrunkConfiguration 不起作用。</span><span class="sxs-lookup"><span data-stu-id="409a3-121">Running Test-CsTrunkConfiguration without first running Get-CsTrunkConfiguration won't work.</span></span> <span data-ttu-id="409a3-122">例如，在不返回任何数据的情况下，此命令将失败：</span><span class="sxs-lookup"><span data-stu-id="409a3-122">For example, this command will fail without returning any data:</span></span>

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

<span data-ttu-id="409a3-123">如果您有多个 SIP 中继配置设置集合，则可以使用与以下类似的命令来针对同一电话号码测试每个集合：</span><span class="sxs-lookup"><span data-stu-id="409a3-123">If you have multiple collections of SIP trunk configuration settings, you can use a command similar to the following to at the same time test each collection against the same phone number:</span></span>

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="409a3-124">有关详细信息，请参阅 Test-CsTrunkConfiguration cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="409a3-124">For more information, see the Help documentation for the Test-CsTrunkConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="409a3-125">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="409a3-125">Determining success or failure</span></span>

<span data-ttu-id="409a3-126">如果 Test-CsTrunkConfiguration 可以呼叫已拨打的号码，则转换的电话号码将 (以164格式) ，并且用于转换该电话号码的规则将显示在屏幕上：</span><span class="sxs-lookup"><span data-stu-id="409a3-126">If Test-CsTrunkConfiguration can place a call to the dialed number then the translated phone number (in the E.164 format) and the rule used to translate that phone number will both be displayed on screen:</span></span>

<span data-ttu-id="409a3-127">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="409a3-127">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="409a3-128">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="409a3-128">\---------------- ------------</span></span>

<span data-ttu-id="409a3-129">\+12065551219全球/雷德蒙</span><span class="sxs-lookup"><span data-stu-id="409a3-129">\+12065551219 Global/Redmond</span></span>

<span data-ttu-id="409a3-130">如果测试失败，Test-CsTrunkConfiguration 将返回空属性值：</span><span class="sxs-lookup"><span data-stu-id="409a3-130">If the test fails, Test-CsTrunkConfiguration will return empty property values:</span></span>

<span data-ttu-id="409a3-131">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="409a3-131">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="409a3-132">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="409a3-132">\---------------- ------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="409a3-133">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="409a3-133">Reasons why the test might have failed</span></span>

<span data-ttu-id="409a3-134">如果 Test-CsTrunkConfiguration 不返回一个通常意味着要测试的中继配置设置没有一个传出呼叫号码转换规则，可以将所拨打的号码转换为 e.164 格式。</span><span class="sxs-lookup"><span data-stu-id="409a3-134">If Test-CsTrunkConfiguration does not return a match that typically means that the trunk configuration settings being test do not have an outgoing calling number translation rule capable to converting the dialed number to the E.164 format.</span></span> <span data-ttu-id="409a3-135">若要检索分配给中继配置设置集合的转换规则，可以使用类似如下的语法：</span><span class="sxs-lookup"><span data-stu-id="409a3-135">To retrieve the translation rules assigned to a collection of trunk configuration settings, you can use syntax similar to this:</span></span>

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

<span data-ttu-id="409a3-136">对于每个转换规则，返回类似于以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="409a3-136">That returns information similar to this for each translation rule:</span></span>

<span data-ttu-id="409a3-137">说明：不带国家/地区代码或区号的电话号码。</span><span class="sxs-lookup"><span data-stu-id="409a3-137">Description : Phone numbers without a country code or area code.</span></span>

<span data-ttu-id="409a3-138">模式： ^ \\ + (\\ d \*) $</span><span class="sxs-lookup"><span data-stu-id="409a3-138">Pattern : ^\\+(\\d\*)$</span></span>

`Translation : $1`

<span data-ttu-id="409a3-139">名称： NoAreaCode</span><span class="sxs-lookup"><span data-stu-id="409a3-139">Name : NoAreaCode</span></span>

<span data-ttu-id="409a3-140">此时，您需要检查 Pattern 属性的值 (它是 [正则表达式](https://go.microsoft.com/fwlink/?linkid=400464) 字符串) ，以查看是否有任何转换规则配置为处理所拨打的号码。</span><span class="sxs-lookup"><span data-stu-id="409a3-140">At that point, you check the value of the Pattern property (which is a [regular expression](https://go.microsoft.com/fwlink/?linkid=400464) string) to see whether any of the translation rules are configured to handle the dialed number.</span></span> <span data-ttu-id="409a3-141">如果不是，则必须更改现有规则 (CsOutboundTranslationRule) 中的一个，或使用 New-CsOutboundTranslationRule cmdlet 将新规则添加到集合中。</span><span class="sxs-lookup"><span data-stu-id="409a3-141">If not, you'll either have to change one of the existing rules (Set-CsOutboundTranslationRule) or use the New-CsOutboundTranslationRule cmdlet to add a new rule to the collection.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="409a3-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="409a3-142">See Also</span></span>


[<span data-ttu-id="409a3-143">Test-Remove-cstrunkconfiguration</span><span class="sxs-lookup"><span data-stu-id="409a3-143">Test-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

