---
title: Lync Server 2013：测试 IIS 服务器配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8893964ce1982c67dc97ed93bca9ba19ec2f24e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536009"
---
# <a name="testing-lis-server-configuration-in-lync-server-2013"></a><span data-ttu-id="226e7-102">在 Lync Server 2013 中测试 IIS 服务器配置</span><span class="sxs-lookup"><span data-stu-id="226e7-102">Testing LIS server configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="226e7-103">_**上次修改的主题：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="226e7-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="226e7-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="226e7-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="226e7-105">每天</span><span class="sxs-lookup"><span data-stu-id="226e7-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="226e7-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="226e7-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="226e7-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="226e7-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="226e7-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="226e7-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="226e7-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="226e7-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="226e7-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsLisConfiguration cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="226e7-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLisConfiguration cmdlet.</span></span> <span data-ttu-id="226e7-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="226e7-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="226e7-112">说明</span><span class="sxs-lookup"><span data-stu-id="226e7-112">Description</span></span>

<span data-ttu-id="226e7-113">Test-CsLisConfiguration cmdlet 可验证您是否能够联系 IIS web 服务。</span><span class="sxs-lookup"><span data-stu-id="226e7-113">The Test-CsLisConfiguration cmdlet verifies your ability to contact the LIS web service.</span></span> <span data-ttu-id="226e7-114">如果可以联系到 web 服务，则会将测试视为成功，而不管是否找到了任何特定位置。</span><span class="sxs-lookup"><span data-stu-id="226e7-114">If the web service can be contacted, then the test will be considered a success, regardless of whether any specific locations can be found.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="226e7-115">运行测试</span><span class="sxs-lookup"><span data-stu-id="226e7-115">Running the test</span></span>

