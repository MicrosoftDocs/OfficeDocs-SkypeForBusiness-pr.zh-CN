---
title: Lync Server 2013：对照电话号码检查中继配置
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
ms.openlocfilehash: 7932e4cb7a7a9d74b945dcd60c2a1211ca5af694
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a><span data-ttu-id="9ab30-102">对照 Lync Server 2013 中的电话号码检查中继配置</span><span class="sxs-lookup"><span data-stu-id="9ab30-102">Check trunk configuration against a phone number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ab30-103">_**主题上次修改时间：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="9ab30-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ab30-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="9ab30-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9ab30-105">每月</span><span class="sxs-lookup"><span data-stu-id="9ab30-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ab30-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="9ab30-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9ab30-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ab30-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ab30-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="9ab30-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9ab30-109">当使用 Lync Server 命令行管理程序在本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="9ab30-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9ab30-110">使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 New-cstrunkconfiguration cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="9ab30-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="9ab30-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9ab30-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9ab30-112">说明</span><span class="sxs-lookup"><span data-stu-id="9ab30-112">Description</span></span>

<span data-ttu-id="9ab30-113">SIP 中继将 Lync Server 内部企业语音网络连接到以下任何内容：</span><span class="sxs-lookup"><span data-stu-id="9ab30-113">SIP trunks connect the Lync Server internal Enterprise Voice network to any of the following:</span></span>

  - <span data-ttu-id="9ab30-114">公共交换电话网络（PSTN）。</span><span class="sxs-lookup"><span data-stu-id="9ab30-114">The Public Switched Telephone network (PSTN).</span></span>

  - <span data-ttu-id="9ab30-115">IP-公共分支交换（PBX）。</span><span class="sxs-lookup"><span data-stu-id="9ab30-115">An IP-public branch exchange (PBX).</span></span>

  - <span data-ttu-id="9ab30-116">会话边框控制器（SBC）。</span><span class="sxs-lookup"><span data-stu-id="9ab30-116">A Session Border Controller (SBC).</span></span>

<span data-ttu-id="9ab30-117">New-cstrunkconfiguration cmdlet 验证电话号码（由用户拨出）是否可以转换为 E-164 网络，并通过指定的 SIP 主干进行路由。</span><span class="sxs-lookup"><span data-stu-id="9ab30-117">The Test-CsTrunkConfiguration cmdlet verifies that a phone number (as dialed by a user) can be converted to the E.164 network and routed over a specified SIP trunk.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9ab30-118">运行测试</span><span class="sxs-lookup"><span data-stu-id="9ab30-118">Running the test</span></span>

<span data-ttu-id="9ab30-119">若要运行 New-cstrunkconfiguration cmdlet，必须首先使用 New-cstrunkconfiguration cmdlet 检索 SIP 中继配置设置的实例;然后，将该实例管道传送到 Test-New-cstrunkconfiguration：</span><span class="sxs-lookup"><span data-stu-id="9ab30-119">To run the Test-CsTrunkConfiguration cmdlet you must first use the Get-CsTrunkConfiguration cmdlet to retrieve an instance of your SIP trunk configuration settings; that instance is then piped to Test-CsTrunkConfiguration:</span></span>

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="9ab30-120">运行 Test-New-cstrunkconfiguration 而不事先运行 New-cstrunkconfiguration 将不起作用。</span><span class="sxs-lookup"><span data-stu-id="9ab30-120">Running Test-CsTrunkConfiguration without first running Get-CsTrunkConfiguration won't work.</span></span> <span data-ttu-id="9ab30-121">例如，此命令将失败，且不返回任何数据：</span><span class="sxs-lookup"><span data-stu-id="9ab30-121">For example, this command will fail without returning any data:</span></span>

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

<span data-ttu-id="9ab30-122">如果您有多个 SIP 中继配置设置集合，则可以使用如下所示的命令在每个集合中测试相同的电话号码：</span><span class="sxs-lookup"><span data-stu-id="9ab30-122">If you have multiple collections of SIP trunk configuration settings, you can use a command similar to the following to at the same time test each collection against the same phone number:</span></span>

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="9ab30-123">有关详细信息，请参阅 New-cstrunkconfiguration cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="9ab30-123">For more information, see the Help documentation for the Test-CsTrunkConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9ab30-124">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="9ab30-124">Determining success or failure</span></span>

