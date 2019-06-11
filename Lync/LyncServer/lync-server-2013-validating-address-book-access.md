---
title: 'Lync Server 2013: 验证通讯簿访问'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 233ad9804ea0f9ddd1075ea01bf7a4c8f35da819
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="a9d65-102">在 Lync Server 2013 中验证通讯簿访问</span><span class="sxs-lookup"><span data-stu-id="a9d65-102">Validating address book access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9d65-103">_**主题上次修改时间:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="a9d65-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9d65-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="a9d65-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a9d65-105">每天</span><span class="sxs-lookup"><span data-stu-id="a9d65-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9d65-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="a9d65-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a9d65-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9d65-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9d65-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="a9d65-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a9d65-109">当使用 Lync Server 命令行管理程序在本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="a9d65-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a9d65-110">使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsAddressBookService cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="a9d65-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="a9d65-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="a9d65-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a9d65-112">说明</span><span class="sxs-lookup"><span data-stu-id="a9d65-112">Description</span></span>

<span data-ttu-id="a9d65-113">CsAddressBookService cmdlet 为你提供一种验证用户是否可以连接到通讯簿下载 Web 服务的方法。</span><span class="sxs-lookup"><span data-stu-id="a9d65-113">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="a9d65-114">运行 cmdlet 时, CsAddressBookService 将连接到指定池上的通讯簿下载 Web 服务, 并请求通讯簿文件的位置。</span><span class="sxs-lookup"><span data-stu-id="a9d65-114">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="a9d65-115">如果 "通讯簿" 下载 Web 服务提供该位置, 则该测试视为成功。</span><span class="sxs-lookup"><span data-stu-id="a9d65-115">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="a9d65-116">如果请求被拒绝, 则测试被视为失败。</span><span class="sxs-lookup"><span data-stu-id="a9d65-116">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a9d65-117">运行测试</span><span class="sxs-lookup"><span data-stu-id="a9d65-117">Running the test</span></span>

