---
title: 测试分配给网站的 Kerberos 帐户的配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c096edc0267501bb17870a5c018e4b6b0c513422
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a><span data-ttu-id="da831-102">在 Lync Server 2013 中测试分配给网站的 Kerberos 帐户的配置</span><span class="sxs-lookup"><span data-stu-id="da831-102">Testing configuration of the Kerberos account assigned to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da831-103">_**主题上次修改时间：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="da831-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da831-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="da831-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="da831-105">每天</span><span class="sxs-lookup"><span data-stu-id="da831-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da831-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="da831-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="da831-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="da831-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da831-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="da831-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="da831-109">当使用 Lync Server 命令行管理程序在本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="da831-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="da831-110">使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsKerberosAccountAssignment cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="da831-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsKerberosAccountAssignment cmdlet.</span></span> <span data-ttu-id="da831-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="da831-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="da831-112">说明</span><span class="sxs-lookup"><span data-stu-id="da831-112">Description</span></span>

<span data-ttu-id="da831-113">CsKerberosAccountAssignment cmdlet 使你能够验证 Kerberos 帐户是否与给定的网站相关联、此帐户是否已正确配置以及帐户是否按预期工作。</span><span class="sxs-lookup"><span data-stu-id="da831-113">The Test-CsKerberosAccountAssignment cmdlet enables you to verify that a Kerberos account is associated with a given site, that this account is configured correctly, and that the account is working as expected.</span></span> <span data-ttu-id="da831-114">Kerberos 帐户是计算机帐户，可用作运行 Internet 信息服务器（IIS）的网站中的所有计算机的身份验证主体。</span><span class="sxs-lookup"><span data-stu-id="da831-114">Kerberos accounts are computer accounts that can serve as the authentication principal for all the computers in a site that are running Internet Information Server (IIS).</span></span> <span data-ttu-id="da831-115">由于这些帐户使用 Kerberos 身份验证协议，因此帐户称为 Kerberos 帐户，新的身份验证过程称为 Kerberos web 身份验证。</span><span class="sxs-lookup"><span data-stu-id="da831-115">Because these accounts use the Kerberos authentication protocol, the accounts are known as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="da831-116">这使你可以使用单个帐户管理所有 IIS 服务器。</span><span class="sxs-lookup"><span data-stu-id="da831-116">This enables you to manage all IIS servers by using a single account.</span></span>