<span data-ttu-id="226e7-116">可以使用预配置的测试帐户运行 Test-CsLisConfguration cmdlet (请参阅设置用于运行 Lync Server 测试的测试帐户) 或启用了 Lync Server 的任何用户的帐户。</span><span class="sxs-lookup"><span data-stu-id="226e7-116">The Test-CsLisConfguration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="226e7-117">若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 池的 FQDN 即可。</span><span class="sxs-lookup"><span data-stu-id="226e7-117">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="226e7-118">例如：</span><span class="sxs-lookup"><span data-stu-id="226e7-118">For example:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="226e7-119">若要使用实际用户帐户运行此检查，必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。</span><span class="sxs-lookup"><span data-stu-id="226e7-119">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="226e7-120">然后，您必须在调用 CsLisConfiguration 时包含该凭据对象和分配给该帐户的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="226e7-120">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLisConfiguration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="226e7-121">有关详细信息，请参阅 [CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="226e7-121">For more information, see the Help documentation for the [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="226e7-122">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="226e7-122">Determining success or failure</span></span>

<span data-ttu-id="226e7-123">如果已正确配置了 .LIS，则会收到与以下内容类似的输出，并将 Result 属性标记为 " **成功"：**</span><span class="sxs-lookup"><span data-stu-id="226e7-123">If the LIS is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="226e7-124">TargetUri https://atl-cs-001.litwareinc.com:443/locationinformation/</span><span class="sxs-lookup"><span data-stu-id="226e7-124">TargetUri : https://atl-cs-001.litwareinc.com:443/locationinformation/</span></span>

<span data-ttu-id="226e7-125">liservice</span><span class="sxs-lookup"><span data-stu-id="226e7-125">liservice.svc</span></span>

<span data-ttu-id="226e7-126">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="226e7-126">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="226e7-127">结果：成功</span><span class="sxs-lookup"><span data-stu-id="226e7-127">Result : Success</span></span>

<span data-ttu-id="226e7-128">延迟：00：00：06.1616913</span><span class="sxs-lookup"><span data-stu-id="226e7-128">Latency : 00:00:06.1616913</span></span>

<span data-ttu-id="226e7-129">误差</span><span class="sxs-lookup"><span data-stu-id="226e7-129">Error :</span></span>

<span data-ttu-id="226e7-130">诊断</span><span class="sxs-lookup"><span data-stu-id="226e7-130">Diagnosis :</span></span>

<span data-ttu-id="226e7-131">如果指定用户无法登录或注销，则结果将显示为 "失败"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="226e7-131">If the specified user can't log on or log off, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="226e7-132">TargetUri</span><span class="sxs-lookup"><span data-stu-id="226e7-132">TargetUri :</span></span>

<span data-ttu-id="226e7-133">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="226e7-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="226e7-134">结果：失败</span><span class="sxs-lookup"><span data-stu-id="226e7-134">Result : Failure</span></span>

<span data-ttu-id="226e7-135">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="226e7-135">Latency : 00:00:00</span></span>

<span data-ttu-id="226e7-136">错误：11004，请求的名称有效，但没有请求的数据</span><span class="sxs-lookup"><span data-stu-id="226e7-136">Error : 11004, The requested name is valid but no data of the requested</span></span>

<span data-ttu-id="226e7-137">已找到类型</span><span class="sxs-lookup"><span data-stu-id="226e7-137">type was found</span></span>

<span data-ttu-id="226e7-138">诊断</span><span class="sxs-lookup"><span data-stu-id="226e7-138">Diagnosis :</span></span>

<span data-ttu-id="226e7-139">Test-CsLisConfiguration：在拓扑中找不到匹配的群集。</span><span class="sxs-lookup"><span data-stu-id="226e7-139">Test-CsLisConfiguration : No matching cluster found in topology.</span></span>

<span data-ttu-id="226e7-140">例如，上一个输出中包含 "没有匹配的群集在拓扑中找到" 这一说明。</span><span class="sxs-lookup"><span data-stu-id="226e7-140">For example, the previous output includes the note “No matching cluster found in topology.”</span></span> <span data-ttu-id="226e7-141">这通常表明边缘服务器存在问题： IIS 使用边缘服务器连接到服务提供程序并验证地址。</span><span class="sxs-lookup"><span data-stu-id="226e7-141">That typically indicates a problem with the Edge Server: the LIS using the Edge Server to connect to the service provider and validate addresses.</span></span>

<span data-ttu-id="226e7-142">如果 Test-CsLisConfiguration 失败，您可能需要重新运行测试，这一次包括 Verbose 参数：</span><span class="sxs-lookup"><span data-stu-id="226e7-142">If Test-CsLisConfiguration fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="226e7-143">包含 Verbose 参数时，Test-CsLisConfiguration 将返回其在检查指定用户登录到 Lync Server 的能力时所尝试的每个操作的分步帐户。</span><span class="sxs-lookup"><span data-stu-id="226e7-143">When the Verbose parameter is included, Test-CsLisConfiguration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="226e7-144">例如：</span><span class="sxs-lookup"><span data-stu-id="226e7-144">For example:</span></span>

<span data-ttu-id="226e7-145">调用位置信息服务。</span><span class="sxs-lookup"><span data-stu-id="226e7-145">Calling Location Information Service.</span></span>

<span data-ttu-id="226e7-146">服务路径 = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="226e7-146">Service Path = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span></span>

<span data-ttu-id="226e7-147">子网 =</span><span class="sxs-lookup"><span data-stu-id="226e7-147">Subnet =</span></span>

<span data-ttu-id="226e7-148">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="226e7-148">BssId = 5</span></span>

<span data-ttu-id="226e7-149">ChassisId =</span><span class="sxs-lookup"><span data-stu-id="226e7-149">ChassisId =</span></span>

<span data-ttu-id="226e7-150">PortId =</span><span class="sxs-lookup"><span data-stu-id="226e7-150">PortId =</span></span>

<span data-ttu-id="226e7-151">PortIdSubType = 未定义的类型</span><span class="sxs-lookup"><span data-stu-id="226e7-151">PortIdSubType = Undefined Type</span></span>

<span data-ttu-id="226e7-152">Mac</span><span class="sxs-lookup"><span data-stu-id="226e7-152">Mac</span></span>

<span data-ttu-id="226e7-153">异常 "位置信息 Web 服务请求失败，响应代码为 Item400。"</span><span class="sxs-lookup"><span data-stu-id="226e7-153">An exception 'Location Information Web Service request has failed with a response code Item400.'</span></span> <span data-ttu-id="226e7-154">在工作流 STLisConfigurationWorkflow 执行过程中发生。</span><span class="sxs-lookup"><span data-stu-id="226e7-154">occurred during Workflow Microsoft.Rtc.SyntheticTrsnactions.Workflows.STLisConfigurationWorkflow execution.</span></span>

<span data-ttu-id="226e7-155">如果您仔细检查以前的输出，您会发现 cmdlet 在尝试调用 Location 信息服务后失败。</span><span class="sxs-lookup"><span data-stu-id="226e7-155">If you examine the previous output closely, you’ll see that the cmdlet failed after it tried to call the Location Information Service.</span></span> <span data-ttu-id="226e7-156">该调用中使用的参数之一是：</span><span class="sxs-lookup"><span data-stu-id="226e7-156">One of the parameters that were used in that call was this:</span></span>

<span data-ttu-id="226e7-157">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="226e7-157">BssId = 5</span></span>

<span data-ttu-id="226e7-158">对于基本服务集标识符 (BssID) ，这并不是有效的值。</span><span class="sxs-lookup"><span data-stu-id="226e7-158">That’s not a valid value for the Basic Service Set Identifier (BssID).</span></span> <span data-ttu-id="226e7-159">相反，BssID 应如下所示：</span><span class="sxs-lookup"><span data-stu-id="226e7-159">Instead, a BssID should resemble this:</span></span>

<span data-ttu-id="226e7-160">12-34-56-78-90-ab</span><span class="sxs-lookup"><span data-stu-id="226e7-160">12-34-56-78-90-ab</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="226e7-161">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="226e7-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="226e7-162">下面是 Test-CsLisConfiguration 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="226e7-162">Here are some common reasons why Test-CsLisConfiguration might fail:</span></span>

  - <span data-ttu-id="226e7-163">提供的参数值不正确。</span><span class="sxs-lookup"><span data-stu-id="226e7-163">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="226e7-164">如前面的示例中所示，必须正确配置可选参数或测试将失败。</span><span class="sxs-lookup"><span data-stu-id="226e7-164">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="226e7-165">重新运行不带可选参数的命令，并查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="226e7-165">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

