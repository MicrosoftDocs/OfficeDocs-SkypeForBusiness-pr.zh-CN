---
title: 测试分配给站点的 Kerberos 帐户的配置
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
ms.openlocfilehash: d916ba2123f6a34150a9fe5c9c3977d75743dae0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a><span data-ttu-id="7b0df-102">在 Lync Server 2013 中测试分配给某个站点的 Kerberos 帐户的配置</span><span class="sxs-lookup"><span data-stu-id="7b0df-102">Testing configuration of the Kerberos account assigned to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b0df-103">_**上次修改的主题：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="7b0df-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b0df-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="7b0df-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7b0df-105">每天</span><span class="sxs-lookup"><span data-stu-id="7b0df-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b0df-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="7b0df-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7b0df-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b0df-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b0df-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="7b0df-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7b0df-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="7b0df-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7b0df-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsKerberosAccountAssignment cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="7b0df-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsKerberosAccountAssignment cmdlet.</span></span> <span data-ttu-id="7b0df-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="7b0df-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7b0df-112">描述</span><span class="sxs-lookup"><span data-stu-id="7b0df-112">Description</span></span>

<span data-ttu-id="7b0df-113">CsKerberosAccountAssignment cmdlet 使您能够验证 Kerberos 帐户是否与给定网站相关联，该帐户是否已正确配置，以及该帐户是否按预期正常运行。</span><span class="sxs-lookup"><span data-stu-id="7b0df-113">The Test-CsKerberosAccountAssignment cmdlet enables you to verify that a Kerberos account is associated with a given site, that this account is configured correctly, and that the account is working as expected.</span></span> <span data-ttu-id="7b0df-114">Kerberos 帐户是计算机帐户，可充当运行 Internet 信息服务器（IIS）的站点中的所有计算机的身份验证主体。</span><span class="sxs-lookup"><span data-stu-id="7b0df-114">Kerberos accounts are computer accounts that can serve as the authentication principal for all the computers in a site that are running Internet Information Server (IIS).</span></span> <span data-ttu-id="7b0df-115">由于这些帐户使用 Kerberos 身份验证协议，因此这些帐户称为 Kerberos 帐户，而新的身份验证过程称为 Kerberos web 身份验证。</span><span class="sxs-lookup"><span data-stu-id="7b0df-115">Because these accounts use the Kerberos authentication protocol, the accounts are known as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="7b0df-116">这使您可以使用单个帐户管理所有 IIS 服务器。</span><span class="sxs-lookup"><span data-stu-id="7b0df-116">This enables you to manage all IIS servers by using a single account.</span></span>

