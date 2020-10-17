---
title: Lync Server 2013：验证通讯簿访问
description: Lync Server 2013：验证通讯簿访问权限。
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
ms.openlocfilehash: 6da08e48be24b3325bc1f415b9baa3c9197717c3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547238"
---
# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="14e10-103">在 Lync Server 2013 中验证通讯簿访问权限</span><span class="sxs-lookup"><span data-stu-id="14e10-103">Validating address book access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14e10-104">_**上次修改的主题：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="14e10-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14e10-105">验证计划</span><span class="sxs-lookup"><span data-stu-id="14e10-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="14e10-106">每天</span><span class="sxs-lookup"><span data-stu-id="14e10-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14e10-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="14e10-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="14e10-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="14e10-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14e10-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="14e10-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="14e10-110">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="14e10-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="14e10-111">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsAddressBookService cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="14e10-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="14e10-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="14e10-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="14e10-113">说明</span><span class="sxs-lookup"><span data-stu-id="14e10-113">Description</span></span>

<span data-ttu-id="14e10-114">Test-CsAddressBookService cmdlet 提供了一种方法，用于验证用户是否可以连接到通讯簿下载 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="14e10-114">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="14e10-115">在运行 cmdlet 时，Test-CsAddressBookService 会连接到指定池上的通讯簿下载 Web 服务，并请求通讯簿文件的位置。</span><span class="sxs-lookup"><span data-stu-id="14e10-115">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="14e10-116">如果通讯簿下载 Web 服务提供该位置，则认为测试已成功。</span><span class="sxs-lookup"><span data-stu-id="14e10-116">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="14e10-117">如果请求被拒绝，则将测试视为失败。</span><span class="sxs-lookup"><span data-stu-id="14e10-117">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="14e10-118">运行测试</span><span class="sxs-lookup"><span data-stu-id="14e10-118">Running the test</span></span>

