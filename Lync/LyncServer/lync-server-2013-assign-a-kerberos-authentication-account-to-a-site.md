---
title: Lync Server 2013：将 Kerberos 身份验证帐户分配给站点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6137224f313238dae33462298931167ba7bb810
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529519"
---
# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a><span data-ttu-id="2ae78-102">在 Lync Server 2013 中向网站分配 Kerberos 身份验证帐户</span><span class="sxs-lookup"><span data-stu-id="2ae78-102">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ae78-103">_**上次修改的主题：** 2017-04-18_</span><span class="sxs-lookup"><span data-stu-id="2ae78-103">_**Topic Last Modified:** 2017-04-18_</span></span>

<span data-ttu-id="2ae78-104">要成功完成此过程，应以 RTCUniversalServerAdmins 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="2ae78-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="2ae78-105">创建 Kerberos 帐户后，必须将其分配给站点。</span><span class="sxs-lookup"><span data-stu-id="2ae78-105">After creating the Kerberos account, you must assign it to a site.</span></span> <span data-ttu-id="2ae78-106">这是 Lync Server 2013 网站，而不是 Active Directory 站点。</span><span class="sxs-lookup"><span data-stu-id="2ae78-106">This is a Lync Server 2013 site, not an Active Directory site.</span></span> <span data-ttu-id="2ae78-107">每个部署可以创建多个 Kerberos 身份验证帐户，但只能将一个帐户分配给站点。</span><span class="sxs-lookup"><span data-stu-id="2ae78-107">You can create multiple Kerberos authentication accounts per deployment, but you can assign only one account to a site.</span></span> <span data-ttu-id="2ae78-108">使用以下过程将之前创建的 Kerberos 身份验证帐户分配给站点。</span><span class="sxs-lookup"><span data-stu-id="2ae78-108">Use the following procedure to assign a previously created Kerberos authentication account to a site.</span></span> <span data-ttu-id="2ae78-109">有关创建 Kerberos 帐户的详细信息，请参阅 [在 Lync Server 2013 中创建 kerberos 身份验证帐户](lync-server-2013-create-a-kerberos-authentication-account.md)。</span><span class="sxs-lookup"><span data-stu-id="2ae78-109">For details about creating the Kerberos account, see [Create a Kerberos authentication account in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span></span>

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a><span data-ttu-id="2ae78-110">将 Kerberos 身份验证帐户分配给站点</span><span class="sxs-lookup"><span data-stu-id="2ae78-110">To assign a Kerberos authentication account to a site</span></span>

1.  <span data-ttu-id="2ae78-111">作为 RTCUniversalServerAdmins 组的成员，登录到运行 Lync Server 2013 的域中的计算机或登录到安装了管理工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="2ae78-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="2ae78-112">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2ae78-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2ae78-113">通过命令行运行以下两个命令：</span><span class="sxs-lookup"><span data-stu-id="2ae78-113">From the command line, run the following two commands:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="2ae78-114">例如：</span><span class="sxs-lookup"><span data-stu-id="2ae78-114">For example:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="2ae78-p102">必须使用 Domain\User 格式指定 UserAccount 参数。User@Domain.extension 格式不支持引用出于 Kerberos 身份验证目的创建的计算机对象。</span><span class="sxs-lookup"><span data-stu-id="2ae78-p102">You must specify the UserAccount parameter by using the Domain\User format. The User@Domain.extension format is not supported for referring to the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>

4.  <span data-ttu-id="2ae78-117">**可选**：您可能已为您的 WebServices 配置替代 FQDN (完全限定的域名) ，因为 [在 Lync Server 2013 中，根据更改 Web 服务 URL](lync-server-2013-change-the-web-services-url.md)。</span><span class="sxs-lookup"><span data-stu-id="2ae78-117">**OPTIONAL**: You may have configured an override FQDN (fully qualified domain name) for your WebServices, as per [Change the Web Services URL in Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span></span> <span data-ttu-id="2ae78-118">如果是这种情况，您还需要为此 FQDN 添加 SPN。</span><span class="sxs-lookup"><span data-stu-id="2ae78-118">If that's the case, you'll need to add a SPN for this FQDN as well.</span></span> <span data-ttu-id="2ae78-119">例如，如果 FQDN 为 webservices，则应运行：</span><span class="sxs-lookup"><span data-stu-id="2ae78-119">For example, if the FQDN was webservices.contoso.local, you would run:</span></span>
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2ae78-120">在对 Kerberos 身份验证（如添加帐户或删除帐户）进行任何更改之后，您必须从 Lync Server 命令行管理程序命令提示符处运行 <STRONG>Enable-enable-cstopology</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="2ae78-120">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

