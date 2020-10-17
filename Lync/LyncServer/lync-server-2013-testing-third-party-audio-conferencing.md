---
title: Lync Server 2013：测试第三方音频会议
description: Lync Server 2013：测试第三方音频会议。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f009d95834768d8a4e6619a79ff1f3be0a2b92bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556098"
---
# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a><span data-ttu-id="59a26-103">在 Lync Server 2013 中测试第三方音频会议</span><span class="sxs-lookup"><span data-stu-id="59a26-103">Testing third-party audio conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59a26-104">_**上次修改的主题：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="59a26-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59a26-105">验证计划</span><span class="sxs-lookup"><span data-stu-id="59a26-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="59a26-106">每天</span><span class="sxs-lookup"><span data-stu-id="59a26-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59a26-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="59a26-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="59a26-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="59a26-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59a26-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="59a26-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="59a26-110">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="59a26-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="59a26-111">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsAudioConferencingProvider cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="59a26-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAudioConferencingProvider cmdlet.</span></span> <span data-ttu-id="59a26-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="59a26-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="59a26-113">说明</span><span class="sxs-lookup"><span data-stu-id="59a26-113">Description</span></span>

<span data-ttu-id="59a26-p102">音频会议提供商是为组织提供会议服务的第三方公司。此外，音频会议提供商使外出且未连接到企业网络或 Internet 的用户可以通过音频参加会议。音频会议提供商通常会提供一些高端服务，例如实时翻译、转录和每个会议的实时接线员协助。</span><span class="sxs-lookup"><span data-stu-id="59a26-p102">An audio conferencing provider is a third-party company that provides organizations with conferencing services. Among other things, audio conferencing providers enable users located off site, and not connected to the corporate network or the Internet, to participate in the audio portion of a conference or meeting. Audio conferencing providers often provide high-end services such as live translation, transcription, and live per-conference operator assistance.</span></span>

<span data-ttu-id="59a26-117">**CsAudioConferencingProvider** cmdlet 用于验证用户是否能够建立与他/她的音频会议提供商的连接。</span><span class="sxs-lookup"><span data-stu-id="59a26-117">The **Test-CsAudioConferencingProvider** cmdlet is used to verify that a user is able to make a connection to his or her audio conferencing provider.</span></span> <span data-ttu-id="59a26-118">请注意，此 cmdlet 可以采用两种方式之一运行。</span><span class="sxs-lookup"><span data-stu-id="59a26-118">Note that this cmdlet can be run in one of two ways.</span></span> <span data-ttu-id="59a26-119">许多管理员会使用 CsHealthMonitoringConfiguration cmdlet 为其每个注册器池设置测试用户。</span><span class="sxs-lookup"><span data-stu-id="59a26-119">Many administrators will use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="59a26-120">这些测试用户表示预先配置的与综合事务配合使用的一对用户帐户。</span><span class="sxs-lookup"><span data-stu-id="59a26-120">These test users represent a pair of user accounts that have been preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="59a26-121"> (通常是测试帐户，而不是属于实际用户的帐户。 ) 如果为池配置了测试用户，则管理员可以对该池运行 **CsAudioConferencingProvider** cmdlet，而无需指定 (的标识，并提供用于) 测试中所涉及的用户帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="59a26-121">(Typically these are test accounts and not accounts that belong to actual users.) If test users are configured for a pool, administrators can run the **Test-CsAudioConferencingProvider** cmdlet against that pool without having to specify the identity of (and supply the credentials for) the user account involved in the test.</span></span>

<span data-ttu-id="59a26-122">此外，管理员还可以使用实际用户帐户运行 **CsAudioConferencingProvider** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="59a26-122">Alternatively, administrators can run the **Test-CsAudioConferencingProvider** cmdlet using an actual user account.</span></span> <span data-ttu-id="59a26-123">如果您决定使用实际用户帐户进行测试，则需要提供该帐户的登录名和密码。</span><span class="sxs-lookup"><span data-stu-id="59a26-123">If you decide to conduct the test using an actual user account you will need to supply the logon name and password for that account.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="59a26-124">运行测试</span><span class="sxs-lookup"><span data-stu-id="59a26-124">Running the test</span></span>

