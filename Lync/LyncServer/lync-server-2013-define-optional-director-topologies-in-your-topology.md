---
title: Lync Server 2013：在拓扑中定义可选控制器拓扑
description: Lync Server 2013：在拓扑中定义可选控制器拓扑。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bc82108d4277969489739fc81db07ec6f96bb96
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542648"
---
# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a><span data-ttu-id="6a83a-103">在拓扑中为 Lync Server 2013 定义可选控制器拓扑</span><span class="sxs-lookup"><span data-stu-id="6a83a-103">Define optional Director topologies in your topology for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a83a-104">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="6a83a-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="6a83a-105">Lync Server 2013 控制器可以是单实例服务器，也可以将其作为多个控制器的负载平衡池进行安装，以实现更高的可用性和容量。</span><span class="sxs-lookup"><span data-stu-id="6a83a-105">Lync Server 2013 Directors can be single-instance servers or they can be installed as a load-balanced pool of multiple Directors for higher availability and capacity.</span></span> <span data-ttu-id="6a83a-106">支持硬件负载平衡和域名系统 (DNS) 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="6a83a-106">Both hardware load balancing and Domain Name System (DNS) load balancing are supported.</span></span> <span data-ttu-id="6a83a-107">本主题介绍如何为控制器池配置 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="6a83a-107">This topic explains how to configure DNS load balancing for Director pools.</span></span>

<span data-ttu-id="6a83a-108">要在添加或删除服务器角色后成功发布、启用或禁用拓扑，您应该以 **RTCUniversalServerAdmins** 和 **Domain Admins** 组成员的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="6a83a-108">To successfully publish, enable, or disable a topology when you add or remove a server role, you should be logged on as a user who is a member of the **RTCUniversalServerAdmins** and **Domain Admins** groups.</span></span> <span data-ttu-id="6a83a-109">还可以委派适当的管理员权限，以添加服务器角色。</span><span class="sxs-lookup"><span data-stu-id="6a83a-109">You can also delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="6a83a-110">有关详细信息，请参阅 Standard Edition server 或 Enterprise Edition server Deployment 文档中的 " [在 Lync Server 2013 中委派安装程序权限](lync-server-2013-delegate-setup-permissions.md) "。</span><span class="sxs-lookup"><span data-stu-id="6a83a-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="6a83a-111">对于其他配置更改，只需要“RTCUniversalServerAdmins”\*\*\*\* 组的成员身份。</span><span class="sxs-lookup"><span data-stu-id="6a83a-111">For other configuration changes, only membership in the **RTCUniversalServerAdmins** group is required.</span></span>

<span data-ttu-id="6a83a-112">本主题介绍为两个控制器拓扑定义和发布拓扑的步骤：</span><span class="sxs-lookup"><span data-stu-id="6a83a-112">This topic describes the steps to define and publish the topology for the two Director topologies:</span></span>

  - <span data-ttu-id="6a83a-113">定义控制器（单实例）</span><span class="sxs-lookup"><span data-stu-id="6a83a-113">To define the Director (single instance)</span></span>

  - <span data-ttu-id="6a83a-114">定义控制器（多控制器池）</span><span class="sxs-lookup"><span data-stu-id="6a83a-114">To define the Director (multiple Director pool)</span></span>

<div>

## <a name="to-define-the-director-single-instance"></a><span data-ttu-id="6a83a-115">定义控制器（单实例）</span><span class="sxs-lookup"><span data-stu-id="6a83a-115">To define the Director (single instance)</span></span>

1.  <span data-ttu-id="6a83a-116">启动拓扑生成器：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="6a83a-116">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="6a83a-117">在欢迎页上，单击“从现有部署下载拓扑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a83a-117">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="6a83a-118">在“将拓扑另存为”\*\*\*\* 对话框中，键入现有拓扑的本地副本的名称和位置，然后单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a83a-118">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="6a83a-119">展开计划向其中添加控制器的站点，右键单击“控制器池”\*\*\*\*，然后单击“新建控制器池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a83a-119">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="6a83a-120">在“定义控制器池 FQDN”\*\*\*\* 对话框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6a83a-120">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="6a83a-121">在“池 FQDN”\*\*\*\* 中，键入控制器池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6a83a-121">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="6a83a-122">单击“单个计算机池”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a83a-122">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="6a83a-123">在“定义文件共享”\*\*\*\* 对话框中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="6a83a-123">In the **Define the file share** dialog box, do one of the following:</span></span>
    
    1.  <span data-ttu-id="6a83a-124">要使用现有的文件共享，请单击“使用先前定义的文件共享”\*\*\*\*，从列表中选择一个文件共享，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a83a-124">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
    2.  <span data-ttu-id="6a83a-125">要创建新的文件共享，请单击“定义新的文件共享”\*\*\*\*，在“文件服务器 FQDN”\*\*\*\* 中键入文件共享位置的 FQDN，在“文件共享”\*\*\*\* 中键入共享的名称，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a83a-125">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6a83a-126">在发布拓扑前，此步骤中指定或创建的文件共享必须已存在或已创建。</span><span class="sxs-lookup"><span data-stu-id="6a83a-126">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="6a83a-127">实际上未使用分配给控制器的文件共享，因此可以分配组织中任何池的文件共享。</span><span class="sxs-lookup"><span data-stu-id="6a83a-127">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

