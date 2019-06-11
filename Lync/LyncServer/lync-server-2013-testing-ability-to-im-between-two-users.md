---
title: 'Lync Server 2013: 测试在两个用户之间即时消息的功能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea824216c456e9f673a5383eab0b788933bf53d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a><span data-ttu-id="39c75-102">在 Lync Server 2013 中的两个用户之间进行即时消息测试的功能</span><span class="sxs-lookup"><span data-stu-id="39c75-102">Testing ability to IM between two users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39c75-103">_**主题上次修改时间:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="39c75-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39c75-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="39c75-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="39c75-105">每天</span><span class="sxs-lookup"><span data-stu-id="39c75-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39c75-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="39c75-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="39c75-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="39c75-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39c75-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="39c75-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="39c75-109">当使用 Lync Server 命令行管理程序在本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="39c75-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="39c75-110">使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsIM cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="39c75-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsIM cmdlet.</span></span> <span data-ttu-id="39c75-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="39c75-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="39c75-112">说明</span><span class="sxs-lookup"><span data-stu-id="39c75-112">Description</span></span>

<span data-ttu-id="39c75-113">CsIM cmdlet 验证一对测试用户是否可以交换即时消息。</span><span class="sxs-lookup"><span data-stu-id="39c75-113">The Test-CsIM cmdlet verifies that a pair of test users can exchange instant messages.</span></span> <span data-ttu-id="39c75-114">调用后, CsIM cmdlet 将通过尝试登录到 Lync Server 的一对测试用户来启动。</span><span class="sxs-lookup"><span data-stu-id="39c75-114">When called, the Test-CsIM cmdlet starts off by trying to log on a pair of test users to Lync Server.</span></span> <span data-ttu-id="39c75-115">假设两次登录成功, 则该 cmdlet 将在两个测试用户之间启动 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="39c75-115">Assuming the two logons are successful, the cmdlet then starts an IM session between the two test users.</span></span> <span data-ttu-id="39c75-116">(用户1邀请用户2加入 IM 会话, 而用户2接受邀请。)验证消息可以在两个用户之间交换后, CsIM 将结束 IM 会话并将这两个用户从系统注销。</span><span class="sxs-lookup"><span data-stu-id="39c75-116">(User 1 invites User 2 to an IM session, and User 2 accepts the invitation.) After verifying that messages can be exchanged between the two users, Test-CsIM then ends the IM session and logs both users off the system.</span></span>