<span data-ttu-id="59a26-125">示例 1 检查为池 atl-cs-001.litwareinc.com 定义的测试用户能否连接到其音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="59a26-125">Example 1 checks to see if a test user defined for the pool atl-cs-001.litwareinc.com is able to connect to his or her audio conferencing provider.</span></span> <span data-ttu-id="59a26-126">该命令要求为池定义了至少一个测试用户。</span><span class="sxs-lookup"><span data-stu-id="59a26-126">This command requires that at least one test user be defined for the pool.</span></span> <span data-ttu-id="59a26-127">如果没有为 atl-cs-001.litwareinc.com 定义测试用户，则该命令将失败;这是因为 **CsAudioConferencingProvider** cmdlet 将不知道在测试中使用哪个用户。</span><span class="sxs-lookup"><span data-stu-id="59a26-127">If no test users have been defined for atl-cs-001.litwareinc.com, then the command will fail; that's because the **Test-CsAudioConferencingProvider** cmdlet will not know which user to employ in the test.</span></span> <span data-ttu-id="59a26-128">如果没有为池定义测试用户，则必须包括 UserSipAddress 参数以及该命令在验证与音频会议提供商的连接时应使用的用户帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="59a26-128">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user account that the command should employ when verifying the connection with an audio conferencing provider.</span></span>

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

<span data-ttu-id="59a26-129">示例2中显示的命令测试特定用户 (litwareinc kenmyer) 的功能 \\ ，以连接到其音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="59a26-129">The commands shown in Example 2 test the ability of a specific user (litwareinc\\kenmyer) to connect to his audio conferencing provider.</span></span> <span data-ttu-id="59a26-130">若要执行此操作，示例中的第一个命令使用 Get-Credential cmdlet 来创建 Windows PowerShell 命令行接口凭据对象，其中包含用户 Ken Myer 的名称和密码。</span><span class="sxs-lookup"><span data-stu-id="59a26-130">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credentials object containing the name and password of the user Ken Myer.</span></span> <span data-ttu-id="59a26-131"> (因为登录名 litwareinc \\ kenmyer 已作为参数包括在内，所以 "Windows PowerShell 凭据请求" 对话框仅要求管理员输入 Ken Myer 帐户的密码。 ) 生成的凭据对象存储在名为 $credential 的变量中。</span><span class="sxs-lookup"><span data-stu-id="59a26-131">(Because the logon name litwareinc\\kenmyer has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Myer account.) The resulting credentials object is stored in a variable named $credential.</span></span>

<span data-ttu-id="59a26-132">然后第二个命令检查此用户能否连接到其音频会议提供商。</span><span class="sxs-lookup"><span data-stu-id="59a26-132">The second command then checks to see if this user can connect to his audio conferencing provider.</span></span> <span data-ttu-id="59a26-133">若要执行此任务，请调用 Test-CsAudioConferencingProvider cmdlet 以及以下三个参数： TargetFqdn (注册器池的 FQDN) ;UserCredential (包含 Ken Myer 的用户凭据的 Windows PowerShell 对象) ;和 UserSipAddress (与提供的用户凭据) 对应的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="59a26-133">To carry out this task, the Test-CsAudioConferencingProvider cmdlet is called, along with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object containing Ken Myer's user credentials); and UserSipAddress (the SIP address corresponding to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="59a26-134">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="59a26-134">Determining success or failure</span></span>

<span data-ttu-id="59a26-135">如果正确配置了音频会议提供商，则会收到与以下内容类似的输出，并将 Result 属性标记为 **成功：**</span><span class="sxs-lookup"><span data-stu-id="59a26-135">If the audio conferencing provider is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="59a26-136">目标 Fqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="59a26-136">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="59a26-137">结果：成功</span><span class="sxs-lookup"><span data-stu-id="59a26-137">Result : Success</span></span>

