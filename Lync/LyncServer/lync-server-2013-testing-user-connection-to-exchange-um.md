---
title: Lync Server 2013：测试用户与 Exchange UM 的连接
description: Lync Server 2013：测试用户与 Exchange UM 的连接。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea6f7d446fe3fd98db67bab4ffee9cc976202689
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556060"
---
# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a><span data-ttu-id="370db-103">在 Lync Server 2013 中测试用户与 Exchange UM 的连接</span><span class="sxs-lookup"><span data-stu-id="370db-103">Testing user connection to Exchange UM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="370db-104">_**上次修改的主题：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="370db-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="370db-105">验证计划</span><span class="sxs-lookup"><span data-stu-id="370db-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="370db-106">每天</span><span class="sxs-lookup"><span data-stu-id="370db-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="370db-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="370db-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="370db-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="370db-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="370db-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="370db-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="370db-110">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="370db-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="370db-111">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 <strong>test-csexumconnectivity</strong> cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="370db-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMConnectivity</strong> cmdlet.</span></span> <span data-ttu-id="370db-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="370db-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="370db-113">说明</span><span class="sxs-lookup"><span data-stu-id="370db-113">Description</span></span>

<span data-ttu-id="370db-114">**Test-csexumconnectivity** cmdlet 验证指定的用户是否可以连接到 Microsoft Exchange Server 2013 统一消息服务。</span><span class="sxs-lookup"><span data-stu-id="370db-114">The **Test-CsExUMConnectivity** cmdlet verifies that the specified user can connect to the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="370db-115">请注意，此 cmdlet 仅验证是否可以与服务建立连接。</span><span class="sxs-lookup"><span data-stu-id="370db-115">Note that this cmdlet only verifies that a connection can be made to the service.</span></span> <span data-ttu-id="370db-116">它不测试服务本身。</span><span class="sxs-lookup"><span data-stu-id="370db-116">It does not test the service itself.</span></span> <span data-ttu-id="370db-117">若要测试统一消息服务（通过运行实际在用户的邮箱中留下语音邮件的综合事务 cmdlet），请使用 Test-CsExUMVoiceMail cmdlet。</span><span class="sxs-lookup"><span data-stu-id="370db-117">To test the unified messaging service (by running a synthetic transaction cmdlet that actually leaves a voice mail message in a user's mailbox) use the Test-CsExUMVoiceMail cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="370db-118">运行测试</span><span class="sxs-lookup"><span data-stu-id="370db-118">Running the test</span></span>

<span data-ttu-id="370db-119">下面的示例测试 pool atl-cs-001.litwareinc.com 的 Exchange 统一消息连接。</span><span class="sxs-lookup"><span data-stu-id="370db-119">The following example tests Exchange Unified Messaging connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="370db-120">仅当为池 atl-cs-001.litwareinc.com 定义了测试用户时，才能使用此命令。</span><span class="sxs-lookup"><span data-stu-id="370db-120">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="370db-121">如果有，则该命令将确定第一个测试用户是否可以连接到统一消息。</span><span class="sxs-lookup"><span data-stu-id="370db-121">If they have, then the command will determine whether the first test user can connect to Unified Messaging.</span></span> <span data-ttu-id="370db-122">如果没有为池配置测试用户，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="370db-122">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="370db-123">以下示例中所示的命令测试用户 litwareinc kenmyer 的 Exchange 统一消息连接 \\ 。</span><span class="sxs-lookup"><span data-stu-id="370db-123">The commands shown in the following example test Exchange Unified Messaging connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="370db-124">若要执行此操作，示例中的第一个命令使用了 **Get Credential** cmdlet 为用户 litwareinc Kenmyer 创建 Windows PowerShell 命令行接口凭据对象 \\ 。</span><span class="sxs-lookup"><span data-stu-id="370db-124">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="370db-125">请注意，您必须为此帐户提供密码才能创建有效的凭据对象，并确保 **test-csexumconnectivity** cmdlet 可以运行其检查。</span><span class="sxs-lookup"><span data-stu-id="370db-125">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMConnectivity** cmdlet can run its check.</span></span>

<span data-ttu-id="370db-126">该示例中的第二个命令使用提供的凭据对象 ($x) 和用户 litwareinc kenmyer 的 SIP 地址， \\ 以确定用户是否可以连接到 Exchange 统一消息。</span><span class="sxs-lookup"><span data-stu-id="370db-126">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="370db-127">下一个示例中所示的命令是刚刚显示的命令的变体。</span><span class="sxs-lookup"><span data-stu-id="370db-127">The command shown in the next example is a variation of the command just shown.</span></span> <span data-ttu-id="370db-128">在这种情况下，将包含 OutLoggerVariable 参数，以生成由 **测试 test-csexumconnectivity** 执行的每个步骤的详细日志，cmdletand 每个步骤的成功或失败。</span><span class="sxs-lookup"><span data-stu-id="370db-128">In this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMConnectivity** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="370db-129">若要执行此操作，请将 OutLoggerVariable 参数添加到参数值 ExumText 中。这会导致详细的日志记录信息存储在名为 $ExumTest 的变量中。</span><span class="sxs-lookup"><span data-stu-id="370db-129">To do this, the OutLoggerVariable parameter is added together with the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="370db-130">在示例的最后一个命令中，ToXML() 方法用于将日志信息转换为 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="370db-130">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="370db-131">然后，将 XML 数据写入名为 C： LogsExumTest.xml 的文件 \\ ， \\ 方法是使用 Out-File cmdlet。</span><span class="sxs-lookup"><span data-stu-id="370db-131">That XML data is then written to a file that is named C:\\Logs\\ExumTest.xml by using the Out-File cmdlet.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="370db-132">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="370db-132">Determining success or failure</span></span>

<span data-ttu-id="370db-133">如果已正确配置 Exchange 集成，则会收到类似于以下内容的输出，并将 Result 属性标记为 **成功**：</span><span class="sxs-lookup"><span data-stu-id="370db-133">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="370db-134">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="370db-134">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="370db-135">结果：成功</span><span class="sxs-lookup"><span data-stu-id="370db-135">Result : Success</span></span>

<span data-ttu-id="370db-136">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="370db-136">Latency : 00:00:00</span></span>

<span data-ttu-id="370db-137">错误消息：</span><span class="sxs-lookup"><span data-stu-id="370db-137">Error Message :</span></span>

<span data-ttu-id="370db-138">诊断</span><span class="sxs-lookup"><span data-stu-id="370db-138">Diagnosis :</span></span>

<span data-ttu-id="370db-139">如果指定的用户无法接收通知，则结果将显示为 " **失败**"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="370db-139">If the specified user can't receive notifications, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="370db-140">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="370db-140">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="370db-141">结果：失败</span><span class="sxs-lookup"><span data-stu-id="370db-141">Result : Failure</span></span>

<span data-ttu-id="370db-142">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="370db-142">Latency : 00:00:00</span></span>

<span data-ttu-id="370db-143">错误消息：10060，连接尝试失败，因为连接方</span><span class="sxs-lookup"><span data-stu-id="370db-143">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="370db-144">在一段时间后未正确响应，或者</span><span class="sxs-lookup"><span data-stu-id="370db-144">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="370db-145">已建立连接失败，因为连接的主机具有</span><span class="sxs-lookup"><span data-stu-id="370db-145">established connection failed because connected host has</span></span>

<span data-ttu-id="370db-146">未能响应10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="370db-146">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="370db-147">内部异常：连接尝试失败，因为</span><span class="sxs-lookup"><span data-stu-id="370db-147">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="370db-148">连接方在一段时间后未正确响应</span><span class="sxs-lookup"><span data-stu-id="370db-148">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="370db-149">时间，或已建立的连接失败，因为连接的主机</span><span class="sxs-lookup"><span data-stu-id="370db-149">time, or established connection failed because connected host</span></span>

<span data-ttu-id="370db-150">未能响应10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="370db-150">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="370db-151">诊断</span><span class="sxs-lookup"><span data-stu-id="370db-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="370db-152">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="370db-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="370db-153">以下是 **测试 test-csexumconnectivity** 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="370db-153">Here are some common reasons why **Test-CsExUMConnectivity** might fail:</span></span>

  - <span data-ttu-id="370db-154">提供的参数值不正确。</span><span class="sxs-lookup"><span data-stu-id="370db-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="370db-155">如果使用，则必须正确配置可选参数或测试将失败。</span><span class="sxs-lookup"><span data-stu-id="370db-155">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="370db-156">重新运行不带可选参数的命令，并查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="370db-156">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="370db-157">如果 Exchange 服务器配置错误或尚未部署，则此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="370db-157">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

  - <span data-ttu-id="370db-158">如果无法通过网络访问 Exchange 服务器，则此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="370db-158">This command will fail if the Exchange Server is not reachable over your network.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="370db-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="370db-159">See Also</span></span>


[<span data-ttu-id="370db-160">Test-CsExUMVoiceMail</span><span class="sxs-lookup"><span data-stu-id="370db-160">Test-CsExUMVoiceMail</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