<span data-ttu-id="da831-117">有关详细信息，请参阅[CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="da831-117">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="da831-118">运行测试</span><span class="sxs-lookup"><span data-stu-id="da831-118">Running the Test</span></span>

<span data-ttu-id="da831-119">默认情况下，测试 CsKerberosAccountAssignment 在屏幕上显示非常少的输出。</span><span class="sxs-lookup"><span data-stu-id="da831-119">By default, Test-CsKerberosAccountAssignment displays very little output on-screen.</span></span> <span data-ttu-id="da831-120">而是将 cmdlet 返回的信息写入 HTML 文件。</span><span class="sxs-lookup"><span data-stu-id="da831-120">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="da831-121">因此，我们建议你在运行 Test CsKerberosAccountAssignment 时随时包括 Verbose 参数和 Report 参数。</span><span class="sxs-lookup"><span data-stu-id="da831-121">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="da831-122">在运行 cmdlet 时，Verbose 参数将在屏幕上提供稍有更详细的输出。</span><span class="sxs-lookup"><span data-stu-id="da831-122">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="da831-123">Report 参数允许你为由 Test CsKerberosAccountAssignment 生成的 HTML 文件指定文件路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="da831-123">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="da831-124">如果不包含报表参数，则 HTML 文件将自动保存到 "用户" 文件夹，并获得类似于以下内容的名称： ce84964a-c4da-4622-ad34-c54ff3ed361f。</span><span class="sxs-lookup"><span data-stu-id="da831-124">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="da831-125">在运行 Test CsKerberosAccountAssignment 时，还必须指定网站标识。</span><span class="sxs-lookup"><span data-stu-id="da831-125">You must also specify a site Identity when you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="da831-126">在网站范围内分配 Kerberos 帐户。</span><span class="sxs-lookup"><span data-stu-id="da831-126">Kerberos accounts are assigned at the site scope.</span></span>

<span data-ttu-id="da831-127">以下命令运行 Test-CsKerberosAccountAssignment 并将输出保存到名为 C：\\Logs\\KerberosTest 的文件中：</span><span class="sxs-lookup"><span data-stu-id="da831-127">The following command runs Test-CsKerberosAccountAssignment and saves the output to a file that is named C:\\Logs\\KerberosTest.html:</span></span>

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

<span data-ttu-id="da831-128">有关详细信息，请参阅[CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="da831-128">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="da831-129">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="da831-129">Determining Success or Failure</span></span>

<span data-ttu-id="da831-130">CsKerberosAccountAssignment cmdlet 不会返回简单的成功或失败指示。</span><span class="sxs-lookup"><span data-stu-id="da831-130">The Test-CsKerberosAccountAssignment cmdlet does not return a simple indication of success or failure.</span></span> <span data-ttu-id="da831-131">而是必须使用 Internet Explorer 查看生成的 HTML 文件。</span><span class="sxs-lookup"><span data-stu-id="da831-131">Instead, you must view the generated HTML file by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="da831-132">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="da831-132">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="da831-133">下面是测试 CsKerberosAccountAssignment 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="da831-133">Here are some common reasons why Test-CsKerberosAccountAssignment might fail:</span></span>

  - <span data-ttu-id="da831-134">您可能指定了一个不正确的站点标识。</span><span class="sxs-lookup"><span data-stu-id="da831-134">You might have specified an incorrect site Identity.</span></span> <span data-ttu-id="da831-135">若要返回有效网站标识的列表，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="da831-135">To return a list of valid site Identity, use this command:</span></span>
    
        Get-CsSite | Select-Identity Identity
    
    <span data-ttu-id="da831-136">网站标识通常如下所示：</span><span class="sxs-lookup"><span data-stu-id="da831-136">A site Identity typically looks as follows:</span></span>
    
    <span data-ttu-id="da831-137">网站：雷德蒙</span><span class="sxs-lookup"><span data-stu-id="da831-137">site:Redmond</span></span>

  - <span data-ttu-id="da831-138">指定网站可能未分配 Kerberos 帐户。</span><span class="sxs-lookup"><span data-stu-id="da831-138">The specified site might not have a Kerberos account assigned to it.</span></span> <span data-ttu-id="da831-139">你可以通过运行如下命令确定是否将 Kerberos 帐户分配给网站：</span><span class="sxs-lookup"><span data-stu-id="da831-139">You can determine whether or not a Kerberos account is assigned to a site by running a command similar to this:</span></span>
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - <span data-ttu-id="da831-140">您的 Kerberos 帐户可能有一个无效密码。</span><span class="sxs-lookup"><span data-stu-id="da831-140">Your Kerberos account might have a password that isn't valid.</span></span> <span data-ttu-id="da831-141">如果在报告中收到以下错误消息，您可能需要重置 Kerberos 帐户密码：</span><span class="sxs-lookup"><span data-stu-id="da831-141">If you receive the following error message in report, you'll probably have to reset the Kerberos account password:</span></span>
    
    <span data-ttu-id="da831-142">InvalidKerberosConfiguration： Kerberos 配置无效。</span><span class="sxs-lookup"><span data-stu-id="da831-142">InvalidKerberosConfiguration: The Kerberos configuration is invalid.</span></span>
    
    <span data-ttu-id="da831-143">InvalidKerberosConfiguration： atl-cs001.litwareinc.com 上的 Kerberos 配置无效。</span><span class="sxs-lookup"><span data-stu-id="da831-143">InvalidKerberosConfiguration: The Kerberos configuration on atl-cs001.litwareinc.com is invalid.</span></span> <span data-ttu-id="da831-144">所需的指定帐户为\\litwareinc kerberostest。</span><span class="sxs-lookup"><span data-stu-id="da831-144">The expected assigned account is litwareinc\\kerberostest.</span></span> <span data-ttu-id="da831-145">确保帐户未过期，并且计算机上配置的密码与帐户的 Active Directory 密码相匹配。</span><span class="sxs-lookup"><span data-stu-id="da831-145">Ensure that the account has not expired, and the configured password on the machine matches the Active Directory password of the account.</span></span>
    
    <span data-ttu-id="da831-146">你可以使用[CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) cmdlet 设置密码。</span><span class="sxs-lookup"><span data-stu-id="da831-146">You can set the password using the [Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