<span data-ttu-id="7b0df-117">有关详细信息，请参阅[CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="7b0df-117">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7b0df-118">运行测试</span><span class="sxs-lookup"><span data-stu-id="7b0df-118">Running the Test</span></span>

<span data-ttu-id="7b0df-119">默认情况下，CsKerberosAccountAssignment 在屏幕上显示非常少的输出。</span><span class="sxs-lookup"><span data-stu-id="7b0df-119">By default, Test-CsKerberosAccountAssignment displays very little output on-screen.</span></span> <span data-ttu-id="7b0df-120">相反，cmdlet 返回的信息将写入到 HTML 文件中。</span><span class="sxs-lookup"><span data-stu-id="7b0df-120">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="7b0df-121">因此，我们建议您在每次运行 CsKerberosAccountAssignment 时都包含 Verbose 参数和 Report 参数。</span><span class="sxs-lookup"><span data-stu-id="7b0df-121">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="7b0df-122">在 cmdlet 运行时，Verbose 参数将在屏幕上提供略微更详细的输出。</span><span class="sxs-lookup"><span data-stu-id="7b0df-122">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="7b0df-123">Report 参数允许您为由 CsKerberosAccountAssignment 生成的 HTML 文件指定文件路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="7b0df-123">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="7b0df-124">如果不包含 Report 参数，则 HTML 文件将自动保存到用户文件夹中，并提供如下所示的名称： ce84964a-c4da-c4da-4622-ad34-c54ff3ed361f。</span><span class="sxs-lookup"><span data-stu-id="7b0df-124">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="7b0df-125">在运行 CsKerberosAccountAssignment 时，还必须指定一个网站标识。</span><span class="sxs-lookup"><span data-stu-id="7b0df-125">You must also specify a site Identity when you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="7b0df-126">在站点范围内分配 Kerberos 帐户。</span><span class="sxs-lookup"><span data-stu-id="7b0df-126">Kerberos accounts are assigned at the site scope.</span></span>

<span data-ttu-id="7b0df-127">下面的命令运行 CsKerberosAccountAssignment，并将输出保存到名为 C：\\Logs\\KerberosTest 的文件中：</span><span class="sxs-lookup"><span data-stu-id="7b0df-127">The following command runs Test-CsKerberosAccountAssignment and saves the output to a file that is named C:\\Logs\\KerberosTest.html:</span></span>

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

<span data-ttu-id="7b0df-128">有关详细信息，请参阅[CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) Cmdlet 的帮助文档。</span><span class="sxs-lookup"><span data-stu-id="7b0df-128">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7b0df-129">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="7b0df-129">Determining Success or Failure</span></span>

<span data-ttu-id="7b0df-130">CsKerberosAccountAssignment cmdlet 不会返回成功或失败的简单指示。</span><span class="sxs-lookup"><span data-stu-id="7b0df-130">The Test-CsKerberosAccountAssignment cmdlet does not return a simple indication of success or failure.</span></span> <span data-ttu-id="7b0df-131">相反，您必须使用 Internet Explorer 查看生成的 HTML 文件。</span><span class="sxs-lookup"><span data-stu-id="7b0df-131">Instead, you must view the generated HTML file by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7b0df-132">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="7b0df-132">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="7b0df-133">以下是测试 CsKerberosAccountAssignment 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="7b0df-133">Here are some common reasons why Test-CsKerberosAccountAssignment might fail:</span></span>

  - <span data-ttu-id="7b0df-134">您可能指定了错误的站点标识。</span><span class="sxs-lookup"><span data-stu-id="7b0df-134">You might have specified an incorrect site Identity.</span></span> <span data-ttu-id="7b0df-135">若要返回有效网站标识的列表，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="7b0df-135">To return a list of valid site Identity, use this command:</span></span>
    
        Get-CsSite | Select-Identity Identity
    
    <span data-ttu-id="7b0df-136">网站标识通常如下所示：</span><span class="sxs-lookup"><span data-stu-id="7b0df-136">A site Identity typically looks as follows:</span></span>
    
    <span data-ttu-id="7b0df-137">网站： Redmond</span><span class="sxs-lookup"><span data-stu-id="7b0df-137">site:Redmond</span></span>

  - <span data-ttu-id="7b0df-138">指定的网站可能没有分配给它的 Kerberos 帐户。</span><span class="sxs-lookup"><span data-stu-id="7b0df-138">The specified site might not have a Kerberos account assigned to it.</span></span> <span data-ttu-id="7b0df-139">您可以通过运行与以下内容类似的命令来确定是否向某个网站分配了 Kerberos 帐户：</span><span class="sxs-lookup"><span data-stu-id="7b0df-139">You can determine whether or not a Kerberos account is assigned to a site by running a command similar to this:</span></span>
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - <span data-ttu-id="7b0df-140">您的 Kerberos 帐户的密码可能无效。</span><span class="sxs-lookup"><span data-stu-id="7b0df-140">Your Kerberos account might have a password that isn't valid.</span></span> <span data-ttu-id="7b0df-141">如果您在报告中收到以下错误消息，则您可能需要重置 Kerberos 帐户密码：</span><span class="sxs-lookup"><span data-stu-id="7b0df-141">If you receive the following error message in report, you'll probably have to reset the Kerberos account password:</span></span>
    
    <span data-ttu-id="7b0df-142">InvalidKerberosConfiguration： Kerberos 配置无效。</span><span class="sxs-lookup"><span data-stu-id="7b0df-142">InvalidKerberosConfiguration: The Kerberos configuration is invalid.</span></span>
    
    <span data-ttu-id="7b0df-143">InvalidKerberosConfiguration： atl-cs001.litwareinc.com 上的 Kerberos 配置无效。</span><span class="sxs-lookup"><span data-stu-id="7b0df-143">InvalidKerberosConfiguration: The Kerberos configuration on atl-cs001.litwareinc.com is invalid.</span></span> <span data-ttu-id="7b0df-144">预期分配的帐户为 litwareinc\\kerberostest。</span><span class="sxs-lookup"><span data-stu-id="7b0df-144">The expected assigned account is litwareinc\\kerberostest.</span></span> <span data-ttu-id="7b0df-145">确保帐户未过期，并且计算机上配置的密码与帐户的 Active Directory 密码相匹配。</span><span class="sxs-lookup"><span data-stu-id="7b0df-145">Ensure that the account has not expired, and the configured password on the machine matches the Active Directory password of the account.</span></span>
    
    <span data-ttu-id="7b0df-146">您可以使用[CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) cmdlet 设置密码。</span><span class="sxs-lookup"><span data-stu-id="7b0df-146">You can set the password using the [Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

