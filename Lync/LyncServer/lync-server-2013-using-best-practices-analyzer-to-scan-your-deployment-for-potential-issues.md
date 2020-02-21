---
title: 使用最佳实践分析工具扫描部署以发现潜在问题
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f620712404fffe8e46f8f2a6f066c6ffa7b77d74
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a><span data-ttu-id="426f1-102">使用最佳实践分析工具扫描 Lync Server 2013 部署以发现潜在问题</span><span class="sxs-lookup"><span data-stu-id="426f1-102">Using Best Practices Analyzer to scan your Lync Server 2013 deployment for potential issues</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="426f1-103">_**上次修改的主题：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="426f1-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="426f1-104">要运行最佳做法分析器扫描，您必须指定以下项：</span><span class="sxs-lookup"><span data-stu-id="426f1-104">To run a Best Practices Analyzer scan, you must specify the following:</span></span>

  - <span data-ttu-id="426f1-105">**凭据**   若要运行扫描，您必须使用作为本地 Administrators 组成员的帐户登录到安装了最佳实践分析工具的计算机。</span><span class="sxs-lookup"><span data-stu-id="426f1-105">**Credentials**   To run a scan, you must log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group.</span></span> <span data-ttu-id="426f1-106">此外，您还需要使用具有运行适当扫描所需的用户权限的用户帐户登录，否则在运行最佳做法分析器时，必须指定具有适当用户权限的凭据。</span><span class="sxs-lookup"><span data-stu-id="426f1-106">Additionally, you need to log on by using a user account that has the user rights and permissions required to run the appropriate scans, or you must specify credentials that have the appropriate user rights and permissions when you run Best Practices Analyzer.</span></span> <span data-ttu-id="426f1-107">有关详细信息，请参阅[Lync Server 2013 中的最佳实践分析工具组成员身份和用户权限要求](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md)。</span><span class="sxs-lookup"><span data-stu-id="426f1-107">For details, see [Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span></span>

  - <span data-ttu-id="426f1-108">**扫描范围若**   要指定扫描范围，请选择要扫描的类别和服务器。</span><span class="sxs-lookup"><span data-stu-id="426f1-108">**Scope of scan**   To specify the scope of the scan, select the categories and servers that you want to scan.</span></span> <span data-ttu-id="426f1-109">您可以在 Lync Server 环境中选择特定类别中的所有类别、一个或多个类别或一个或多个服务器。</span><span class="sxs-lookup"><span data-stu-id="426f1-109">You can select all categories, one or more categories, or one or more servers within a specific category in your Lync Server environment.</span></span>

  - <span data-ttu-id="426f1-110">**扫描类型目前**   ，运行状况检查扫描是唯一可用的扫描类型（默认情况下处于选中状态）。</span><span class="sxs-lookup"><span data-stu-id="426f1-110">**Type of scan**   Currently, the Health Check scan is the only type of scan available (selected by default).</span></span> <span data-ttu-id="426f1-111">状况检查扫描生成的报告中包含有关范围中指定的所有服务器的错误、警告和其他信息。</span><span class="sxs-lookup"><span data-stu-id="426f1-111">The Health Check scan generates a report that includes errors, warnings, and other information for all servers specified in the scope.</span></span>

  - <span data-ttu-id="426f1-112">**网络速度**   网络速度选项包括快速 lan （100 mbps 或更高）、LAN （10 Mbps）、Fast WAN （1.5 Mbps）或 WAN （64 kbps）。</span><span class="sxs-lookup"><span data-stu-id="426f1-112">**Network speed**   Network speed options include Fast LAN (100 Mbps or more), LAN (10 Mbps), Fast WAN (1.5 Mbps), or WAN (64 kbps).</span></span> <span data-ttu-id="426f1-113">估计完成扫描的时间基于此设置。</span><span class="sxs-lookup"><span data-stu-id="426f1-113">The estimated time to complete the scan is based on this setting.</span></span> <span data-ttu-id="426f1-114">此设置还用于设置超时期限。</span><span class="sxs-lookup"><span data-stu-id="426f1-114">This setting is also used to set the time-out period.</span></span> <span data-ttu-id="426f1-115">扫描期间，最佳做法分析器在指定时间内等待来自服务器的响应。</span><span class="sxs-lookup"><span data-stu-id="426f1-115">During the scan, the Best Practices Analyzer waits for a response from a server for a specified time.</span></span> <span data-ttu-id="426f1-116">如果没有在指定超时期限内收到响应，它将移到扫描中的下一个服务器。</span><span class="sxs-lookup"><span data-stu-id="426f1-116">If it does not receive a response within the specified time-out period, it moves to the next server in the scan.</span></span> <span data-ttu-id="426f1-117">在速度较慢的网络上，考虑到网络延迟更长，所以此指定超时期限更长。</span><span class="sxs-lookup"><span data-stu-id="426f1-117">On slower networks, this specified time-out period is longer to account for longer network latencies.</span></span> <span data-ttu-id="426f1-118">我们建议您为此参数选择拓扑中最慢的链接，以便该工具不会超时太快。</span><span class="sxs-lookup"><span data-stu-id="426f1-118">We recommend that you select the slowest link in your topology for this parameter so that the tool does not time out too quickly.</span></span>

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a><span data-ttu-id="426f1-119">扫描 Lync Server 2013 部署</span><span class="sxs-lookup"><span data-stu-id="426f1-119">To scan your Lync Server 2013 deployment</span></span>

1.  <span data-ttu-id="426f1-120">使用属于本地 Administrators 组成员并拥有其他所需用户权限的帐户登录安装有最佳做法分析器的计算机。</span><span class="sxs-lookup"><span data-stu-id="426f1-120">Log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group, and has other required user rights and permissions.</span></span>

2.  <span data-ttu-id="426f1-121">单击 "**开始**"，依次指向 "**所有程序**"、" **Microsoft Lync Server 2013**"，然后单击 "**最佳实践分析工具**"。</span><span class="sxs-lookup"><span data-stu-id="426f1-121">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="426f1-122">在“欢迎”\*\*\*\* 屏幕上，单击“为新扫描选择选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="426f1-122">On the **Welcome** screen, click **Select options for a new scan**.</span></span>

4.  <span data-ttu-id="426f1-123">在“连接到 Active Directory”\*\*\*\* 页面上，验证在 **Active Directory 服务器**中指定的名称，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="426f1-123">On the **Connect to Active Directory** page, verify the name specified in **Active Directory Server**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="426f1-124">若要使用您用来登录计算机的凭据运行扫描，请单击“连接到 Active Directory 服务器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="426f1-124">To run a scan using the credentials that you used to log on to the computer, click **Connect to the Active Directory server**.</span></span>
    
      - <span data-ttu-id="426f1-125">若要指定要用于 Active Directory 域服务、边缘服务器或 Exchange Server 的不同凭据，请单击“显示高级登录选项”\*\*\*\*，选中需要单独凭据的每个复选框，为每个选中的复选框指定凭据，然后单击“连接到 Active Directory 服务器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="426f1-125">To specify different credentials that you want to use for Active Directory Domain Services, Edge Server, or Exchange Server, click **Show advanced logon options**, select each check box for which separate credentials are required, specify the credentials for each selected check box, and then click **Connect to the Active Directory server**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="426f1-p105">在开始扫描之前，最佳做法分析器会执行网络和权限检查，以确保指定帐户凭据有效并且最佳做法分析器可以连接到 Active Directory 域服务。如果该工具在工作组服务器上运行，则该工具还验证它能否连接到外围网络中的边缘服务器（即，它们是否包括在扫描中）。</span><span class="sxs-lookup"><span data-stu-id="426f1-p105">Before beginning the scan, Best Practices Analyzer performs a network and permissions check to ensure that the specified account credentials are valid and that Best Practices Analyzer can connect to Active Directory Domain Services. If the tool is running on a workgroup server, the tool also verifies that it can connect to Edge Servers in the perimeter network (that is, if they are included in the scan).</span></span>

    
    </div>

5.  <span data-ttu-id="426f1-128">在“启动新的最佳实践扫描”\*\*\*\* 页面上，选择您要包括在扫描中的选项，指定网络速度，然后单击“开始扫描”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="426f1-128">On the **Start a new Best Practices scan** page, select the options that you want to include in the scan, specify the network speed, and then click **Start scanning**.</span></span>

6.  <span data-ttu-id="426f1-129">在“扫描已完成”\*\*\*\* 页面上，单击“查看该最佳实践扫描的报告”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="426f1-129">On the **Scanning Completed** page, click **View a report of this Best Practices scan**.</span></span>

7.  <span data-ttu-id="426f1-130">在“查看最佳实践报告”\*\*\*\* 页面上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="426f1-130">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="426f1-131">若要以按服务器组件组织的列表的形式查看报告，请单击“列表报告”\*\*\*\*，然后单击“所有问题”\*\*\*\* 选项卡或“信息项”\*\*\*\* 选项卡。</span><span class="sxs-lookup"><span data-stu-id="426f1-131">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="426f1-132">若要以按结果类型组织的层次列表形式查看报告，请单击“目录树报告”\*\*\*\*，然后单击“详细视图”\*\*\*\* 选项卡或“摘要视图”\*\*\*\* 选项卡。</span><span class="sxs-lookup"><span data-stu-id="426f1-132">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="426f1-133">若要查看其他报告，请单击“其他报告”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="426f1-133">To view other reports, click **Other Reports**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="426f1-134">有关最佳实践分析工具报告和这些报告所识别的问题的详细信息，请参阅<A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">在 2013 lync server 2013 中查看并使用最佳实践分析工具创建的报告</A>，并<A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">分析和解决 lync server 中的最佳实践分析工具识别的问题</A>。</span><span class="sxs-lookup"><span data-stu-id="426f1-134">For details about the Best Practices Analyzer reports and the issues they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

