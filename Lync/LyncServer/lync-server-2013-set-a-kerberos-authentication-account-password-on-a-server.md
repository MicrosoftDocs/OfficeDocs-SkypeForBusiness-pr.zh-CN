---
title: Lync Server 2013：在服务器上设置 Kerberos 身份验证帐户密码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97130b93052c0e14e1e4b4863be8ceea6118db05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a><span data-ttu-id="8ec53-102">在 Lync Server 2013 中在服务器上设置 Kerberos 身份验证帐户密码</span><span class="sxs-lookup"><span data-stu-id="8ec53-102">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ec53-103">_**主题上次修改时间：** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="8ec53-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="8ec53-104">若要成功完成此过程，你应以 RTCUniversalServerAdmins 组成员的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="8ec53-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="8ec53-105">对于拥有前端服务器、标准版服务器和控制器的每个网站，必须在 Kerberos 帐户上设置密码。</span><span class="sxs-lookup"><span data-stu-id="8ec53-105">You must set up a password on the Kerberos account for each site that has Front End Servers, Standard Edition servers, and Directors.</span></span> <span data-ttu-id="8ec53-106">你可以通过在网站中的一台服务器（例如，一台前端服务器）上运行**CsKerberosAccountPassword** Windows PowerShell cmdlet 来设置密码。</span><span class="sxs-lookup"><span data-stu-id="8ec53-106">You can set up the password by running the **Set-CsKerberosAccountPassword** Windows PowerShell cmdlet on one server in the site (for example, one Front End Server).</span></span> <span data-ttu-id="8ec53-107">对于每个网站，必须运行**CsKerberosAccountPassword** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8ec53-107">For each site, you must run the **Set-CsKerberosAccountPassword** cmdlet.</span></span> <span data-ttu-id="8ec53-108">该 cmdlet 为 Web 服务服务配置 Internet 信息服务（IIS），然后在 Active Directory 域服务中的计算机帐户上设置密码。</span><span class="sxs-lookup"><span data-stu-id="8ec53-108">The cmdlet configures Internet Information Services (IIS) for the Web Services service, and then sets the password on the computer account in Active Directory Domain Services.</span></span> <span data-ttu-id="8ec53-109">根据与 cmdlet 一起使用的参数，另一种方法是在一台服务器上配置 IIS，同时使用已配置为 Kerberos 帐户密码源的另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="8ec53-109">An alternate method, based on which parameter is used with the cmdlet, configures IIS on one server while using another server that has been configured as the source of the Kerberos account password.</span></span>

<span data-ttu-id="8ec53-110">使用**CsKerberosAccountPassword** cmdlet 设置密码时，Kerberos 将密码设置为随机生成的字符串。</span><span class="sxs-lookup"><span data-stu-id="8ec53-110">When you use the **Set-CsKerberosAccountPassword** cmdlet to set a password, Kerberos sets the password to a randomly generated string.</span></span> <span data-ttu-id="8ec53-111">此 cmdlet 将联系人分配给此帐户的所有 Lync Server 2013 中央站点中的所有 IIS 实例。</span><span class="sxs-lookup"><span data-stu-id="8ec53-111">This cmdlet contacts all IIS instances in all Lync Server 2013 central sites to which this account is assigned.</span></span>

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a><span data-ttu-id="8ec53-112">为 Kerberos 身份验证帐户设置密码</span><span class="sxs-lookup"><span data-stu-id="8ec53-112">To set a password for a Kerberos authentication account</span></span>

1.  <span data-ttu-id="8ec53-113">以 RTCUniversalServerAdmins 组成员的身份登录到安装了 Lync Server 管理外壳的任何域计算机。</span><span class="sxs-lookup"><span data-stu-id="8ec53-113">Log on to any domain computer with Lync Server Management Shell installed as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="8ec53-114">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="8ec53-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8ec53-115">从命令行运行以下两个命令：</span><span class="sxs-lookup"><span data-stu-id="8ec53-115">From the command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    <span data-ttu-id="8ec53-116">例如：</span><span class="sxs-lookup"><span data-stu-id="8ec53-116">For example:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8ec53-117">必须使用 "域 \ 用户名" 格式指定 UserAccount 参数。</span><span class="sxs-lookup"><span data-stu-id="8ec53-117">You must specify the UserAccount parameter by using the Domain\User format.</span></span> <span data-ttu-id="8ec53-118">User@Domain 扩展名格式不受支持，无法引用为 Kerberos 身份验证创建的计算机对象。</span><span class="sxs-lookup"><span data-stu-id="8ec53-118">The User@Domain.extension format is not supported for referencing the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8ec53-119">对 Kerberos 身份验证进行任何更改（如添加帐户或删除帐户）后，必须从 Lync Server Management Shell 命令提示符运行<STRONG>Enable-CsTopology</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="8ec53-119">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

