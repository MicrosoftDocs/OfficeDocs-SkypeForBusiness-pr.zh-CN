---
title: Lync Server 2013：检查语音规范化规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52820473a632598779aae9023967598b8ae27f89
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="c2b1a-102">在 Lync Server 2013 中检查语音规范化规则</span><span class="sxs-lookup"><span data-stu-id="c2b1a-102">Check voice normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2b1a-103">_**上次修改的主题：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="c2b1a-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2b1a-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="c2b1a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c2b1a-105">每月</span><span class="sxs-lookup"><span data-stu-id="c2b1a-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2b1a-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="c2b1a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c2b1a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2b1a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2b1a-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="c2b1a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c2b1a-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="c2b1a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c2b1a-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsVoiceNormalizationRule cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="c2b1a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceNormalizationRule cmdlet.</span></span> <span data-ttu-id="c2b1a-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c2b1a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c2b1a-112">说明</span><span class="sxs-lookup"><span data-stu-id="c2b1a-112">Description</span></span>

<span data-ttu-id="c2b1a-113">语音规范化规则用于将用户拨打的电话号码（例如，2065551219）转换为 Lync Server 使用的164格式（+ 12065551219）。</span><span class="sxs-lookup"><span data-stu-id="c2b1a-113">Voice normalization rules are used to convert a phone number dialed by a user (for example, 2065551219) to the E.164 format that is used by Lync Server (+12065551219).</span></span> <span data-ttu-id="c2b1a-114">例如，如果用户习惯于拨打电话号码，而不包括国家/地区代码或区号（例如，5551219），则您必须有一个可以将该号码转换为. 164 格式的语音规范化规则： + 12065551219。</span><span class="sxs-lookup"><span data-stu-id="c2b1a-114">For example, if users are in the habit of dialing a phone number without including the country code or the area code (e.g., 5551219) then you must have a voice normalization rule that can convert that number to the E.164 format: +12065551219.</span></span> <span data-ttu-id="c2b1a-115">如果没有此类规则，则用户将无法调用555-1219。</span><span class="sxs-lookup"><span data-stu-id="c2b1a-115">Without such a rule, the user won't be able to call 555-1219.</span></span>

<span data-ttu-id="c2b1a-116">CsVoiceNormalizationRule cmdlet 验证指定的语音规范化规则是否可以成功转换指定的电话号码。</span><span class="sxs-lookup"><span data-stu-id="c2b1a-116">The Test-CsVoiceNormalizationRule cmdlet verifies that a specified voice normalization rule can successfully convert a specified phone number.</span></span> <span data-ttu-id="c2b1a-117">例如，此命令会检查全局规范化规则 NoAreaCode 是否可以规范化和转换拨号字符串5551219。</span><span class="sxs-lookup"><span data-stu-id="c2b1a-117">For example, this command checks whether the global normalization rule NoAreaCode can normalize and convert the dial string 5551219.</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c2b1a-118">运行测试</span><span class="sxs-lookup"><span data-stu-id="c2b1a-118">Running the test</span></span>

<span data-ttu-id="c2b1a-119">若要运行 CsVoiceNormalizationRule cmdlet，必须首先使用 CsVoiceNormalizationRule cmdlet 检索正在测试的规则的实例，然后通过管道将该实例指定为 Test-CsVoiceNormalizationRule。</span><span class="sxs-lookup"><span data-stu-id="c2b1a-119">To run the Test-CsVoiceNormalizationRule cmdlet, you must first use the Get-CsVoiceNormalizationRule cmdlet to retrieve an instance of the rule being tested, and then pipe that instance to Test-CsVoiceNormalizationRule.</span></span> <span data-ttu-id="c2b1a-120">与此类似的语法不起作用：</span><span class="sxs-lookup"><span data-stu-id="c2b1a-120">Syntax similar to this won't work:</span></span>

<span data-ttu-id="c2b1a-121">CsVoiceNormalizationRule-DialedNumber "12065551219" – NormalizationRule "global/Prefix All"</span><span class="sxs-lookup"><span data-stu-id="c2b1a-121">Test-CsVoiceNormalizationRule -DialedNumber "12065551219" –NormalizationRule "global/Prefix All"</span></span>

<span data-ttu-id="c2b1a-122">请改用如下所示的语法，其中组合了 CsVoiceNormalizationRule 和 CsVoiceNormalizationRule cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c2b1a-122">Instead, use syntax such as the following, which combines both the Get-CsVoiceNormalizationRule and the Test-CsVoiceNormalizationRule cmdlets:</span></span>

<span data-ttu-id="c2b1a-123">CsVoiceNormalizationRule-Identity "global/Prefix All" |CsVoiceNormalizationRule-DialedNumber "12065551219"</span><span class="sxs-lookup"><span data-stu-id="c2b1a-123">Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Test-CsVoiceNormalizationRule -DialedNumber "12065551219"</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c2b1a-124">.</span><span class="sxs-lookup"><span data-stu-id="c2b1a-124">.</span></span> <span data-ttu-id="c2b1a-125">或者，您也可以使用此方法检索规则的实例，然后针对指定的电话号码测试该规则：</span><span class="sxs-lookup"><span data-stu-id="c2b1a-125">Or, you can also use this approach to retrieve an instance of a rule and then test that rule against a specified phone number:</span></span>



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

