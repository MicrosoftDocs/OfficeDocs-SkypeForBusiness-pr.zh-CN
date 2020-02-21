---
title: 测试和报告 Kerberos 身份验证的功能准备情况
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e160af5920f58b3813bd168c7f4fbe2e0f0cf95c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="532c1-102">在 Lync Server 2013 中测试和报告 Kerberos 身份验证的功能准备情况</span><span class="sxs-lookup"><span data-stu-id="532c1-102">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="532c1-103">_**上次修改的主题：** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="532c1-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="532c1-104">要成功完成此过程，应以 RTCUniversalServerAdmins 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="532c1-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="532c1-105">您可以使用**CsKerberosAccountAssignment** Windows PowerShell cmdlet 测试和报告 Kerberos 身份验证的网站分配的功能准备情况。</span><span class="sxs-lookup"><span data-stu-id="532c1-105">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="532c1-106">此命令查询必需参数 Identity 中指定的站点。</span><span class="sxs-lookup"><span data-stu-id="532c1-106">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="532c1-107">可选报告参数使 cmdlet 将 HTML 报告写入 C：\\运行该命令的计算机上的日志。</span><span class="sxs-lookup"><span data-stu-id="532c1-107">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="532c1-108">可选参数 Verbose 会将活动信息显示在屏幕上。</span><span class="sxs-lookup"><span data-stu-id="532c1-108">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="532c1-109">测试并报告站点的 Kerberos 身份验证的运行就绪情况</span><span class="sxs-lookup"><span data-stu-id="532c1-109">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="532c1-110">作为 RTCUniversalServerAdmins 组的成员，登录到运行 Lync Server 2013 的域中的计算机，或登录到安装了管理工具的计算机上。</span><span class="sxs-lookup"><span data-stu-id="532c1-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="532c1-111">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="532c1-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="532c1-112">在命令行中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="532c1-112">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="532c1-113">例如：</span><span class="sxs-lookup"><span data-stu-id="532c1-113">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

