---
title: 将服务器到服务器身份验证证书分配给 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 952f4c1b14ce7260d4b320ea7feacddb9a85a8f0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a><span data-ttu-id="2ae20-102">将服务器到服务器身份验证证书分配给 Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ae20-102">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ae20-103">_**上次修改的主题：** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="2ae20-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="2ae20-104">若要确定是否已将服务器到服务器身份验证证书分配给 Microsoft Lync Server 2013，请从 Lync Server 2013 命令行管理程序中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="2ae20-104">To determine whether or not a server-to-server authentication certificate has already been assigned to Microsoft Lync Server 2013, run the following command from the Lync Server 2013 Management Shell:</span></span>

    Get-CsCertificate -Type OAuthTokenIssuer

<span data-ttu-id="2ae20-105">如果没有返回任何证书信息，则必须在分配令牌颁发者证书后才能使用服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="2ae20-105">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="2ae20-106">作为一般规则，任何 Lync Server 2013 证书都可用作 OAuthTokenIssuer 证书;例如，你的 Lync Server 2013 默认证书也可以用作 OAuthTokenIssuer 证书。</span><span class="sxs-lookup"><span data-stu-id="2ae20-106">As a general rule, any Lync Server 2013 certificate can be used as your OAuthTokenIssuer certificate; for example, your Lync Server 2013 default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="2ae20-107">（OAUthTokenIssuer 证书也可以是在 "Subject" 字段中包含您的 SIP 域名称的任何 Web 服务器证书。）用于服务器到服务器身份验证的证书的主要要求如下：1）必须在所有前端服务器上将相同的证书配置为 OAuthTokenIssuer 证书;和2）证书必须至少为2048位。</span><span class="sxs-lookup"><span data-stu-id="2ae20-107">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>

<span data-ttu-id="2ae20-p102">如果没有可用于服务器到服务器身份验证的证书，则可以获取新证书，导入新证书，然后将该证书用于服务器到服务器身份验证。在请求并获取新证书后，可以登录到任一前端服务器并使用类似如下的 Windows PowerShell 命令导入和分配该证书：</span><span class="sxs-lookup"><span data-stu-id="2ae20-p102">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication. After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

<span data-ttu-id="2ae20-p103">在上述命令中，Path 参数表示证书文件的完整路径，Password 参数表示分配给该证书的密码。此过程只应运行一次：Lync Server 的复制服务随后将自动创建一组计划任务，这些任务会将证书解密并部署到所有前端服务器。</span><span class="sxs-lookup"><span data-stu-id="2ae20-p103">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate. This procedure should be run just one time: Lync Server's replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>

