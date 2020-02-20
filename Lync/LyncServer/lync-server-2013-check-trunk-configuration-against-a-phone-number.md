---
title: Lync Server 2013：检查对电话号码的中继配置
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
ms.openlocfilehash: 2832af2c038383e0cca9f8cb931ce4b675b44f2b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a><span data-ttu-id="5a2e3-102">在 Lync Server 2013 中检查对电话号码的中继配置</span><span class="sxs-lookup"><span data-stu-id="5a2e3-102">Check trunk configuration against a phone number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a2e3-103">_**上次修改的主题：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="5a2e3-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a2e3-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="5a2e3-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5a2e3-105">每月</span><span class="sxs-lookup"><span data-stu-id="5a2e3-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a2e3-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="5a2e3-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5a2e3-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a2e3-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a2e3-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="5a2e3-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5a2e3-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="5a2e3-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5a2e3-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Remove-cstrunkconfiguration cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="5a2e3-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="5a2e3-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5a2e3-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5a2e3-112">说明</span><span class="sxs-lookup"><span data-stu-id="5a2e3-112">Description</span></span>

<span data-ttu-id="5a2e3-113">SIP 中继将 Lync Server 内部企业语音网络连接到以下任一项：</span><span class="sxs-lookup"><span data-stu-id="5a2e3-113">SIP trunks connect the Lync Server internal Enterprise Voice network to any of the following:</span></span>

  - <span data-ttu-id="5a2e3-114">公共交换电话网络（PSTN）。</span><span class="sxs-lookup"><span data-stu-id="5a2e3-114">The Public Switched Telephone network (PSTN).</span></span>

  - <span data-ttu-id="5a2e3-115">IP-公共交换机（PBX）。</span><span class="sxs-lookup"><span data-stu-id="5a2e3-115">An IP-public branch exchange (PBX).</span></span>

  - <span data-ttu-id="5a2e3-116">会话边界控制器（SBC）。</span><span class="sxs-lookup"><span data-stu-id="5a2e3-116">A Session Border Controller (SBC).</span></span>

<span data-ttu-id="5a2e3-117">Remove-cstrunkconfiguration cmdlet 验证电话号码（由用户拨打）是否可以转换为 e.164 网络，并通过指定的 SIP 中继进行路由。</span><span class="sxs-lookup"><span data-stu-id="5a2e3-117">The Test-CsTrunkConfiguration cmdlet verifies that a phone number (as dialed by a user) can be converted to the E.164 network and routed over a specified SIP trunk.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5a2e3-118">运行测试</span><span class="sxs-lookup"><span data-stu-id="5a2e3-118">Running the test</span></span>

<span data-ttu-id="5a2e3-119">若要运行 Remove-cstrunkconfiguration cmdlet，必须首先使用 Remove-cstrunkconfiguration cmdlet 检索 SIP 中继配置设置的实例;然后，将该实例通过管道传递到 Remove-cstrunkconfiguration：</span><span class="sxs-lookup"><span data-stu-id="5a2e3-119">To run the Test-CsTrunkConfiguration cmdlet you must first use the Get-CsTrunkConfiguration cmdlet to retrieve an instance of your SIP trunk configuration settings; that instance is then piped to Test-CsTrunkConfiguration:</span></span>

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="5a2e3-120">运行 Remove-cstrunkconfiguration，而不事先运行 Remove-cstrunkconfiguration 将不起作用。</span><span class="sxs-lookup"><span data-stu-id="5a2e3-120">Running Test-CsTrunkConfiguration without first running Get-CsTrunkConfiguration won't work.</span></span> <span data-ttu-id="5a2e3-121">例如，在不返回任何数据的情况下，此命令将失败：</span><span class="sxs-lookup"><span data-stu-id="5a2e3-121">For example, this command will fail without returning any data:</span></span>

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

<span data-ttu-id="5a2e3-122">如果您有多个 SIP 中继配置设置集合，则可以使用与以下类似的命令来针对同一电话号码测试每个集合：</span><span class="sxs-lookup"><span data-stu-id="5a2e3-122">If you have multiple collections of SIP trunk configuration settings, you can use a command similar to the following to at the same time test each collection against the same phone number:</span></span>

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="5a2e3-123">有关详细信息，请参阅 Remove-cstrunkconfiguration cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="5a2e3-123">For more information, see the Help documentation for the Test-CsTrunkConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5a2e3-124">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="5a2e3-124">Determining success or failure</span></span>

