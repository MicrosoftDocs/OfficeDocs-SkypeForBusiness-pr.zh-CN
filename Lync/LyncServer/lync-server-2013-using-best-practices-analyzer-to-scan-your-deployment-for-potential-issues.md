---
title: 使用最佳做法分析程序扫描部署以发现潜在问题
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
ms.openlocfilehash: 1f787268301570d4440240289c19fdd1e266a607
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a><span data-ttu-id="2497f-102">使用最佳做法分析程序扫描 Lync Server 2013 部署以发现潜在问题</span><span class="sxs-lookup"><span data-stu-id="2497f-102">Using Best Practices Analyzer to scan your Lync Server 2013 deployment for potential issues</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2497f-103">_**主题上次修改时间：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="2497f-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="2497f-104">若要运行最佳做法分析器扫描，必须指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="2497f-104">To run a Best Practices Analyzer scan, you must specify the following:</span></span>

  - <span data-ttu-id="2497f-105">**凭据**   若要运行扫描，您必须使用作为本地管理员组成员的帐户登录到安装了最佳做法分析器的计算机。</span><span class="sxs-lookup"><span data-stu-id="2497f-105">**Credentials**   To run a scan, you must log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group.</span></span> <span data-ttu-id="2497f-106">此外，你需要使用具有运行相应扫描所需的用户权限和权限的用户帐户进行登录，或者你必须指定在运行最佳做法分析器时具有相应的用户权限和权限的凭据。</span><span class="sxs-lookup"><span data-stu-id="2497f-106">Additionally, you need to log on by using a user account that has the user rights and permissions required to run the appropriate scans, or you must specify credentials that have the appropriate user rights and permissions when you run Best Practices Analyzer.</span></span> <span data-ttu-id="2497f-107">有关详细信息，请参阅[Lync Server 2013 中的最佳做法分析器的组成员身份和用户权限要求](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md)。</span><span class="sxs-lookup"><span data-stu-id="2497f-107">For details, see [Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span></span>

  - <span data-ttu-id="2497f-108">**扫描范围若**   要指定扫描的范围，请选择要扫描的类别和服务器。</span><span class="sxs-lookup"><span data-stu-id="2497f-108">**Scope of scan**   To specify the scope of the scan, select the categories and servers that you want to scan.</span></span> <span data-ttu-id="2497f-109">你可以选择 Lync Server 环境中特定类别内的所有类别、一个或多个类别，或者一个或多个服务器。</span><span class="sxs-lookup"><span data-stu-id="2497f-109">You can select all categories, one or more categories, or one or more servers within a specific category in your Lync Server environment.</span></span>

  - <span data-ttu-id="2497f-110">**扫描类型目前**   ，运行状况检查扫描是唯一可用的扫描类型（默认情况下处于选中状态）。</span><span class="sxs-lookup"><span data-stu-id="2497f-110">**Type of scan**   Currently, the Health Check scan is the only type of scan available (selected by default).</span></span> <span data-ttu-id="2497f-111">运行状况检查扫描将生成一个报表，其中包含作用域中指定的所有服务器的错误、警告和其他信息。</span><span class="sxs-lookup"><span data-stu-id="2497f-111">The Health Check scan generates a report that includes errors, warnings, and other information for all servers specified in the scope.</span></span>

  - <span data-ttu-id="2497f-112">**网络速度**   的网络速度选项包括快速 lan （100 mbps 或更高）、LAN （10 mbps）、快速 WAN （1.5 Mbps）或 WAN （64 kbps）。</span><span class="sxs-lookup"><span data-stu-id="2497f-112">**Network speed**   Network speed options include Fast LAN (100 Mbps or more), LAN (10 Mbps), Fast WAN (1.5 Mbps), or WAN (64 kbps).</span></span> <span data-ttu-id="2497f-113">完成扫描的估计时间基于此设置。</span><span class="sxs-lookup"><span data-stu-id="2497f-113">The estimated time to complete the scan is based on this setting.</span></span> <span data-ttu-id="2497f-114">此设置还用于设置超时时间。</span><span class="sxs-lookup"><span data-stu-id="2497f-114">This setting is also used to set the time-out period.</span></span> <span data-ttu-id="2497f-115">在扫描期间，最佳做法分析器会等待服务器的响应指定时间。</span><span class="sxs-lookup"><span data-stu-id="2497f-115">During the scan, the Best Practices Analyzer waits for a response from a server for a specified time.</span></span> <span data-ttu-id="2497f-116">如果在指定的超时期限内未收到响应，则它将移动到扫描中的下一个服务器。</span><span class="sxs-lookup"><span data-stu-id="2497f-116">If it does not receive a response within the specified time-out period, it moves to the next server in the scan.</span></span> <span data-ttu-id="2497f-117">在较慢的网络上，此指定的超时周期会延长较长的网络延迟时间。</span><span class="sxs-lookup"><span data-stu-id="2497f-117">On slower networks, this specified time-out period is longer to account for longer network latencies.</span></span> <span data-ttu-id="2497f-118">我们建议你选择此参数的拓扑中最慢的链接，以便该工具的时间不会太快。</span><span class="sxs-lookup"><span data-stu-id="2497f-118">We recommend that you select the slowest link in your topology for this parameter so that the tool does not time out too quickly.</span></span>

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a><span data-ttu-id="2497f-119">扫描 Lync Server 2013 部署</span><span class="sxs-lookup"><span data-stu-id="2497f-119">To scan your Lync Server 2013 deployment</span></span>

1.  <span data-ttu-id="2497f-120">使用本地管理员组成员的帐户登录到安装了最佳做法分析器的计算机，并具有其他所需的用户权限和权限。</span><span class="sxs-lookup"><span data-stu-id="2497f-120">Log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group, and has other required user rights and permissions.</span></span>

2.  <span data-ttu-id="2497f-121">单击 "**开始**"，指向 "**所有程序**"，单击 " **Microsoft Lync Server 2013**"，然后单击 "**最佳做法分析器**"。</span><span class="sxs-lookup"><span data-stu-id="2497f-121">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="2497f-122">在 "**欢迎**" 屏幕上，单击 "**选择新扫描的选项**"。</span><span class="sxs-lookup"><span data-stu-id="2497f-122">On the **Welcome** screen, click **Select options for a new scan**.</span></span>

4.  <span data-ttu-id="2497f-123">在 "**连接到 Active directory** " 页面上，验证**active directory Server**中指定的名称，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="2497f-123">On the **Connect to Active Directory** page, verify the name specified in **Active Directory Server**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="2497f-124">若要使用用于登录计算机的凭据运行扫描，请单击 "**连接到 Active Directory 服务器**"。</span><span class="sxs-lookup"><span data-stu-id="2497f-124">To run a scan using the credentials that you used to log on to the computer, click **Connect to the Active Directory server**.</span></span>
    
      - <span data-ttu-id="2497f-125">若要指定要用于 Active Directory 域服务、边缘服务器或 Exchange Server 的其他凭据，请单击 "**显示高级登录选项**"，选中每个需要单独凭据的复选框，指定每个所选复选框的凭据，然后单击 "**连接到 Active Directory 服务器**"。</span><span class="sxs-lookup"><span data-stu-id="2497f-125">To specify different credentials that you want to use for Active Directory Domain Services, Edge Server, or Exchange Server, click **Show advanced logon options**, select each check box for which separate credentials are required, specify the credentials for each selected check box, and then click **Connect to the Active Directory server**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="2497f-126">在开始扫描之前，最佳做法分析器会执行网络和权限检查，以确保指定的帐户凭据有效，并且最佳做法分析器可以连接到 Active Directory 域服务。</span><span class="sxs-lookup"><span data-stu-id="2497f-126">Before beginning the scan, Best Practices Analyzer performs a network and permissions check to ensure that the specified account credentials are valid and that Best Practices Analyzer can connect to Active Directory Domain Services.</span></span> <span data-ttu-id="2497f-127">如果该工具在工作组服务器上运行，则该工具还会验证它是否可以连接到外围网络中的边缘服务器（即它们是否包含在扫描中）。</span><span class="sxs-lookup"><span data-stu-id="2497f-127">If the tool is running on a workgroup server, the tool also verifies that it can connect to Edge Servers in the perimeter network (that is, if they are included in the scan).</span></span>

    
    </div>

5.  <span data-ttu-id="2497f-128">在 "**启动新的最佳做法扫描**" 页面上，选择要包括在扫描中的选项，指定网络速度，然后单击 "**开始扫描**"。</span><span class="sxs-lookup"><span data-stu-id="2497f-128">On the **Start a new Best Practices scan** page, select the options that you want to include in the scan, specify the network speed, and then click **Start scanning**.</span></span>

6.  <span data-ttu-id="2497f-129">在 "**扫描已完成**" 页面上，单击 "**查看此最佳做法扫描的报告**"。</span><span class="sxs-lookup"><span data-stu-id="2497f-129">On the **Scanning Completed** page, click **View a report of this Best Practices scan**.</span></span>

7.  <span data-ttu-id="2497f-130">在 "**查看最佳做法报告**" 页面上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="2497f-130">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="2497f-131">若要查看按服务器组件组织的列表中的报告，请单击 "**列表报告**"，然后单击 "**所有问题**" 选项卡或 "**信息性项目**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2497f-131">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="2497f-132">若要将报表作为按结果类型组织的分层列表进行查看，请单击 "**树报表**"，然后单击 "**详细视图**" 选项卡或 "**摘要视图**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2497f-132">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="2497f-133">若要查看其他报表，请单击 "**其他报表**"。</span><span class="sxs-lookup"><span data-stu-id="2497f-133">To view other reports, click **Other Reports**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="2497f-134">有关最佳做法分析器报告及其标识问题的详细信息，请参阅<A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">在 lync server 2013 中查看和使用由最佳</A>做法分析器创建的报表，并<A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">分析和解决 lync server 2013 中由最佳做法分析器识别的问题</A>。</span><span class="sxs-lookup"><span data-stu-id="2497f-134">For details about the Best Practices Analyzer reports and the issues they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

