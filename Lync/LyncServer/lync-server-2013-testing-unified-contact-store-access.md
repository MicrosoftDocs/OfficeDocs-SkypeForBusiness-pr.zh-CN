---
title: Lync Server 2013：测试统一联系人存储区访问
description: Lync Server 2013：测试统一联系人存储区访问。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58238685133c51130c414e0d7a8cd761d0233f5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556078"
---
# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="ba9d7-103">在 Lync Server 2013 中测试统一联系人存储区访问</span><span class="sxs-lookup"><span data-stu-id="ba9d7-103">Testing Unified Contact Store access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba9d7-104">_**上次修改的主题：** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="ba9d7-104">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba9d7-105">验证计划</span><span class="sxs-lookup"><span data-stu-id="ba9d7-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ba9d7-106">每天</span><span class="sxs-lookup"><span data-stu-id="ba9d7-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba9d7-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="ba9d7-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ba9d7-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba9d7-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba9d7-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="ba9d7-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ba9d7-110">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ba9d7-111">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 <strong>test-csunifiedcontactstore</strong> cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="ba9d7-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ba9d7-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ba9d7-113">说明</span><span class="sxs-lookup"><span data-stu-id="ba9d7-113">Description</span></span>

<span data-ttu-id="ba9d7-114">Lync Server 2013 中引入的统一联系人存储使管理员可以选择将用户的联系人存储在 Microsoft Exchange Server 2013 中，而不是在 Lync Server 中。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-114">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="ba9d7-115">这样，除了 Lync 2013 之外，用户还可以访问 Outlook Web Access 中的一组相同的联系人。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-115">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="ba9d7-116"> (或者，您可以继续在 Lync Server 中存储联系人。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-116">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="ba9d7-117">在这种情况下，用户将必须维护两组独立的联系人：一个用于 Outlook 和 Outlook Web Access，另一个用于 Lync 2013。 ) </span><span class="sxs-lookup"><span data-stu-id="ba9d7-117">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="ba9d7-118">您可以通过运行 **test-csunifiedcontactstore** cmdlet 来确定是否已将用户的联系人移动到统一联系人存储库。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-118">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="ba9d7-119">**Test-csunifiedcontactstore** cmdlet 将使用指定的用户帐户，并连接到统一的联系人存储库，并尝试为该用户检索联系人。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-119">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="ba9d7-120">如果不能检索联系人，则命令将会失败，并出现 "该用户未收到联系人信息" 消息。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-120">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="ba9d7-121">”</span><span class="sxs-lookup"><span data-stu-id="ba9d7-121">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="ba9d7-122">请注意，如果用户已成功迁移到统一联系人存储区，但其联系人列表中没有联系人， **test-csunifiedcontactstore** cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-122">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="ba9d7-123">指定用户必须至少有一个联系人的 **test-csunifiedcontactstore** cmdlet 才能成功完成。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-123">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ba9d7-124">运行测试</span><span class="sxs-lookup"><span data-stu-id="ba9d7-124">Running the test</span></span>

<span data-ttu-id="ba9d7-125">以下示例中所示的命令决定了用户 litwareinc kenmyer 的联系人是否 \\ 可以在统一联系人存储库中找到。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-125">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="ba9d7-126">若要执行此操作，示例中的第一个命令使用了 **Get Credential** cmdlet 为用户 litwareinc Kenmyer 创建 Windows PowerShell 命令行接口凭据对象 \\ 。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-126">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="ba9d7-127">请注意，您必须为此帐户提供密码才能创建有效的凭据对象并确保 **test-csunifiedcontactstore** cmdlet 可以运行其检查。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-127">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="ba9d7-128">该示例中的第二个命令使用提供的凭据对象 ($x) 和用户 litwareinc kenmyer 的 SIP 地址， \\ 以确定是否可以在统一联系人存储库中找到其联系人。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-128">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ba9d7-129">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="ba9d7-129">Determining success or failure</span></span>

<span data-ttu-id="ba9d7-130">如果正确配置了对联系人存储的访问，您将收到与以下内容类似的输出，并将 Result 属性标记为 " **成功"：**</span><span class="sxs-lookup"><span data-stu-id="ba9d7-130">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="ba9d7-131">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ba9d7-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ba9d7-132">结果：成功</span><span class="sxs-lookup"><span data-stu-id="ba9d7-132">Result : Success</span></span>

<span data-ttu-id="ba9d7-133">延迟：00：00：14.9862716</span><span class="sxs-lookup"><span data-stu-id="ba9d7-133">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="ba9d7-134">错误消息：</span><span class="sxs-lookup"><span data-stu-id="ba9d7-134">Error Message :</span></span>

<span data-ttu-id="ba9d7-135">诊断</span><span class="sxs-lookup"><span data-stu-id="ba9d7-135">Diagnosis :</span></span>

<span data-ttu-id="ba9d7-136">如果未正确配置对联系人存储区的访问，则结果将显示为 " **失败**"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="ba9d7-136">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ba9d7-137">警告：无法读取给定的完全限定的注册器端口号</span><span class="sxs-lookup"><span data-stu-id="ba9d7-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="ba9d7-138"> (FQDN) 的域名称。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-138">domain name (FQDN).</span></span> <span data-ttu-id="ba9d7-139">使用默认注册器端口号。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-139">Using default Registrar port number.</span></span> <span data-ttu-id="ba9d7-140">异常</span><span class="sxs-lookup"><span data-stu-id="ba9d7-140">Exception:</span></span>

<span data-ttu-id="ba9d7-141">InvalidOperationException：在拓扑中找不到匹配的群集。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="ba9d7-142">个</span><span class="sxs-lookup"><span data-stu-id="ba9d7-142">at</span></span>

<span data-ttu-id="ba9d7-143">TryRetri 的 SipSyntheticTransaction。 SyntheticTransactions</span><span class="sxs-lookup"><span data-stu-id="ba9d7-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="ba9d7-144">eveRegistrarPortFromTopology (Int32& registrarPortNumber) </span><span class="sxs-lookup"><span data-stu-id="ba9d7-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="ba9d7-145">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ba9d7-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ba9d7-146">结果：失败</span><span class="sxs-lookup"><span data-stu-id="ba9d7-146">Result : Failure</span></span>

<span data-ttu-id="ba9d7-147">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="ba9d7-147">Latency : 00:00:00</span></span>

<span data-ttu-id="ba9d7-148">错误消息：10060，连接尝试失败，因为连接方</span><span class="sxs-lookup"><span data-stu-id="ba9d7-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="ba9d7-149">在一段时间后未正确响应，或者</span><span class="sxs-lookup"><span data-stu-id="ba9d7-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="ba9d7-150">已建立连接失败，因为连接的主机具有</span><span class="sxs-lookup"><span data-stu-id="ba9d7-150">established connection failed because connected host has</span></span>

<span data-ttu-id="ba9d7-151">未能响应10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="ba9d7-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="ba9d7-152">内部异常：连接尝试失败，因为</span><span class="sxs-lookup"><span data-stu-id="ba9d7-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="ba9d7-153">连接方在一段时间后未正确响应</span><span class="sxs-lookup"><span data-stu-id="ba9d7-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="ba9d7-154">时间，或已建立的连接失败，因为连接的主机</span><span class="sxs-lookup"><span data-stu-id="ba9d7-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="ba9d7-155">未能响应10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="ba9d7-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="ba9d7-156">诊断</span><span class="sxs-lookup"><span data-stu-id="ba9d7-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ba9d7-157">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="ba9d7-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="ba9d7-158">以下是 **测试 test-csunifiedcontactstore** 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="ba9d7-158">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="ba9d7-159">提供的参数值不正确。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="ba9d7-160">如果使用，则必须正确配置可选参数或测试将失败。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="ba9d7-161">重新运行不带可选参数的命令，并查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="ba9d7-162">连接到统一联系人存储失败，并且尝试检索用户的联系人失败。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-162">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="ba9d7-163">可能存在网络连接问题。</span><span class="sxs-lookup"><span data-stu-id="ba9d7-163">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ba9d7-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba9d7-164">See Also</span></span>


[<span data-ttu-id="ba9d7-165">新 CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="ba9d7-165">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="ba9d7-166">CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="ba9d7-166">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

