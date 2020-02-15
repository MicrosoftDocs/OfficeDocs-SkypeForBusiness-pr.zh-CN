---
title: 部署试点边缘服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69d6d83751dd4e8b28a460f154b35416d80e0bb6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="50a25-102">部署试点边缘服务器</span><span class="sxs-lookup"><span data-stu-id="50a25-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50a25-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="50a25-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="50a25-104">本主题重点介绍在部署 Lync Server 2013 边缘服务器之前应注意的配置设置。</span><span class="sxs-lookup"><span data-stu-id="50a25-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="50a25-105">本节只着重介绍在部署试点边缘池的过程中应考虑的关键点。</span><span class="sxs-lookup"><span data-stu-id="50a25-105">This section only highlights key points you should consider as part of your pilot Edge pool deployment.</span></span> <span data-ttu-id="50a25-106">有关详细步骤，请参阅部署文档中的在[Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)，它介绍了部署过程，同时提供了外部用户访问的配置信息。</span><span class="sxs-lookup"><span data-stu-id="50a25-106">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="50a25-p102">在“定义新的边缘池”\*\*\*\* 向导中导航时，查看以下步骤中显示的关键配置设置。请注意，仅显示了“定义新的边缘池”\*\*\*\* 向导的部分页面。</span><span class="sxs-lookup"><span data-stu-id="50a25-p102">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="50a25-109">**定义边缘池**</span><span class="sxs-lookup"><span data-stu-id="50a25-109">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="50a25-110">使用拓扑生成器打开试点池拓扑。</span><span class="sxs-lookup"><span data-stu-id="50a25-110">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="50a25-111">导航到 "Lync Server 2013" 节点。</span><span class="sxs-lookup"><span data-stu-id="50a25-111">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="50a25-112">右键单击“边缘池”\*\*\*\*，然后单击“新建边缘池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="50a25-112">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="50a25-113">!["定义新的边缘池" 对话框](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg ""定义新的边缘池" 对话框")</span><span class="sxs-lookup"><span data-stu-id="50a25-113">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="50a25-114">边缘池可以是**多计算机池**，也可以是**单计算机池**。</span><span class="sxs-lookup"><span data-stu-id="50a25-114">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="50a25-115">![定义 "边缘池 FQDN" 对话框](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "定义 "边缘池 FQDN" 对话框")</span><span class="sxs-lookup"><span data-stu-id="50a25-115">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="50a25-116">在“选择功能”\*\*\*\* 页上，不要启用联盟或 XMPP 联盟。</span><span class="sxs-lookup"><span data-stu-id="50a25-116">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="50a25-117">联盟和 XMPP 联合身份验证当前是通过旧版 Office 通信服务器 2007 R2 Edge 服务器路由的。</span><span class="sxs-lookup"><span data-stu-id="50a25-117">Federation and XMPP federation are currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="50a25-118">将在迁移的稍后阶段中配置这些功能。</span><span class="sxs-lookup"><span data-stu-id="50a25-118">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="50a25-119">!["选择功能" 对话框](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg ""选择功能" 对话框")</span><span class="sxs-lookup"><span data-stu-id="50a25-119">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="50a25-120">接下来，继续完成以下向导页：“选择 IP 选项”\*\*\*\*、“外部 FQDN”\*\*\*\*、“定义内部 IP 地址”\*\*\*\* 和“定义外部 IP 地址”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="50a25-120">Next, continue completing the following wizard pages: **Select IP options**, **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="50a25-121">在 "**定义下一个跃点**" 页上，选择 Lync Server 2013 边缘池的下一个跃点的控制器。</span><span class="sxs-lookup"><span data-stu-id="50a25-121">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2013 Edge pool.</span></span>
    
    <span data-ttu-id="50a25-122">!["定义新的边缘池" 对话框，"下一跃点池" 列表](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg ""定义新的边缘池" 对话框，"下一跃点池" 列表")</span><span class="sxs-lookup"><span data-stu-id="50a25-122">![Define New Edge Pool dialog, Next hop pool list](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Define New Edge Pool dialog, Next hop pool list")</span></span>

7.  <span data-ttu-id="50a25-123">在 "**关联前端池**" 页上，此时不要将池与此边缘池相关联。</span><span class="sxs-lookup"><span data-stu-id="50a25-123">On the **Associate Front End pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="50a25-124">外部媒体流量当前通过旧版 Office 通信服务器 2007 R2 边缘服务器路由。</span><span class="sxs-lookup"><span data-stu-id="50a25-124">External media traffic is currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="50a25-125">将在迁移的稍后阶段中配置此设置。</span><span class="sxs-lookup"><span data-stu-id="50a25-125">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="50a25-126">!["定义新的边缘池" 对话框](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg ""定义新的边缘池" 对话框")</span><span class="sxs-lookup"><span data-stu-id="50a25-126">![Define New Edge Pool dialog](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Define New Edge Pool dialog")</span></span>

8.  <span data-ttu-id="50a25-127">单击“完成”\*\*\*\*，然后**发布**拓扑。</span><span class="sxs-lookup"><span data-stu-id="50a25-127">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="50a25-128">按照部署文档中的安装边缘服务器上的[Lync Server 2013](lync-server-2013-install-edge-servers.md)中的步骤操作，将文件安装在新的边缘服务器上，配置证书，并启动这些服务。</span><span class="sxs-lookup"><span data-stu-id="50a25-128">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="50a25-129">请务必遵循部署文档中的 "在[Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)" 主题中的准则。</span><span class="sxs-lookup"><span data-stu-id="50a25-129">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="50a25-130">本节仅提供了一些有关安装这些服务器角色时的配置设置的指南。</span><span class="sxs-lookup"><span data-stu-id="50a25-130">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="50a25-131">现在，您应具有与 Lync Server 2013 边缘服务器部署并行存在的 BackCompatSite 的旧版 Office 通信服务器 2007 R2 Edge 服务器部署。</span><span class="sxs-lookup"><span data-stu-id="50a25-131">You should now have a legacy Office Communications Server 2007 R2 Edge server deployment, indicated by the presence of the BackCompatSite, in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="50a25-132">将联盟配置为使用 Office 通信服务器 2007 R2 控制器。</span><span class="sxs-lookup"><span data-stu-id="50a25-132">Federation is configured to use the Office Communications Server 2007 R2 Director.</span></span> <span data-ttu-id="50a25-133">在进入下一个阶段之前，确认这两个部署都正常运行，服务已启动，并且您可以管理每个部署。</span><span class="sxs-lookup"><span data-stu-id="50a25-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

<span data-ttu-id="50a25-134">![显示 OCS 边缘服务器的拓扑生成器](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "显示 OCS 边缘服务器的拓扑生成器")</span><span class="sxs-lookup"><span data-stu-id="50a25-134">![Topology Builder showing OCS Edge Server](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topology Builder showing OCS Edge Server")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

