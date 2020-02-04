---
title: Lync Server 2013：测试统一联系人存储访问权限
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
ms.openlocfilehash: 47d5d216a1d7a389f20bf2c59f94baf54636d409
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="af804-102">在 Lync Server 2013 中测试统一联系人存储访问</span><span class="sxs-lookup"><span data-stu-id="af804-102">Testing Unified Contact Store access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af804-103">_**主题上次修改时间：** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="af804-103">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af804-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="af804-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="af804-105">每天</span><span class="sxs-lookup"><span data-stu-id="af804-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af804-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="af804-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="af804-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="af804-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af804-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="af804-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="af804-109">当使用 Lync Server 命令行管理程序在本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="af804-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="af804-110">使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行<strong>CsUnifiedContactStore</strong> cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="af804-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="af804-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="af804-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="af804-112">说明</span><span class="sxs-lookup"><span data-stu-id="af804-112">Description</span></span>

<span data-ttu-id="af804-113">Lync Server 2013 中引入的统一联系人存储使管理员可以选择将用户的联系人存储在 Microsoft Exchange Server 2013 中，而不是在 Lync Server 中。</span><span class="sxs-lookup"><span data-stu-id="af804-113">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="af804-114">这样，除了 Lync 2013 之外，用户还可以在 Outlook Web Access 中访问同一组联系人。</span><span class="sxs-lookup"><span data-stu-id="af804-114">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="af804-115">（或者，您可以继续在 Lync Server 中存储联系人。</span><span class="sxs-lookup"><span data-stu-id="af804-115">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="af804-116">在这种情况下，用户将必须维护两个单独的联系人集：一个用于 Outlook 和 Outlook Web Access，另一个用于 Lync 2013。）</span><span class="sxs-lookup"><span data-stu-id="af804-116">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="af804-117">你可以通过运行**CsUnifiedContactStore** cmdlet 确定是否已将用户的联系人移动到 "统一联系人存储"。</span><span class="sxs-lookup"><span data-stu-id="af804-117">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="af804-118">**CsUnifiedContactStore** cmdlet 将采用指定的用户帐户，连接到 "统一联系人存储"，然后尝试检索用户的联系人。</span><span class="sxs-lookup"><span data-stu-id="af804-118">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="af804-119">如果无法检索任何联系人，则该命令将失败，并显示 "用户未收到任何联系人" 消息。</span><span class="sxs-lookup"><span data-stu-id="af804-119">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="af804-120">验证用户是否存在联系人。 "</span><span class="sxs-lookup"><span data-stu-id="af804-120">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="af804-121">请注意，如果用户已成功迁移到 "统一联系人存储"，但其 "联系人" 列表中没有联系人，则**CsUnifiedContactStore** cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="af804-121">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="af804-122">指定的用户必须至少有一个联系人， **CsUnifiedContactStore** cmdlet 才能成功完成。</span><span class="sxs-lookup"><span data-stu-id="af804-122">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="af804-123">运行测试</span><span class="sxs-lookup"><span data-stu-id="af804-123">Running the test</span></span>

<span data-ttu-id="af804-124">以下示例中所示的命令确定是否可在 "统一联系人\\" 存储中找到用户 litwareinc kenmyer 的联系人。</span><span class="sxs-lookup"><span data-stu-id="af804-124">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="af804-125">为此，示例中的第一个命令使用了**Get 凭据**cmdlet 为用户 litwareinc\\kenmyer 创建 Windows PowerShell 命令行界面凭据对象。</span><span class="sxs-lookup"><span data-stu-id="af804-125">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="af804-126">请注意，你必须为此帐户提供密码才能创建有效的凭据对象并确保**CsUnifiedContactStore** cmdlet 可以运行其检查。</span><span class="sxs-lookup"><span data-stu-id="af804-126">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="af804-127">示例中的第二个命令使用提供的凭据对象（$x）和用户 litwareinc\\KENMYER 的 SIP 地址，以确定是否可以在 "统一联系人" 存储中找到其联系人。</span><span class="sxs-lookup"><span data-stu-id="af804-127">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="af804-128">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="af804-128">Determining success or failure</span></span>