<span data-ttu-id="14e10-119">可以使用预配置的测试帐户运行 Test-CsAddressBookService cmdlet (请参阅设置用于运行 Lync Server 测试的测试帐户) 或已为 Lync Server 启用的任何用户的帐户。</span><span class="sxs-lookup"><span data-stu-id="14e10-119">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="14e10-120">若要使用测试帐户运行此检查，您只需指定要测试的 Lync Server 池 (FQDN) 的完全限定的域名称。</span><span class="sxs-lookup"><span data-stu-id="14e10-120">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="14e10-121">例如：</span><span class="sxs-lookup"><span data-stu-id="14e10-121">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="14e10-122">若要使用实际用户帐户运行此检查，必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。</span><span class="sxs-lookup"><span data-stu-id="14e10-122">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="14e10-123">然后，您必须在调用 CsAddressBookService 时包含该凭据对象和分配给该帐户的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="14e10-123">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="14e10-124">有关详细信息，请参阅 [CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="14e10-124">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="14e10-125">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="14e10-125">Determining success or failure</span></span>

<span data-ttu-id="14e10-126">如果指定用户可以连接到通讯簿服务，则将返回类似于以下的输出结果，并将 Result 属性标记为 **成功**：</span><span class="sxs-lookup"><span data-stu-id="14e10-126">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="14e10-127">TargetUri https://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="14e10-127">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="14e10-128">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="14e10-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="14e10-129">结果：成功</span><span class="sxs-lookup"><span data-stu-id="14e10-129">Result : Success</span></span>

<span data-ttu-id="14e10-130">延迟：00：00：06.2260399</span><span class="sxs-lookup"><span data-stu-id="14e10-130">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="14e10-131">误差</span><span class="sxs-lookup"><span data-stu-id="14e10-131">Error :</span></span>

<span data-ttu-id="14e10-132">诊断</span><span class="sxs-lookup"><span data-stu-id="14e10-132">Diagnosis :</span></span>

<span data-ttu-id="14e10-133">如果指定用户无法建立此连接，则结果将显示为 "失败"，并将在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="14e10-133">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="14e10-134">TargetUri</span><span class="sxs-lookup"><span data-stu-id="14e10-134">TargetUri :</span></span>

<span data-ttu-id="14e10-135">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="14e10-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="14e10-136">结果：失败</span><span class="sxs-lookup"><span data-stu-id="14e10-136">Result : Failure</span></span>

<span data-ttu-id="14e10-137">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="14e10-137">Latency : 00:00:00</span></span>

<span data-ttu-id="14e10-138">诊断： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，</span><span class="sxs-lookup"><span data-stu-id="14e10-138">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="14e10-139">原因 = 未对 SIP 启用目标 URI 或不为其启用目标 URI</span><span class="sxs-lookup"><span data-stu-id="14e10-139">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="14e10-140">尚.</span><span class="sxs-lookup"><span data-stu-id="14e10-140">exist.</span></span>

<span data-ttu-id="14e10-141">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="14e10-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="14e10-142">例如，由于指定的用户 (即 "目标 URI" ) 不存在或尚未为 Lync Server 启用，因此上述输出表明测试失败。</span><span class="sxs-lookup"><span data-stu-id="14e10-142">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="14e10-143">您可以通过运行类似以下的命令来验证用户帐户是否有效，并验证是否提供了正确的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="14e10-143">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="14e10-144">Get-CsUser-Identity "sip:kenmyer@litwareinc.com" |Select-Object SipAddress，已启用</span><span class="sxs-lookup"><span data-stu-id="14e10-144">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="14e10-145">如果 Test-CsAddressBookService 失败，您可能需要重新运行测试，这一次包括 Verbose 参数：</span><span class="sxs-lookup"><span data-stu-id="14e10-145">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="14e10-146">Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="14e10-146">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="14e10-147">当包含详细参数时 Test-CsAddressBookService 将返回它在检查指定用户登录到 Lync Server 的能力时尝试的每个操作的分步帐户。</span><span class="sxs-lookup"><span data-stu-id="14e10-147">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="14e10-148">例如，以下示例输出显示，CsAddressBookService （至少在此示例中）可以下载通讯簿文件：</span><span class="sxs-lookup"><span data-stu-id="14e10-148">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="14e10-149">发送 Http GET 请求。</span><span class="sxs-lookup"><span data-stu-id="14e10-149">Sending Http GET Request.</span></span>

<span data-ttu-id="14e10-150">文件路径 = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="14e10-150">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="14e10-151">尝试次数 = 1</span><span class="sxs-lookup"><span data-stu-id="14e10-151">Attempt Number = 1</span></span>

<span data-ttu-id="14e10-152">TimeOut (毫秒) = 60000</span><span class="sxs-lookup"><span data-stu-id="14e10-152">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="14e10-153">成功下载了 ABS 文件 https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="14e10-153">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="14e10-154">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="14e10-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="14e10-155">下面是 Test-CsAddressBookService 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="14e10-155">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="14e10-156">您指定的用户帐户无效。</span><span class="sxs-lookup"><span data-stu-id="14e10-156">You specified an invalid user account.</span></span> <span data-ttu-id="14e10-157">您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：</span><span class="sxs-lookup"><span data-stu-id="14e10-157">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="14e10-158">用户帐户有效，但当前没有为 Lync Server 启用该帐户。</span><span class="sxs-lookup"><span data-stu-id="14e10-158">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="14e10-159">若要验证是否已为 Lync Server 启用了用户帐户，请运行与以下内容类似的命令：</span><span class="sxs-lookup"><span data-stu-id="14e10-159">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="14e10-160">如果 Enabled 属性设置为 False，则表示当前尚未为 Lync Server 启用用户。</span><span class="sxs-lookup"><span data-stu-id="14e10-160">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="14e10-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14e10-161">See Also</span></span>


[<span data-ttu-id="14e10-162">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="14e10-162">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

