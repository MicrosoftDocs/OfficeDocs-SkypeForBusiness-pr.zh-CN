---
title: Lync Server 2013：验证通讯簿 web 查询
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7306b56fca8feada05ee895eea64dc2aecfafb0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42115105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a><span data-ttu-id="31ea6-102">在 Lync Server 2013 中验证通讯簿 web 查询</span><span class="sxs-lookup"><span data-stu-id="31ea6-102">Validating address book web query in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31ea6-103">_**上次修改的主题：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="31ea6-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31ea6-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="31ea6-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="31ea6-105">每天</span><span class="sxs-lookup"><span data-stu-id="31ea6-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31ea6-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="31ea6-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="31ea6-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="31ea6-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31ea6-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="31ea6-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="31ea6-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="31ea6-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="31ea6-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsAddressBookWebQuery cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="31ea6-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookWebQuery cmdlet.</span></span> <span data-ttu-id="31ea6-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="31ea6-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="31ea6-112">说明</span><span class="sxs-lookup"><span data-stu-id="31ea6-112">Description</span></span>

<span data-ttu-id="31ea6-113">CsAddressBookWebQuery cmdlet 使管理员能够验证用户是否可以使用通讯簿 Web 查询服务搜索特定的联系人。</span><span class="sxs-lookup"><span data-stu-id="31ea6-113">The Test-CsAddressBookWebQuery cmdlet enables administrators to verify that users can use the Address Book Web Query service to search for a specific contact.</span></span> <span data-ttu-id="31ea6-114">运行 cmdlet 时，CsAddressBookWebQuery 将首先连接到要进行身份验证的 Web 票证服务。</span><span class="sxs-lookup"><span data-stu-id="31ea6-114">When you run the cmdlet, Test-CsAddressBookWebQuery will first connect to the Web Ticket service to be authenticated.</span></span> <span data-ttu-id="31ea6-115">如果身份验证成功，则 cmdlet 将连接到通讯簿 Web 查询服务，并搜索指定的联系人。</span><span class="sxs-lookup"><span data-stu-id="31ea6-115">If authentication is successful, the cmdlet will then connect to the Address Book Web Query service and search for the specified contact.</span></span> <span data-ttu-id="31ea6-116">如果找到该联系人，则此 cmdlet 会尝试将该信息返回到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="31ea6-116">If that contact is found, the cmdlet will attempt to return that information to the local computer.</span></span> <span data-ttu-id="31ea6-117">只有在所有这些步骤都可以完成时，测试才会被标记为成功。</span><span class="sxs-lookup"><span data-stu-id="31ea6-117">The test will be marked a success only if all those steps can be completed.</span></span>