<span data-ttu-id="39c75-117">有关详细信息, 请参阅[CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="39c75-117">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="39c75-118">运行测试</span><span class="sxs-lookup"><span data-stu-id="39c75-118">Running the Test</span></span>

<span data-ttu-id="39c75-119">CsIM cmdlet 可以使用一对预配置的测试帐户运行 (请参阅设置运行 Lync Server 测试的测试帐户) 或已启用 Lync Server 的任何两个用户的帐户。</span><span class="sxs-lookup"><span data-stu-id="39c75-119">The Test-CsIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="39c75-120">若要使用测试帐户运行此检查, 只需指定正在测试的 Lync Server 池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="39c75-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="39c75-121">例如：</span><span class="sxs-lookup"><span data-stu-id="39c75-121">For example:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="39c75-122">若要使用实际用户帐户运行此检查, 必须为每个帐户创建两个 Windows PowerShell 凭据对象 (包含帐户名和密码的对象)。</span><span class="sxs-lookup"><span data-stu-id="39c75-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="39c75-123">然后, 当你调用 Test-CsIM 时, 你必须包含这些凭据对象和两个帐户的 SIP 地址:</span><span class="sxs-lookup"><span data-stu-id="39c75-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="39c75-124">有关详细信息, 请参阅[CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="39c75-124">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="39c75-125">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="39c75-125">Determining Success or Failure</span></span>

<span data-ttu-id="39c75-126">如果两个用户可以完成即时消息会话, 则会收到与此类似的输出, 结果属性标记为**成功:**</span><span class="sxs-lookup"><span data-stu-id="39c75-126">If the two users can complete an instant messaging session, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="39c75-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="39c75-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="39c75-128">结果: 成功</span><span class="sxs-lookup"><span data-stu-id="39c75-128">Result : Success</span></span>

<span data-ttu-id="39c75-129">延迟:00:00: 06.6630911</span><span class="sxs-lookup"><span data-stu-id="39c75-129">Latency : 00:00:06.6630911</span></span>

<span data-ttu-id="39c75-130">时发生</span><span class="sxs-lookup"><span data-stu-id="39c75-130">Error :</span></span>

<span data-ttu-id="39c75-131">自检</span><span class="sxs-lookup"><span data-stu-id="39c75-131">Diagnosis :</span></span>

<span data-ttu-id="39c75-132">如果测试用户无法完成会话, 则结果将显示为 "失败", 并且将在 "错误" 和 "诊断" 属性中记录其他信息:</span><span class="sxs-lookup"><span data-stu-id="39c75-132">If the test users can't complete the session, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="39c75-133">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="39c75-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="39c75-134">结果: 失败</span><span class="sxs-lookup"><span data-stu-id="39c75-134">Result : Failure</span></span>

<span data-ttu-id="39c75-135">延迟: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="39c75-135">Latency : 00:00:00</span></span>

<span data-ttu-id="39c75-136">错误: 504, 服务器超时</span><span class="sxs-lookup"><span data-stu-id="39c75-136">Error : 504, Server time-out</span></span>

<span data-ttu-id="39c75-137">诊断: ErrorCode = 2, Source = atl-litwareinc, Reason = 请参阅</span><span class="sxs-lookup"><span data-stu-id="39c75-137">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="39c75-138">响应代码和原因短语。</span><span class="sxs-lookup"><span data-stu-id="39c75-138">response code and reason phrase.</span></span>

<span data-ttu-id="39c75-139">Microsoft DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="39c75-139">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="39c75-140">例如, 以前的输出表明由于找不到指定用户, 测试失败。</span><span class="sxs-lookup"><span data-stu-id="39c75-140">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="39c75-141">可通过运行以下命令确定 SIP 地址是否有效 (以及用户是否已为 Lync Server 启用了该 SIP 地址):</span><span class="sxs-lookup"><span data-stu-id="39c75-141">You can determine whether a SIP address is valid (and whether the user assigned that SIP address was enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

<span data-ttu-id="39c75-142">如果 CsIM 失败, 则可能需要重新运行测试, 这一次包括 Verbose 参数:</span><span class="sxs-lookup"><span data-stu-id="39c75-142">If Test-CsIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="39c75-143">当包含 Verbose 参数时, CsIM 会在检查两个测试用户是否参与 IM 会话的能力时返回它尝试的每个操作的分步帐户。</span><span class="sxs-lookup"><span data-stu-id="39c75-143">When the Verbose parameter is included, Test-CsIM will return a step-by-step account of each action it tried when it checked the ability of the two test users to take part in an IM session.</span></span> <span data-ttu-id="39c75-144">例如, 以下是在为 CsIM 提供错误的用户凭据集 (在此情况下, 密码不正确) 时发生的示例输出:</span><span class="sxs-lookup"><span data-stu-id="39c75-144">For example, here’s sample output that occurs when an incorrect set of user credentials (in this case, an incorrect password) is supplied to Test-CsIM:</span></span>

<span data-ttu-id="39c75-145">正在发送注册请求:</span><span class="sxs-lookup"><span data-stu-id="39c75-145">Sending Registration request :</span></span>

<span data-ttu-id="39c75-146">目标 Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="39c75-146">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="39c75-147">用户 Sip 地址 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="39c75-147">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="39c75-148">注册机构端口 = 5061</span><span class="sxs-lookup"><span data-stu-id="39c75-148">Registrar Port = 5061</span></span>

<span data-ttu-id="39c75-149">已选择身份验证类型 "IWA"。</span><span class="sxs-lookup"><span data-stu-id="39c75-149">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="39c75-150">对 sip/atl-cs-001 的注册命中率 litwareinc</span><span class="sxs-lookup"><span data-stu-id="39c75-150">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="39c75-151">"Register" 活动在 "0.0601795" 秒内完成。</span><span class="sxs-lookup"><span data-stu-id="39c75-151">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="39c75-152">"登录被拒绝" 异常。</span><span class="sxs-lookup"><span data-stu-id="39c75-152">An exception 'The log on was denied.</span></span> <span data-ttu-id="39c75-153">检查使用的凭据是否正确, 帐户是否处于活动状态。 '</span><span class="sxs-lookup"><span data-stu-id="39c75-153">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="39c75-154">在工作流期间发生。</span><span class="sxs-lookup"><span data-stu-id="39c75-154">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="39c75-155">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="39c75-155">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="39c75-156">下面是测试 CsIM 可能失败的一些常见原因:</span><span class="sxs-lookup"><span data-stu-id="39c75-156">Here are some common reasons why Test-CsIM might fail:</span></span>

  - <span data-ttu-id="39c75-157">您指定的用户帐户无效。</span><span class="sxs-lookup"><span data-stu-id="39c75-157">You specified a user account that is not valid.</span></span> <span data-ttu-id="39c75-158">你可以通过运行类似如下所示的命令来验证用户帐户是否存在:</span><span class="sxs-lookup"><span data-stu-id="39c75-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="39c75-159">用户帐户有效, 但当前没有为 Lync Server 启用该帐户。</span><span class="sxs-lookup"><span data-stu-id="39c75-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="39c75-160">若要验证是否已启用 Lync Server 的用户帐户, 请运行类似如下的命令:</span><span class="sxs-lookup"><span data-stu-id="39c75-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="39c75-161">如果 Enabled 属性设置为 False, 表示当前未对 Lync Server 启用用户。</span><span class="sxs-lookup"><span data-stu-id="39c75-161">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="39c75-162">即时消息服务可能不可用。</span><span class="sxs-lookup"><span data-stu-id="39c75-162">The instant messaging service might not be available.</span></span> <span data-ttu-id="39c75-163">使用 Lync Server, 你可以配置系统, 以便在无法访问存档数据库时即时消息不可用。</span><span class="sxs-lookup"><span data-stu-id="39c75-163">With Lync Server, you can configure the system so that IM is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="39c75-164">你可以通过运行如下所示的命令来验证该命令:</span><span class="sxs-lookup"><span data-stu-id="39c75-164">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="39c75-165">如果 BlockOnArchiveFailure 设置为 True, 则应确定存档数据库是否可用。</span><span class="sxs-lookup"><span data-stu-id="39c75-165">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="39c75-166">你可以使用以下命令返回存档数据库的位置:</span><span class="sxs-lookup"><span data-stu-id="39c75-166">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="39c75-167">存档服务器可能不可用。</span><span class="sxs-lookup"><span data-stu-id="39c75-167">The Archiving server might not be available.</span></span> <span data-ttu-id="39c75-168">你可以使用以下命令检索存档服务器的 FQDN:</span><span class="sxs-lookup"><span data-stu-id="39c75-168">You can retrieve the FQDN of your Archiving servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="39c75-169">然后, 你可以 ping 相应的服务器以验证其是否可用。</span><span class="sxs-lookup"><span data-stu-id="39c75-169">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="39c75-170">例如：</span><span class="sxs-lookup"><span data-stu-id="39c75-170">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

