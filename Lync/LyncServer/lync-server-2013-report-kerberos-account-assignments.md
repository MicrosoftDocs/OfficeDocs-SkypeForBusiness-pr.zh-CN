---
title: Lync Server 2013：报告 Kerberos 帐户分配
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b02eb3cae7a7d2bbeb4cc3b9dce0a7daa8ee5c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a><span data-ttu-id="31da5-102">在 Lync Server 2013 中报告 Kerberos 帐户分配</span><span class="sxs-lookup"><span data-stu-id="31da5-102">Report Kerberos account assignments in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31da5-103">_**主题上次修改时间:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="31da5-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="31da5-104">若要成功完成此过程, 你应以 RTCUniversalServerAdmins 组成员的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="31da5-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="31da5-105">你可以使用**CsKerberosAccountAssignment** cmdlet 查询有关 Kerberos 身份验证帐户分配的信息, 并报告有关你的部署中的当前作业的信息。</span><span class="sxs-lookup"><span data-stu-id="31da5-105">You can use the **Get-CsKerberosAccountAssignment** cmdlet to query information about the Kerberos authentication account assignments and report information about the current assignments in your deployment.</span></span>

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a><span data-ttu-id="31da5-106">查询网站的 Kerberos 身份验证帐户分配</span><span class="sxs-lookup"><span data-stu-id="31da5-106">To query Kerberos authentication account assignments for a site</span></span>

1.  <span data-ttu-id="31da5-107">作为 RTCUniversalServerAdmins 组的成员, 请登录到运行 Lync Server 2013 的域中的计算机或登录到安装了管理工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="31da5-107">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="31da5-108">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="31da5-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="31da5-109">从命令行运行以下命令之一:</span><span class="sxs-lookup"><span data-stu-id="31da5-109">From the command line, run one of the following commands:</span></span>
    
      - <span data-ttu-id="31da5-110">若要查询组织中的所有 Kerberos 身份验证帐户分配并返回每个的作业信息, 请运行不带任何参数的 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="31da5-110">To query all Kerberos authentication account assignments in your organization and return assignment information about each of them, run the cmdlet without any parameters:</span></span>
        
            Get-CsKerberosAccountAssignment
    
      - <span data-ttu-id="31da5-111">若要在部署中查询所有 Kerberos 身份验证帐户分配并返回每个 Kerberos 身份验证帐户分配的信息, 请通过 Identity 参数运行 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="31da5-111">To query all Kerberos authentication account assignments in your deployment and return site assignment information about each of them, run the cmdlet with the Identity parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        <span data-ttu-id="31da5-112">例如：</span><span class="sxs-lookup"><span data-stu-id="31da5-112">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - <span data-ttu-id="31da5-113">若要查询单个网站中的所有 Kerberos 身份验证帐户分配并返回有关每个帐户的作业信息, 请使用筛选器参数运行 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="31da5-113">To query all Kerberos authentication account assignments in a single site and return assignment information about each of them, run the cmdlet with the Filter parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        <span data-ttu-id="31da5-114">例如：</span><span class="sxs-lookup"><span data-stu-id="31da5-114">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="31da5-115">为 Filter 参数指定 \* SiteName 返回有关包含指定网站名称的所有网站的信息, 这些网站在网站标识符中的任意位置 (例如, 包含字符串 Redmond 的所有网站位于网站标识符中)。</span><span class="sxs-lookup"><span data-stu-id="31da5-115">Specifying \*SiteName for the Filter parameter returns information about all sites that contain the specified site name anywhere in the site identifier (for example, all sites that contain the string Redmond in the site identifier).</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

