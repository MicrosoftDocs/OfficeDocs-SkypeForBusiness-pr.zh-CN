---
title: Lync Server 2013：测试副本服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e30d0b8c0e570605c8c6556d42224a205741a821
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503959"
---
# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="9ddc0-102">在 Lync Server 2013 中测试副本服务</span><span class="sxs-lookup"><span data-stu-id="9ddc0-102">Testing the replica service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ddc0-103">_**上次修改的主题：** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="9ddc0-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ddc0-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="9ddc0-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9ddc0-105">每天</span><span class="sxs-lookup"><span data-stu-id="9ddc0-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ddc0-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="9ddc0-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9ddc0-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ddc0-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ddc0-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="9ddc0-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9ddc0-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9ddc0-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 <strong>CsReplica</strong> cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="9ddc0-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9ddc0-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9ddc0-112">说明</span><span class="sxs-lookup"><span data-stu-id="9ddc0-112">Description</span></span>

<span data-ttu-id="9ddc0-113">**CsReplica** Cmdlet 验证 Lync Server 2013 副本服务是否正在本地计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-113">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="9ddc0-114">**CsReplica** cmdlet 执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="9ddc0-114">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="9ddc0-115">检查复制器代理和集中日志记录代理服务的状态</span><span class="sxs-lookup"><span data-stu-id="9ddc0-115">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="9ddc0-116">验证是否已在 Windows 防火墙中打开所需的端口</span><span class="sxs-lookup"><span data-stu-id="9ddc0-116">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="9ddc0-117">确保所需的 Active Directory 和本地计算机安全组存在。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-117">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="9ddc0-118">请注意，此 cmdlet 必须在本地运行。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-118">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="9ddc0-119">也就是说，它必须在运行副本服务的同一台计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-119">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="9ddc0-120">没有用于对远程服务器运行 **CsReplica** cmdlet 的选项。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-120">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9ddc0-121">运行测试</span><span class="sxs-lookup"><span data-stu-id="9ddc0-121">Running the test</span></span>

<span data-ttu-id="9ddc0-122">示例1中显示的命令测试本地计算机上的 Lync Server 2013 副本服务。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-122">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="9ddc0-123">在此示例中，Verbose 参数用于确保有关测试的信息（包括测试的最终故障或成功）以及由测试生成的报告的位置显示在屏幕上。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-123">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="9ddc0-124">示例 2 是示例 1 中显示的命令的变体。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-124">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="9ddc0-125">在这种情况下，将包含 Report 参数，以指定由测试生成的报告的文件夹路径和名称。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-125">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="9ddc0-126">如果不指定报告路径，将向报告提供如下所示的自动生成的名称：</span><span class="sxs-lookup"><span data-stu-id="9ddc0-126">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="9ddc0-127">C： \\ 用户 \\ Litwareinc \\ AppData \\ 本地 \\ 临时 \\ 1 \\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span><span class="sxs-lookup"><span data-stu-id="9ddc0-127">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9ddc0-128">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="9ddc0-128">Determining success or failure</span></span>

<span data-ttu-id="9ddc0-129">在此处插入章节正文。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-129">Insert section body here.</span></span>

<span data-ttu-id="9ddc0-130">详细：创建新的日志文件 "C： \\ 用户 \\ 测试 \\ AppData \\ 本地 \\ 临时 \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml"。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-130">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="9ddc0-131">详细：创建新的日志文件 "C： \\ 用户 \\ 测试 \\ AppData \\ 本地 \\ 临时 \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml"。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="9ddc0-132">详细： "Test-CsReplica" 处理已成功完成。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-132">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="9ddc0-133">详细：可在 "C： \\ 用户 \\ 测试 \\ AppData \\ 本地 \\ 临时 \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml" 中找到详细结果。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-133">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="9ddc0-134">详细：创建新的日志文件</span><span class="sxs-lookup"><span data-stu-id="9ddc0-134">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="9ddc0-135">"C： \\ 用户 \\ 测试 \\ AppData \\ 本地 \\ 临时 \\ 2 \\ 测试-CsReplica-29fddb35-f56e-4e3c-8f4c-e"</span><span class="sxs-lookup"><span data-stu-id="9ddc0-135">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="9ddc0-136">d3bd0e4a083.xml "。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-136">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="9ddc0-137">详细：创建新的日志文件</span><span class="sxs-lookup"><span data-stu-id="9ddc0-137">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="9ddc0-138">"C： \\ 用户 \\ 测试 \\ AppData \\ 本地 \\ 临时 \\ 2 \\ 测试-CsReplica-29fddb35-f56e-4e3c-8f4c-e"</span><span class="sxs-lookup"><span data-stu-id="9ddc0-138">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="9ddc0-139">d3bd0e4a083.html "。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-139">d3bd0e4a083.html".</span></span>

<span data-ttu-id="9ddc0-140">警告： Test-CsReplica 失败。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-140">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="9ddc0-141">警告：详细结果可在以下位置找到：</span><span class="sxs-lookup"><span data-stu-id="9ddc0-141">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="9ddc0-142">"C： \\ 用户 \\ 测试 \\ AppData \\ 本地 \\ 临时 \\ 2 \\ 测试-CsReplica-29fddb35-f56e-4e3c-8f4c-e"</span><span class="sxs-lookup"><span data-stu-id="9ddc0-142">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="9ddc0-143">d3bd0e4a083.html "。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-143">d3bd0e4a083.html".</span></span>

