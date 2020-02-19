---
title: Lync Server 2013：验证通讯簿访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02747101523351823b8abfb85a58691323262ece
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42115165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="dca68-102">在 Lync Server 2013 中验证通讯簿访问权限</span><span class="sxs-lookup"><span data-stu-id="dca68-102">Validating address book access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dca68-103">_**上次修改的主题：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="dca68-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dca68-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="dca68-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="dca68-105">每天</span><span class="sxs-lookup"><span data-stu-id="dca68-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dca68-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="dca68-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="dca68-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dca68-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dca68-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="dca68-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="dca68-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="dca68-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="dca68-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsAddressBookService cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="dca68-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="dca68-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="dca68-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="dca68-112">说明</span><span class="sxs-lookup"><span data-stu-id="dca68-112">Description</span></span>

<span data-ttu-id="dca68-113">CsAddressBookService cmdlet 提供了一种方法，用于验证用户是否可以连接到通讯簿下载 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="dca68-113">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="dca68-114">运行 cmdlet 时，CsAddressBookService 会连接到指定池上的通讯簿下载 Web 服务，并请求通讯簿文件的位置。</span><span class="sxs-lookup"><span data-stu-id="dca68-114">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="dca68-115">如果通讯簿下载 Web 服务提供该位置，则认为测试已成功。</span><span class="sxs-lookup"><span data-stu-id="dca68-115">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="dca68-116">如果请求被拒绝，则将测试视为失败。</span><span class="sxs-lookup"><span data-stu-id="dca68-116">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="dca68-117">运行测试</span><span class="sxs-lookup"><span data-stu-id="dca68-117">Running the test</span></span>

<span data-ttu-id="dca68-118">CsAddressBookService cmdlet 可以使用预配置的测试帐户（请参阅设置运行 Lync Server 测试的测试帐户）或已启用 Lync Server 的任何用户的帐户运行。</span><span class="sxs-lookup"><span data-stu-id="dca68-118">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="dca68-119">若要使用测试帐户运行此检查，您只需指定要测试的 Lync Server 池的完全限定域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="dca68-119">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="dca68-120">例如：</span><span class="sxs-lookup"><span data-stu-id="dca68-120">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="dca68-121">若要使用实际用户帐户运行此检查，必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。</span><span class="sxs-lookup"><span data-stu-id="dca68-121">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="dca68-122">然后，您必须在调用 CsAddressBookService 时包含该凭据对象和分配给该帐户的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="dca68-122">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="dca68-123">有关详细信息，请参阅[CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="dca68-123">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="dca68-124">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="dca68-124">Determining success or failure</span></span>

<span data-ttu-id="dca68-125">如果指定用户可以连接到通讯簿服务，则将返回类似于以下的输出结果，并将 Result 属性标记为**成功**：</span><span class="sxs-lookup"><span data-stu-id="dca68-125">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="dca68-126">TargetUrihttps://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="dca68-126">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="dca68-127">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dca68-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="dca68-128">结果：成功</span><span class="sxs-lookup"><span data-stu-id="dca68-128">Result : Success</span></span>

<span data-ttu-id="dca68-129">延迟：00：00：06.2260399</span><span class="sxs-lookup"><span data-stu-id="dca68-129">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="dca68-130">误差</span><span class="sxs-lookup"><span data-stu-id="dca68-130">Error :</span></span>

<span data-ttu-id="dca68-131">诊断</span><span class="sxs-lookup"><span data-stu-id="dca68-131">Diagnosis :</span></span>

<span data-ttu-id="dca68-132">如果指定用户无法建立此连接，则结果将显示为 "失败"，并将在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="dca68-132">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="dca68-133">TargetUri</span><span class="sxs-lookup"><span data-stu-id="dca68-133">TargetUri :</span></span>

<span data-ttu-id="dca68-134">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dca68-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="dca68-135">结果：失败</span><span class="sxs-lookup"><span data-stu-id="dca68-135">Result : Failure</span></span>

<span data-ttu-id="dca68-136">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="dca68-136">Latency : 00:00:00</span></span>

<span data-ttu-id="dca68-137">诊断： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，</span><span class="sxs-lookup"><span data-stu-id="dca68-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="dca68-138">原因 = 未对 SIP 启用目标 URI 或不为其启用目标 URI</span><span class="sxs-lookup"><span data-stu-id="dca68-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="dca68-139">尚.</span><span class="sxs-lookup"><span data-stu-id="dca68-139">exist.</span></span>

<span data-ttu-id="dca68-140">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="dca68-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="dca68-141">例如，由于指定的用户（即 "目标 URI"）不存在或尚未为 Lync Server 启用，因此上述输出表明测试失败。</span><span class="sxs-lookup"><span data-stu-id="dca68-141">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="dca68-142">您可以通过运行类似以下的命令来验证用户帐户是否有效，并验证是否提供了正确的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="dca68-142">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="dca68-143">Get-csuser-Identity "sip:kenmyer@litwareinc.com" |选择-对象 SipAddress，已启用</span><span class="sxs-lookup"><span data-stu-id="dca68-143">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="dca68-144">如果 CsAddressBookService 失败，您可能需要重新运行测试，这一次包括 Verbose 参数：</span><span class="sxs-lookup"><span data-stu-id="dca68-144">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="dca68-145">CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="dca68-145">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="dca68-146">当包含 Verbose 参数时，CsAddressBookService 将返回在检查指定用户登录到 Lync Server 的能力时所尝试的每个操作的分步帐户。</span><span class="sxs-lookup"><span data-stu-id="dca68-146">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="dca68-147">例如，以下示例输出显示，CsAddressBookService （至少在此示例中）可以下载通讯簿文件：</span><span class="sxs-lookup"><span data-stu-id="dca68-147">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="dca68-148">发送 Http GET 请求。</span><span class="sxs-lookup"><span data-stu-id="dca68-148">Sending Http GET Request.</span></span>

<span data-ttu-id="dca68-149">文件路径 =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="dca68-149">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="dca68-150">尝试次数 = 1</span><span class="sxs-lookup"><span data-stu-id="dca68-150">Attempt Number = 1</span></span>

<span data-ttu-id="dca68-151">TimeOut （毫秒） = 60000</span><span class="sxs-lookup"><span data-stu-id="dca68-151">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="dca68-152">成功下载了 ABS 文件https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="dca68-152">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="dca68-153">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="dca68-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="dca68-154">以下是测试 CsAddressBookService 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="dca68-154">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="dca68-155">您指定的用户帐户无效。</span><span class="sxs-lookup"><span data-stu-id="dca68-155">You specified an invalid user account.</span></span> <span data-ttu-id="dca68-156">您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：</span><span class="sxs-lookup"><span data-stu-id="dca68-156">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="dca68-157">用户帐户有效，但当前没有为 Lync Server 启用该帐户。</span><span class="sxs-lookup"><span data-stu-id="dca68-157">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="dca68-158">若要验证是否已为 Lync Server 启用了用户帐户，请运行与以下内容类似的命令：</span><span class="sxs-lookup"><span data-stu-id="dca68-158">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="dca68-159">如果 Enabled 属性设置为 False，则表示当前尚未为 Lync Server 启用用户。</span><span class="sxs-lookup"><span data-stu-id="dca68-159">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dca68-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dca68-160">See Also</span></span>


[<span data-ttu-id="dca68-161">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="dca68-161">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