7.  <span data-ttu-id="6a83a-128">在“指定 Web 服务 URL”\*\*\*\* 对话框的“外部基 URL”\*\*\*\* 中，指定控制器的 FQDN，然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a83a-128">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6a83a-129">该名称必须可以从 Internet DNS 服务器进行解析并指向反向代理的公共 IP 地址，以侦听对该 URL 的 HTTP/HTTPS 请求，并将其代理到该控制器上的外部 Web 服务虚拟目录中。</span><span class="sxs-lookup"><span data-stu-id="6a83a-129">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests to that URL and proxies them to the external Web Services virtual directory on that Director.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="6a83a-130">如果您有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="6a83a-130">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="6a83a-131">例如，如果将前端服务器的外部 Web 服务 FQDN 定义为 <STRONG>pool01.contoso.com</STRONG>，则不能将 <STRONG>pool01.contoso.com</STRONG> 用于另一个前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="6a83a-131">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="6a83a-132">如果还部署控制器，则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须与任何其他控制器或控制器池以及任何前端池或前端服务器都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="6a83a-132">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="6a83a-133">如果决定使用自定义的 FQDN 覆盖内部 web 服务，则每个 FQDN 必须与任何其他前端池、控制器或控制器池都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="6a83a-133">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

8.  <span data-ttu-id="6a83a-134">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="6a83a-134">Publish the topology.</span></span>

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a><span data-ttu-id="6a83a-135">定义控制器（多控制器池）</span><span class="sxs-lookup"><span data-stu-id="6a83a-135">To define the Director (multiple Director pool)</span></span>

1.  <span data-ttu-id="6a83a-136">启动拓扑生成器：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="6a83a-136">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="6a83a-137">在欢迎页上，单击“从现有部署下载拓扑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a83a-137">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="6a83a-138">在“将拓扑另存为”\*\*\*\* 对话框中，键入现有拓扑的本地副本的名称和位置，然后单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a83a-138">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="6a83a-139">展开计划向其中添加控制器的站点，右键单击“控制器池”\*\*\*\*，然后单击“新建控制器池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a83a-139">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="6a83a-140">在“定义控制器池 FQDN”\*\*\*\* 对话框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6a83a-140">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="6a83a-141">在“池 FQDN”\*\*\*\* 中，键入控制器池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6a83a-141">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="6a83a-142">单击“多个计算机池”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a83a-142">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="6a83a-143">在“定义此池中的计算机”\*\*\*\* 对话框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6a83a-143">In the **Define the computers in this pool** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="6a83a-144">指定第一个池成员的计算机 FQDN，然后单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a83a-144">Specify the computer FQDN of the first pool member, and then click **Add**.</span></span>
    
      - <span data-ttu-id="6a83a-p104">为想要添加的每台计算机重复以上步骤。完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a83a-p104">Repeat the previous step for each computer that you want to add. When you are finished, click **Next**.</span></span>

7.  <span data-ttu-id="6a83a-147">在“定义文件共享”\*\*\*\* 对话框中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="6a83a-147">In the **Define the file share** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="6a83a-148">要使用现有的文件共享，请单击“使用先前定义的文件共享”\*\*\*\*，从列表中选择一个文件共享，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a83a-148">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
      - <span data-ttu-id="6a83a-149">要创建新的文件共享，请单击“定义新的文件共享”\*\*\*\*，在“文件服务器 FQDN”\*\*\*\* 中键入文件共享位置的 FQDN，在“文件共享”\*\*\*\* 中键入共享的名称，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a83a-149">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6a83a-150">在发布拓扑前，此步骤中指定或创建的文件共享必须已存在或已创建。</span><span class="sxs-lookup"><span data-stu-id="6a83a-150">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="6a83a-151">实际上未使用分配给控制器的文件共享，因此可以分配组织中任何池的文件共享。</span><span class="sxs-lookup"><span data-stu-id="6a83a-151">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

8.  <span data-ttu-id="6a83a-152">在“指定 Web 服务 URL”\*\*\*\* 对话框的“外部基 URL”\*\*\*\* 中，指定控制器的 FQDN，然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a83a-152">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6a83a-153">该名称必须可从 Internet DNS 服务器解析，并指向反向代理的公用 IP 地址，该代理侦听发送到该 URL 的 HTTP/HTTPS 请求，并将其代理到该控制器池上的外部 Web 服务虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="6a83a-153">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests sent to that URL and proxies them to the external Web Services virtual directory on that Director pool.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="6a83a-154">如果您有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="6a83a-154">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="6a83a-155">例如，如果将前端服务器的外部 Web 服务 FQDN 定义为 <STRONG>pool01.contoso.com</STRONG>，则不能将 <STRONG>pool01.contoso.com</STRONG> 用于另一个前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="6a83a-155">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="6a83a-156">如果还部署控制器，则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须与任何其他控制器或控制器池以及任何前端池或前端服务器都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="6a83a-156">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="6a83a-157">如果决定使用自定义的 FQDN 覆盖内部 web 服务，则每个 FQDN 必须与任何其他前端池、控制器或控制器池都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="6a83a-157">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

9.  <span data-ttu-id="6a83a-158">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="6a83a-158">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

