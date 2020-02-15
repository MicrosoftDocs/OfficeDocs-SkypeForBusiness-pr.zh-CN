---
title: Lync Server 2013：测试电话拨入式会议会话
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d83d3c3fe933a4538d9c2508668497af42c3340
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a><span data-ttu-id="361c4-102">在 Lync Server 2013 中测试电话拨入式会议会话</span><span class="sxs-lookup"><span data-stu-id="361c4-102">Testing dial-in conferencing session in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="361c4-103">_**上次修改的主题：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="361c4-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="361c4-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="361c4-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="361c4-105">每天</span><span class="sxs-lookup"><span data-stu-id="361c4-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="361c4-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="361c4-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="361c4-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="361c4-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="361c4-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="361c4-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="361c4-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="361c4-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="361c4-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-csdialinconferencing cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="361c4-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialInConferencing cmdlet.</span></span> <span data-ttu-id="361c4-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="361c4-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="361c4-112">说明</span><span class="sxs-lookup"><span data-stu-id="361c4-112">Description</span></span>

<span data-ttu-id="361c4-113">Test-csdialinconferencing cmdlet 验证用户是否可以参与电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="361c4-113">The Test-CsDialInConferencing cmdlet verifies whether a user can participate in a dial-in conference.</span></span> <span data-ttu-id="361c4-114">测试-Test-csdialinconferencing 通过尝试将测试用户登录到系统来工作。</span><span class="sxs-lookup"><span data-stu-id="361c4-114">Test-CsDialInConferencing works by trying to log a test user onto the system.</span></span> <span data-ttu-id="361c4-115">如果登录成功，则 cmdlet 将使用用户的凭据和权限来尝试所有可用的电话拨入式会议访问号码。</span><span class="sxs-lookup"><span data-stu-id="361c4-115">If the logon succeeds, the cmdlet will then use the user’s credentials and permissions to try all of the available dial-in conferencing access numbers.</span></span> <span data-ttu-id="361c4-116">将记录每个拨入尝试的成功或失败情况，然后将从 Lync Server 注销测试用户。测试 Test-csdialinconferencing 仅验证是否可以建立适当的连接。</span><span class="sxs-lookup"><span data-stu-id="361c4-116">The success or failure of each dial-in try will be noted, then the test user will be logged off from Lync Server.Test-CsDialInConferencing only verifies that the appropriate connections can be made.</span></span> <span data-ttu-id="361c4-117">Cmdlet 实际上不会进行任何电话呼叫，也不会创建任何其他用户可以加入的电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="361c4-117">The cmdlet does not actually make any phone calls or create any dial-in conferences that other users can join.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="361c4-118">运行测试</span><span class="sxs-lookup"><span data-stu-id="361c4-118">Running the test</span></span>

