---
title: 测试并报告 Kerberos 身份验证的功能准备工作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30dda07eb0152f43f60627fcee3a75b14745eea2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="224f7-102">在 Lync Server 2013 中测试并报告 Kerberos 身份验证的功能准备工作</span><span class="sxs-lookup"><span data-stu-id="224f7-102">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="224f7-103">_**主题上次修改时间:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="224f7-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="224f7-104">若要成功完成此过程, 你应以 RTCUniversalServerAdmins 组成员的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="224f7-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="224f7-105">你可以使用**CsKerberosAccountAssignment** Windows PowerShell cmdlet 测试和报告用于 Kerberos 身份验证的网站分配的功能准备情况。</span><span class="sxs-lookup"><span data-stu-id="224f7-105">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="224f7-106">此命令将查询在必需的 Identity 参数中指定的网站。</span><span class="sxs-lookup"><span data-stu-id="224f7-106">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="224f7-107">可选报表参数使 cmdlet 在运行该命令的计算机上将 HTML 报表\\写入 C: 日志。</span><span class="sxs-lookup"><span data-stu-id="224f7-107">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="224f7-108">可选的详细参数将活动信息报告到屏幕。</span><span class="sxs-lookup"><span data-stu-id="224f7-108">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="224f7-109">测试和报告适用于网站的 Kerberos 身份验证的功能准备情况</span><span class="sxs-lookup"><span data-stu-id="224f7-109">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="224f7-110">作为 RTCUniversalServerAdmins 组的成员, 登录到运行 Lync Server 2013 的域或安装了管理工具的计算机上的计算机。</span><span class="sxs-lookup"><span data-stu-id="224f7-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="224f7-111">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="224f7-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="224f7-112">从命令行运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="224f7-112">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="224f7-113">例如：</span><span class="sxs-lookup"><span data-stu-id="224f7-113">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

