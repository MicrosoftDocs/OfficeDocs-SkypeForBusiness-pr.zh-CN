---
title: Lync Server 2013：测试用户与 Exchange UM 语音邮件的连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa3ad3f51d1342ac99d3c58be66931ba0770bf6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a><span data-ttu-id="da661-102">在 Lync Server 2013 中测试用户与 Exchange UM 语音邮件的连接</span><span class="sxs-lookup"><span data-stu-id="da661-102">Testing user connection to Exchange UM voicemail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da661-103">_**上次修改的主题：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="da661-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da661-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="da661-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="da661-105">每天</span><span class="sxs-lookup"><span data-stu-id="da661-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da661-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="da661-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="da661-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="da661-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da661-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="da661-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="da661-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="da661-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="da661-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行<strong>CsExUMVoiceMail</strong> cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="da661-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMVoiceMail</strong> cmdlet.</span></span> <span data-ttu-id="da661-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="da661-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="da661-112">说明</span><span class="sxs-lookup"><span data-stu-id="da661-112">Description</span></span>

<span data-ttu-id="da661-113">**CsExUMVoiceMail** cmdlet 使管理员能够验证用户是否可以访问和使用 Microsoft Exchange Server 2013 统一消息服务。</span><span class="sxs-lookup"><span data-stu-id="da661-113">The **Test-CsExUMVoiceMail** cmdlet enables administrators to verify that a user can access and use the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="da661-114">为此，cmdlet 连接到统一消息服务并将语音邮件留在指定的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="da661-114">To do this, the cmdlet connects to the unified messaging service and leaves a voice mail in the specified mailbox.</span></span> <span data-ttu-id="da661-115">这可以是系统提供的语音邮件，也可以是您自己记录的定制 .WAV 文件。</span><span class="sxs-lookup"><span data-stu-id="da661-115">This can be a system-supplied voice mail, or it can be a custom .WAV file that you have recorded yourself.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="da661-116">运行测试</span><span class="sxs-lookup"><span data-stu-id="da661-116">Running the test</span></span>

<span data-ttu-id="da661-117">下面的示例测试 pool atl-cs-001.litwareinc.com 的 Exchange 统一消息语音邮件连接。</span><span class="sxs-lookup"><span data-stu-id="da661-117">The following example tests Exchange Unified Messaging voice mail connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="da661-118">仅当为池 atl-cs-001.litwareinc.com 定义了测试用户时，才能使用此命令。</span><span class="sxs-lookup"><span data-stu-id="da661-118">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="da661-119">如果有，则该命令将确定第一个测试用户是否可以使用统一消息语音邮件。</span><span class="sxs-lookup"><span data-stu-id="da661-119">If they have, then the command will determine whether the first test user can use Unified Messaging voice mail.</span></span> <span data-ttu-id="da661-120">如果没有为池配置测试用户，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="da661-120">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="da661-121">下一个示例中所示的命令为用户 litwareinc\\Kenmyer 测试 Exchange 统一消息语音邮件连接。</span><span class="sxs-lookup"><span data-stu-id="da661-121">The commands shown in the next example test Exchange Unified Messaging voice mail connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="da661-122">若要执行此操作，示例中的第一个命令使用了**Get Credential** cmdlet 为用户 litwareinc\\kenmyer 创建 Windows PowerShell 命令行接口凭据对象。</span><span class="sxs-lookup"><span data-stu-id="da661-122">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="da661-123">请注意，您必须为此帐户提供密码才能创建有效的凭据对象，并确保**CsExUMVoiceMail** cmdlet 可以运行其检查。</span><span class="sxs-lookup"><span data-stu-id="da661-123">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMVoiceMail** cmdlet can run its check.</span></span>

<span data-ttu-id="da661-124">该示例中的第二个命令使用提供的凭据对象（$x）和用户 litwareinc\\KENMYER 的 SIP 地址，以确定此用户是否可以连接到 Exchange 统一消息语音邮件。</span><span class="sxs-lookup"><span data-stu-id="da661-124">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging voice mail.</span></span>

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

<span data-ttu-id="da661-125">在下一个示例中显示的命令是示例1中显示的命令的变体。在这种情况下，将包含 OutLoggerVariable 参数，以生成由**测试 CsExUMVoiceMail**执行的每个步骤的详细日志，cmdletand 每个步骤的成功或失败。</span><span class="sxs-lookup"><span data-stu-id="da661-125">The command shown in the next example is a variation of the command shown in Example 1; in this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMVoiceMail** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="da661-126">为此，请在参数值的旁边添加 OutLoggerVariable 参数 ExumText;这会导致详细的日志记录信息存储在名为 $ExumTest 的变量中。</span><span class="sxs-lookup"><span data-stu-id="da661-126">To do this, the OutLoggerVariable parameter is added alongside the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="da661-127">在示例的最后一个命令中，ToXML() 方法用于将日志信息转换为 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="da661-127">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="da661-128">然后，将 XML 数据写入到一个名为 C：\\的文件中\\，并使用 Out file cmdlet 来记录 VoicemailTest。</span><span class="sxs-lookup"><span data-stu-id="da661-128">That XML data is then written to a file that is named C:\\Logs\\VoicemailTest.xml by using the Out-File cmdlet.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="da661-129">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="da661-129">Determining success or failure</span></span>

