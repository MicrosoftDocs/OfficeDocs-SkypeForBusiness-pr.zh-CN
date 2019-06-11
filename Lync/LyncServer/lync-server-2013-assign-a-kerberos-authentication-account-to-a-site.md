---
title: Lync Server 2013：将 Kerberos 身份验证帐户分配给站点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c706f9fdd8932456a9f1617e55dc9231dbd6a84
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a><span data-ttu-id="5c992-102">在 Lync Server 2013 中将 Kerberos 身份验证帐户分配给站点</span><span class="sxs-lookup"><span data-stu-id="5c992-102">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c992-103">_**主题上次修改时间:** 2017-04-18_</span><span class="sxs-lookup"><span data-stu-id="5c992-103">_**Topic Last Modified:** 2017-04-18_</span></span>

<span data-ttu-id="5c992-104">若要成功完成此过程, 你应以 RTCUniversalServerAdmins 组成员的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="5c992-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="5c992-105">创建 Kerberos 帐户后, 必须将其分配给网站。</span><span class="sxs-lookup"><span data-stu-id="5c992-105">After creating the Kerberos account, you must assign it to a site.</span></span> <span data-ttu-id="5c992-106">这是 Lync Server 2013 网站, 而不是 Active Directory 网站。</span><span class="sxs-lookup"><span data-stu-id="5c992-106">This is a Lync Server 2013 site, not an Active Directory site.</span></span> <span data-ttu-id="5c992-107">你可以为每个部署创建多个 Kerberos 身份验证帐户, 但只能向网站分配一个帐户。</span><span class="sxs-lookup"><span data-stu-id="5c992-107">You can create multiple Kerberos authentication accounts per deployment, but you can assign only one account to a site.</span></span> <span data-ttu-id="5c992-108">使用以下过程将以前创建的 Kerberos 身份验证帐户分配到网站。</span><span class="sxs-lookup"><span data-stu-id="5c992-108">Use the following procedure to assign a previously created Kerberos authentication account to a site.</span></span> <span data-ttu-id="5c992-109">有关创建 Kerberos 帐户的详细信息, 请参阅[在 Lync Server 2013 中创建 Kerberos 身份验证帐户](lync-server-2013-create-a-kerberos-authentication-account.md)。</span><span class="sxs-lookup"><span data-stu-id="5c992-109">For details about creating the Kerberos account, see [Create a Kerberos authentication account in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span></span>

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a><span data-ttu-id="5c992-110">将 Kerberos 身份验证帐户分配给网站</span><span class="sxs-lookup"><span data-stu-id="5c992-110">To assign a Kerberos authentication account to a site</span></span>

1.  <span data-ttu-id="5c992-111">作为 RTCUniversalServerAdmins 组的成员, 请登录到运行 Lync Server 2013 的域中的计算机或登录到安装了管理工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="5c992-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="5c992-112">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="5c992-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5c992-113">从命令行运行以下两个命令:</span><span class="sxs-lookup"><span data-stu-id="5c992-113">From the command line, run the following two commands:</span></span>
    
       ```
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```
        Enable-CsTopology
       ```
    
    <span data-ttu-id="5c992-114">例如：</span><span class="sxs-lookup"><span data-stu-id="5c992-114">For example:</span></span>
    
       ```
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="5c992-115">必须使用 "域 \ 用户名" 格式指定 UserAccount 参数。</span><span class="sxs-lookup"><span data-stu-id="5c992-115">You must specify the UserAccount parameter by using the Domain\User format.</span></span> <span data-ttu-id="5c992-116">用户 @ 域扩展名不支持引用为 Kerberos 身份验证而创建的计算机对象。</span><span class="sxs-lookup"><span data-stu-id="5c992-116">The User@Domain.extension format is not supported for referring to the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>

4.  <span data-ttu-id="5c992-117">**可选**: 你可能已为你的 WebServices 配置替代 FQDN (完全限定域名), 如[在 Lync Server 2013 中按更改 Web 服务 URL](lync-server-2013-change-the-web-services-url.md)。</span><span class="sxs-lookup"><span data-stu-id="5c992-117">**OPTIONAL**: You may have configured an override FQDN (fully qualified domain name) for your WebServices, as per [Change the Web Services URL in Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span></span> <span data-ttu-id="5c992-118">如果是这种情况, 你还需要为此 FQDN 添加 SPN。</span><span class="sxs-lookup"><span data-stu-id="5c992-118">If that's the case, you'll need to add a SPN for this FQDN as well.</span></span> <span data-ttu-id="5c992-119">例如, 如果 FQDN 是 webservices, 您将运行:</span><span class="sxs-lookup"><span data-stu-id="5c992-119">For example, if the FQDN was webservices.contoso.local, you would run:</span></span>
    
        setspn -S http/webservices.contoso.local kerbauth

5.     
    <div class="">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5c992-120">对 Kerberos 身份验证进行任何更改 (如添加帐户或删除帐户) 后, 必须从 Lync Server Management Shell 命令提示符运行<STRONG>Enable-CsTopology</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="5c992-120">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