<span data-ttu-id="c2b1a-126">输入 DialedNumber 参数的值，完全就像您预期要拨打的号码一样。</span><span class="sxs-lookup"><span data-stu-id="c2b1a-126">Enter the value for the DialedNumber parameter exactly as you expect that number to be dialed.</span></span> <span data-ttu-id="c2b1a-127">例如，如果指定的语音规范化规则应自动添加国家/地区代码（值12065551219中的第1个），则应保留国家/地区代码：</span><span class="sxs-lookup"><span data-stu-id="c2b1a-127">For example, if the specified voice normalization rule is supposed to automatically add the country code (the initial 1 in the value 12065551219) then you should leave off the country code:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="c2b1a-128">如果正确配置了规则，则会在将号码转换为 Lync Server 使用的 e.164 格式时自动添加国家/地区代码。</span><span class="sxs-lookup"><span data-stu-id="c2b1a-128">If the rule is configured correctly, it will automatically add the country code when translating the number to the E.164 format that is used by Lync Server.</span></span>

<span data-ttu-id="c2b1a-129">有关详细信息，请参阅 CsVoiceNormalizationRule cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="c2b1a-129">For more information, see the Help documentation for the Test-CsVoiceNormalizationRule cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c2b1a-130">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="c2b1a-130">Determining success or failure</span></span>

<span data-ttu-id="c2b1a-131">如果指定的语音规范化规则可以转换所提供的数字，则会在屏幕上显示转换后的数字：</span><span class="sxs-lookup"><span data-stu-id="c2b1a-131">If the specified voice normalization rule can translate the supplied number then the translated number will be displayed on-screen:</span></span>

<span data-ttu-id="c2b1a-132">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="c2b1a-132">TranslatedNumber</span></span>

\----------------

<span data-ttu-id="c2b1a-133">\+12065551219</span><span class="sxs-lookup"><span data-stu-id="c2b1a-133">\+12065551219</span></span>

<span data-ttu-id="c2b1a-134">如果测试失败，则返回一个空的已翻译数字：</span><span class="sxs-lookup"><span data-stu-id="c2b1a-134">If the test fails then a blank translated number will be returned:</span></span>

<span data-ttu-id="c2b1a-135">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="c2b1a-135">TranslatedNumber</span></span>

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c2b1a-136">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="c2b1a-136">Reasons why the test might have failed</span></span>

<span data-ttu-id="c2b1a-137">如果 CsVoiceNormalizationRule 确实返回一个已翻译的号码，这意味着指定的语音规范化规则无法将提供的电话号码转换为 Lync Server 使用的 e.164 格式。</span><span class="sxs-lookup"><span data-stu-id="c2b1a-137">If the Test-CsVoiceNormalizationRule does return a translated number that means that the specified voice normalization rule was unable to translate the supplied telephone number into the E.164 format that is used by Lync Server.</span></span> <span data-ttu-id="c2b1a-138">若要验证这一点，请首先确保键入的电话号码正确。</span><span class="sxs-lookup"><span data-stu-id="c2b1a-138">To verify that, first make sure that you typed the telephone number in correctly.</span></span> <span data-ttu-id="c2b1a-139">例如，您可能希望语音规范化规则在翻译类似以下内容的数字时遇到问题：</span><span class="sxs-lookup"><span data-stu-id="c2b1a-139">For example, you would expect your voice normalization rule to have problems translating a number similar to this:</span></span>

`-DialedNumber "1"`

<span data-ttu-id="c2b1a-140">如果正确输入了号码，下一步应是验证指定的规范化规则是否设计为可处理该电话号码。</span><span class="sxs-lookup"><span data-stu-id="c2b1a-140">Assuming the number was entered correctly, your next step should be to verify that the specified normalization rule is designed to handle that phone number.</span></span> <span data-ttu-id="c2b1a-141">例如，一个规范化规则设计为可处理格式12065551219，但第二个规则可能设计为处理数字2065551219。</span><span class="sxs-lookup"><span data-stu-id="c2b1a-141">For example, one normalization rule might be designed to handle the format 12065551219, but a second rule might be designed to handle the number 2065551219.</span></span> <span data-ttu-id="c2b1a-142">（这是与开头的国家/地区代码1相同的电话号码。）若要返回有关语音规范化规则的详细信息，请运行与以下内容类似的命令：</span><span class="sxs-lookup"><span data-stu-id="c2b1a-142">(That’s the same phone number, minus the country code 1 at the very beginning.) To return detailed information about a voice normalization rule, run a command similar to this:</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

<span data-ttu-id="c2b1a-143">若要返回有关所有语音规范化规则的详细信息，请改为运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c2b1a-143">To return detailed information about all the voice normalization rules, run this command instead:</span></span>

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c2b1a-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2b1a-144">See Also</span></span>


[<span data-ttu-id="c2b1a-145">Test-CsVoiceNormalizationRule</span><span class="sxs-lookup"><span data-stu-id="c2b1a-145">Test-CsVoiceNormalizationRule</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