<span data-ttu-id="2ae20-p104">您也可以使用现有证书作为服务器到服务器身份验证证书。（如前所述，默认证书可用作服务器到服务器身份验证证书。）以下 Windows PowerShell 命令对可检索默认证书的 Thumbprint 属性的值，然后使用该值使默认证书成为服务器到服务器身份验证证书：</span><span class="sxs-lookup"><span data-stu-id="2ae20-p104">Alternatively, you can use an existing certificate as your server-to-server authentication certificate. (As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

<span data-ttu-id="2ae20-p105">在上述命令中，所检索的证书配置为用作全局服务器到服务器身份验证证书；这意味着该证书将被复制到所有前端服务器并被这些服务器使用。再强调一次，此命令只应在其中一台前端服务器上运行一次。尽管所有前端服务器都必须使用相同证书，但您不应在每台前端服务器上都配置 OAuthTokenIssuer 证书。相反，只需配置该证书一次，然后让 Lync Server 的复制服务器负责将该证书复制到每台服务器。</span><span class="sxs-lookup"><span data-stu-id="2ae20-p105">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers. Again, this command should only be run one time, and only on one of your Front End Servers. Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server. Instead, configure the certificate once, then let Lync Server's replication server take care of copying that certificate to each server.</span></span>

<span data-ttu-id="2ae20-118">Set-cscertificate cmdlet 接受有问题的证书，并立即将该证书配置为充当当前的 OAuthTokenIssuer 证书。</span><span class="sxs-lookup"><span data-stu-id="2ae20-118">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="2ae20-119">（Lync Server 2013 保留证书类型的两个副本：当前证书和以前的证书。）如果您需要新证书立即开始充当 OAuthTokenIssuer 证书，则应使用 Set-cscertificate cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2ae20-119">(Lync Server 2013 keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="2ae20-p107">您还可以使用 Set-CsCertificate cmdlet“滚动”新证书。“滚动”证书仅意味着在指定时间点将新证书配置为成为当前 OAuthTokenIssuer 证书。例如，以下命令将检索默认证书，然后将该证书配置为从 2012 年 7 月 1 日起成为当前 OAuthTokenIssuer 证书：</span><span class="sxs-lookup"><span data-stu-id="2ae20-p107">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate. "Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time. For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2012:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

<span data-ttu-id="2ae20-123">在 2012 年 7 月 1 日，新证书将配置为当前 OAuthTokenIssuer 证书，“旧”OAuthTokenIssuer 证书将配置为上一个证书。</span><span class="sxs-lookup"><span data-stu-id="2ae20-123">On July 1, 2012 the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>

<span data-ttu-id="2ae20-p108">如果不想使用 Windows PowerShell，还可以使用证书 MMC 控制台从一台前端服务器中导出证书，然后在所有其他前端服务器上导入相同证书。如果执行此操作，请确保将私钥连同证书本身一起导出。</span><span class="sxs-lookup"><span data-stu-id="2ae20-p108">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers. If you do this, make sure that you export the private key along with the certificate itself.</span></span>

<div>


> [!WARNING]
> <span data-ttu-id="2ae20-126">在这种情况下，必须在每台前端服务器上执行该过程。</span><span class="sxs-lookup"><span data-stu-id="2ae20-126">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="2ae20-127">以这种方式导出和导入证书时，Lync Server 2013 不会将该证书复制到每台前端服务器。</span><span class="sxs-lookup"><span data-stu-id="2ae20-127">When exporting and importing certificates in this manner Lync Server 2013 will not replicate that certificate to each Front End Server.</span></span>



</div>

<span data-ttu-id="2ae20-128">在将证书导入到所有前端服务器之后，可以使用 Lync Server 部署向导而不是 Windows PowerShell 来分配该证书。</span><span class="sxs-lookup"><span data-stu-id="2ae20-128">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Lync Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="2ae20-129">要使用部署向导分配证书，请在安装了部署向导的计算机上完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="2ae20-129">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>

1.  <span data-ttu-id="2ae20-130">依次单击 "开始"、"所有程序"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 部署向导**"。</span><span class="sxs-lookup"><span data-stu-id="2ae20-130">Click Start, click All Programs, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="2ae20-131">在部署向导中，单击“安装或更新 Lync Server 系统”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2ae20-131">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="2ae20-132">在 "Microsoft Lync Server 2013" 页上，单击 "标题**步骤3：请求、安装或分配证书**" 下的 "**运行**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="2ae20-132">On the Microsoft Lync Server 2013 page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="2ae20-133">（注意：如果已在此计算机上安装了证书，则 "**运行**" 按钮将被标记为 "**再次运行**"。）</span><span class="sxs-lookup"><span data-stu-id="2ae20-133">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>

4.  <span data-ttu-id="2ae20-134">在证书向导中，选择 OAuthTokenIssuer\*\*\*\* 证书，然后单击“分配”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2ae20-134">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>

5.  <span data-ttu-id="2ae20-135">在证书分配向导的“证书分配”\*\*\*\* 页上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2ae20-135">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>

6.  <span data-ttu-id="2ae20-136">在“证书存储”\*\*\*\* 页上，选择要用于服务器到服务器身份验证的证书，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2ae20-136">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>

7.  <span data-ttu-id="2ae20-137">在“证书分配摘要”页上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2ae20-137">On the Certificate Assignment Summary page, click **Next**.</span></span>

8.  <span data-ttu-id="2ae20-138">在“正在执行命令”页上，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2ae20-138">On the Executing Commands page, click **Finish**.</span></span>

9.  <span data-ttu-id="2ae20-139">关闭证书向导和部署向导。</span><span class="sxs-lookup"><span data-stu-id="2ae20-139">Close the Certificate Wizard and the Deployment Wizard.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