<span data-ttu-id="da661-130">如果已正确配置 Exchange 集成，则会收到类似于以下内容的输出，并将 Result 属性标记为**成功**：</span><span class="sxs-lookup"><span data-stu-id="da661-130">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="da661-131">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="da661-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="da661-132">结果：成功</span><span class="sxs-lookup"><span data-stu-id="da661-132">Result : Success</span></span>

<span data-ttu-id="da661-133">延迟：00：00：02.9911345</span><span class="sxs-lookup"><span data-stu-id="da661-133">Latency : 00:00:02.9911345</span></span>

<span data-ttu-id="da661-134">错误消息：</span><span class="sxs-lookup"><span data-stu-id="da661-134">Error Message :</span></span>

<span data-ttu-id="da661-135">诊断</span><span class="sxs-lookup"><span data-stu-id="da661-135">Diagnosis :</span></span>

<span data-ttu-id="da661-136">如果指定用户无法连接到语音邮件，则结果将显示为 "**失败**"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="da661-136">If the specified user can't connect to voicemail, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="da661-137">警告：无法读取给定的完全限定的注册器端口号</span><span class="sxs-lookup"><span data-stu-id="da661-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="da661-138">域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="da661-138">domain name (FQDN).</span></span> <span data-ttu-id="da661-139">使用默认注册器端口号。</span><span class="sxs-lookup"><span data-stu-id="da661-139">Using default Registrar port number.</span></span> <span data-ttu-id="da661-140">异常</span><span class="sxs-lookup"><span data-stu-id="da661-140">Exception:</span></span>

<span data-ttu-id="da661-141">InvalidOperationException：在拓扑中找不到匹配的群集。</span><span class="sxs-lookup"><span data-stu-id="da661-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="da661-142">个</span><span class="sxs-lookup"><span data-stu-id="da661-142">at</span></span>

<span data-ttu-id="da661-143">TryRetri 的 SipSyntheticTransaction。 SyntheticTransactions</span><span class="sxs-lookup"><span data-stu-id="da661-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="da661-144">eveRegistrarPortFromTopology （Int32& registrarPortNumber）</span><span class="sxs-lookup"><span data-stu-id="da661-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="da661-145">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="da661-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="da661-146">结果：失败</span><span class="sxs-lookup"><span data-stu-id="da661-146">Result : Failure</span></span>

<span data-ttu-id="da661-147">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="da661-147">Latency : 00:00:00</span></span>

<span data-ttu-id="da661-148">错误消息：10060，连接尝试失败，因为连接方</span><span class="sxs-lookup"><span data-stu-id="da661-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="da661-149">在一段时间后未正确响应，或者</span><span class="sxs-lookup"><span data-stu-id="da661-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="da661-150">已建立连接失败，因为连接的主机具有</span><span class="sxs-lookup"><span data-stu-id="da661-150">established connection failed because connected host has</span></span>

<span data-ttu-id="da661-151">未能响应10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="da661-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="da661-152">内部异常：连接尝试失败，因为</span><span class="sxs-lookup"><span data-stu-id="da661-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="da661-153">连接方在一段时间后未正确响应</span><span class="sxs-lookup"><span data-stu-id="da661-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="da661-154">时间，或已建立的连接失败，因为连接的主机</span><span class="sxs-lookup"><span data-stu-id="da661-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="da661-155">未能响应10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="da661-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="da661-156">诊断</span><span class="sxs-lookup"><span data-stu-id="da661-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="da661-157">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="da661-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="da661-158">以下是**测试 CsExUMVoiceMail**可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="da661-158">Here are some common reasons why **Test-CsExUMVoiceMail** might fail:</span></span>

  - <span data-ttu-id="da661-159">提供的参数值不正确。</span><span class="sxs-lookup"><span data-stu-id="da661-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="da661-160">如果使用，则必须正确配置可选参数或测试将失败。</span><span class="sxs-lookup"><span data-stu-id="da661-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="da661-161">重新运行不带可选参数的命令，并查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="da661-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="da661-162">如果 Exchange 服务器配置错误或尚未部署，则此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="da661-162">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="da661-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da661-163">See Also</span></span>


[<span data-ttu-id="da661-164">Test-Test-csexumconnectivity</span><span class="sxs-lookup"><span data-stu-id="da661-164">Test-CsExUMConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