<span data-ttu-id="a9d65-118">CsAddressBookService cmdlet 可以使用预配置的测试帐户运行 (请参阅设置运行 Lync Server 测试的测试帐户) 或已为 Lync Server 启用的任何用户的帐户。</span><span class="sxs-lookup"><span data-stu-id="a9d65-118">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="a9d65-119">若要使用测试帐户运行此检查, 只需指定正在测试的 Lync Server 池的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="a9d65-119">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="a9d65-120">例如：</span><span class="sxs-lookup"><span data-stu-id="a9d65-120">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="a9d65-121">若要使用实际用户帐户运行此检查, 必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。</span><span class="sxs-lookup"><span data-stu-id="a9d65-121">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="a9d65-122">然后, 在调用 Test-CsAddressBookService 时, 必须包含该凭据对象和分配给该帐户的 SIP 地址:</span><span class="sxs-lookup"><span data-stu-id="a9d65-122">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="a9d65-123">有关详细信息, 请参阅[CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="a9d65-123">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a9d65-124">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="a9d65-124">Determining success or failure</span></span>

<span data-ttu-id="a9d65-125">如果指定用户能够连接到通讯簿服务, 则会返回与此类似的输出, 结果属性标记为**成功**:</span><span class="sxs-lookup"><span data-stu-id="a9d65-125">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="a9d65-126">TargetUri :https://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="a9d65-126">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="a9d65-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a9d65-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a9d65-128">结果: 成功</span><span class="sxs-lookup"><span data-stu-id="a9d65-128">Result : Success</span></span>

<span data-ttu-id="a9d65-129">延迟:00:00: 06.2260399</span><span class="sxs-lookup"><span data-stu-id="a9d65-129">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="a9d65-130">时发生</span><span class="sxs-lookup"><span data-stu-id="a9d65-130">Error :</span></span>

<span data-ttu-id="a9d65-131">自检</span><span class="sxs-lookup"><span data-stu-id="a9d65-131">Diagnosis :</span></span>

<span data-ttu-id="a9d65-132">如果指定用户无法进行此连接, 则结果将显示为 "失败", 并且将在 "错误" 和 "诊断" 属性中记录其他信息:</span><span class="sxs-lookup"><span data-stu-id="a9d65-132">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="a9d65-133">TargetUri :</span><span class="sxs-lookup"><span data-stu-id="a9d65-133">TargetUri :</span></span>

<span data-ttu-id="a9d65-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a9d65-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a9d65-135">结果: 失败</span><span class="sxs-lookup"><span data-stu-id="a9d65-135">Result : Failure</span></span>

<span data-ttu-id="a9d65-136">延迟: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="a9d65-136">Latency : 00:00:00</span></span>

<span data-ttu-id="a9d65-137">诊断: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="a9d65-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="a9d65-138">原因 = 没有为 SIP 启用目标 URI, 或者没有为其启用目标 URI</span><span class="sxs-lookup"><span data-stu-id="a9d65-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="a9d65-139">并存.</span><span class="sxs-lookup"><span data-stu-id="a9d65-139">exist.</span></span>

<span data-ttu-id="a9d65-140">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="a9d65-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="a9d65-141">例如, 由于指定的用户 (即 "目标 URI") 不存在或尚未为 Lync Server 启用, 因此上述输出表明测试失败。</span><span class="sxs-lookup"><span data-stu-id="a9d65-141">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="a9d65-142">你可以验证用户帐户是否有效, 并通过运行类似的命令验证你提供的 SIP 地址是否正确:</span><span class="sxs-lookup"><span data-stu-id="a9d65-142">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="a9d65-143">Move-csuser-Identity "sip:kenmyer@litwareinc.com" |选择-对象 SipAddress, 已启用</span><span class="sxs-lookup"><span data-stu-id="a9d65-143">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="a9d65-144">如果测试 CsAddressBookService 失败, 您可能需要重新运行测试, 这一次包括 Verbose 参数:</span><span class="sxs-lookup"><span data-stu-id="a9d65-144">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="a9d65-145">Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="a9d65-145">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="a9d65-146">当包含 Verbose 参数时, CsAddressBookService 将返回它在检查指定用户登录到 Lync Server 的能力时尝试的每个操作的分步帐户。</span><span class="sxs-lookup"><span data-stu-id="a9d65-146">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="a9d65-147">例如, 此示例输出显示, CsAddressBookService 在此示例中至少可以下载通讯簿文件:</span><span class="sxs-lookup"><span data-stu-id="a9d65-147">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="a9d65-148">发送 Http GET 请求。</span><span class="sxs-lookup"><span data-stu-id="a9d65-148">Sending Http GET Request.</span></span>

<span data-ttu-id="a9d65-149">文件路径 =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="a9d65-149">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="a9d65-150">尝试次数 = 1</span><span class="sxs-lookup"><span data-stu-id="a9d65-150">Attempt Number = 1</span></span>

<span data-ttu-id="a9d65-151">TimeOut (毫秒) = 60000</span><span class="sxs-lookup"><span data-stu-id="a9d65-151">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="a9d65-152">已成功下载 ABS 文件https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="a9d65-152">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a9d65-153">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="a9d65-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="a9d65-154">下面是测试 CsAddressBookService 可能失败的一些常见原因:</span><span class="sxs-lookup"><span data-stu-id="a9d65-154">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="a9d65-155">您指定了无效的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a9d65-155">You specified an invalid user account.</span></span> <span data-ttu-id="a9d65-156">你可以通过运行类似如下所示的命令来验证用户帐户是否存在:</span><span class="sxs-lookup"><span data-stu-id="a9d65-156">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="a9d65-157">用户帐户有效, 但当前未为 Lync Server 启用该帐户。</span><span class="sxs-lookup"><span data-stu-id="a9d65-157">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="a9d65-158">若要验证是否已启用 Lync Server 的用户帐户, 请运行类似以下内容的命令:</span><span class="sxs-lookup"><span data-stu-id="a9d65-158">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="a9d65-159">如果 Enabled 属性设置为 False, 则表示当前尚未为 Lync Server 启用用户。</span><span class="sxs-lookup"><span data-stu-id="a9d65-159">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a9d65-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9d65-160">See Also</span></span>


[<span data-ttu-id="a9d65-161">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="a9d65-161">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