<span data-ttu-id="361c4-119">可以使用预配置的测试帐户（请参阅设置运行 Lync Server 测试的测试帐户）或已启用 Lync Server 的任何用户的帐户运行 Test-csdialinconferencing cmdlet。</span><span class="sxs-lookup"><span data-stu-id="361c4-119">The Test-CsDialInConferencing cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="361c4-120">若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 池的 FQDN 即可。</span><span class="sxs-lookup"><span data-stu-id="361c4-120">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="361c4-121">例如：</span><span class="sxs-lookup"><span data-stu-id="361c4-121">For example:</span></span>

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="361c4-122">若要使用实际用户帐户运行此检查，必须创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。</span><span class="sxs-lookup"><span data-stu-id="361c4-122">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="361c4-123">然后，必须将该凭据对象和帐户 SIP 地址包括在调用的 Test-csdialinconferencing：</span><span class="sxs-lookup"><span data-stu-id="361c4-123">You must then include that credentials object and the account SIP address the calling Test-CsDialInConferencing:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="361c4-124">有关详细信息，请参阅[test-csdialinconferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="361c4-124">For more information, see the Help documentation for the [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="361c4-125">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="361c4-125">Determining success or failure</span></span>

<span data-ttu-id="361c4-126">如果指定用户可以登录到 Lync Server，然后使用其中一个可用的电话拨入式会议访问号码进行连接，则会收到类似于以下内容的输出，并将 Result 属性标记为 "**成功"：**</span><span class="sxs-lookup"><span data-stu-id="361c4-126">If the specified user can log on to Lync Server and then make a connection using one of the available dial-in conferencing access numbers, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="361c4-127">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="361c4-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="361c4-128">结果：成功</span><span class="sxs-lookup"><span data-stu-id="361c4-128">Result : Success</span></span>

<span data-ttu-id="361c4-129">延迟：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="361c4-129">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="361c4-130">误差</span><span class="sxs-lookup"><span data-stu-id="361c4-130">Error :</span></span>

<span data-ttu-id="361c4-131">诊断</span><span class="sxs-lookup"><span data-stu-id="361c4-131">Diagnosis :</span></span>

<span data-ttu-id="361c4-132">如果指定的用户无法建立此连接，则结果将显示为 "失败"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="361c4-132">If the specified user can't make this connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="361c4-133">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="361c4-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="361c4-134">结果：失败</span><span class="sxs-lookup"><span data-stu-id="361c4-134">Result : Failure</span></span>

<span data-ttu-id="361c4-135">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="361c4-135">Latency : 00:00:00</span></span>

<span data-ttu-id="361c4-136">错误：登录被拒绝。</span><span class="sxs-lookup"><span data-stu-id="361c4-136">Error : The log on was denied.</span></span> <span data-ttu-id="361c4-137">检查正确的凭据是否</span><span class="sxs-lookup"><span data-stu-id="361c4-137">Check that the proper credentials are</span></span>

<span data-ttu-id="361c4-138">正在使用，帐户处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="361c4-138">being used and the account is active.</span></span>

<span data-ttu-id="361c4-139">内部异常： NegotiateSecurityAssociation 失败，错误：-</span><span class="sxs-lookup"><span data-stu-id="361c4-139">Inner Exception:NegotiateSecurityAssociation failed, error: -</span></span>

<span data-ttu-id="361c4-140">2146893044</span><span class="sxs-lookup"><span data-stu-id="361c4-140">2146893044</span></span>

<span data-ttu-id="361c4-141">诊断</span><span class="sxs-lookup"><span data-stu-id="361c4-141">Diagnosis :</span></span>

<span data-ttu-id="361c4-142">以前的输出指示已拒绝测试用户对 Lync Server 本身的访问。</span><span class="sxs-lookup"><span data-stu-id="361c4-142">The previous output indicates that the test user was denied access to Lync Server itself.</span></span> <span data-ttu-id="361c4-143">这通常意味着传递给 Test-Test-csdialinconferencing 的用户凭据无效。</span><span class="sxs-lookup"><span data-stu-id="361c4-143">This typically means that the user credentials passed to Test-CsDialInConferencing were not valid.</span></span> <span data-ttu-id="361c4-144">反过来，您应该重新创建 Windows PowerShell 凭据对象。</span><span class="sxs-lookup"><span data-stu-id="361c4-144">In turn, you should re-create the Windows PowerShell credentials object.</span></span> <span data-ttu-id="361c4-145">虽然您可以检索用户帐户的密码，但您可以通过使用类似如下的命令来验证 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="361c4-145">Although you can retrieve the password for the user account, you can verify the SIP address by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="361c4-146">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="361c4-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="361c4-147">以下是测试 Test-csdialinconferencing 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="361c4-147">Here are some common reasons why Test-CsDialInConferencing might fail:</span></span>

  - <span data-ttu-id="361c4-148">您指定的用户帐户无效。</span><span class="sxs-lookup"><span data-stu-id="361c4-148">You specified a user account that is not valid.</span></span> <span data-ttu-id="361c4-149">您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：</span><span class="sxs-lookup"><span data-stu-id="361c4-149">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="361c4-150">用户帐户有效，但当前未对 Lync Server 启用该帐户。</span><span class="sxs-lookup"><span data-stu-id="361c4-150">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="361c4-151">若要验证是否已为 Lync Server 启用用户帐户，请运行与以下内容类似的命令：</span><span class="sxs-lookup"><span data-stu-id="361c4-151">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="361c4-152">如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。</span><span class="sxs-lookup"><span data-stu-id="361c4-152">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="361c4-153">您可能有一个不正确的电话拨入式会议访问号码。</span><span class="sxs-lookup"><span data-stu-id="361c4-153">You might have an incorrect dial-in conferencing access number.</span></span> <span data-ttu-id="361c4-154">您可以使用以下命令返回当前配置的电话拨入式会议访问号码列表：</span><span class="sxs-lookup"><span data-stu-id="361c4-154">You can return your currently-configured list of dial-in conferencing access numbers by using this command:</span></span>
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