<span data-ttu-id="9ab30-125">如果 New-cstrunkconfiguration 可以拨打电话号码，则已翻译的电话号码（以 E：164格式）和用于转换该电话号码的规则都将显示在屏幕上：</span><span class="sxs-lookup"><span data-stu-id="9ab30-125">If Test-CsTrunkConfiguration can place a call to the dialed number then the translated phone number (in the E.164 format) and the rule used to translate that phone number will both be displayed on screen:</span></span>

<span data-ttu-id="9ab30-126">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="9ab30-126">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="9ab30-127">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="9ab30-127">\---------------- ------------</span></span>

<span data-ttu-id="9ab30-128">\+12065551219全球/雷德蒙</span><span class="sxs-lookup"><span data-stu-id="9ab30-128">\+12065551219 Global/Redmond</span></span>

<span data-ttu-id="9ab30-129">如果测试失败，New-cstrunkconfiguration 将返回空属性值：</span><span class="sxs-lookup"><span data-stu-id="9ab30-129">If the test fails, Test-CsTrunkConfiguration will return empty property values:</span></span>

<span data-ttu-id="9ab30-130">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="9ab30-130">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="9ab30-131">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="9ab30-131">\---------------- ------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9ab30-132">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="9ab30-132">Reasons why the test might have failed</span></span>

<span data-ttu-id="9ab30-133">如果 New-cstrunkconfiguration 不返回一个匹配项，这通常意味着正在测试的 trunk 配置设置没有传出呼叫号码转换规则，可用于将已拨号码转换为 E-164 格式。</span><span class="sxs-lookup"><span data-stu-id="9ab30-133">If Test-CsTrunkConfiguration does not return a match that typically means that the trunk configuration settings being test do not have an outgoing calling number translation rule capable to converting the dialed number to the E.164 format.</span></span> <span data-ttu-id="9ab30-134">若要检索分配给主干配置设置集合的转换规则，可以使用类似下面的语法：</span><span class="sxs-lookup"><span data-stu-id="9ab30-134">To retrieve the translation rules assigned to a collection of trunk configuration settings, you can use syntax similar to this:</span></span>

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

<span data-ttu-id="9ab30-135">这将针对每个翻译规则返回类似于以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="9ab30-135">That returns information similar to this for each translation rule:</span></span>

<span data-ttu-id="9ab30-136">说明：没有国家/地区代码或区号的电话号码。</span><span class="sxs-lookup"><span data-stu-id="9ab30-136">Description : Phone numbers without a country code or area code.</span></span>

<span data-ttu-id="9ab30-137">模式： ^\\+ （\\d\*） $</span><span class="sxs-lookup"><span data-stu-id="9ab30-137">Pattern : ^\\+(\\d\*)$</span></span>

`Translation : $1`

<span data-ttu-id="9ab30-138">名称： NoAreaCode</span><span class="sxs-lookup"><span data-stu-id="9ab30-138">Name : NoAreaCode</span></span>

<span data-ttu-id="9ab30-139">此时，你检查 Pattern 属性的值（这是一个[正则表达式](http://go.microsoft.com/fwlink/?linkid=400464)字符串），以查看是否有任何翻译规则配置为处理已拨号码。</span><span class="sxs-lookup"><span data-stu-id="9ab30-139">At that point, you check the value of the Pattern property (which is a [regular expression](http://go.microsoft.com/fwlink/?linkid=400464) string) to see whether any of the translation rules are configured to handle the dialed number.</span></span> <span data-ttu-id="9ab30-140">如果不是，你将必须更改现有规则之一（Set-CsOutboundTranslationRule）或使用 CsOutboundTranslationRule cmdlet 向集合添加新规则。</span><span class="sxs-lookup"><span data-stu-id="9ab30-140">If not, you'll either have to change one of the existing rules (Set-CsOutboundTranslationRule) or use the New-CsOutboundTranslationRule cmdlet to add a new rule to the collection.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9ab30-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ab30-141">See Also</span></span>


[<span data-ttu-id="9ab30-142">Test-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="9ab30-142">Test-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