<span data-ttu-id="31ea6-118">有关详细信息，请参阅[CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="31ea6-118">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="31ea6-119">运行测试</span><span class="sxs-lookup"><span data-stu-id="31ea6-119">Running the test</span></span>

<span data-ttu-id="31ea6-120">可以使用预配置的测试帐户（请参阅设置运行 Lync Server 测试的测试帐户）或已启用 Lync Server 的任何用户的帐户运行 CsAddressBookWebQuery cmdlet。</span><span class="sxs-lookup"><span data-stu-id="31ea6-120">The Test-CsAddressBookWebQuery cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="31ea6-121">若要使用测试帐户运行此检查，只需指定 Lync Server 池的 FQDN 以及充当搜索目标的用户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="31ea6-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool and the SIP address of the user acting as the target of the search.</span></span> <span data-ttu-id="31ea6-122">例如：</span><span class="sxs-lookup"><span data-stu-id="31ea6-122">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="31ea6-123">若要使用实际用户帐户运行此检查，必须创建一个包含有效用户名和密码的 Windows PowerShell 凭据对象。</span><span class="sxs-lookup"><span data-stu-id="31ea6-123">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains a valid user name and password.</span></span> <span data-ttu-id="31ea6-124">然后，您必须在代码调用 CsAddressBookWebQuery 时包含该凭据对象和分配给该帐户的 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="31ea6-124">You must then include that credentials object and the SIP address assigned to the account when the code calls Test-CsAddressBookWebQuery:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="31ea6-125">有关详细信息，请参阅[CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="31ea6-125">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="31ea6-126">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="31ea6-126">Determining success or failure</span></span>

<span data-ttu-id="31ea6-127">如果指定的用户可以连接到通讯簿服务并检索目标用户地址，则将返回类似于以下的输出，并将 Result 属性标记为成功：</span><span class="sxs-lookup"><span data-stu-id="31ea6-127">If the specified user can connect to the Address Book Service and retrieve the targeted user address, you'll return output similar to this with the Result property marked as Success:</span></span>

<span data-ttu-id="31ea6-128">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="31ea6-128">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="31ea6-129">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="31ea6-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="31ea6-130">结果：成功</span><span class="sxs-lookup"><span data-stu-id="31ea6-130">Result : Success</span></span>

<span data-ttu-id="31ea6-131">延迟：00：00：06.2611356</span><span class="sxs-lookup"><span data-stu-id="31ea6-131">Latency : 00:00:06.2611356</span></span>

<span data-ttu-id="31ea6-132">误差</span><span class="sxs-lookup"><span data-stu-id="31ea6-132">Error :</span></span>

<span data-ttu-id="31ea6-133">诊断</span><span class="sxs-lookup"><span data-stu-id="31ea6-133">Diagnosis :</span></span>

<span data-ttu-id="31ea6-134">如果指定的用户无法连接，或者无法检索目标用户地址，则结果将显示为 "失败"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：</span><span class="sxs-lookup"><span data-stu-id="31ea6-134">If the specified user can't connect or if the target user address cannot be retrieved, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="31ea6-135">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="31ea6-135">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="31ea6-136">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="31ea6-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="31ea6-137">结果：失败</span><span class="sxs-lookup"><span data-stu-id="31ea6-137">Result : Failure</span></span>

<span data-ttu-id="31ea6-138">延迟：00:00:00</span><span class="sxs-lookup"><span data-stu-id="31ea6-138">Latency : 00:00:00</span></span>

<span data-ttu-id="31ea6-139">错误：通讯簿 Web 服务请求失败，响应代码为</span><span class="sxs-lookup"><span data-stu-id="31ea6-139">Error : Address Book Web service request has failed with response code</span></span>

<span data-ttu-id="31ea6-140">NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="31ea6-140">NoEntryFound.</span></span>

<span data-ttu-id="31ea6-141">诊断</span><span class="sxs-lookup"><span data-stu-id="31ea6-141">Diagnosis :</span></span>

<span data-ttu-id="31ea6-142">以前的输出表明由于找不到目标用户而导致测试失败。</span><span class="sxs-lookup"><span data-stu-id="31ea6-142">The previous output states that the test failed because the target user couldn't be found.</span></span> <span data-ttu-id="31ea6-143">您可以通过运行与以下内容类似的命令来确定是否已将有效的 SIP 地址传递给测试 CsAddressBookWebQuery：</span><span class="sxs-lookup"><span data-stu-id="31ea6-143">You can determine whether or not a valid SIP address was passed to Test-CsAddressBookWebQuery by running a command similar to the following:</span></span>

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="31ea6-144">如果 CsAddressBookWebQuery 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：</span><span class="sxs-lookup"><span data-stu-id="31ea6-144">If Test-CsAddressBookWebQuery fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

<span data-ttu-id="31ea6-145">包含 Verbose 参数时，CsAddressBookWebQuery 将返回它在检查指定用户登录到 Lync Server 的能力时所尝试的每个操作的分步帐户。</span><span class="sxs-lookup"><span data-stu-id="31ea6-145">When the Verbose parameter is included, Test-CsAddressBookWebQuery will return a step-by-step account of each action it tried while checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="31ea6-146">例如，以下输出表明，CsAddressBookWebQuery 能够连接到通讯簿服务，但无法找到目标 SIP 地址：</span><span class="sxs-lookup"><span data-stu-id="31ea6-146">For example, this output indicates that Test-CsAddressBookWebQuery was able to connect to the Address Book Service, but was not able to locate the target SIP address:</span></span>

<span data-ttu-id="31ea6-147">"QueryAddressBookWebService" 活动已启动。</span><span class="sxs-lookup"><span data-stu-id="31ea6-147">'QueryAddressBookWebService' activity started.</span></span>

<span data-ttu-id="31ea6-148">呼叫通讯簿 Web 查询服务。</span><span class="sxs-lookup"><span data-stu-id="31ea6-148">Calling Address Book Web Query Service.</span></span> <span data-ttu-id="31ea6-149">ABWS URL =</span><span class="sxs-lookup"><span data-stu-id="31ea6-149">ABWS URL =</span></span>

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

<span data-ttu-id="31ea6-150">通讯簿查询异常：通讯簿 Web 服务请求失败，响应代码为 NoEntryFound。</span><span class="sxs-lookup"><span data-stu-id="31ea6-150">Address book query exception : Address Book Web service request has failed with response code NoEntryFound.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="31ea6-151">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="31ea6-151">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="31ea6-152">以下是测试 CsAddressBookWebQuery 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="31ea6-152">Here are some common reasons why Test-CsAddressBookWebQuery might fail:</span></span>

  - <span data-ttu-id="31ea6-153">您指定的用户帐户无效。</span><span class="sxs-lookup"><span data-stu-id="31ea6-153">You specified an invalid user account.</span></span> <span data-ttu-id="31ea6-154">您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：</span><span class="sxs-lookup"><span data-stu-id="31ea6-154">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="31ea6-155">用户帐户有效，但当前没有为 Lync Server 启用该帐户。</span><span class="sxs-lookup"><span data-stu-id="31ea6-155">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="31ea6-156">若要验证是否已为 Lync Server 启用了用户帐户，请运行与以下内容类似的命令：</span><span class="sxs-lookup"><span data-stu-id="31ea6-156">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="31ea6-157">如果 Enabled 属性设置为 False，则表示当前尚未为 Lync Server 启用用户。</span><span class="sxs-lookup"><span data-stu-id="31ea6-157">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

  - <span data-ttu-id="31ea6-158">目标用户可能不在通讯簿中。</span><span class="sxs-lookup"><span data-stu-id="31ea6-158">The target user might not be in the Address Book.</span></span>

  - <span data-ttu-id="31ea6-159">通讯簿可能未完全更新和复制。</span><span class="sxs-lookup"><span data-stu-id="31ea6-159">The Address Book might not have fully updated and replicated.</span></span> <span data-ttu-id="31ea6-160">您可以通过运行以下命令来强制更新组织中的所有通讯簿服务器：</span><span class="sxs-lookup"><span data-stu-id="31ea6-160">You can force an update of all the Address Book Servers in your organization by running the following command:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

