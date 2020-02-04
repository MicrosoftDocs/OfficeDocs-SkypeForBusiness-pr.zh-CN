---
title: Lync Server 2013：将 Kerberos 身份验证从站点中删除
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
ms.openlocfilehash: e88f3de6f653354087d1abd0f7884ee09eda2f36
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="593fb-102">在 Lync Server 2013 中将 Kerberos 身份验证从站点中删除</span><span class="sxs-lookup"><span data-stu-id="593fb-102">In Lync Server 2013 remove Kerberos authentication from a site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="593fb-103">_**主题上次修改时间：** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="593fb-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="593fb-104">若要成功完成此过程，你应以 RTCUniversalServerAdmins 组成员的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="593fb-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="593fb-105">如果需要从网站中删除 Kerberos 身份验证或停用网站，则必须使用**CsKerberosAccountAssignment** cmdlet 从网站中删除 kerberos 身份验证帐户分配。</span><span class="sxs-lookup"><span data-stu-id="593fb-105">If you need to remove Kerberos authentication from a site or retire a site, you must remove the Kerberos authentication account assignment from the site by using the **Remove-CsKerberosAccountAssignment** cmdlet.</span></span> <span data-ttu-id="593fb-106">使用以下过程删除 Kerberos 身份验证帐户分配，这将从网站中的所有计算机中删除作业。</span><span class="sxs-lookup"><span data-stu-id="593fb-106">Use the following procedure to remove the Kerberos authentication account assignment, which removes the assignment from all computers in the site.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="593fb-107">如果你永久停止启用 Kerberos 的帐户，则在删除作业后，你应该使用 Active Directory 用户和计算机从 Active Directory 域服务中删除它。</span><span class="sxs-lookup"><span data-stu-id="593fb-107">If you are permanently retiring the Kerberos-enabled account, you should use Active Directory Users and Computers to delete it from Active Directory Domain Services after you have removed the assignment.</span></span> <span data-ttu-id="593fb-108">如果计划将来使用该对象，可能需要保留 Active Directory 对象。</span><span class="sxs-lookup"><span data-stu-id="593fb-108">If you plan to use the object in the future, you might want to keep the Active Directory object.</span></span>



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="593fb-109">从网站中删除 Kerberos 身份验证</span><span class="sxs-lookup"><span data-stu-id="593fb-109">To remove Kerberos authentication from a site</span></span>

1.  <span data-ttu-id="593fb-110">作为 RTCUniversalServerAdmins 组的成员，请登录到运行 Lync Server 2013 的域中的计算机或登录到安装了管理工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="593fb-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="593fb-111">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="593fb-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="593fb-112">从命令行运行以下两个命令：</span><span class="sxs-lookup"><span data-stu-id="593fb-112">From the command line, run the following two commands:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="593fb-113">例如：</span><span class="sxs-lookup"><span data-stu-id="593fb-113">For example:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="593fb-114">对 Kerberos 身份验证进行任何更改（如添加帐户或删除帐户）后，必须从 Lync Server Management Shell 命令提示符运行<STRONG>Enable-CsTopology</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="593fb-114">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

