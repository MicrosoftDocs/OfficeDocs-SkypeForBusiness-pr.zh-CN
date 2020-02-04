---
title: Lync Server 2013：测试使用组扩展的能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d79c5432bc2efca0d3a958d3837793eaf227b251
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="b95bc-102">测试在 Lync Server 2013 中使用组扩展的能力</span><span class="sxs-lookup"><span data-stu-id="b95bc-102">Testing ability to employ group expansion in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b95bc-103">_**主题上次修改时间：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="b95bc-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b95bc-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="b95bc-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b95bc-105">每天</span><span class="sxs-lookup"><span data-stu-id="b95bc-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b95bc-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="b95bc-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b95bc-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b95bc-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b95bc-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="b95bc-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b95bc-109">当使用 Lync Server 命令行管理程序在本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="b95bc-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b95bc-110">使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsGroupExpansion cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="b95bc-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="b95bc-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b95bc-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b95bc-112">说明</span><span class="sxs-lookup"><span data-stu-id="b95bc-112">Description</span></span>

<span data-ttu-id="b95bc-113">CsGroupExpansion cmdlet 使你可以确定组扩展是否在你的组织内工作。</span><span class="sxs-lookup"><span data-stu-id="b95bc-113">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="b95bc-114">启用组扩展后，用户将通讯组配置为联系人。</span><span class="sxs-lookup"><span data-stu-id="b95bc-114">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="b95bc-115">这意味着，这些用户可以通过将邮件寻址到组而不是该组的单个成员来向所有组成员发送相同的即时消息。</span><span class="sxs-lookup"><span data-stu-id="b95bc-115">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="b95bc-116">组扩展使你能够快速轻松地查看所有组成员及其当前状态。</span><span class="sxs-lookup"><span data-stu-id="b95bc-116">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="b95bc-117">使用 CsGroupExpansion cmdlet，你可以使用组的电子邮件地址指定 Active Directory 通讯组。</span><span class="sxs-lookup"><span data-stu-id="b95bc-117">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="b95bc-118">CsGroupExpansion 然后使用组扩展检索组成员身份，并将检索到的列表与您提供的组电子邮件地址的成员身份进行比较。</span><span class="sxs-lookup"><span data-stu-id="b95bc-118">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="b95bc-119">如果两个列表匹配，则组扩展正常工作。</span><span class="sxs-lookup"><span data-stu-id="b95bc-119">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="b95bc-120">请注意，你可以通过两种方式测试组扩展：测试服务本身或测试关联的 web 服务。</span><span class="sxs-lookup"><span data-stu-id="b95bc-120">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="b95bc-121">有关详细信息，请参阅[CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="b95bc-121">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b95bc-122">运行测试</span><span class="sxs-lookup"><span data-stu-id="b95bc-122">Running the test</span></span>

<span data-ttu-id="b95bc-123">CsGroupExpansion cmdlet 可以使用预配置的测试帐户运行（请参阅设置运行 Lync Server 测试的测试帐户）或已启用 Lync Server 的任何用户的帐户。</span><span class="sxs-lookup"><span data-stu-id="b95bc-123">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="b95bc-124">若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 池的 FQDN 和有效通讯组的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b95bc-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="b95bc-125">例如：</span><span class="sxs-lookup"><span data-stu-id="b95bc-125">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="b95bc-126">若要使用实际用户帐户运行此检查，必须首先创建一个 Lync Server 凭据对象，其中包含帐户名称和密码。</span><span class="sxs-lookup"><span data-stu-id="b95bc-126">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="b95bc-127">然后，在系统调用 Test-CsGroupExpansion 时，必须包含该凭据对象和分配给该帐户的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="b95bc-127">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="b95bc-128">有关详细信息，请参阅[CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="b95bc-128">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b95bc-129">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="b95bc-129">Determining success or failure</span></span>

<span data-ttu-id="b95bc-130">如果指定的用户可以使用组扩展，则会收到与以下内容类似的输出：结果属性标记为**成功：**</span><span class="sxs-lookup"><span data-stu-id="b95bc-130">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="b95bc-131">TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="b95bc-131">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="b95bc-132">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b95bc-132">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b95bc-133">结果：成功</span><span class="sxs-lookup"><span data-stu-id="b95bc-133">Result : Success</span></span>

<span data-ttu-id="b95bc-134">延迟：00：00：01.1234976</span><span class="sxs-lookup"><span data-stu-id="b95bc-134">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="b95bc-135">时发生</span><span class="sxs-lookup"><span data-stu-id="b95bc-135">Error :</span></span>

<span data-ttu-id="b95bc-136">自检</span><span class="sxs-lookup"><span data-stu-id="b95bc-136">Diagnosis :</span></span>

<span data-ttu-id="b95bc-137">如果指定用户不能使用组扩展，则结果将显示为 "失败"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="b95bc-137">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="b95bc-138">TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="b95bc-138">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="b95bc-139">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b95bc-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b95bc-140">结果：失败</span><span class="sxs-lookup"><span data-stu-id="b95bc-140">Result : Failure</span></span>

<span data-ttu-id="b95bc-141">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="b95bc-141">Latency : 00:00:00</span></span>

<span data-ttu-id="b95bc-142">时发生</span><span class="sxs-lookup"><span data-stu-id="b95bc-142">Error :</span></span>

<span data-ttu-id="b95bc-143">自检</span><span class="sxs-lookup"><span data-stu-id="b95bc-143">Diagnosis :</span></span>

<span data-ttu-id="b95bc-144">测试-CsGroupExpansion：终结点无法注册。</span><span class="sxs-lookup"><span data-stu-id="b95bc-144">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="b95bc-145">有关特定原因，请参阅错误代码。</span><span class="sxs-lookup"><span data-stu-id="b95bc-145">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="b95bc-146">以前的输出表明测试失败的原因是指定的用户无法向 Lync 服务器注册。</span><span class="sxs-lookup"><span data-stu-id="b95bc-146">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="b95bc-147">如果测试帐户不存在或尚未为 Lync Server 启用，则通常会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="b95bc-147">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="b95bc-148">你可以通过运行类似如下所示的命令来验证帐户是否存在，并确定是否已启用 nm-ocs-第14级帐户：</span><span class="sxs-lookup"><span data-stu-id="b95bc-148">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="b95bc-149">如果 CsGroupExpansion 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：</span><span class="sxs-lookup"><span data-stu-id="b95bc-149">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="b95bc-150">当包含 Verbose 参数时，CsGroupExpansion 将返回在检查指定用户登录到 Lync Server 的能力时尝试的每个操作的分步帐户。</span><span class="sxs-lookup"><span data-stu-id="b95bc-150">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="b95bc-151">例如，以下输出表明找不到指定的通讯组：</span><span class="sxs-lookup"><span data-stu-id="b95bc-151">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="b95bc-152">正在尝试获取 web 票证。</span><span class="sxs-lookup"><span data-stu-id="b95bc-152">Trying to get web ticket.</span></span>

<span data-ttu-id="b95bc-153">Web 服务 url：https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="b95bc-153">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="b95bc-154">使用 NTLM/Kerb auth。</span><span class="sxs-lookup"><span data-stu-id="b95bc-154">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="b95bc-155">GetWebTicketActivity 已完成。</span><span class="sxs-lookup"><span data-stu-id="b95bc-155">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="b95bc-156">已开始 "VerifyDistributionList" 活动。</span><span class="sxs-lookup"><span data-stu-id="b95bc-156">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="b95bc-157">DLX Web 服务响应状态为： NotFound。</span><span class="sxs-lookup"><span data-stu-id="b95bc-157">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="b95bc-158">"VerifyDistributionList" 活动在 "0.2597923" 秒内完成。</span><span class="sxs-lookup"><span data-stu-id="b95bc-158">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b95bc-159">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="b95bc-159">Reasons why the test might have failed</span></span>

<span data-ttu-id="b95bc-160">下面是测试 CsGroupExpansion 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="b95bc-160">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="b95bc-161">您指定了无效的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b95bc-161">You specified an invalid user account.</span></span> <span data-ttu-id="b95bc-162">你可以通过运行类似如下所示的命令来验证用户帐户是否存在：</span><span class="sxs-lookup"><span data-stu-id="b95bc-162">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="b95bc-163">用户帐户有效，但当前没有为 Lync Server 启用该帐户。</span><span class="sxs-lookup"><span data-stu-id="b95bc-163">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="b95bc-164">若要验证是否已启用 Lync Server 的用户帐户，请运行类似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="b95bc-164">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="b95bc-165">如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。</span><span class="sxs-lookup"><span data-stu-id="b95bc-165">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="b95bc-166">组扩展可能已禁用。</span><span class="sxs-lookup"><span data-stu-id="b95bc-166">Group expansion might be disabled.</span></span> <span data-ttu-id="b95bc-167">可以关闭组扩展。</span><span class="sxs-lookup"><span data-stu-id="b95bc-167">It is possible to turn off group expansion.</span></span> <span data-ttu-id="b95bc-168">如果组扩展已禁用，则 CsGroupExpansion cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="b95bc-168">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="b95bc-169">若要确定是否已启用组扩展，请使用类似下面的命令：</span><span class="sxs-lookup"><span data-stu-id="b95bc-169">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