<span data-ttu-id="af804-129">如果已正确配置对联系人存储区的访问，则会收到类似于此的输出，结果属性标记为 "**成功"：**</span><span class="sxs-lookup"><span data-stu-id="af804-129">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="af804-130">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="af804-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="af804-131">结果：成功</span><span class="sxs-lookup"><span data-stu-id="af804-131">Result : Success</span></span>

<span data-ttu-id="af804-132">延迟：00：00：14.9862716</span><span class="sxs-lookup"><span data-stu-id="af804-132">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="af804-133">错误消息：</span><span class="sxs-lookup"><span data-stu-id="af804-133">Error Message :</span></span>

<span data-ttu-id="af804-134">自检</span><span class="sxs-lookup"><span data-stu-id="af804-134">Diagnosis :</span></span>

<span data-ttu-id="af804-135">如果未正确配置对联系人存储的访问，则结果将显示为 "**失败**"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="af804-135">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="af804-136">警告：无法读取给定的完全限定的注册机构端口号</span><span class="sxs-lookup"><span data-stu-id="af804-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="af804-137">域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="af804-137">domain name (FQDN).</span></span> <span data-ttu-id="af804-138">使用默认注册器端口号。</span><span class="sxs-lookup"><span data-stu-id="af804-138">Using default Registrar port number.</span></span> <span data-ttu-id="af804-139">除了</span><span class="sxs-lookup"><span data-stu-id="af804-139">Exception:</span></span>

<span data-ttu-id="af804-140">InvalidOperationException：在拓扑中找不到匹配的群集。</span><span class="sxs-lookup"><span data-stu-id="af804-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="af804-141">看</span><span class="sxs-lookup"><span data-stu-id="af804-141">at</span></span>

<span data-ttu-id="af804-142">SipSyntheticTransaction. TryRetri 的 SyntheticTransactions</span><span class="sxs-lookup"><span data-stu-id="af804-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="af804-143">eveRegistrarPortFromTopology （Int32& registrarPortNumber）</span><span class="sxs-lookup"><span data-stu-id="af804-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="af804-144">目标 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="af804-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="af804-145">结果：失败</span><span class="sxs-lookup"><span data-stu-id="af804-145">Result : Failure</span></span>

<span data-ttu-id="af804-146">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="af804-146">Latency : 00:00:00</span></span>

<span data-ttu-id="af804-147">错误消息：10060，连接尝试失败，因为已连接的参与方</span><span class="sxs-lookup"><span data-stu-id="af804-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="af804-148">在一段时间后未正确响应，或者</span><span class="sxs-lookup"><span data-stu-id="af804-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="af804-149">已建立连接失败，因为连接的主机已</span><span class="sxs-lookup"><span data-stu-id="af804-149">established connection failed because connected host has</span></span>

<span data-ttu-id="af804-150">无法响应10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="af804-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="af804-151">内部异常：连接尝试失败，因为</span><span class="sxs-lookup"><span data-stu-id="af804-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="af804-152">已连接方在一段时间后未正确响应</span><span class="sxs-lookup"><span data-stu-id="af804-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="af804-153">时间，或已建立的连接失败，因为已连接的主机</span><span class="sxs-lookup"><span data-stu-id="af804-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="af804-154">无法响应10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="af804-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="af804-155">自检</span><span class="sxs-lookup"><span data-stu-id="af804-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="af804-156">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="af804-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="af804-157">下面是**测试 CsUnifiedContactStore**可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="af804-157">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="af804-158">提供的参数值不正确。</span><span class="sxs-lookup"><span data-stu-id="af804-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="af804-159">如果使用，则必须正确配置可选参数，否则测试将失败。</span><span class="sxs-lookup"><span data-stu-id="af804-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="af804-160">重新运行不带可选参数的命令，并查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="af804-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="af804-161">连接到 "统一联系人存储" 失败，并且不可能尝试检索用户的联系人。</span><span class="sxs-lookup"><span data-stu-id="af804-161">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="af804-162">可能存在网络连接问题。</span><span class="sxs-lookup"><span data-stu-id="af804-162">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="af804-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af804-163">See Also</span></span>


[<span data-ttu-id="af804-164">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="af804-164">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="af804-165">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="af804-165">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