<span data-ttu-id="5a2e3-125">如果 Remove-cstrunkconfiguration 可以呼叫已拨打的号码，则转换的电话号码（以. 164 格式）和用于转换该电话号码的规则都将显示在屏幕上：</span><span class="sxs-lookup"><span data-stu-id="5a2e3-125">If Test-CsTrunkConfiguration can place a call to the dialed number then the translated phone number (in the E.164 format) and the rule used to translate that phone number will both be displayed on screen:</span></span>

<span data-ttu-id="5a2e3-126">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="5a2e3-126">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="5a2e3-127">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="5a2e3-127">\---------------- ------------</span></span>

<span data-ttu-id="5a2e3-128">\+12065551219全球/雷德蒙</span><span class="sxs-lookup"><span data-stu-id="5a2e3-128">\+12065551219 Global/Redmond</span></span>

<span data-ttu-id="5a2e3-129">如果测试失败，Remove-cstrunkconfiguration 将返回空的属性值：</span><span class="sxs-lookup"><span data-stu-id="5a2e3-129">If the test fails, Test-CsTrunkConfiguration will return empty property values:</span></span>

<span data-ttu-id="5a2e3-130">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="5a2e3-130">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="5a2e3-131">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="5a2e3-131">\---------------- ------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5a2e3-132">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="5a2e3-132">Reasons why the test might have failed</span></span>

<span data-ttu-id="5a2e3-133">如果 Remove-cstrunkconfiguration 不返回一个与之匹配的值，这通常意味着要测试的中继配置设置没有一个传出呼叫号码转换规则，可以将拨打的号码转换为 e.164 格式。</span><span class="sxs-lookup"><span data-stu-id="5a2e3-133">If Test-CsTrunkConfiguration does not return a match that typically means that the trunk configuration settings being test do not have an outgoing calling number translation rule capable to converting the dialed number to the E.164 format.</span></span> <span data-ttu-id="5a2e3-134">若要检索分配给中继配置设置集合的转换规则，可以使用类似如下的语法：</span><span class="sxs-lookup"><span data-stu-id="5a2e3-134">To retrieve the translation rules assigned to a collection of trunk configuration settings, you can use syntax similar to this:</span></span>

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

<span data-ttu-id="5a2e3-135">对于每个转换规则，返回类似于以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="5a2e3-135">That returns information similar to this for each translation rule:</span></span>

<span data-ttu-id="5a2e3-136">说明：不带国家/地区代码或区号的电话号码。</span><span class="sxs-lookup"><span data-stu-id="5a2e3-136">Description : Phone numbers without a country code or area code.</span></span>

<span data-ttu-id="5a2e3-137">模式： ^\\+ （\\d\*） $</span><span class="sxs-lookup"><span data-stu-id="5a2e3-137">Pattern : ^\\+(\\d\*)$</span></span>

`Translation : $1`

<span data-ttu-id="5a2e3-138">名称： NoAreaCode</span><span class="sxs-lookup"><span data-stu-id="5a2e3-138">Name : NoAreaCode</span></span>

<span data-ttu-id="5a2e3-139">此时，您需要检查 Pattern 属性的值（它是一个[正则表达式](https://go.microsoft.com/fwlink/?linkid=400464)字符串），以查看是否有任何转换规则配置为用于处理所拨打的号码。</span><span class="sxs-lookup"><span data-stu-id="5a2e3-139">At that point, you check the value of the Pattern property (which is a [regular expression](https://go.microsoft.com/fwlink/?linkid=400464) string) to see whether any of the translation rules are configured to handle the dialed number.</span></span> <span data-ttu-id="5a2e3-140">如果不是，则必须更改现有规则之一（CsOutboundTranslationRule）或使用 CsOutboundTranslationRule cmdlet 将新规则添加到集合中。</span><span class="sxs-lookup"><span data-stu-id="5a2e3-140">If not, you'll either have to change one of the existing rules (Set-CsOutboundTranslationRule) or use the New-CsOutboundTranslationRule cmdlet to add a new rule to the collection.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5a2e3-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a2e3-141">See Also</span></span>


[<span data-ttu-id="5a2e3-142">Test-Remove-cstrunkconfiguration</span><span class="sxs-lookup"><span data-stu-id="5a2e3-142">Test-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

