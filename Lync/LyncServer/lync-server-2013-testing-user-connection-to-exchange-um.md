---
title: Lync Server 2013：测试用户到 Exchange UM 的连接
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
ms.openlocfilehash: 0d4a4c4194ad730a64b167aaaf33151c8a7684e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a><span data-ttu-id="1ebc3-102">在 Lync Server 2013 中测试用户到 Exchange UM 的连接</span><span class="sxs-lookup"><span data-stu-id="1ebc3-102">Testing user connection to Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ebc3-103">_**主题上次修改时间：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="1ebc3-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ebc3-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="1ebc3-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1ebc3-105">每天</span><span class="sxs-lookup"><span data-stu-id="1ebc3-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ebc3-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="1ebc3-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1ebc3-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ebc3-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ebc3-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="1ebc3-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1ebc3-109">当使用 Lync Server 命令行管理程序在本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1ebc3-110">使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行<strong>CsExUMConnectivity</strong> cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMConnectivity</strong> cmdlet.</span></span> <span data-ttu-id="1ebc3-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1ebc3-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1ebc3-112">说明</span><span class="sxs-lookup"><span data-stu-id="1ebc3-112">Description</span></span>

<span data-ttu-id="1ebc3-113">**CsExUMConnectivity** cmdlet 验证指定的用户是否可以连接到 Microsoft Exchange Server 2013 统一消息服务。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-113">The **Test-CsExUMConnectivity** cmdlet verifies that the specified user can connect to the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="1ebc3-114">请注意，此 cmdlet 仅验证是否可以与服务建立连接。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-114">Note that this cmdlet only verifies that a connection can be made to the service.</span></span> <span data-ttu-id="1ebc3-115">它不会测试服务本身。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-115">It does not test the service itself.</span></span> <span data-ttu-id="1ebc3-116">若要测试统一消息服务（通过运行可在用户邮箱中实际保留语音邮件的合成事务 cmdlet），请使用 CsExUMVoiceMail cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-116">To test the unified messaging service (by running a synthetic transaction cmdlet that actually leaves a voice mail message in a user's mailbox) use the Test-CsExUMVoiceMail cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1ebc3-117">运行测试</span><span class="sxs-lookup"><span data-stu-id="1ebc3-117">Running the test</span></span>

<span data-ttu-id="1ebc3-118">以下示例测试 pool atl-cs-001.litwareinc.com 的 Exchange 统一消息连接。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-118">The following example tests Exchange Unified Messaging connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="1ebc3-119">仅当为池 atl-cs-001.litwareinc.com 定义了测试用户时，此命令才会运行。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-119">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="1ebc3-120">如果有，则该命令将确定第一个测试用户是否可以连接到统一消息。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-120">If they have, then the command will determine whether the first test user can connect to Unified Messaging.</span></span> <span data-ttu-id="1ebc3-121">如果没有为池配置测试用户，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-121">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="1ebc3-122">以下示例中所示的命令为用户 litwareinc\\Kenmyer 测试 Exchange 统一消息连接。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-122">The commands shown in the following example test Exchange Unified Messaging connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="1ebc3-123">为此，示例中的第一个命令使用了**Get 凭据**cmdlet 为用户 litwareinc\\kenmyer 创建 Windows PowerShell 命令行界面凭据对象。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-123">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="1ebc3-124">请注意，你必须为此帐户提供密码才能创建有效的凭据对象，并确保**CsExUMConnectivity** cmdlet 可以运行其检查。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-124">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMConnectivity** cmdlet can run its check.</span></span>

<span data-ttu-id="1ebc3-125">示例中的第二个命令使用提供的凭据对象（$x）和用户 litwareinc\\KENMYER 的 SIP 地址，以确定是否或此用户可以连接到 Exchange 统一消息。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-125">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="1ebc3-126">下一个示例中所示的命令是刚才显示的命令的变体。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-126">The command shown in the next example is a variation of the command just shown.</span></span> <span data-ttu-id="1ebc3-127">在这种情况下，将包含 OutLoggerVariable 参数，以便为**测试 CsExUMConnectivity** cmdletand 每个步骤的成功或失败生成每个步骤所执行步骤的详细日志。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-127">In this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMConnectivity** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="1ebc3-128">若要执行此操作，请将 OutLoggerVariable 参数与参数值一起添加 ExumText;这会导致详细日志记录信息存储在名为 $ExumTest 的变量中。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-128">To do this, the OutLoggerVariable parameter is added together with the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="1ebc3-129">在该示例的最后一个命令中，ToXML （）方法用于将日志信息转换为 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-129">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="1ebc3-130">然后，将该 XML 数据写入一个名为 C：\\的文件，\\该文件使用 Out-file cmdlet 来记录 ExumTest。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-130">That XML data is then written to a file that is named C:\\Logs\\ExumTest.xml by using the Out-File cmdlet.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1ebc3-131">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="1ebc3-131">Determining success or failure</span></span>

<span data-ttu-id="1ebc3-132">如果已正确配置 Exchange 集成，你将收到类似于此的输出，并将 Result 属性标记为**成功**：</span><span class="sxs-lookup"><span data-stu-id="1ebc3-132">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="1ebc3-133">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1ebc3-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1ebc3-134">结果：成功</span><span class="sxs-lookup"><span data-stu-id="1ebc3-134">Result : Success</span></span>

<span data-ttu-id="1ebc3-135">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="1ebc3-135">Latency : 00:00:00</span></span>

<span data-ttu-id="1ebc3-136">错误消息：</span><span class="sxs-lookup"><span data-stu-id="1ebc3-136">Error Message :</span></span>

<span data-ttu-id="1ebc3-137">自检</span><span class="sxs-lookup"><span data-stu-id="1ebc3-137">Diagnosis :</span></span>

<span data-ttu-id="1ebc3-138">如果指定的用户无法接收通知，则结果将显示为 "**失败**"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="1ebc3-138">If the specified user can't receive notifications, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="1ebc3-139">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1ebc3-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1ebc3-140">结果：失败</span><span class="sxs-lookup"><span data-stu-id="1ebc3-140">Result : Failure</span></span>

<span data-ttu-id="1ebc3-141">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="1ebc3-141">Latency : 00:00:00</span></span>

<span data-ttu-id="1ebc3-142">错误消息：10060，连接尝试失败，因为已连接的参与方</span><span class="sxs-lookup"><span data-stu-id="1ebc3-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="1ebc3-143">在一段时间后未正确响应，或者</span><span class="sxs-lookup"><span data-stu-id="1ebc3-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="1ebc3-144">已建立连接失败，因为连接的主机已</span><span class="sxs-lookup"><span data-stu-id="1ebc3-144">established connection failed because connected host has</span></span>

<span data-ttu-id="1ebc3-145">无法响应10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="1ebc3-145">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="1ebc3-146">内部异常：连接尝试失败，因为</span><span class="sxs-lookup"><span data-stu-id="1ebc3-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="1ebc3-147">已连接方在一段时间后未正确响应</span><span class="sxs-lookup"><span data-stu-id="1ebc3-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="1ebc3-148">时间，或已建立的连接失败，因为已连接的主机</span><span class="sxs-lookup"><span data-stu-id="1ebc3-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="1ebc3-149">无法响应10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="1ebc3-149">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="1ebc3-150">自检</span><span class="sxs-lookup"><span data-stu-id="1ebc3-150">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1ebc3-151">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="1ebc3-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="1ebc3-152">下面是**测试 CsExUMConnectivity**可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="1ebc3-152">Here are some common reasons why **Test-CsExUMConnectivity** might fail:</span></span>

  - <span data-ttu-id="1ebc3-153">提供的参数值不正确。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-153">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="1ebc3-154">如果使用，则必须正确配置可选参数，否则测试将失败。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-154">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="1ebc3-155">重新运行不带可选参数的命令，并查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-155">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="1ebc3-156">如果 Exchange 服务器配置错误或尚未部署，此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-156">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

  - <span data-ttu-id="1ebc3-157">如果无法通过网络访问 Exchange 服务器，此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="1ebc3-157">This command will fail if the Exchange Server is not reachable over your network.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1ebc3-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ebc3-158">See Also</span></span>


[<span data-ttu-id="1ebc3-159">Test-CsExUMVoiceMail</span><span class="sxs-lookup"><span data-stu-id="1ebc3-159">Test-CsExUMVoiceMail</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

