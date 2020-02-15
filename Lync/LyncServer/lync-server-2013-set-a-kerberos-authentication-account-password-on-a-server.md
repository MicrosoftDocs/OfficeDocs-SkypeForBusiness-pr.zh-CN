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
ms.openlocfilehash: 9799be0fda2b1a3c5b7765774b1f9e3199cc61f3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a><span data-ttu-id="5cad1-102">在 Lync Server 2013 中的服务器上设置 Kerberos 身份验证帐户密码</span><span class="sxs-lookup"><span data-stu-id="5cad1-102">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cad1-103">_**上次修改的主题：** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="5cad1-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="5cad1-104">要成功完成此过程，应以 RTCUniversalServerAdmins 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="5cad1-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="5cad1-105">必须为拥有前端服务器、Standard Edition Server 和控制器的每个站点设置 Kerberos 帐户密码。</span><span class="sxs-lookup"><span data-stu-id="5cad1-105">You must set up a password on the Kerberos account for each site that has Front End Servers, Standard Edition servers, and Directors.</span></span> <span data-ttu-id="5cad1-106">您可以通过在站点中的一台服务器（例如，一台前端服务器）上运行**CsKerberosAccountPassword** Windows PowerShell cmdlet 来设置密码。</span><span class="sxs-lookup"><span data-stu-id="5cad1-106">You can set up the password by running the **Set-CsKerberosAccountPassword** Windows PowerShell cmdlet on one server in the site (for example, one Front End Server).</span></span> <span data-ttu-id="5cad1-107">对于每个网站，必须运行**CsKerberosAccountPassword** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5cad1-107">For each site, you must run the **Set-CsKerberosAccountPassword** cmdlet.</span></span> <span data-ttu-id="5cad1-108">Cmdlet 为 Web 服务服务配置 Internet 信息服务（IIS），然后在 Active Directory 域服务中的计算机帐户上设置密码。</span><span class="sxs-lookup"><span data-stu-id="5cad1-108">The cmdlet configures Internet Information Services (IIS) for the Web Services service, and then sets the password on the computer account in Active Directory Domain Services.</span></span> <span data-ttu-id="5cad1-109">使用已配置为 Kerberos 帐户密码源的其他服务器时，另一种基于与 cmdlet 一起使用的参数的方法会在服务器上配置 IIS。</span><span class="sxs-lookup"><span data-stu-id="5cad1-109">An alternate method, based on which parameter is used with the cmdlet, configures IIS on one server while using another server that has been configured as the source of the Kerberos account password.</span></span>

<span data-ttu-id="5cad1-110">使用 **Set-CsKerberosAccountPassword** cmdlet 设置密码时，Kerberos 会将密码设置为随机生成的字符串。</span><span class="sxs-lookup"><span data-stu-id="5cad1-110">When you use the **Set-CsKerberosAccountPassword** cmdlet to set a password, Kerberos sets the password to a randomly generated string.</span></span> <span data-ttu-id="5cad1-111">此 cmdlet 将联系分配此帐户的所有 Lync Server 2013 中央站点中的所有 IIS 实例。</span><span class="sxs-lookup"><span data-stu-id="5cad1-111">This cmdlet contacts all IIS instances in all Lync Server 2013 central sites to which this account is assigned.</span></span>

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a><span data-ttu-id="5cad1-112">为 Kerberos 身份验证帐户设置密码</span><span class="sxs-lookup"><span data-stu-id="5cad1-112">To set a password for a Kerberos authentication account</span></span>

1.  <span data-ttu-id="5cad1-113">以 RTCUniversalServerAdmins 组成员的身份登录到安装了 Lync Server 命令行管理程序的任何域计算机。</span><span class="sxs-lookup"><span data-stu-id="5cad1-113">Log on to any domain computer with Lync Server Management Shell installed as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="5cad1-114">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5cad1-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5cad1-115">通过命令行运行以下两个命令：</span><span class="sxs-lookup"><span data-stu-id="5cad1-115">From the command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    <span data-ttu-id="5cad1-116">例如：</span><span class="sxs-lookup"><span data-stu-id="5cad1-116">For example:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5cad1-p103">必须使用 Domain\User 格式指定 UserAccount 参数。User@Domain.extension 格式不支持引用出于 Kerberos 身份验证目的创建的计算机对象。</span><span class="sxs-lookup"><span data-stu-id="5cad1-p103">You must specify the UserAccount parameter by using the Domain\User format. The User@Domain.extension format is not supported for referencing the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5cad1-119">在对 Kerberos 身份验证（如添加帐户或删除帐户）进行任何更改之后，您必须从 Lync Server 命令行管理程序命令提示符处运行<STRONG>Enable-enable-cstopology</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="5cad1-119">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