<span data-ttu-id="59a26-138">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="59a26-138">Latency : 00:00:00</span></span>

<span data-ttu-id="59a26-139">错误消息：</span><span class="sxs-lookup"><span data-stu-id="59a26-139">Error Message :</span></span>

<span data-ttu-id="59a26-140">诊断</span><span class="sxs-lookup"><span data-stu-id="59a26-140">Diagnosis :</span></span>

<span data-ttu-id="59a26-141">如果指定的用户无法登录或注销，则结果将显示为 " **失败**"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="59a26-141">If the specified user can't log on or log off, the Result will be shown as a **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="59a26-142">目标 Fqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="59a26-142">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="59a26-143">结果：失败</span><span class="sxs-lookup"><span data-stu-id="59a26-143">Result : Failure</span></span>

<span data-ttu-id="59a26-144">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="59a26-144">Latency : 00:00:00</span></span>

<span data-ttu-id="59a26-145">错误消息：10060，连接尝试失败，因为连接方</span><span class="sxs-lookup"><span data-stu-id="59a26-145">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="59a26-146">在一段时间后未正确响应，或者</span><span class="sxs-lookup"><span data-stu-id="59a26-146">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="59a26-147">已建立连接失败，因为连接的主机具有</span><span class="sxs-lookup"><span data-stu-id="59a26-147">established connection failed because connected host has</span></span>

<span data-ttu-id="59a26-148">无法响应 \[ 2001：4898： e8： f39e：5c9a： ad83：81b3： 9944 \] ：5061</span><span class="sxs-lookup"><span data-stu-id="59a26-148">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="59a26-149">内部异常：连接尝试失败，因为</span><span class="sxs-lookup"><span data-stu-id="59a26-149">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="59a26-150">连接方在一段时间后未正确响应</span><span class="sxs-lookup"><span data-stu-id="59a26-150">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="59a26-151">时间，或已建立的连接失败，因为连接的主机</span><span class="sxs-lookup"><span data-stu-id="59a26-151">time, or established connection failed because connected host</span></span>

<span data-ttu-id="59a26-152">未能响应</span><span class="sxs-lookup"><span data-stu-id="59a26-152">has failed to respond</span></span>

<span data-ttu-id="59a26-153">\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944 \] ：5061</span><span class="sxs-lookup"><span data-stu-id="59a26-153">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="59a26-154">诊断</span><span class="sxs-lookup"><span data-stu-id="59a26-154">Diagnosis :</span></span>

<span data-ttu-id="59a26-155">例如，以前的输出包括 "连接方未正确响应" 这一说明，这通常表示边缘服务器存在问题。</span><span class="sxs-lookup"><span data-stu-id="59a26-155">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="59a26-156">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="59a26-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="59a26-157">以下是 **测试 CsAudioConferencingProvider** 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="59a26-157">Here are some common reasons why **Test-CsAudioConferencingProvider** might fail:</span></span>

  - <span data-ttu-id="59a26-158">提供的参数值不正确。</span><span class="sxs-lookup"><span data-stu-id="59a26-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="59a26-159">如前面的示例中所示，必须正确配置可选参数或测试将失败。</span><span class="sxs-lookup"><span data-stu-id="59a26-159">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="59a26-160">重新运行不带可选参数的命令，并查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="59a26-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="59a26-161">请注意，如果尚未为 **CsAudioConferencingProvider** cmdlet 所采用的用户分配音频会议提供商，则测试将失败。</span><span class="sxs-lookup"><span data-stu-id="59a26-161">Note that the test will fail if the user employed by the **Test-CsAudioConferencingProvider** cmdlet has not been assigned an audio conferencing provider.</span></span>

  - <span data-ttu-id="59a26-162">如果边缘服务器配置错误或尚未部署，则此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="59a26-162">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

