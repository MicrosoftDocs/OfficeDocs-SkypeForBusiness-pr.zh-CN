---
title: Lync Server 2013：报告 Kerberos 帐户分配
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9576d772aa340e7d578186974fb00418479ea691
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a><span data-ttu-id="1c650-102">在 Lync Server 2013 中报告 Kerberos 帐户分配</span><span class="sxs-lookup"><span data-stu-id="1c650-102">Report Kerberos account assignments in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c650-103">_**上次修改的主题：** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="1c650-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="1c650-104">要成功完成此过程，应以 RTCUniversalServerAdmins 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="1c650-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="1c650-105">可以使用 **Get-CsKerberosAccountAssignment** cmdlet 来查询有关 Kerberos 身份验证帐户分配的信息和报告部署中的当前分配的相关信息。</span><span class="sxs-lookup"><span data-stu-id="1c650-105">You can use the **Get-CsKerberosAccountAssignment** cmdlet to query information about the Kerberos authentication account assignments and report information about the current assignments in your deployment.</span></span>

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a><span data-ttu-id="1c650-106">查询某个站点的 Kerberos 身份验证帐户分配</span><span class="sxs-lookup"><span data-stu-id="1c650-106">To query Kerberos authentication account assignments for a site</span></span>

1.  <span data-ttu-id="1c650-107">作为 RTCUniversalServerAdmins 组的成员，登录到运行 Lync Server 2013 的域中的计算机或登录到安装了管理工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="1c650-107">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="1c650-108">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1c650-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1c650-109">从命令行运行下列命令之一：</span><span class="sxs-lookup"><span data-stu-id="1c650-109">From the command line, run one of the following commands:</span></span>
    
      - <span data-ttu-id="1c650-110">要查询组织中的所有 Kerberos 身份验证帐户分配并返回每一个的相关分配信息，请运行不带任何参数的 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="1c650-110">To query all Kerberos authentication account assignments in your organization and return assignment information about each of them, run the cmdlet without any parameters:</span></span>
        
            Get-CsKerberosAccountAssignment
    
      - <span data-ttu-id="1c650-111">要查询部署中的所有 Kerberos 身份验证帐户分配并返回每一个的相关站点分配信息，请运行带有 Identity 参数的 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="1c650-111">To query all Kerberos authentication account assignments in your deployment and return site assignment information about each of them, run the cmdlet with the Identity parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        <span data-ttu-id="1c650-112">例如：</span><span class="sxs-lookup"><span data-stu-id="1c650-112">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - <span data-ttu-id="1c650-113">要查询单个站点中的所有 Kerberos 身份验证帐户分配并返回每一个的相关分配信息，请运行带有 Filter 参数的 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="1c650-113">To query all Kerberos authentication account assignments in a single site and return assignment information about each of them, run the cmdlet with the Filter parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        <span data-ttu-id="1c650-114">例如：</span><span class="sxs-lookup"><span data-stu-id="1c650-114">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1c650-115">指定 Filter 参数的 \*SiteName 将返回有关在站点标识符的任何位置包含指定的站点名称的所有站点（例如，在站点标识符中包含字符串 Redmond 的所有站点）的相关信息。</span><span class="sxs-lookup"><span data-stu-id="1c650-115">Specifying \*SiteName for the Filter parameter returns information about all sites that contain the specified site name anywhere in the site identifier (for example, all sites that contain the string Redmond in the site identifier).</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