<span data-ttu-id="9ddc0-144">Test-CsReplica：命令执行失败：请求的注册表访问不是</span><span class="sxs-lookup"><span data-stu-id="9ddc0-144">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="9ddc0-145">支持.</span><span class="sxs-lookup"><span data-stu-id="9ddc0-145">allowed.</span></span>

<span data-ttu-id="9ddc0-146">位于第1行：1个字符：1</span><span class="sxs-lookup"><span data-stu-id="9ddc0-146">At line:1 char:1</span></span>

<span data-ttu-id="9ddc0-147">\+ Test-CsReplica-详细</span><span class="sxs-lookup"><span data-stu-id="9ddc0-147">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="9ddc0-148">\+ CategoryInfo： InvalidOperation： (： ) \[ Test-CsReplica \] 、Security</span><span class="sxs-lookup"><span data-stu-id="9ddc0-148">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="9ddc0-149">异常</span><span class="sxs-lookup"><span data-stu-id="9ddc0-149">Exception</span></span>

<span data-ttu-id="9ddc0-150">\+ FullyQualifiedErrorId： ProcessingFailed，Microsoft .aspx. .Deploy</span><span class="sxs-lookup"><span data-stu-id="9ddc0-150">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="9ddc0-151">。TestReplicaCmdlet</span><span class="sxs-lookup"><span data-stu-id="9ddc0-151">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="9ddc0-152">PS C： \\ 用户 \\ 测试\></span><span class="sxs-lookup"><span data-stu-id="9ddc0-152">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="9ddc0-153">PS C： \\ 用户 \\ 测试 \> Test-CsUcwaConference TargetFqdn "LyncTest"</span><span class="sxs-lookup"><span data-stu-id="9ddc0-153">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="9ddc0-154">icrosoft.com "</span><span class="sxs-lookup"><span data-stu-id="9ddc0-154">icrosoft.com"</span></span>

<span data-ttu-id="9ddc0-155">警告：无法读取给定的完全限定的注册器端口号</span><span class="sxs-lookup"><span data-stu-id="9ddc0-155">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="9ddc0-156"> (FQDN) 的域名称。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-156">domain name (FQDN).</span></span> <span data-ttu-id="9ddc0-157">使用默认注册器端口号。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-157">Using default Registrar port number.</span></span> <span data-ttu-id="9ddc0-158">异常</span><span class="sxs-lookup"><span data-stu-id="9ddc0-158">Exception:</span></span>

<span data-ttu-id="9ddc0-159">InvalidOperationException：在拓扑中找不到匹配的群集。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-159">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="9ddc0-160">个</span><span class="sxs-lookup"><span data-stu-id="9ddc0-160">at</span></span>

<span data-ttu-id="9ddc0-161">TryRetri 的 SipSyntheticTransaction。 SyntheticTransactions</span><span class="sxs-lookup"><span data-stu-id="9ddc0-161">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="9ddc0-162">eveRegistrarPortFromTopology (Int32& registrarPortNumber) </span><span class="sxs-lookup"><span data-stu-id="9ddc0-162">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="9ddc0-163">Test-CsUcwaConference：没有分配的测试用户</span><span class="sxs-lookup"><span data-stu-id="9ddc0-163">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="9ddc0-164">\[LyncTest.SelfHost.Corp.Microsoft.com \] 。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="9ddc0-165">验证测试用户配置。</span><span class="sxs-lookup"><span data-stu-id="9ddc0-165">Verify test user configuration.</span></span>

<span data-ttu-id="9ddc0-166">位于第1行：1个字符：1</span><span class="sxs-lookup"><span data-stu-id="9ddc0-166">At line:1 char:1</span></span>

<span data-ttu-id="9ddc0-167">\+ Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="9ddc0-167">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="9ddc0-168">\+ CategoryInfo： ResourceUnavailable： (： ) \[ Test-test-csucwaconference\]</span><span class="sxs-lookup"><span data-stu-id="9ddc0-168">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="9ddc0-169">，InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="9ddc0-169">, InvalidOperationException</span></span>

<span data-ttu-id="9ddc0-170">\+ FullyQualifiedErrorId： NotFoundTestUsers、</span><span class="sxs-lookup"><span data-stu-id="9ddc0-170">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="9ddc0-171">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="9ddc0-171">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9ddc0-172">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="9ddc0-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="9ddc0-173">以下是 **测试 CsReplica** 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="9ddc0-173">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="9ddc0-174">副本复制器代理和集中日志记录代理服务可能存在更大的问题</span><span class="sxs-lookup"><span data-stu-id="9ddc0-174">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="9ddc0-175">可能未在 Windows 防火墙中打开所需的端口</span><span class="sxs-lookup"><span data-stu-id="9ddc0-175">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="9ddc0-176">必需的 Active Directory 和本地计算机安全组可能不存在</span><span class="sxs-lookup"><span data-stu-id="9ddc0-176">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

