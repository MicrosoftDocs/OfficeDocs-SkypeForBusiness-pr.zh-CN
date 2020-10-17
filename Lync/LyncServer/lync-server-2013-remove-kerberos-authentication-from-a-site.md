---
title: Lync Server 2013：从站点中删除 Kerberos 身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7fdf5a304d428efb3b1192d02ade0187f052171
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536409"
---
# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="94aa0-102">在 Lync Server 2013 中，从站点中删除 Kerberos 身份验证</span><span class="sxs-lookup"><span data-stu-id="94aa0-102">In Lync Server 2013 remove Kerberos authentication from a site</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94aa0-103">_**上次修改的主题：** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="94aa0-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="94aa0-104">要成功完成此过程，应以 RTCUniversalServerAdmins 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="94aa0-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="94aa0-105">如果需要从网站中删除 Kerberos 身份验证或淘汰网站，则必须使用 **CsKerberosAccountAssignment** cmdlet 从网站中删除 kerberos 身份验证帐户分配。</span><span class="sxs-lookup"><span data-stu-id="94aa0-105">If you need to remove Kerberos authentication from a site or retire a site, you must remove the Kerberos authentication account assignment from the site by using the **Remove-CsKerberosAccountAssignment** cmdlet.</span></span> <span data-ttu-id="94aa0-106">使用以下过程可删除 Kerberos 身份验证帐户分配，这将从网站中的所有计算机中删除分配。</span><span class="sxs-lookup"><span data-stu-id="94aa0-106">Use the following procedure to remove the Kerberos authentication account assignment, which removes the assignment from all computers in the site.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="94aa0-107">如果要永久停用已启用 Kerberos 的帐户，则在删除分配后，应使用 Active Directory 用户和计算机将其从 Active Directory 域服务中删除。</span><span class="sxs-lookup"><span data-stu-id="94aa0-107">If you are permanently retiring the Kerberos-enabled account, you should use Active Directory Users and Computers to delete it from Active Directory Domain Services after you have removed the assignment.</span></span> <span data-ttu-id="94aa0-108">如果将来打算使用该对象，则可能需要保留 Active Directory 对象。</span><span class="sxs-lookup"><span data-stu-id="94aa0-108">If you plan to use the object in the future, you might want to keep the Active Directory object.</span></span>



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="94aa0-109">从站点中删除 Kerberos 身份验证</span><span class="sxs-lookup"><span data-stu-id="94aa0-109">To remove Kerberos authentication from a site</span></span>

1.  <span data-ttu-id="94aa0-110">作为 RTCUniversalServerAdmins 组的成员，登录到运行 Lync Server 2013 的域中的计算机或登录到安装了管理工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="94aa0-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="94aa0-111">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="94aa0-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="94aa0-112">通过命令行运行以下两个命令：</span><span class="sxs-lookup"><span data-stu-id="94aa0-112">From the command line, run the following two commands:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="94aa0-113">例如：</span><span class="sxs-lookup"><span data-stu-id="94aa0-113">For example:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="94aa0-114">在对 Kerberos 身份验证（如添加帐户或删除帐户）进行任何更改之后，您必须从 Lync Server 命令行管理程序命令提示符处运行 <STRONG>Enable-enable-cstopology</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="94aa0-114">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

