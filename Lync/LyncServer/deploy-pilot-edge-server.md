---
title: 部署试点边缘服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4d8fbf34e618c5bf41d3b005c70897c5dddb69
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="a4f58-102">部署试点边缘服务器</span><span class="sxs-lookup"><span data-stu-id="a4f58-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4f58-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a4f58-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a4f58-104">本主题重点介绍在部署 Lync Server 2013 边缘服务器之前应注意的配置设置。</span><span class="sxs-lookup"><span data-stu-id="a4f58-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="a4f58-105">Lync Server 2013 的部署和配置过程与 Lync Server 2010 非常相似。</span><span class="sxs-lookup"><span data-stu-id="a4f58-105">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="a4f58-106">本节仅重点介绍了应作为试点池部署的一部分考虑的关键点。</span><span class="sxs-lookup"><span data-stu-id="a4f58-106">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="a4f58-107">有关详细步骤，请参阅部署文档中的在[Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)，它介绍了部署过程，同时提供了外部用户访问的配置信息。</span><span class="sxs-lookup"><span data-stu-id="a4f58-107">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="a4f58-p102">在“定义新的边缘池”\*\*\*\* 向导中导航时，查看以下步骤中显示的关键配置设置。请注意，仅显示了“定义新的边缘池”\*\*\*\* 向导的部分页面。</span><span class="sxs-lookup"><span data-stu-id="a4f58-p102">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="a4f58-110">**定义边缘池**</span><span class="sxs-lookup"><span data-stu-id="a4f58-110">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="a4f58-111">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="a4f58-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="a4f58-112">导航到 "Lync Server 2013" 节点。</span><span class="sxs-lookup"><span data-stu-id="a4f58-112">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="a4f58-113">右键单击“边缘池”\*\*\*\*，然后单击“新建边缘池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a4f58-113">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="a4f58-114">!["定义新的边缘池" 对话框](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg ""定义新的边缘池" 对话框")</span><span class="sxs-lookup"><span data-stu-id="a4f58-114">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="a4f58-115">边缘池可以是**多计算机池**，也可以是**单计算机池**。</span><span class="sxs-lookup"><span data-stu-id="a4f58-115">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="a4f58-116">![定义 "边缘池 FQDN" 对话框](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "定义 "边缘池 FQDN" 对话框")</span><span class="sxs-lookup"><span data-stu-id="a4f58-116">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="a4f58-117">在“选择功能”\*\*\*\* 页上，不要启用联盟或 XMPP 联盟。</span><span class="sxs-lookup"><span data-stu-id="a4f58-117">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="a4f58-118">联合身份验证和 XMPP 联盟当前通过旧版 Lync Server 2010 边缘服务器进行路由。</span><span class="sxs-lookup"><span data-stu-id="a4f58-118">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="a4f58-119">将在迁移的稍后阶段中配置这些功能。</span><span class="sxs-lookup"><span data-stu-id="a4f58-119">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="a4f58-120">!["选择功能" 对话框](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg ""选择功能" 对话框")</span><span class="sxs-lookup"><span data-stu-id="a4f58-120">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="a4f58-121">接下来，继续完成以下向导页：**外部 fqdn**、**定义内部 Ip 地址**和**定义外部 ip 地址**。</span><span class="sxs-lookup"><span data-stu-id="a4f58-121">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="a4f58-122">在 "**定义下一个跃点**" 页上，选择 Lync Server 2010 边缘池的下一个跃点的控制器。</span><span class="sxs-lookup"><span data-stu-id="a4f58-122">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="a4f58-123">!["定义下一跃点" 对话框](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg ""定义下一跃点" 对话框")</span><span class="sxs-lookup"><span data-stu-id="a4f58-123">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="a4f58-124">在 "**关联前端或中介池**" 页上，此时不要将池与此边缘池相关联。</span><span class="sxs-lookup"><span data-stu-id="a4f58-124">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="a4f58-125">外部媒体流量当前通过旧版 Lync Server 2010 边缘服务器路由。</span><span class="sxs-lookup"><span data-stu-id="a4f58-125">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="a4f58-126">将在迁移的稍后阶段中配置此设置。</span><span class="sxs-lookup"><span data-stu-id="a4f58-126">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="a4f58-127">!["关联前端池" 对话框](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg ""关联前端池" 对话框")</span><span class="sxs-lookup"><span data-stu-id="a4f58-127">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="a4f58-128">单击“完成”\*\*\*\*，然后**发布**拓扑。</span><span class="sxs-lookup"><span data-stu-id="a4f58-128">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="a4f58-129">按照部署文档中的安装边缘服务器上的[Lync Server 2013](lync-server-2013-install-edge-servers.md)中的步骤操作，将文件安装在新的边缘服务器上，配置证书，并启动这些服务。</span><span class="sxs-lookup"><span data-stu-id="a4f58-129">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="a4f58-130">请务必遵循部署文档中的 "在[Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)" 主题中的准则。</span><span class="sxs-lookup"><span data-stu-id="a4f58-130">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="a4f58-131">本节仅提供了一些有关安装这些服务器角色时的配置设置的指南。</span><span class="sxs-lookup"><span data-stu-id="a4f58-131">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="a4f58-132">现在，您应该已与 Lync Server 2013 Edge 服务器部署并行部署了旧版 Lync Server 2010 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="a4f58-132">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="a4f58-133">在进入下一个阶段之前，确认这两个部署都正常运行，服务已启动，并且您可以管理每个部署。</span><span class="sxs-lookup"><span data-stu-id="a4f58-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

